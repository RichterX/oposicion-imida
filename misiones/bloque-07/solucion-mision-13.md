# 🔐 BLOQUE 07 · SEGURIDAD
# 🧪 MISIÓN 13 · SOLUCIONES
## Identidad + PKI + Firewalls

> **Objetivo de la corrección:** proporcionar una solución de referencia para el caso práctico. En las preguntas abiertas puede haber varias respuestas válidas si están correctamente justificadas.
>
> La idea fundamental de esta misión es relacionar **identidad + confianza + control de tráfico + segmentación**. Un firewall aislado no sustituye a una arquitectura de seguridad, y una VLAN tampoco constituye por sí sola una barrera de seguridad suficiente.

---

# 🔴 BLOQUE A · ANÁLISIS DE FIREWALL

## A.1 · Reglas actuales

### `ANY → LDAP TCP/389`

❌ **No debería estar expuesto a Internet.**

LDAP debe estar restringido a los sistemas que realmente necesiten utilizar el servicio de directorio.

Una arquitectura razonable sería:

```text
SERVIDORES AUTORIZADOS
        ↓
     LDAP/LDAPS
        ↓
DIRECTORIO
```

Nunca:

```text
INTERNET
    ↓
  LDAP
```

Además, cuando sea aplicable, debe utilizarse una configuración segura del servicio, como LDAPS o LDAP protegido mediante TLS, evitando credenciales circulando sin protección.

---

### `ANY → DB TCP/3306`

🔴 **Críticamente peligrosa.**

Una base de datos no debería estar directamente accesible desde Internet.

La regla debería eliminarse.

La arquitectura correcta sería:

```text
INTERNET
   ↓
FIREWALL
   ↓
WEB / API
   ↓
SERVICIO DE APLICACIÓN
   ↓
DB
```

---

### `WEB → DB TCP/3306`

🟡 Puede ser legítima, pero debe restringirse.

Por ejemplo:

```text
WEB-APP-SERVER
      ↓
   TCP/3306
      ↓
DATABASE
```

Solo el servidor o servidores que realmente necesiten acceder a la DB.

No:

```text
WEB
↓
ANY DB
```

Además, si existe una API o capa de aplicación, debe evitarse que un servidor web tenga más privilegios o acceso de red del estrictamente necesario.

---

### `USUARIOS → DB TCP/3306`

🔴 En principio debería eliminarse.

Los usuarios normalmente deberían acceder a:

```text
APLICACIÓN
    ↓
BASE DE DATOS
```

y no:

```text
USUARIO
   ↓
DATABASE
```

Una excepción podría existir para determinados perfiles técnicos o herramientas de administración, pero tendría que estar:

```text
RESTRINGIDA
+
AUTENTICADA
+
AUTORIZADA
+
REGISTRADA
```

---

# A.2 · ¿Por qué `ANY → DB` es tan peligrosa?

Porque convierte la base de datos en un objetivo directamente alcanzable desde prácticamente cualquier origen.

El problema no es solamente el puerto `3306`.

El problema es:

```text
ALCANCE EXCESIVO
        +
SERVICIO CRÍTICO
        +
SUPERFICIE DE ATAQUE
```

Un atacante podría intentar:

```text
escaneo
↓
identificación del servicio
↓
explotación de vulnerabilidad
↓
ataque a credenciales
↓
acceso a datos
```

Por tanto:

> **Una base de datos debe estar detrás de capas de aplicación y controles de red, no expuesta directamente a Internet.**

---

# A.3 · `Deny by default`

La filosofía es:

```text
TODO DENEGADO
      ↓
EXCEPCIONES NECESARIAS
      ↓
PERMITIR SOLO LO JUSTIFICADO
```

Por ejemplo:

```text
Internet → Web :443       PERMITIR
Internet → API :443       PERMITIR
Internet → DB  :3306      DENEGAR
Internet → LDAP:389       DENEGAR
```

Ventajas:

- Reduce superficie de ataque.
- Evita accesos accidentales.
- Obliga a justificar las comunicaciones.
- Facilita auditoría.
- Limita el movimiento lateral.

No significa que "cerramos todo".

Significa:

> **Solo existe comunicación cuando existe una necesidad legítima y explícita.**

---

# A.4 · `INTERNET → DB`

❌ **No.**

Debe ser:

```text
INTERNET
   X
   ↓
DATABASE
```

La DB debería estar en una red protegida.

---

# A.5 · `USUARIOS → DB`

❌ **Normalmente no.**

Preferible:

```text
USUARIO
  ↓
APLICACIÓN
  ↓
DATABASE
```

Excepciones:

```text
Administrador autorizado
+
red administrativa
+
MFA
+
cuenta privilegiada
+
registro
```

---

# 🟠 BLOQUE B · SEGMENTACIÓN

## B.1 · Arquitectura propuesta

Una arquitectura posible:

```text
                         INTERNET
                            │
                       ┌────▼────┐
                       │ FIREWALL│
                       └────┬────┘
                            │
                           DMZ
                    ┌───────┴───────┐
                    │               │
                   WEB             API
                    │               │
                    └───────┬───────┘
                            │
                    FIREWALL INTERNO
                            │
       ┌────────────┬───────┼────────┬───────────┐
       │            │       │        │           │
   USUARIOS      SERVERS    DB      ADMIN      BACKUP
       │
       ├── Wi-Fi CORPORATIVO
       │
       └── ENDPOINTS

       GUEST Wi-Fi
            │
            └── INTERNET ONLY
```

La arquitectura puede dividirse todavía más:

```text
DMZ
USER VLAN
SERVER VLAN
DATABASE VLAN
ADMIN VLAN
BACKUP VLAN
GUEST VLAN
IOT VLAN
MANAGEMENT VLAN
```

---

# B.2 · Tráfico permitido

Una matriz razonable:

| Origen | Destino | Permitido | Motivo |
|---|---|---|---|
| Internet | Web DMZ | TCP 443 | Portal |
| Internet | API DMZ | TCP 443 | API pública |
| Internet | VPN | Puerto VPN | Acceso remoto |
| Web | App/DB | Solo puertos necesarios | Funcionamiento |
| API | DB | TCP 3306 | Acceso de aplicación |
| Usuarios | Aplicaciones | Solo puertos necesarios | Uso normal |
| Usuarios | DB | ❌ | Evitar acceso directo |
| Guest | Internet | ✅ | Navegación |
| Guest | Red interna | ❌ | Aislamiento |
| Admin | Servidores | Solo puertos administrativos | Gestión |
| Admin | Firewall | HTTPS/SSH según necesidad | Administración |
| Backup | Servidores | Solo tráfico de backup | Copias |
| Internet | DB | ❌ | No exposición |

La regla general:

```text
PERMITIR
solo lo necesario.
```

---

# B.3 · ¿Cómo limita la segmentación el movimiento lateral?

Supongamos:

```text
PORTÁTIL COMPROMETIDO
        ↓
USUARIOS
```

Si todo está en una única red:

```text
USUARIO
 ↓
LDAP
 ↓
SERVIDORES
 ↓
DB
 ↓
BACKUP
```

El atacante puede desplazarse con mayor facilidad.

Con segmentación:

```text
USUARIOS
   ↓
FIREWALL
   X
DB
```

El atacante necesita superar controles adicionales.

La segmentación convierte:

```text
UNA RED GRANDE
```

en:

```text
VARIOS DOMINIOS DE CONFIANZA
```

y permite controlar el tráfico entre ellos.

---

# 🟡 BLOQUE C · WI-FI

## C.1 · Problema de Guest

Es una vulnerabilidad grave:

```text
GUEST
 ↓
RED INTERNA
```

Un dispositivo de visitante comprometido puede utilizarse como punto de partida para:

```text
ESCANEAR
↓
ENUMERAR
↓
ATACAR
```

recursos internos.

---

# C.2 · Política Wi-Fi

## Corporativo

```text
AUTENTICACIÓN CORPORATIVA
+
CONTROL DE DISPOSITIVOS
+
ACCESO A RECURSOS AUTORIZADOS
+
SEGMENTACIÓN
```

Idealmente:

```text
Wi-Fi corporativo
      ↓
VLAN corporativa
      ↓
recursos autorizados
```

## Invitados

```text
GUEST
 ↓
FIREWALL
 ↓
INTERNET
```

y:

```text
GUEST
 X
RED INTERNA
```

---

# C.3 · IoT en la misma VLAN

Si un dispositivo IoT es comprometido:

```text
IOT COMPROMETIDO
        ↓
MISMA VLAN
        ↓
DESCUBRIMIENTO DE SERVIDORES
        ↓
MOVIMIENTO LATERAL
```

Por eso conviene:

```text
IOT VLAN
```

y controlar estrictamente qué puede alcanzar.

---

# 🟢 BLOQUE D · VPN

## D.1 · MFA no resuelve toda la arquitectura

Aunque exista MFA:

```text
VPN
 ↓
TODA LA RED
```

sigue siendo demasiado permisivo.

Si una cuenta legítima es comprometida:

```text
MFA superado
↓
VPN
↓
acceso excesivo
```

Por tanto:

> **MFA protege la autenticación, pero no sustituye la autorización ni la segmentación.**

---

# D.2 · VPN por roles

## Administradores

```text
VPN
 ↓
MFA
 ↓
ADMIN VLAN
 ↓
SERVIDORES / FIREWALL / DIRECTORIO
```

Acceso privilegiado, registrado y controlado.

## Investigadores

```text
VPN
 ↓
MFA
 ↓
RECURSOS DE INVESTIGACIÓN
```

Sin acceso administrativo.

## Personal administrativo

```text
VPN
 ↓
MFA
 ↓
APLICACIONES NECESARIAS
```

## Proveedores

Idealmente:

```text
ACCESO TEMPORAL
+
MFA
+
ALCANCE LIMITADO
+
HORARIO / CONDICIONES
+
AUDITORÍA
```

No deberían recibir:

```text
ACCESO COMPLETO A LA RED
```

---

# D.3 · Controles adicionales a MFA

```text
MÍNIMO PRIVILEGIO
+
SEGMENTACIÓN
+
CONTROL DE DISPOSITIVO
+
CERTIFICADOS DE CLIENTE
+
ACCESO CONDICIONAL
+
MONITORIZACIÓN
+
LÍMITES DE SESIÓN
+
REVISIÓN DE CUENTAS
```

---

# 🔵 BLOQUE E · CERTIFICADOS

## E.1 · Conceptos

### Certificado digital

Documento electrónico que vincula una identidad con una clave pública y contiene información firmada por una autoridad de certificación.

### Clave pública

Puede distribuirse.

Se utiliza, según el sistema criptográfico, para:

```text
verificación
+
cifrado
```

### Clave privada

Debe mantenerse secreta.

Se utiliza, según el sistema criptográfico, para:

```text
firma
+
descifrado
```

y, en TLS, participa en la autenticación mediante mecanismos de clave pública.

### CA

**Certificate Authority / Autoridad de Certificación.**

Entidad que emite y firma certificados.

### PKI

**Public Key Infrastructure.**

Conjunto de:

```text
PERSONAS
+
POLÍTICAS
+
PROCEDIMIENTOS
+
CERTIFICADOS
+
CLAVES
+
CA
+
REVOCACIÓN
```

que permiten gestionar confianza basada en criptografía de clave pública.

---

# E.2 · Clave privada en carpeta compartida

🔴 Es un problema crítico.

Una clave privada debe mantenerse:

```text
SECRETA
+
PROTEGIDA
+
CONTROLADA
```

Si está en una carpeta compartida:

```text
USUARIO NO AUTORIZADO
        ↓
COPIA DE CLAVE
        ↓
SUPLANTACIÓN
```

El atacante podría utilizarla para hacerse pasar por el titular del certificado.

---

# E.3 · Sospecha de compromiso de clave privada

Procedimiento:

```text
1. Identificar el certificado afectado.

2. Determinar si la clave privada sigue activa.

3. Aislar/proteger el sistema afectado.

4. Revocar el certificado comprometido.

5. Generar un nuevo par de claves.

6. Solicitar un nuevo certificado.

7. Instalar el nuevo certificado.

8. Retirar el antiguo.

9. Investigar el origen de la exposición.

10. Revisar logs y posibles usos fraudulentos.

11. Actualizar inventario.

12. Documentar el incidente.
```

⚠️ **Importante:**

Si se sospecha compromiso de la clave privada, no basta con renovar el certificado manteniendo la misma clave.

Debe generarse:

```text
NUEVA CLAVE PRIVADA
+
NUEVA CLAVE PÚBLICA
+
NUEVO CERTIFICADO
```

---

# E.4 · Ciclo de vida

```text
SOLICITUD
   ↓
EMISIÓN
   ↓
INSTALACIÓN
   ↓
USO
   ↓
MONITORIZACIÓN
   ↓
RENOVACIÓN
   ↓
REVOCACIÓN si procede
   ↓
EXPIRACIÓN
```

### Renovación

Se sustituye el certificado antes de que expire.

### Revocación

Se invalida antes de su fecha de expiración porque existe un motivo, por ejemplo:

```text
CLAVE COMPROMETIDA
CAMBIO DE IDENTIDAD
CERTIFICADO EMITIDO INCORRECTAMENTE
```

### Expiración

Llega la fecha de finalización de validez.

No son conceptos equivalentes:

```text
EXPIRAR
≠
REVOCAR
```

---

# 🟣 BLOQUE F · CA INTERNA VS CA PÚBLICA

## F.1 · CA interna

Ventajas:

```text
CONTROL INTERNO
+
CERTIFICADOS PARA SERVICIOS PRIVADOS
+
AUTOMATIZACIÓN
+
CONTROL DE POLÍTICAS
+
NO DEPENDER DE UNA CA PÚBLICA PARA CADA SERVICIO INTERNO
```

Especialmente útil para:

```text
servidores internos
autenticación interna
dispositivos corporativos
servicios internos
```

---

# F.2 · CA pública

Ventajas:

```text
CONFIANZA AMPLIAMENTE RECONOCIDA
+
NO REQUIERE DISTRIBUIR UNA CA RAÍZ PROPIA A CADA USUARIO
+
ADECUADA PARA SERVICIOS PÚBLICOS EN INTERNET
```

Por ejemplo:

```text
api.invega.es
```

puede utilizar un certificado emitido por una CA pública para facilitar que navegadores y clientes confíen en él.

---

# F.3 · ¿Una sola CA para todo?

❌ No necesariamente.

Una arquitectura razonable podría ser:

```text
                 PKI INVEGA
                     │
            ┌────────┴────────┐
            │                 │
       CA INTERNA        CA PÚBLICA
            │                 │
       SERVICIOS           INTERNET
        INTERNOS            PÚBLICA
```

Por ejemplo:

```text
INTRANET
LDAP
SERVICIOS INTERNOS
DISPOSITIVOS
        ↓
CA INTERNA
```

mientras:

```text
PORTAL PÚBLICO
API PÚBLICA
        ↓
CA PÚBLICA
```

La elección debe depender del escenario y del modelo de confianza.

---

# 🧩 BLOQUE G · TLS

La afirmación:

> "Tenemos HTTPS, así que todo está cifrado y seguro."

es ❌ **incorrecta**.

HTTPS utiliza HTTP sobre TLS, pero TLS correctamente desplegado aporta principalmente:

```text
CONFIDENCIALIDAD
+
INTEGRIDAD
+
AUTENTICACIÓN DEL SERVIDOR
```

### Certificado

Permite al cliente verificar la identidad presentada por el servidor mediante una cadena de confianza.

### Claves

Permiten establecer las condiciones criptográficas de la sesión.

### Validación

Hay que comprobar:

```text
NOMBRE DEL HOST
+
VALIDEZ TEMPORAL
+
CADENA DE CONFIANZA
+
ESTADO DEL CERTIFICADO
```

### Configuración TLS

Una configuración incorrecta puede dejar problemas aunque exista HTTPS.

Por ejemplo:

```text
protocolos obsoletos
cifrados débiles
certificado incorrecto
validación defectuosa
```

Por tanto:

> **HTTPS es un mecanismo de seguridad, no una garantía absoluta de seguridad de la aplicación.**

---

# 🧪 BLOQUE H · CERTIFICADO QUE CADUCA MAÑANA

Tenemos:

```text
api.invega.es
```

y nadie sabe:

```text
CA
clave privada
servidor
```

### Procedimiento

```text
1. Identificar todos los sistemas que utilizan el certificado.

2. Consultar el certificado actual:
   - CN/SAN
   - emisor
   - fechas
   - cadena

3. Localizar la clave privada de forma segura.

4. Determinar quién gestiona el servicio.

5. Comprobar si la clave privada está comprometida.

6. Generar nuevo par de claves.

7. Solicitar nuevo certificado.

8. Instalarlo en el servicio.

9. Instalar la cadena intermedia necesaria.

10. Validar desde clientes externos e internos.

11. Comprobar que la aplicación continúa funcionando.

12. Retirar el certificado antiguo cuando corresponda.

13. Actualizar inventario.

14. Registrar responsable y fecha de renovación.

15. Establecer alertas de expiración.
```

### Lo que NO deberíamos hacer

```text
❌ Esperar a que expire.
❌ Reutilizar una clave privada posiblemente comprometida.
❌ Instalarlo manualmente sin registrar nada.
❌ Ignorar la cadena de confianza.
```

---

# 🔥 BLOQUE I · HARDENING DEL FIREWALL

Diez medidas posibles:

```text
1. Deny by default.

2. Eliminar reglas ANY innecesarias.

3. Eliminar exposición directa de DB.

4. Eliminar exposición directa de LDAP a Internet.

5. Restringir reglas por origen.

6. Restringir reglas por destino.

7. Restringir puertos/protocolos.

8. Centralizar y revisar logs.

9. Monitorizar tráfico de salida.

10. Separar administración del firewall.

11. Utilizar MFA para administración.

12. Revisar reglas periódicamente.

13. Documentar cada regla.

14. Eliminar reglas obsoletas.

15. Utilizar segmentación interna.

16. Integrar IDS/IPS cuando corresponda.

17. Utilizar WAF para aplicaciones web.

18. Aplicar controles de egress filtering.

19. Generar alertas sobre tráfico anómalo.

20. Realizar auditorías periódicas.
```

---

# 🚨 BLOQUE J · INCIDENTE

Tenemos:

```text
PORTÁTIL COMPROMETIDO
        ↓
LDAP
        ↓
ENUMERACIÓN
        ↓
SERVIDORES
        ↓
INTENTO DB
```

## J.1 · Controles que han fallado

```text
SEGMENTACIÓN
CONTROL DE ACCESO
MÍNIMO PRIVILEGIO
CONTROL INTERNO DEL FIREWALL
PROTECCIÓN DEL DIRECTORIO
MONITORIZACIÓN
```

El problema principal es que:

> Un endpoint comprometido puede hablar con demasiados recursos internos.

---

# J.2 · Controles que deberían haber impedido el movimiento

```text
VLAN / SEGMENTACIÓN
+
FIREWALL INTERNO
+
ACL
+
MÍNIMO PRIVILEGIO
+
CONTROL DE ACCESO
+
EDR
+
SIEM
```

Por ejemplo:

```text
USER VLAN
    X
LDAP
```

si ese usuario no necesita acceso directo al directorio.

---

# J.3 · Logs

Revisaría:

```text
FIREWALL
+
VPN
+
LDAP / DIRECTORIO
+
EDR
+
DNS
+
DHCP
+
SERVIDORES
+
DB
+
SWITCHES
+
WAF
```

Especialmente:

```text
timestamp
origen
destino
puerto
usuario
resultado
```

---

# J.4 · Medidas inmediatas

```text
1. Aislar el portátil.

2. Bloquear/revocar credenciales comprometidas.

3. Revocar sesiones.

4. Analizar el endpoint.

5. Revisar accesos al directorio.

6. Revisar enumeración.

7. Identificar servidores contactados.

8. Revisar intentos de acceso a DB.

9. Bloquear tráfico innecesario.

10. Preservar evidencias.

11. Buscar otros equipos comprometidos.

12. Aumentar monitorización.
```

---

# 🧠 BLOQUE K · RAZONAMIENTO

## K.1 · "Firewall con antivirus = no necesitamos EDR"

❌ Incorrecto.

Son controles diferentes.

```text
FIREWALL
→ tráfico de red

ANTIVIRUS
→ detección de malware

EDR
→ comportamiento y actividad del endpoint
```

EDR puede aportar:

```text
procesos
conexiones
comandos
árboles de procesos
actividad sospechosa
investigación
respuesta
```

---

# K.2 · "VLAN = segmentación completa"

❌ Incorrecto.

Una VLAN puede proporcionar separación lógica, pero:

```text
VLAN
≠
CONTROL DE ACCESO COMPLETO
```

Para obtener una segmentación de seguridad efectiva se necesitan mecanismos que controlen el tráfico entre segmentos:

```text
FIREWALL
+
ACL
+
POLÍTICAS
+
MONITORIZACIÓN
```

---

# K.3 · "HTTPS = no necesitamos certificados"

❌ Incorrecto.

HTTPS depende de TLS y el certificado participa en la autenticación del servidor.

Sin certificado correctamente gestionado:

```text
NO HAY CADENA DE CONFIANZA ADECUADA
```

---

# K.4 · "CA interna es menos segura que pública"

❌ No necesariamente.

Depende del escenario.

Una CA interna puede ser apropiada para:

```text
SERVICIOS INTERNOS
DISPOSITIVOS
AUTENTICACIÓN CORPORATIVA
```

Una CA pública resulta especialmente apropiada para:

```text
SERVICIOS PÚBLICOS
```

La seguridad depende también de:

```text
DISEÑO
PROTECCIÓN DE CLAVES
PROCEDIMIENTOS
GESTIÓN
REVOCACIÓN
AUDITORÍA
```

---

# K.5 · "Cerrar todos los puertos es más seguro"

❌ No como estrategia operativa.

La política correcta es:

```text
DENEGAR POR DEFECTO
+
PERMITIR LO NECESARIO
```

Cerrar absolutamente todo rompería servicios legítimos.

El objetivo es:

> **Minimizar superficie de ataque manteniendo únicamente las comunicaciones necesarias y justificadas.**

---

# 🏗️ BLOQUE L · ARQUITECTURA FINAL

Una arquitectura de referencia:

```text
                         INTERNET
                            │
                     ┌──────▼──────┐
                     │ FIREWALL EXT │
                     └──────┬───────┘
                            │
                           DMZ
                 ┌──────────┴──────────┐
                 │                     │
                WEB                   API
                 │                     │
                 └──────────┬──────────┘
                            │
                     FIREWALL INT
                            │
        ┌───────────┬───────┼────────┬───────────┐
        │           │       │        │           │
     USUARIOS    SERVERS    DB     ADMIN       BACKUP
        │           │        │        │
        │           │        │     GESTIÓN
        │           │        │
     CORP-WIFI      │        │
                    │        │
                APP/FICHEROS │
                             │
                         DATOS CRÍTICOS

        GUEST WIFI
             │
             ▼
         INTERNET
             X
        RED INTERNA
```

Elementos adicionales:

```text
VPN
 ↓
MFA
 ↓
ACCESO SEGMENTADO

PKI
 ↓
CA INTERNA
 ↓
SERVICIOS INTERNOS

CA PÚBLICA
 ↓
SERVICIOS PÚBLICOS

EDR
 ↓
ENDPOINTS

SIEM
 ↓
LOGS

WAF
 ↓
WEB/APIs

IDS/IPS
 ↓
MONITORIZACIÓN
```

---

# 📊 BLOQUE M · MATRIZ DE REGLAS

Una solución posible:

| Origen | Destino | Protocolo | Puerto | Acción | Justificación |
|---|---|---|---:|---|---|
| Internet | Web DMZ | TCP | 443 | PERMITIR | Portal HTTPS |
| Internet | API DMZ | TCP | 443 | PERMITIR | API pública |
| Internet | VPN | VPN | Según solución | PERMITIR | Acceso remoto |
| Internet | LDAP | TCP | 389 | DENEGAR | No exponer directorio |
| Internet | DB | TCP | 3306 | DENEGAR | No exponer DB |
| Web/App | DB | TCP | 3306 | PERMITIR | Necesidad funcional |
| Usuarios | DB | TCP | 3306 | DENEGAR | Evitar acceso directo |
| Admin | Servidores | TCP | Según servicio | PERMITIR | Administración |
| Guest | Red interna | ANY | ANY | DENEGAR | Aislamiento |
| Guest | Internet | ANY | ANY | PERMITIR | Navegación |
| Backup | Servidores | Según backup | Según backup | PERMITIR | Copias |
| Usuarios | Aplicaciones | Según servicio | Según servicio | PERMITIR | Uso normal |
| Servidores | Internet | Según necesidad | Según necesidad | RESTRINGIR | Egress filtering |
| Admin | Firewall | HTTPS/SSH | Según gestión | PERMITIR | Administración |
| Cualquiera | Cualquiera | ANY | ANY | DENEGAR | Deny by default |

### Observación

La última regla:

```text
ANY → ANY → DENY
```

actúa como regla final de cierre.

Las excepciones anteriores deben estar justificadas y documentadas.

---

# 🏆 BLOQUE N · INFORME EJECUTIVO

### Respuesta de referencia

> La infraestructura actual presenta una superficie de ataque excesiva debido a servicios internos accesibles desde redes que no necesitan utilizarlos, ausencia de segmentación suficiente y una política de firewall permisiva. Especialmente preocupantes son la exposición de LDAP y la base de datos, el acceso directo de usuarios a la DB, la comunicación entre la red de invitados y la red interna y el acceso VPN sin restricciones por rol.
>
> Se propone una arquitectura segmentada con DMZ, redes independientes para usuarios, servidores, bases de datos, administración, backup, IoT y Wi-Fi de invitados. El tráfico entre segmentos deberá controlarse mediante firewall y políticas de mínimo privilegio, aplicando deny by default.
>
> La VPN deberá mantener MFA y añadir segmentación por roles, de forma que investigadores, personal administrativo, administradores y proveedores solo accedan a los recursos necesarios.
>
> En materia de certificados se propone una gestión centralizada del ciclo de vida, inventario, protección de claves privadas, renovación y revocación. Una CA interna puede utilizarse para servicios internos, mientras que los servicios públicos pueden utilizar certificados emitidos por una CA pública.
>
> Como prioridades inmediatas se propone eliminar las exposiciones de DB y LDAP, aislar la red de invitados, restringir la VPN, proteger las claves privadas y revisar todas las reglas del firewall. Posteriormente deberían implantarse segmentación completa, monitorización, IDS/IPS, WAF y procesos formales de gestión de certificados.

---

# 🧠 RETO EXTRA · "EL PUERTO MISTERIOSO"

| Puerto | Servicio habitual | ¿Dónde permitirlo? |
|---:|---|---|
| **22** | SSH | Administración → servidores autorizados |
| **389** | LDAP | Solo sistemas autorizados → directorio |
| **3306** | MySQL | Aplicaciones autorizadas → DB |
| **445** | SMB | Redes internas autorizadas → servidores de ficheros |
| **3389** | RDP | Administración → servidores Windows autorizados |

## TCP/22 · SSH

No debería estar:

```text
INTERNET → TODOS LOS SERVIDORES
```

Preferible:

```text
ADMIN
 ↓
FIREWALL
 ↓
SERVIDORES AUTORIZADOS
```

---

## TCP/389 · LDAP

Restringir a:

```text
CLIENTES / SERVICIOS AUTORIZADOS
        ↓
DIRECTORIO
```

No exponerlo directamente a Internet.

---

## TCP/3306 · MySQL

Solo:

```text
APP
 ↓
DB
```

y excepciones administrativas controladas.

---

## TCP/445 · SMB

Debe restringirse mucho porque es un protocolo especialmente sensible para movimiento lateral.

Preferible:

```text
USUARIOS AUTORIZADOS
 ↓
FILE SERVER
```

y bloquearlo entre segmentos donde no sea necesario.

---

## TCP/3389 · RDP

Nunca debería exponerse directamente a Internet.

Preferible:

```text
ADMIN
 ↓
VPN / JUMP SERVER
 ↓
SERVIDOR WINDOWS
```

con MFA y registro.

---

# 🎯 CONCEPTOS CLAVE DE LA MISIÓN

## 1. Firewall

```text
CONTROL DEL TRÁFICO
```

## 2. Segmentación

```text
LIMITAR EL ALCANCE
DEL COMPROMISO
```

## 3. MFA

```text
FORTALECER AUTENTICACIÓN
```

## 4. PKI

```text
GESTIONAR CONFIANZA
BASADA EN CLAVE PÚBLICA
```

## 5. Certificados

```text
VINCULAR IDENTIDAD
+
CLAVE PÚBLICA
```

## 6. Clave privada

```text
SECRETA
+
PROTEGIDA
```

## 7. CA

```text
EMITE / FIRMA CERTIFICADOS
```

## 8. Deny by default

```text
DENEGAR
↓
EXCEPCIONES JUSTIFICADAS
```

---

# 🏆 EVALUACIÓN DE LA MISIÓN

Una respuesta excelente debería demostrar que entiendes que:

```text
IDENTIDAD
    +
AUTENTICACIÓN
    +
AUTORIZACIÓN
    +
SEGMENTACIÓN
    +
FIREWALL
    +
MONITORIZACIÓN
    +
PKI
    ↓
DEFENSA EN PROFUNDIDAD
```

La idea más importante de toda la misión:

> **No debemos confiar únicamente en una capa.**

Si roban una credencial:

```text
MFA
```

debe dificultar el acceso.

Si superan MFA:

```text
VPN SEGMENTADA
```

debe limitar el alcance.

Si llegan a un endpoint:

```text
EDR
```

debe ayudar a detectarlo.

Si intentan desplazarse:

```text
FIREWALL + SEGMENTACIÓN
```

deben limitar el movimiento.

Si acceden a un servicio:

```text
MÍNIMO PRIVILEGIO
```

debe limitar sus permisos.

Y si algo ocurre:

```text
SIEM + LOGS
```

deben permitir detectarlo e investigarlo.

---

# 🎯 RESUMEN DE EXAMEN

```text
DENY BY DEFAULT
        ↓
SOLO PERMITIR LO NECESARIO
        ↓
SEGMENTAR
        ↓
MÍNIMO PRIVILEGIO
        ↓
MFA
        ↓
MONITORIZAR
        ↓
REGISTRAR
```

Y en PKI:

```text
CLAVE PRIVADA
→ SECRETA

CLAVE PÚBLICA
→ DISTRIBUIBLE

CERTIFICADO
→ IDENTIDAD + CLAVE PÚBLICA

CA
→ FIRMA / EMITE

PKI
→ ECOSISTEMA DE CONFIANZA

REVOCACIÓN
→ INVALIDACIÓN ANTES DE EXPIRAR
```

---

# 🏁 MISIÓN 13 · CORREGIDA

```text
7.3 CERTIFICADOS
        ↓
IDENTIDAD + CONFIANZA
        ↓
7.4 FIREWALLS
        ↓
CONTROL DE COMUNICACIONES
        ↓
SEGMENTACIÓN
        ↓
DEFENSA EN PROFUNDIDAD
```

**Misión 13: completada.** 🔐🧱
