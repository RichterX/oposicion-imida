# 🔐 BLOQUE 07 · SEGURIDAD
# 🧪 MISIÓN 13 · IDENTIDAD + PKI + FIREWALLS
## Diseño y fortificación de la infraestructura de INVEGA

> **Tipo:** misión práctica  
> **Bloque:** 07 · Seguridad  
> **Ámbitos:** 7.3 Certificados digitales + 7.4 Firewalls  
> **Dificultad:** 🟡 / 🔴 Alta  
> **Modalidad:** individual, offline  
> **Objetivo:** diseñar una arquitectura segura de identidad, autenticación y comunicaciones para un organismo público.

---

# 🎯 1. CONTEXTO

Han pasado tres meses desde el incidente de la **Misión 12**.

INVEGA ha realizado varias mejoras:

```text
✅ MFA en VPN
✅ Formación anti-phishing
✅ EDR
✅ SIEM
✅ Revisión inicial de permisos
```

Pero la auditoría externa ha detectado un nuevo problema:

> **La infraestructura de identidad y comunicaciones se ha desarrollado durante años sin una arquitectura de seguridad coherente.**

Hay certificados instalados manualmente, reglas de firewall antiguas, servicios expuestos innecesariamente y diferentes sistemas de autenticación.

La dirección te encarga rediseñar la infraestructura.

---

# 🏢 2. INFRAESTRUCTURA ACTUAL

INVEGA dispone de:

```text
                 INTERNET
                    │
               ┌────▼────┐
               │ FIREWALL│
               └────┬────┘
                    │
          ┌─────────┴─────────┐
          │                   │
         DMZ              RED INTERNA
          │                   │
     ┌────┴────┐       ┌──────┴──────┐
     │         │       │             │
    WEB       API   USUARIOS      SERVIDORES
                                  │
                    ┌─────────────┼─────────────┐
                    │             │             │
                   DB          FICHEROS       LDAP
```

Además existen:

```text
VPN
Correo
Wi-Fi corporativo
Wi-Fi invitados
Aplicación interna
Portal web
API
Servidores Linux
Servidores Windows
Dispositivos móviles
Portátiles corporativos
```

---

# 🔑 3. SISTEMA DE IDENTIDAD

Actualmente utilizan un directorio corporativo.

Los usuarios tienen:

```text
usuario
contraseña
```

La autenticación MFA se ha implantado únicamente en:

```text
VPN
```

No existe una política homogénea para:

```text
WEB
API
CORREO
APLICACIONES INTERNAS
ADMINISTRACIÓN
```

---

# 🪪 4. CERTIFICADOS DIGITALES

INVEGA utiliza certificados digitales, pero de manera poco organizada.

Actualmente:

- Algunos servidores utilizan certificados públicos.
- Otros utilizan certificados autofirmados.
- Algunos certificados se instalaron manualmente.
- No existe inventario completo.
- No existe un procedimiento homogéneo de renovación.
- En algunos casos se desconoce quién es responsable del certificado.
- Hay certificados próximos a caducar.
- Algunos servicios internos no validan correctamente la cadena de confianza.

Además:

> Un administrador ha encontrado una clave privada almacenada en una carpeta compartida.

No se sabe si sigue siendo utilizada.

---

# 🏛️ 5. AUTORIDAD CERTIFICADORA

INVEGA quiere implantar una infraestructura PKI.

La propuesta inicial del departamento IT es:

> "Podemos montar una CA interna y utilizarla para todos los certificados."

La dirección pregunta:

> "¿Para qué necesitamos una CA interna si ya existen autoridades certificadoras públicas?"

---

# 🌐 6. SERVICIOS EXPUESTOS

El firewall tiene actualmente estas reglas:

```text
ANY → WEB      TCP 80
ANY → WEB      TCP 443
ANY → API      TCP 443
ANY → VPN      UDP 1194
ANY → LDAP     TCP 389
ANY → DB       TCP 3306
```

Además:

```text
WEB → DB       TCP 3306
API → DB       TCP 3306
USUARIOS → DB  TCP 3306
```

El administrador explica:

> "Funcionan perfectamente, así que no deberíamos tocar las reglas."

---

# 🔥 7. FIREWALL

El firewall permite actualmente:

```text
ENTRADA
→ WEB
→ API
→ VPN
→ LDAP
→ DB

SALIDA
→ TODO
```

No existe filtrado específico de salida.

Tampoco hay reglas específicas entre segmentos internos.

---

# 🧱 8. SEGMENTACIÓN

Actualmente solo existen:

```text
DMZ
RED INTERNA
```

Pero dentro de la red interna están mezclados:

```text
usuarios
servidores
administradores
bases de datos
impresoras
Wi-Fi
dispositivos IoT
```

---

# 📡 9. WI-FI

Existen dos redes:

```text
INVEGA
INVEGA-GUEST
```

Sin embargo:

> La red de invitados puede acceder a algunos recursos internos porque se creó antes de la segmentación actual.

---

# 🖥️ 10. ADMINISTRACIÓN

Los administradores pueden acceder directamente desde sus equipos habituales a:

```text
servidores
firewall
bases de datos
directorio
```

No existe una red de administración separada.

---

# 🔐 11. VPN

La VPN ya utiliza MFA.

Pero:

- Todos los usuarios VPN pueden acceder a toda la red interna.
- No existe segmentación por rol.
- Los investigadores pueden acceder a servidores administrativos que no necesitan.
- Los administradores pueden acceder a prácticamente todo.

---

# 🧪 12. INCIDENTE DE PRUEBA

Durante una auditoría de seguridad se realiza una prueba controlada.

Un auditor externo consigue:

```text
acceso a INVEGA-GUEST
```

Desde ahí descubre:

```text
LDAP
DB
SERVIDOR DE FICHEROS
```

No consigue autenticarse, pero demuestra que los servicios son accesibles.

Después, desde un portátil corporativo comprometido, consigue:

```text
acceso a LDAP
↓
enumeración de usuarios
↓
descubrimiento de servidores
↓
intento de acceso a DB
```

La prueba se detiene antes de acceder a información real.

---

# 🧠 13. TU MISIÓN

Debes elaborar un **plan de rediseño de seguridad**.

No basta con decir:

> "Cerrar puertos."

Debes justificar:

```text
QUÉ
↓
POR QUÉ
↓
QUIÉN
↓
DESDE DÓNDE
↓
HACIA DÓNDE
↓
CON QUÉ AUTENTICACIÓN
```

---

# 🔴 BLOQUE A · ANÁLISIS DE FIREWALL

## A.1

Analiza las siguientes reglas:

```text
ANY → LDAP 389
ANY → DB 3306
WEB → DB 3306
USUARIOS → DB 3306
```

Para cada una:

```text
¿Es necesaria?
¿Es segura?
¿Quién debería acceder?
¿Desde dónde?
¿Qué cambiarías?
```

---

## A.2

Explica por qué:

```text
ANY → DB
```

es especialmente peligrosa.

---

## A.3

Diseña una política de firewall basada en:

> **deny by default**

Explica el principio.

---

## A.4

¿Debería existir tráfico directo:

```text
INTERNET → DB
```

?

Justifica.

---

## A.5

¿Y:

```text
USUARIOS → DB
```

?

¿Podría existir alguna excepción?

---

# 🟠 BLOQUE B · DISEÑO DE SEGMENTACIÓN

Actualmente:

```text
RED INTERNA
└── TODO
```

Diseña una segmentación nueva.

Como mínimo considera:

```text
DMZ
USUARIOS
SERVIDORES
BASE DE DATOS
ADMINISTRACIÓN
BACKUP
WI-FI CORPORATIVO
WI-FI INVITADOS
```

Puedes añadir otras zonas.

---

## B.1

Dibuja la nueva arquitectura.

---

## B.2

Define qué tráfico debería permitirse entre:

```text
INTERNET
DMZ
USUARIOS
SERVIDORES
DB
ADMIN
BACKUP
GUEST
```

---

## B.3

Explica cómo la segmentación limita:

```text
MOVIMIENTO LATERAL
```

---

# 🟡 BLOQUE C · WI-FI

## C.1

¿Qué problema existe con:

```text
INVEGA-GUEST → RED INTERNA
```

?

---

## C.2

Diseña la política correcta para:

```text
WI-FI CORPORATIVO
WI-FI INVITADOS
```

---

## C.3

¿Qué ocurriría si un dispositivo IoT comprometido estuviera en la misma VLAN que los servidores?

---

# 🟢 BLOQUE D · VPN

## D.1

La VPN ya tiene MFA.

¿Por qué sigue siendo inseguro:

```text
VPN
↓
TODA LA RED
```

?

---

## D.2

Diseña acceso VPN diferenciado para:

```text
ADMINISTRADORES
INVESTIGADORES
PERSONAL ADMINISTRATIVO
PROVEEDORES
```

---

## D.3

¿Qué controles añadirías además de MFA?

---

# 🔵 BLOQUE E · CERTIFICADOS

## E.1

Explica la diferencia entre:

```text
CERTIFICADO DIGITAL
CLAVE PÚBLICA
CLAVE PRIVADA
CA
PKI
```

---

## E.2

¿Por qué es peligroso almacenar una clave privada en:

```text
CARPETA COMPARTIDA
```

?

---

## E.3

¿Qué debería hacerse si sospechamos que una clave privada ha sido comprometida?

Describe el procedimiento.

---

## E.4

Explica:

```text
EMISIÓN
↓
INSTALACIÓN
↓
USO
↓
RENOVACIÓN
↓
REVOCACIÓN
↓
EXPIRACIÓN
```

---

# 🟣 BLOQUE F · CA INTERNA VS CA PÚBLICA

La dirección pregunta:

> "¿CA interna o CA pública?"

Explica:

### F.1

¿Qué ventajas ofrece una CA interna?

### F.2

¿Qué ventajas ofrece una CA pública?

### F.3

¿Utilizarías necesariamente una sola para todo?

Justifica.

---

# 🧩 BLOQUE G · TLS

Un desarrollador afirma:

> "Tenemos HTTPS, así que todo está cifrado y seguro."

¿Es correcto?

Analiza:

```text
CIFRADO
AUTENTICACIÓN
INTEGRIDAD
CERTIFICADO
CONFIGURACIÓN TLS
VALIDACIÓN
```

---

# 🧪 BLOQUE H · CASO PRÁCTICO DE CERTIFICADO

El certificado de:

```text
api.invega.es
```

caduca mañana.

El responsable no recuerda:

```text
quién lo emitió
dónde está la clave privada
qué servidor lo utiliza
```

Diseña el procedimiento que seguirías.

---

# 🔥 BLOQUE I · HARDENING DEL FIREWALL

Propón al menos:

```text
10 medidas
```

para mejorar el firewall.

Puedes considerar:

```text
reglas
logging
salida
segmentación
administración
VPN
IDS/IPS
NAT
proxies
WAF
```

---

# 🚨 BLOQUE J · INCIDENTE

Durante la prueba aparece este escenario:

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

## J.1

¿Qué controles han fallado?

---

## J.2

¿Qué controles deberían haber impedido el movimiento?

---

## J.3

¿Qué logs revisarías?

---

## J.4

¿Qué medidas aplicarías inmediatamente?

---

# 🧠 BLOQUE K · PREGUNTAS DE RAZONAMIENTO

## K.1

> "Si el firewall tiene antivirus, no necesitamos EDR."

¿Correcto?

---

## K.2

> "Si tenemos VLANs, ya estamos segmentados."

¿Correcto?

---

## K.3

> "Si utilizamos HTTPS, no necesitamos certificados."

¿Correcto?

---

## K.4

> "Una CA interna es menos segura que una pública."

¿Siempre?

---

## K.5

> "Cerrar todos los puertos es la política de firewall más segura."

¿Correcto?

---

# 🏗️ BLOQUE L · ARQUITECTURA FINAL

Diseña la arquitectura definitiva de INVEGA.

Debe incluir como mínimo:

```text
INTERNET
    │
FIREWALL
    │
   DMZ
    │
FIREWALL INTERNO
    │
 ┌──┴─────────────────────────────┐
 │                               │
USUARIOS                      SERVIDORES
 │                               │
 │                    ┌──────────┼──────────┐
 │                    │          │          │
 │                   APP        DB       FICHEROS
 │
ADMIN
 │
BACKUP
 │
WI-FI
 ├── CORPORATIVO
 └── INVITADOS
```

Añade:

```text
VPN
MFA
PKI
CA
CERTIFICADOS
SIEM
EDR
IDS/IPS
WAF
```

si consideras que deben estar presentes.

---

# 📊 BLOQUE M · MATRIZ DE REGLAS

Diseña al menos **10 reglas de firewall** utilizando:

```text
ORIGEN
DESTINO
PROTOCOLO
PUERTO
ACCIÓN
JUSTIFICACIÓN
```

Ejemplo:

| Origen | Destino | Protocolo | Puerto | Acción | Justificación |
|---|---|---|---:|---|---|
| Internet | Web DMZ | TCP | 443 | PERMITIR | Portal HTTPS |
| | | | | | |
| | | | | | |

---

# 🏆 BLOQUE N · INFORME EJECUTIVO

Redacta un informe de máximo **500 palabras** para dirección explicando:

1. Los principales problemas actuales.
2. Los riesgos.
3. La nueva arquitectura.
4. La estrategia de certificados.
5. La estrategia de firewall.
6. La estrategia VPN.
7. Las prioridades de implantación.

---

# 🧠 RETO EXTRA · "EL PUERTO MISTERIOSO"

Durante la auditoría aparece:

```text
TCP/22
TCP/389
TCP/3306
TCP/445
TCP/3389
```

Explica qué servicios suelen asociarse a ellos y:

```text
¿Dónde permitirías cada uno?
¿Desde dónde?
¿Hacia dónde?
¿Por qué?
```

No basta con memorizar los puertos.

---

# 🎯 OBJETIVOS DE SUPERACIÓN

```text
□ Comprender deny by default.

□ Diseñar reglas de firewall.

□ Identificar reglas peligrosas.

□ Diseñar segmentación.

□ Diferenciar DMZ e interior.

□ Separar usuarios y servidores.

□ Aislar invitados.

□ Diseñar VPN por roles.

□ Comprender certificados.

□ Diferenciar CA y PKI.

□ Proteger claves privadas.

□ Comprender revocación.

□ Diferenciar CA pública e interna.

□ Comprender TLS.

□ Diseñar una arquitectura segura.

□ Relacionar firewall + segmentación + identidad.

□ Detectar movimiento lateral.

□ Priorizar controles.
```

---

# 🧭 REGLA DE ORO

No pienses:

> "¿Qué puerto abro?"

Piensa:

```text
¿QUIÉN?
   ↓
¿NECESITA ACCESO?
   ↓
¿A QUÉ RECURSO?
   ↓
¿DESDE DÓNDE?
   ↓
¿CON QUÉ PROTOCOLO?
   ↓
¿DURANTE CUÁNTO TIEMPO?
   ↓
¿CÓMO LO REGISTRO?
```

Y con certificados:

```text
¿QUIÉN CONFÍA EN QUIÉN?
        ↓
¿CÓMO SE AUTENTICA?
        ↓
¿DÓNDE ESTÁ LA CLAVE PRIVADA?
        ↓
¿CÓMO SE RENUEVA?
        ↓
¿CÓMO SE REVOCA?
```

---

# 🏁 FIN DE LA MISIÓN 13

## IDENTIDAD + PKI + FIREWALLS

```text
7.3 CERTIFICADOS
       │
       ├── identidad
       ├── confianza
       ├── PKI
       └── claves
              │
              ▼
7.4 FIREWALLS
       │
       ├── filtrado
       ├── segmentación
       ├── DMZ
       └── control de tráfico
              │
              ▼
        ARQUITECTURA
              │
              ▼
        DEFENSA EN PROFUNDIDAD
```

### 🚨 IMPORTANTE

**Esta misión NO incluye las soluciones.**

Resuélvela offline.

Cuando terminemos la corrección podremos comparar tu arquitectura con una solución de referencia y, sobre todo, detectar si estás cayendo en alguna de las trampas típicas:

```text
❌ "VLAN = seguridad completa"
❌ "HTTPS = aplicación segura"
❌ "Firewall = seguridad completa"
❌ "MFA = ya no necesito segmentación"
❌ "CA pública = siempre mejor"
❌ "Abrir porque funciona"
❌ "Cerrar todo porque es más seguro"
```

El objetivo final es que empieces a pensar en **capas de seguridad**, no en herramientas aisladas.

**Misión 13 desbloqueada.** 🔐🧱
