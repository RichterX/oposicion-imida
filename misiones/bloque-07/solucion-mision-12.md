# 🔐 BLOQUE 07 · SEGURIDAD
# 🧪 MISIÓN 12 · SOLUCIONES
## ENS + RGPD · Auditoría de seguridad y protección de datos

> **Objetivo de la corrección:** ofrecer una respuesta de referencia. No es necesario coincidir palabra por palabra. En las preguntas abiertas se valoran especialmente la identificación del problema, la justificación y la proporcionalidad de la medida.
>
> **Nota normativa:** para ENS se toma como referencia el Real Decreto 311/2022. Para RGPD se toma como referencia el Reglamento (UE) 2016/679 y la información vigente de la AEPD. El ENS establece, entre otros, seguridad integral, gestión basada en riesgos, prevención/detección/respuesta, líneas de defensa, vigilancia continua y diferenciación de responsabilidades; su Anexo II agrupa las medidas en marco organizativo, operacional y medidas de protección. citeturn0search0turn0search4

---

# 🔴 BLOQUE A · IDENTIFICACIÓN DEL INCIDENTE

## A.1 · ¿Evento, incidente, brecha o brecha de datos personales?

### Respuesta ideal

Estamos ante **un incidente de seguridad confirmado** y, además, existe una **violación de la seguridad de los datos personales**.

La cadena es:

```text
PHISHING
↓
ROBO DE CREDENCIALES
↓
ACCESO VPN
↓
ACCESO A SISTEMAS
↓
ACCESO A DOCUMENTACIÓN
↓
TRANSFERENCIA EXTERNA
↓
DATOS PERSONALES AFECTADOS
```

No es únicamente un evento aislado porque existe evidencia de acceso no autorizado y extracción de información.

También es una brecha de datos personales porque se ha producido una posible **confidencialidad comprometida** de datos personales. El RGPD define la violación de seguridad de los datos personales de forma que incluye, entre otros supuestos, la destrucción, pérdida, alteración, comunicación o acceso no autorizado a datos personales.

### Matiz importante

A las 11:30 todavía puede no conocerse:

```text
¿QUÉ DATOS EXACTOS SALIERON?
¿CUÁNTAS PERSONAS?
¿QUÉ CANTIDAD?
¿QUÉ CONSECUENCIAS?
```

Por tanto, hay que **investigar y evaluar el riesgo**, no esperar a tener certeza absoluta para iniciar el procedimiento.

---

## A.2 · Activos afectados

### Sistemas

```text
• Equipo de la empleada
• VPN
• Directorio corporativo
• Servidores internos
• Servidor de ficheros
• Base de datos potencialmente accesible
• Infraestructura de red
• Sistema de correo
• Sistemas de backup, al menos potencialmente
```

### Datos

```text
• Datos personales
• Documentación de investigación
• Información interna
• Resultados de investigación
• Posibles credenciales / información de identidad
```

### Usuarios

```text
• Cuenta de la empleada
• Posibles cuentas utilizadas posteriormente
• Administradores, si se produjo escalada
```

### Red

```text
• VPN
• Red interna
• Comunicaciones entre servidores
• Canal de salida hacia Internet
```

### Servicios

```text
• Acceso remoto
• Servicios de ficheros
• Servicios de investigación
• Posiblemente otros servicios internos
```

---

## A.3 · Tríada CIA

### 🔴 Confidencialidad

**Claramente afectada.**

Existe evidencia de:

```text
ACCESO NO AUTORIZADO
+
COPIA / TRANSFERENCIA DE ARCHIVOS
```

y parte de los archivos contienen datos personales.

### 🟠 Integridad

**Potencialmente afectada.**

El escenario no demuestra que el atacante haya modificado datos, pero una vez comprometida una cuenta y alcanzados servidores internos debe investigarse:

```text
¿SE MODIFICARON ARCHIVOS?
¿SE CREARON CUENTAS?
¿SE ALTERARON CONFIGURACIONES?
¿SE MODIFICARON DATOS?
```

Por tanto:

> Integridad potencialmente comprometida, pero no necesariamente confirmada.

### 🟡 Disponibilidad

**Potencialmente afectada.**

No hay todavía evidencia de indisponibilidad, pero existe riesgo de:

```text
RANSOMWARE
BORRADO
SABOTAJE
BLOQUEO DE CUENTAS/SERVICIOS
```

Por tanto:

> disponibilidad en riesgo, aunque no necesariamente afectada en el momento descrito.

### Resumen

```text
CONFIDENCIALIDAD → AFECTADA ✅
INTEGRIDAD       → EN RIESGO ⚠️
DISPONIBILIDAD   → EN RIESGO ⚠️
```

---

# 🔵 BLOQUE B · ANÁLISIS DEL ATAQUE

## B.1 · Fases

Una respuesta de referencia:

```text
PHISHING
↓
INITIAL ACCESS
↓
CREDENTIAL ACCESS
↓
ACCESO VPN
↓
DISCOVERY
↓
LATERAL MOVEMENT
↓
COLLECTION
↓
EXFILTRATION
```

No debemos inventar fases no observadas.

Por ejemplo:

```text
PERSISTENCE
PRIVILEGE ESCALATION
C2
```

podrían haber ocurrido, pero el escenario no las confirma.

Una buena respuesta debe distinguir:

```text
CONFIRMADO
vs.
POSIBLE
```

---

## B.2 · MITRE ATT&CK

| Táctica | Aplicación al escenario |
|---|---|
| **Initial Access** | Phishing |
| **Credential Access** | Captura de usuario/contraseña |
| **Discovery** | Investigación del entorno y servidores |
| **Lateral Movement** | Acceso desde el equipo comprometido hacia otros servidores |
| **Collection** | Acceso y recopilación de documentación |
| **Exfiltration** | Transferencia de archivos al exterior |

Podrían existir además:

```text
Persistence
Privilege Escalation
Command and Control
```

pero necesitaríamos evidencia.

**Importante:** una respuesta madura no convierte todas las fases posibles en hechos confirmados.

---

## B.3 · Debilidades que facilitaron el ataque

Hay muchas. Cualquier ocho bien justificadas serían válidas.

### 1. Ausencia de MFA

```text
CREDENCIALES ROBADAS
↓
VPN
↓
ACCESO
```

### 2. Reutilización de contraseñas

Aumenta el impacto de una credencial comprometida.

### 3. Cuentas de antiguos empleados activas

Aumentan la superficie de identidad.

### 4. Cuentas administrativas compartidas

Problemas:

```text
TRAZABILIDAD
+
RESPONSABILIDAD
+
CONTROL DE ACCESO
```

### 5. Permisos excesivos

Violación práctica del principio de:

```text
MÍNIMO PRIVILEGIO
```

### 6. Falta de formación anti-phishing

El usuario constituye un vector de ataque evidente.

### 7. Protección de correo insuficiente

Solo existen filtros antispam básicos.

### 8. Uso de cloud personal

Se pierde control institucional sobre los datos.

### 9. Uso de USB sin política clara

Puede facilitar fuga, pérdida o introducción de malware.

### 10. Falta de SIEM

Dificulta correlacionar:

```text
VPN
+
endpoint
+
servidores
+
transferencias
```

### 11. Logs dispersos

Dificultan investigación.

### 12. Relojes no sincronizados

Complican reconstruir una línea temporal.

### 13. Backups permanentemente conectados

Mayor exposición ante ransomware.

### 14. Falta de pruebas de restauración

No se puede asumir que la recuperación funcionará.

### 15. Falta de copia inmutable

Un atacante podría intentar comprometer también los backups.

### 16. Falta de inventario actualizado de tratamientos

Problema de gobernanza RGPD.

### 17. Falta de procedimiento de derechos

Dificulta atender correctamente a los interesados.

### 18. Falta de procedimiento claro de brechas

Retrasa la respuesta regulatoria.

---

# 🟢 BLOQUE C · ENS

## C.1 · Relación con ENS

Sí existe una relación clara.

INVEGA es un organismo público y sus sistemas soportan:

```text
INFORMACIÓN
+
SERVICIOS
```

El incidente demuestra debilidades en:

```text
CONTROL DE ACCESO
GESTIÓN DE RIESGOS
MONITORIZACIÓN
GESTIÓN DE INCIDENTES
CONTINUIDAD
MÍNIMO PRIVILEGIO
PROTECCIÓN DE LA INFORMACIÓN
```

El ENS exige una visión de seguridad integral y basada en riesgos, junto con prevención, detección y respuesta, líneas de defensa, vigilancia continua y diferenciación de responsabilidades. citeturn0search0turn0search4

Por tanto, no basta con decir:

> "Tenemos un firewall."

El cumplimiento requiere un **sistema integral de gestión de la seguridad**.

---

# C.2 · Medidas ENS

El Anexo II del ENS organiza las medidas en:

```text
MARCO ORGANIZATIVO
MARCO OPERACIONAL
MEDIDAS DE PROTECCIÓN
```

La misión utiliza "organizativas, operacionales y técnicas". La categoría técnica puede entenderse aquí como las medidas de protección/técnicas aplicables a los activos. citeturn0search0

## 🏢 Organizativas

Al menos:

```text
1. Política de seguridad actualizada.
2. Definición de roles y responsabilidades.
3. Comité/estructura de gestión de seguridad.
4. Política de control de acceso.
5. Política de gestión de incidentes.
6. Política de copias de seguridad.
7. Política de uso de cloud y dispositivos.
8. Formación y concienciación.
```

## ⚙️ Operacionales

```text
1. Análisis y gestión de riesgos.
2. Gestión de vulnerabilidades y parcheado.
3. Gestión de incidentes.
4. Monitorización continua.
5. Procedimientos de altas/bajas/cambios.
6. Pruebas de restauración.
7. Auditorías periódicas.
8. Gestión de continuidad.
```

## 🛡️ Técnicas / protección

```text
1. MFA.
2. EDR.
3. SIEM.
4. Segmentación de red.
5. Firewall interno.
6. WAF.
7. DLP.
8. Cifrado.
9. Control de acceso.
10. Backups inmutables.
11. Protección del correo.
12. MDM.
```

El ENS establece que las medidas deben seleccionarse considerando los activos, la categoría del sistema y los riesgos identificados. citeturn0search0

---

# C.3 · Control de acceso

Esta es una de las zonas más débiles de INVEGA.

### Usuarios

```text
CUENTA INDIVIDUAL
+
MÍNIMO PRIVILEGIO
+
REVISIÓN PERIÓDICA
```

### Administradores

Eliminar:

```text
CUENTAS COMPARTIDAS
```

Utilizar:

```text
CUENTAS NOMINALES
+
CUENTAS PRIVILEGIADAS SEPARADAS
+
MFA
+
REGISTRO DE ACTIVIDAD
```

### Altas y bajas

Implantar un proceso:

```text
ALTA
↓
ASIGNACIÓN DE PERMISOS

CAMBIO
↓
REVISIÓN

BAJA
↓
DESACTIVACIÓN INMEDIATA
↓
REVOCACIÓN DE SESIONES/TOKENS
```

### MFA

Especialmente:

```text
VPN
ADMINISTRACIÓN
CLOUD
ACCESOS CRÍTICOS
```

---

# C.4 · Monitorización

## Logs

Centralizar:

```text
VPN
FIREWALL
EDR
SERVIDORES
DIRECTORIO
APLICACIONES
CLOUD
```

## SIEM

Correlacionar:

```text
LOGIN
↓
VPN
↓
ENDPOINT
↓
SERVIDOR
↓
ACCESO A DATOS
↓
TRANSFERENCIA EXTERNA
```

Esto permitiría detectar el patrón completo en lugar de analizar cada log de forma aislada.

## EDR

En el equipo:

```text
PROCESOS
COMANDOS
ARCHIVOS
CONEXIONES
COMPORTAMIENTO
```

## Firewall

Analizar:

```text
CONEXIONES VPN
TRÁFICO INTERNO
SALIDAS
DESTINOS
```

Además, deben sincronizarse los relojes para facilitar la reconstrucción temporal.

---

# C.5 · Backups

La propuesta correcta:

```text
3-2-1
```

y además:

```text
COPIA INMUTABLE
+
COPIA AISLADA / OFFLINE SEGÚN ESTRATEGIA
+
CONTROL DE ACCESO
+
PRUEBAS DE RESTAURACIÓN
```

### RTO

Definir:

```text
¿Cuánto tiempo puede estar
el servicio sin funcionar?
```

### RPO

Definir:

```text
¿Cuánto dato podemos perder?
```

Ejemplo:

```text
RTO = 4 h
RPO = 1 h
```

No es necesario que esos valores sean los de INVEGA. Deben determinarse mediante análisis de impacto y necesidades del servicio.

El ENS establece que los sistemas deben disponer de copias de seguridad y mecanismos que permitan garantizar la continuidad ante pérdida de medios habituales. citeturn0search0

---

# 🟣 BLOQUE D · RGPD

## D.1 · ¿Existe una violación de datos personales?

**Sí, potencialmente y con fuertes indicios de confirmación.**

Tenemos:

```text
DATOS PERSONALES
+
ACCESO NO AUTORIZADO
+
TRANSFERENCIA EXTERNA
```

Eso encaja claramente en el concepto de violación de seguridad de datos personales.

La cuestión posterior es determinar:

```text
¿QUÉ DATOS?
¿CUÁNTAS PERSONAS?
¿QUÉ RIESGO?
```

---

# D.2 · Principios RGPD relacionados

## 🔴 Integridad y confidencialidad

Es el principio más claramente comprometido.

El RGPD exige que los datos se traten con medidas técnicas y organizativas apropiadas frente a acceso o tratamiento no autorizado y pérdida, destrucción o daño accidental. citeturn1search0turn1search5

---

## 🟠 Responsabilidad proactiva

También aparece claramente.

INVEGA debería poder demostrar:

```text
MEDIDAS
+
PROCEDIMIENTOS
+
CONTROL
+
GESTIÓN DE RIESGOS
```

La falta de inventario, procedimientos y formación dificulta esa demostración. El artículo 5.2 establece la responsabilidad del responsable y su capacidad de demostrar el cumplimiento. citeturn1search5

---

## 🟡 Transparencia

Hay indicios de problemas porque los formularios no muestran claramente:

```text
FINALIDAD
+
INFORMACIÓN DE PRIVACIDAD
```

Esto no demuestra por sí solo un incumplimiento completo, pero sí una debilidad clara.

---

## 🟡 Limitación de la finalidad

Puede estar en riesgo si datos recogidos para determinados proyectos terminan en:

```text
CLOUD PERSONAL
```

o se utilizan para finalidades distintas sin la correspondiente base jurídica/compatibilidad.

Pero hay que analizar el tratamiento concreto antes de afirmar incumplimiento.

---

## 🟡 Minimización

No se puede afirmar automáticamente que INVEGA incumpla minimización solo porque almacene nombre, email y fecha de nacimiento.

La pregunta correcta es:

> ¿Son esos datos adecuados, pertinentes y limitados a lo necesario para la finalidad?

El RGPD exige precisamente esa proporcionalidad. citeturn1search1

---

## 🟡 Limitación del plazo de conservación

El escenario no aporta información suficiente para afirmar incumplimiento.

Debe revisarse:

```text
FINALIDAD
+
PLAZOS
+
BASE JURÍDICA
+
NECESIDAD DE CONSERVACIÓN
```

---

## 🟡 Exactitud

No existen datos suficientes para concluir que se haya incumplido.

---

## 🟡 Licitud

Tampoco podemos afirmar automáticamente que exista un problema de licitud por el simple hecho de producirse la brecha.

Hay que determinar:

```text
BASE JURÍDICA
+
FINALIDAD
+
TRATAMIENTO
```

---

# D.3 · Quién debe participar

Equipo mínimo:

```text
IT
+
SEGURIDAD
+
DPO / DPD
+
DIRECCIÓN
+
JURÍDICO
+
RESPONSABLE DEL TRATAMIENTO
```

También pueden participar:

```text
COMUNICACIÓN
RRHH
PROVEEDORES
AUTORIDADES
```

según el caso.

---

# D.4 · ¿Debe notificarse a la autoridad?

La respuesta correcta **no es "siempre" ni "nunca"**.

El responsable debe evaluar el riesgo para los derechos y libertades de las personas.

Si la brecha es susceptible de producir un riesgo:

```text
→ NOTIFICACIÓN A LA AUTORIDAD
```

salvo que sea improbable que exista ese riesgo.

El artículo 33 establece, cuando proceda, notificación sin dilación indebida y, cuando sea factible, dentro de las **72 horas desde que el responsable tiene constancia de la brecha**. Si se supera ese plazo, deben explicarse los motivos. citeturn1search0turn0search3

### En este escenario

Por existir:

```text
DATOS PERSONALES
+
ACCESO NO AUTORIZADO
+
EXFILTRACIÓN CONFIRMADA
```

la organización debería realizar **inmediatamente la evaluación documentada del riesgo** y, si concurre riesgo, tramitar la notificación.

No debería esperar a que el incidente esté completamente cerrado.

---

# D.5 · ¿Debe comunicarse a los afectados?

Aquí el umbral es superior.

```text
RIESGO
    ↓
NOTIFICACIÓN AUTORIDAD
```

pero:

```text
ALTO RIESGO
    ↓
COMUNICACIÓN A AFECTADOS
```

El artículo 34 exige comunicar la brecha a los afectados sin dilación indebida cuando sea probable que entrañe un **alto riesgo** para sus derechos y libertades. citeturn1search0turn0search1

Por tanto:

> No basta con demostrar que hubo una brecha. Hay que valorar la gravedad y probabilidad del riesgo para las personas.

La AEPD indica que la comunicación debe ser clara y dirigida a los afectados para los que exista ese alto riesgo. citeturn0search1turn0search2

---

# 🟠 BLOQUE E · RESPUESTA

## E.1 · Contención inmediata

Una respuesta de referencia:

```text
1. Desactivar/bloquear la cuenta comprometida.

2. Revocar sesiones y tokens asociados.

3. Bloquear temporalmente el acceso VPN de la cuenta.

4. Aislar el endpoint comprometido.

5. Cambiar/rotar credenciales afectadas.

6. Revisar si las credenciales fueron reutilizadas en otros sistemas.

7. Bloquear indicadores de compromiso identificados.

8. Revisar y restringir conexiones entre segmentos.

9. Bloquear temporalmente destinos externos sospechosos.

10. Identificar otros equipos que hayan contactado con los mismos destinos.

11. Revisar cuentas con privilegios elevados.

12. Preservar logs y evidencias antes de perder información.
```

⚠️ Hay que evitar una contención indiscriminada que destruya evidencias o provoque una indisponibilidad innecesaria.

---

# E.2 · Evidencias

Conservar:

```text
EMAIL ORIGINAL DE PHISHING
+
CABECERAS
+
URL
+
LOGS VPN
+
LOGS FIREWALL
+
EDR
+
LOGS DEL ENDPOINT
+
LOGS DE SERVIDORES
+
LOGS DEL DIRECTORIO
+
REGISTROS DE ACCESO A FICHEROS
+
TRÁFICO / NETFLOW SI EXISTE
+
REGISTROS DEL SISTEMA EXTERNO
```

También:

```text
IMAGEN FORENSE DEL EQUIPO
```

cuando sea apropiado y compatible con el procedimiento de investigación.

Objetivo:

```text
RECONSTRUIR
QUÉ
CUÁNDO
CÓMO
DÓNDE
```

---

# E.3 · Erradicación

Antes de considerar controlado el incidente:

```text
• eliminar malware si existe;
• eliminar persistencia;
• corregir vulnerabilidades;
• revocar credenciales;
• invalidar sesiones/tokens;
• revisar cuentas creadas;
• eliminar accesos no autorizados;
• revisar configuraciones;
• parchear;
• revisar otros equipos comprometidos;
• comprobar que no existen otros mecanismos de acceso.
```

No basta con:

> "Formateamos el PC."

Hay que determinar si:

```text
EL ATACANTE
```

ha dejado:

```text
PERSISTENCIA
```

en otros sistemas.

---

# E.4 · Recuperación

Una secuencia válida:

```text
1. Confirmar alcance y erradicación.

2. Preparar sistemas limpios y actualizados.

3. Restaurar desde copias confiables.

4. Cambiar credenciales y secretos comprometidos.

5. Aplicar MFA y controles reforzados.

6. Validar sistemas antes de devolverlos a producción.

7. Monitorizar intensivamente la recuperación.

8. Confirmar integridad de los datos.

9. Confirmar disponibilidad de los servicios.

10. Documentar la recuperación.
```

---

# 🟡 BLOQUE F · MEJORA POSTERIOR

## F.1 · Diez medidas

Una solución posible:

```text
PERSONAS
1. Formación periódica anti-phishing.
2. Simulaciones de phishing.
3. Formación específica RGPD.

PROCESOS
4. Procedimiento de altas/bajas.
5. Procedimiento de incidentes.
6. Procedimiento de brechas RGPD.
7. Revisión periódica de permisos.

TECNOLOGÍA
8. MFA.
9. EDR.
10. SIEM.
11. DLP.
12. MDM.

DATOS
13. Clasificación.
14. Cifrado.
15. Restricción de exportaciones.

INFRAESTRUCTURA
16. Segmentación.
17. Firewalls internos.
18. Backups inmutables.
19. Monitorización centralizada.
20. Gestión de vulnerabilidades.
```

Cualquier diez bien justificadas son válidas.

---

# F.2 · Roban una contraseña y entran por VPN

La medida principal:

```text
MFA
```

Pero una solución madura añadiría:

```text
MFA
+
Conditional Access
+
VPN restringida
+
Device Compliance
+
Detección de anomalías
+
Revocación de sesiones
```

La idea es:

```text
CONTRASEÑA
≠
ACCESO AUTOMÁTICO
```

---

# F.3 · Reducir movimiento lateral

Medidas:

```text
SEGMENTACIÓN
+
FIREWALL INTERNO
+
MÍNIMO PRIVILEGIO
+
SEPARACIÓN DE ADMINISTRACIÓN
+
CUENTAS PRIVILEGIADAS
+
MFA
+
MONITORIZACIÓN
```

---

# F.4 · Reducir exfiltración

Medidas:

```text
DLP
+
EGRESS FILTERING
+
PROXY
+
CONTROL DE CLOUD
+
RESTRICCIÓN DE USB
+
CLASIFICACIÓN DE DATOS
+
MONITORIZACIÓN
```

---

# F.5 · Mejorar detección

```text
SIEM
+
EDR
+
NDR
+
LOGGING CENTRALIZADO
+
NTP / SINCRONIZACIÓN
+
ALERTAS
+
SOC / RESPONSABLE DE MONITORIZACIÓN
```

---

# 🔥 BLOQUE G · AUDITORÍA RÁPIDA

Diez ejemplos:

| Debilidad | Riesgo | Medida |
|---|---|---|
| Sin MFA | Compromiso de cuentas | MFA |
| Cuentas antiguas | Acceso indebido | Baja automática |
| Admins compartidos | Falta de trazabilidad | Cuentas nominales |
| Permisos excesivos | Movimiento lateral | Mínimo privilegio |
| Cloud personal | Fuga de datos | Cloud corporativo aprobado |
| USB sin control | Exfiltración/malware | Política + control |
| Sin SIEM | Detección tardía | SIEM |
| Logs dispersos | Investigación difícil | Centralización |
| Relojes desincronizados | Timeline incorrecto | NTP |
| Backups conectados | Ransomware | Inmutabilidad/aislamiento |
| Sin restore tests | Recuperación incierta | Pruebas periódicas |
| Sin MDM | Riesgo móvil | MDM |
| Sin formación | Phishing | Concienciación |
| Inventario RGPD incompleto | Falta de gobernanza | Registro actualizado |
| Sin procedimiento de brechas | Retraso | Procedimiento formal |

---

# 🧠 BLOQUE H · RAZONAMIENTO

## H.1 · "Tenemos antivirus, firewall y backups"

### Respuesta

No.

Esos controles son importantes pero:

```text
ANTIVIRUS
→ endpoint

FIREWALL
→ tráfico

BACKUP
→ recuperación
```

Ninguno garantiza:

```text
QUE NO ROBEN CREDENCIALES
```

ni:

```text
QUE NO HAYA MOVIMIENTO LATERAL
```

ni:

```text
QUE NO HAYA EXFILTRACIÓN
```

La defensa debe ser en profundidad:

```text
MFA
+
SEGMENTACIÓN
+
EDR
+
SIEM
+
DLP
+
BACKUPS
+
FORMACIÓN
```

---

## H.2 · "Cambiar contraseñas cada 30 días"

Insuficiente porque el problema no es solo:

```text
CONTRASEÑA DÉBIL
```

También existe:

```text
PHISHING
+
REUTILIZACIÓN
+
AUSENCIA DE MFA
+
PERMISOS EXCESIVOS
+
CUENTAS ANTIGUAS
```

Una contraseña puede ser robada hoy y utilizada inmediatamente.

Cambiarla cada 30 días no evita necesariamente:

```text
ROBO
```

---

## H.3 · Cuenta administrativa compartida

Es problemática por:

```text
FALTA DE TRAZABILIDAD
+
NO REPUDIO OPERATIVO
+
DIFICULTAD DE AUDITORÍA
+
RIESGO DE CREDENCIALES COMPARTIDAS
+
DIFICULTAD DE REVOCACIÓN
```

Debe preferirse:

```text
CUENTA NOMINAL
+
PRIVILEGIOS SEPARADOS
+
MFA
+
REGISTRO
```

---

## H.4 · "El cloud tiene contraseña"

No es suficiente.

Hay que evaluar:

```text
¿ESTÁ AUTORIZADO?
¿DÓNDE SE ALOJAN LOS DATOS?
¿QUÉ CONTROLES TIENE?
¿QUIÉN ES EL PROVEEDOR?
¿QUÉ CONTRATO EXISTE?
¿QUÉ TRATAMIENTOS REALIZA?
¿QUÉ PERMISOS?
¿CIFRADO?
¿LOGGING?
¿DÓNDE ESTÁN LOS DATOS?
```

Especialmente grave si contiene:

```text
DATOS PERSONALES
+
INFORMACIÓN CONFIDENCIAL
```

---

## H.5 · "No sabemos que hayan publicado los datos"

No basta.

La confidencialidad puede haberse comprometido mediante:

```text
ACCESO NO AUTORIZADO
```

aunque posteriormente no exista publicación.

En el escenario existe además:

```text
TRANSFERENCIA EXTERNA
```

por lo que hay evidencia de extracción.

La ausencia de publicación pública:

```text
≠
ausencia de brecha
```

---

# 🧪 BLOQUE I · ARQUITECTURA PROPUESTA

Una arquitectura razonable:

```text
                         INTERNET
                            │
                     ┌──────▼──────┐
                     │  FIREWALL   │
                     └──────┬──────┘
                            │
                  ┌─────────┴─────────┐
                  │                   │
                DMZ                RED INTERNA
                  │                   │
             ┌────┴────┐       ┌──────┴──────────┐
             │         │       │                 │
            WAF       WEB   USUARIOS         SERVIDORES
                                               │
                                ┌──────────────┼──────────────┐
                                │              │              │
                               APP             DB           FICHEROS
                                │              │              │
                                └──────────────┼──────────────┘
                                               │
                                          RED DE DATOS
                                               │
                                            BACKUPS
```

Y además:

```text
MFA
 ↓
VPN

EDR
 ↓
ENDPOINTS

SIEM
 ↓
LOGS

DLP
 ↓
DATOS / SALIDAS

MDM
 ↓
MÓVILES
```

### Importante

No se trata de colocar tecnología por colocarla.

Cada control debe responder a un riesgo.

---

# 🏆 BLOQUE J · INFORME EJECUTIVO

### Respuesta de referencia

> INVEGA ha sufrido un incidente de seguridad originado por una campaña de phishing que permitió obtener las credenciales de una empleada y utilizarlas para acceder a la VPN corporativa. La ausencia de MFA facilitó el acceso remoto. Posteriormente se produjo acceso a sistemas internos, documentación de investigación y una transferencia externa de archivos. Parte de la información afectada contiene datos personales, por lo que existe una posible violación de la seguridad de los datos personales que debe ser evaluada y gestionada conforme al RGPD.
>
> El incidente compromete claramente la confidencialidad y puede haber afectado o puesto en riesgo la integridad y disponibilidad de los sistemas. Entre las principales debilidades se encuentran la ausencia de MFA, permisos excesivos, cuentas administrativas compartidas, cuentas de antiguos empleados, falta de monitorización centralizada, uso de servicios cloud personales y una estrategia de backup insuficientemente protegida.
>
> Inmediatamente debe aislarse el equipo comprometido, bloquear las cuentas y sesiones afectadas, revocar credenciales y accesos, preservar evidencias, analizar el alcance, identificar otros sistemas comprometidos y contener cualquier movimiento lateral o exfiltración adicional.
>
> A medio plazo deben implantarse MFA, mínimo privilegio, cuentas administrativas nominales, segmentación, EDR, SIEM, DLP, protección avanzada del correo, políticas de cloud y dispositivos, formación, backups inmutables y procedimientos formales de respuesta a incidentes y brechas de datos personales.
>
> No puede descartarse todavía el acceso a otros sistemas, la persistencia del atacante, la modificación de información ni la extracción adicional de datos. Será necesario completar la investigación y documentar la evaluación de riesgos.

---

# 📊 MATRIZ FINAL DE RIESGO · SOLUCIÓN

Una posible matriz:

| Riesgo | Activo | Amenaza | Vulnerabilidad | Impacto | Probabilidad | Nivel | Medida |
|---|---|---|---|---|---|---|---|
| Robo de cuenta | VPN | Phishing | Sin MFA | Alto | Alta | Crítico | MFA |
| Movimiento lateral | Servidores | Atacante externo | Permisos excesivos | Alto | Alta | Crítico | Segmentación + mínimo privilegio |
| Exfiltración | Datos | Robo de información | Sin DLP/control de salida | Alto | Alta | Crítico | DLP + egress filtering |
| Ransomware | Servidores | Malware | Backups conectados | Alto | Media/Alta | Alto/Crítico | Backups inmutables |
| Fuga cloud | Datos personales | Uso no autorizado | Cloud personal | Alto | Media | Alto | Cloud corporativo |
| Falta de detección | Logs | Ataque persistente | Sin SIEM | Alto | Media | Alto | SIEM |
| Acceso antiguo | Directorio | Ex-empleado | Baja tardía | Alto | Media | Alto | Automatizar bajas |
| Compromiso móvil | Correo | Robo/pérdida | Sin MDM uniforme | Medio/Alto | Media | Alto | MDM |

No existe una única matriz correcta. Lo importante es que:

```text
AMENAZA
+
VULNERABILIDAD
+
IMPACTO
+
PROBABILIDAD
```

estén razonablemente conectados.

---

# 🧠 RETO EXTRA · SIN MALWARE

Supongamos:

```text
CREDENCIALES VÁLIDAS
+
HERRAMIENTAS LEGÍTIMAS
+
SERVICIOS AUTORIZADOS
```

## Indicadores

Al menos cinco:

```text
1. Login desde ubicación/horario anómalo.
2. Acceso VPN desde dispositivo no habitual.
3. Acceso a recursos nunca utilizados por el usuario.
4. Volumen anormal de descarga.
5. Acceso secuencial a múltiples servidores.
6. Transferencias externas inusuales.
7. Uso anómalo de herramientas administrativas.
8. Cambios de permisos.
9. Creación de sesiones simultáneas.
10. Acceso masivo a ficheros.
```

## Controles

```text
1. MFA.
2. UEBA / análisis de comportamiento.
3. SIEM.
4. EDR.
5. NDR.
6. DLP.
7. Segmentación.
8. Conditional Access.
9. PAM.
10. Alertas de comportamiento anómalo.
```

Este escenario es especialmente importante porque demuestra que:

> **"No hay malware detectado" no significa "no hay ataque".**

---

# 🏆 EVALUACIÓN DE LA MISIÓN

Una buena respuesta debería demostrar cuatro capacidades:

```text
1. IDENTIFICACIÓN
   → reconocer qué está ocurriendo.

2. RAZONAMIENTO
   → explicar por qué existe el riesgo.

3. APLICACIÓN
   → asociar ENS/RGPD/seguridad con el problema.

4. PRIORIZACIÓN
   → saber qué hacer primero.
```

## 🔥 La respuesta excelente

No sería la que enumera 50 controles.

Sería la que dice:

```text
PROBLEMA
↓
RIESGO
↓
PRIORIDAD
↓
CONTROL
↓
JUSTIFICACIÓN
```

Ejemplo:

```text
SIN MFA
↓
Credenciales robadas permiten VPN
↓
Riesgo alto de acceso no autorizado
↓
MFA + control de acceso condicional
↓
Una contraseña robada deja de ser suficiente
```

---

# 📚 PUNTOS QUE DEBES REPASAR SI HAS FALLADO

```text
❌ Evento vs incidente
→ 7.5.4

❌ CIA
→ 7.5.1

❌ MITRE ATT&CK
→ 7.5.2

❌ Ataques de credenciales
→ 7.5.3

❌ ENS: requisitos y medidas
→ 7.1

❌ Principios RGPD
→ 7.2

❌ Brechas RGPD
→ 7.2

❌ Control de acceso
→ 7.4 + 7.5

❌ Firewalls / segmentación
→ 7.4

❌ RTO / RPO / backups
→ 7.5.4
```

---

# 🎯 RESUMEN FINAL

La misión completa puede resumirse así:

```text
                  PHISHING
                     ↓
             CREDENCIALES ROBADAS
                     ↓
                    VPN
                     ↓
                 SIN MFA
                     ↓
             ACCESO AL SISTEMA
                     ↓
              MOVIMIENTO LATERAL
                     ↓
                  DATOS
                     ↓
               EXFILTRACIÓN
                     ↓
             DATOS PERSONALES
                     ↓
              ┌──────┴──────┐
              ↓             ↓
             ENS           RGPD
              ↓             ↓
        INCIDENTE       BRECHA
              │             │
              └──────┬──────┘
                     ↓
                  RESPUESTA
                     ↓
             CONTENER + INVESTIGAR
                     ↓
                ERRADICAR
                     ↓
                 RECUPERAR
                     ↓
              MEJORA CONTINUA
```

## ⭐ Las cinco ideas que quiero que te queden

```text
1. UNA CONTRASEÑA ROBADA NO DEBERÍA BASTAR.
   → MFA.

2. ESTAR DENTRO NO SIGNIFICA PODER IR A TODAS PARTES.
   → Segmentación + mínimo privilegio.

3. NO DETECTAR MALWARE NO SIGNIFICA NO TENER INCIDENTE.
   → Monitorización de comportamiento.

4. UNA BRECHA RGPD NO SE EVALÚA SOLO POR "¿SE PUBLICÓ?"
   → Se evalúa el riesgo para derechos y libertades.

5. PREVENIR NO ES EL FINAL.
   → Detectar + responder + recuperar + mejorar.
```

---

# 🏁 MISIÓN 12 · CORREGIDA

**Resultado esperado:**

```text
ENS        → seguridad integral + riesgo + controles
RGPD       → protección de datos + riesgo + brechas
7.5        → ataque + detección + respuesta
7.4        → firewall + segmentación
CIA        → confidencialidad principalmente
```

**Misión 12: completada.** 🔐
