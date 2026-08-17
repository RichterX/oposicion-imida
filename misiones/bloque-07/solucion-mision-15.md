# 🏆 BLOQUE 07 · SEGURIDAD
# 🧪 MISIÓN 15 · SOLUCIONES
## Auditoría integral · ENS + RGPD + Certificados + Firewalls + Ciberseguridad

> **Nota:** Esta es una solución de referencia. En una auditoría real pueden existir varias medidas técnicamente válidas. En las preguntas abiertas se valora especialmente la capacidad de **justificar el riesgo, priorizar y relacionar el control con el problema**.

---

# 🔴 BLOQUE A · CLASIFICACIÓN DE HALLAZGOS

Una clasificación razonable sería:

| Nº | Hallazgo | Prioridad | Motivo |
|---:|---|---|---|
| 01 | ANY → DB 3306 | 🔴 Crítico | Exposición directa de un activo crítico |
| 02 | Internet → LDAP 389 | 🔴 Crítico | Servicio de directorio expuesto innecesariamente |
| 03 | VPN → toda red | 🔴 Alto | Compromiso de una cuenta con alcance excesivo |
| 04 | Equipos normales para administración | 🟠 Alto | Aumenta riesgo de compromiso privilegiado |
| 05 | Certificados sin control + clave compartida | 🔴 Crítico | Riesgo de suplantación y pérdida de confianza |
| 06 | CA sin gestión formal | 🔴 Alto | Debilidad estructural de la PKI |
| 07 | Guest → recursos internos | 🔴 Alto | Facilita movimiento lateral |
| 08 | Egress sin restricciones | 🟠 Alto | Facilita C2 y exfiltración |
| 09 | Backups sin inmutabilidad/pruebas | 🔴 Crítico | Riesgo grave de pérdida de recuperación |
| 10 | Logs 7 días | 🟠 Medio/Alto | Dificulta investigación y trazabilidad |
| 11 | Cuentas de antiguos empleados | 🔴 Crítico | Identidades activas sin necesidad |
| 12 | 23 administradores locales cuando deberían ser 12 | 🔴 Alto | Exceso de privilegios |
| 13 | Datos personales en cloud personal | 🔴 Crítico | Falta de control sobre tratamiento y seguridad |
| 14 | Registro de actividades desactualizado | 🟠 Alto | Falta de conocimiento sobre tratamientos |
| 15 | Sin procedimiento de brechas | 🟠 Alto | Riesgo operativo y de cumplimiento |
| 16 | Formación de hace 3 años | 🟡 Medio | Aumenta probabilidad de ingeniería social |
| 17 | IR sin simulacros | 🟠 Alto | Procedimiento no validado |
| 18 | Política ENS desactualizada | 🟠 Alto | Gobernanza no alineada con entorno actual |
| 19 | Análisis de riesgos de 4 años | 🔴 Alto | No contempla amenazas actuales |
| 20 | Sin RTO/RPO | 🔴 Alto | No existe objetivo formal de recuperación |

> **Matiz importante:** el número exacto de hallazgos "críticos" puede variar según metodología de riesgo. Lo importante es justificar por **impacto + probabilidad + exposición + criticidad del activo**.

---

# 🟠 BLOQUE B · MATRIZ DE RIESGOS

Una solución posible:

| Riesgo | Activo | Amenaza | Vulnerabilidad | Impacto | Prob. | Nivel | Tratamiento |
|---|---|---|---|---|---|---|---|
| DB expuesta | DB | Ataque remoto | ANY → 3306 | Muy alto | Alta | 🔴 Crítico | Mitigar |
| LDAP expuesto | Directorio | Ataque externo | 389 público | Muy alto | Alta | 🔴 Crítico | Mitigar |
| VPN excesiva | Red interna | Robo de cuenta | Sin segmentación | Alto | Alta | 🔴 Alto | Mitigar |
| Clave privada expuesta | PKI | Suplantación | Carpeta compartida | Muy alto | Media/Alta | 🔴 Alto/Crítico | Revocar + renovar |
| Guest interno | Red | Movimiento lateral | Segmentación insuficiente | Alto | Alta | 🔴 Alto | Mitigar |
| Backup comprometible | Copias | Ransomware | Sin inmutabilidad | Muy alto | Media | 🔴 Alto | Mitigar |
| Cuentas antiguas | Identidad | Uso fraudulento | No revocación | Alto | Media | 🔴 Alto | Eliminar |
| Cloud personal | Datos | Exfiltración | Servicio no controlado | Muy alto | Media | 🔴 Alto/Crítico | Eliminar/controlar |
| Exceso admin | Endpoints | Escalada | Privilegios excesivos | Alto | Alta | 🔴 Alto | Reducir |
| Sin RTO/RPO | Servicios | Incidente grave | Sin objetivos | Alto | Media | 🟠 Alto | Definir |

---

# 🏛️ BLOQUE C · ENS

## C.1 · Clasificación

### Marco organizativo

```text
Política de seguridad
Gestión de riesgos
Roles y responsabilidades
Gobernanza
```

Relacionados especialmente con:

```text
18
19
20
```

---

### Marco operacional

```text
Gestión de activos
Gestión de cambios
Gestión de incidentes
Continuidad
Gestión de vulnerabilidades
Copias de seguridad
Monitorización
```

Relacionados especialmente con:

```text
09
10
17
19
20
```

---

### Medidas de protección

```text
Control de acceso
Protección de comunicaciones
Protección de endpoints
Segmentación
Registro de actividad
Protección de información
```

Relacionados especialmente con:

```text
01
02
03
04
05
07
08
11
12
```

---

# C.2 · Medidas a implantar

Prioridad:

```text
1. Eliminar exposiciones innecesarias.
2. Revisar control de acceso.
3. Segmentar redes.
4. Gestionar privilegios.
5. Proteger PKI.
6. Centralizar logs.
7. Mejorar backups.
8. Formalizar incident response.
9. Actualizar análisis de riesgos.
10. Definir continuidad.
```

---

# C.3 · Documentación necesaria

Como mínimo:

```text
Política de seguridad
+
Roles y responsabilidades
+
Inventario de activos
+
Análisis de riesgos
+
Procedimientos de acceso
+
Gestión de incidentes
+
Gestión de vulnerabilidades
+
Gestión de cambios
+
Backups
+
Continuidad
+
Gestión de certificados
+
Registro de actividad
+
Planes de auditoría
```

---

# C.4 · ¿Cómo demostrar cumplimiento?

No basta con:

> "Tenemos una política."

Hay que aportar evidencias:

```text
documentos aprobados
+
registros
+
configuraciones
+
logs
+
tickets
+
revisiones
+
pruebas
+
auditorías
+
simulacros
+
informes
```

La diferencia fundamental:

```text
DECLARAR CONTROL
≠
DEMOSTRAR CONTROL
```

---

# 🟣 BLOQUE D · RGPD

## D.1 · Principios potencialmente afectados

Especialmente:

```text
Responsabilidad proactiva
+
Integridad y confidencialidad
+
Minimización
+
Limitación de finalidad
+
Exactitud, cuando corresponda
+
Transparencia, cuando corresponda
```

En el hallazgo 13 destaca además la necesidad de saber:

```text
QUIÉN TRATA
QUÉ DATOS
PARA QUÉ
DÓNDE
CON QUÉ BASE
BAJO QUÉ CONTROLES
```

---

# D.2 · Documentación

Debe revisarse y mantener actualizada, según corresponda:

```text
Registro de actividades de tratamiento
+
políticas
+
análisis de riesgos
+
medidas de seguridad
+
contratos / acuerdos con encargados
+
gestión de brechas
+
evidencias de cumplimiento
```

---

# D.3 · Cloud personal

Debe **detenerse o regularizarse inmediatamente**.

Pasos:

```text
1. Identificar datos almacenados.

2. Identificar usuarios.

3. Identificar proveedor.

4. Determinar quién controla la cuenta.

5. Determinar ubicación y tratamiento.

6. Recuperar los datos institucionales.

7. Retirar información del servicio no autorizado.

8. Evaluar si ha existido una brecha.

9. Revisar contratos y garantías necesarias.

10. Establecer una solución corporativa autorizada.
```

No debemos asumir automáticamente que todo uso de cloud es ilegal.

El problema principal es:

> **un tratamiento de datos institucionales fuera del control y gobierno de INVEGA.**

---

# D.4 · Procedimiento de brecha

```text
DETECCIÓN
   ↓
REGISTRO
   ↓
TRIAJE
   ↓
IDENTIFICACIÓN DE DATOS
   ↓
EVALUACIÓN DEL RIESGO
   ↓
DECISIÓN
   ├── No notificar
   ├── Notificar autoridad
   └── Notificar autoridad + afectados
   ↓
MITIGACIÓN
   ↓
DOCUMENTACIÓN
   ↓
LECCIONES APRENDIDAS
```

La evaluación debe determinar si existe riesgo para los derechos y libertades de las personas.

Cuando proceda, el RGPD contempla como referencia la notificación a la autoridad de control sin dilación indebida y, cuando sea posible, dentro de las **72 horas desde que el responsable tiene constancia de la brecha**.

---

# 🔵 BLOQUE E · CERTIFICADOS Y PKI

## E.1 · Riesgos

Los hallazgos 05 y 06 implican:

```text
certificados sin propietario
+
inventario incompleto
+
renovaciones inciertas
+
revocación no formalizada
+
clave privada expuesta
+
CA sin gobierno suficiente
```

Riesgos:

```text
suplantación
+
interrupción de servicios
+
pérdida de confianza
+
dificultad de respuesta
+
certificados expirados
```

---

# E.2 · Política de certificados

Debe existir un inventario:

| Campo | Ejemplo |
|---|---|
| Certificado | api.invega.es |
| Propietario | TIC |
| Servicio | API |
| CA | Pública/Interna |
| Fecha emisión | ... |
| Fecha expiración | ... |
| Responsable renovación | ... |
| Ubicación | ... |
| Estado | Activo |
| Clave protegida | Sí |

Ciclo:

```text
SOLICITUD
↓
APROBACIÓN
↓
EMISIÓN
↓
INSTALACIÓN
↓
INVENTARIO
↓
MONITORIZACIÓN
↓
RENOVACIÓN
↓
REVOCACIÓN / EXPIRACIÓN
```

---

# E.3 · Certificado con clave privada compartida

🔴 **Debe tratarse como potencialmente comprometido.**

Procedimiento:

```text
1. Identificar certificado.

2. Determinar exposición de la clave.

3. Restringir acceso.

4. Preservar evidencia si existe sospecha de compromiso.

5. Revocar certificado cuando proceda.

6. Generar NUEVO par de claves.

7. Solicitar nuevo certificado.

8. Instalarlo.

9. Validar servicio.

10. Eliminar la clave antigua de los lugares inseguros.

11. Documentar.
```

Punto clave:

```text
NO reutilizar una clave privada
potencialmente comprometida.
```

---

# E.4 · Diferencias

### Certificado

```text
Vincula identidad + clave pública
mediante una firma de confianza.
```

### Clave privada

```text
Secreto criptográfico que debe protegerse.
```

### CA

```text
Entidad que emite/firma certificados.
```

### PKI

```text
Conjunto de tecnología,
personas, políticas y procedimientos
que gestionan confianza y certificados.
```

---

# 🧱 BLOQUE F · FIREWALL Y SEGMENTACIÓN

## F.1 · Reglas a eliminar

Como mínimo:

```text
❌ ANY → DB :3306
❌ INTERNET → LDAP :389
```

Y debe revisarse:

```text
❌ VPN → toda la red
```

No necesariamente se "elimina" la VPN, sino que se sustituye por acceso segmentado.

---

# F.2 · Reglas a crear

Ejemplos:

```text
Internet → Web DMZ :443       ALLOW
Internet → API DMZ :443       ALLOW
Internet → DB :3306            DENY
Internet → LDAP :389           DENY

App → DB :3306                 ALLOW
Usuarios → DB :3306            DENY

Guest → Internet               ALLOW
Guest → Red interna             DENY

Admin → Servidores              ALLOW
solo puertos necesarios

Backup → Servidores             ALLOW
solo tráfico de backup

Servidores → Internet           RESTRINGIR
solo destinos necesarios
```

Y al final:

```text
ANY → ANY → DENY
```

---

# F.3 · Segmentación definitiva

```text
                         INTERNET
                            │
                     FIREWALL EXTERNO
                            │
                           DMZ
                      ┌─────┴─────┐
                     WEB         API
                      │           │
                      └─────┬─────┘
                            │
                     FIREWALL INTERNO
                            │
       ┌──────────┬─────────┼────────┬──────────┐
       │          │         │        │          │
    USUARIOS   SERVERS      DB      ADMIN     BACKUP
       │          │                  │
       │          └── APP/FILES      │
       │                             │
       ├── WIFI CORP                 │
       ├── GUEST ──────→ INTERNET    │
       └── IOT                       │
                                    │
                               MANAGEMENT
```

---

# F.4 · Movimiento lateral

Control:

```text
SEGMENTACIÓN
+
FIREWALL INTERNO
+
ACL
+
MÍNIMO PRIVILEGIO
+
EDR
+
MONITORIZACIÓN
```

El objetivo:

```text
COMPROMISO DE UN EQUIPO
        ↓
NO DEBE SIGNIFICAR
        ↓
ACCESO A TODA LA ORGANIZACIÓN
```

---

# 🔐 BLOQUE G · IDENTIDAD

## G.1 · Problemas

### Hallazgo 04

Uso de equipos normales para administración.

Riesgo:

```text
phishing
+
malware
+
robo de sesión
+
escalada privilegiada
```

### Hallazgo 11

Cuentas antiguas activas.

```text
identidades innecesarias
+
credenciales potencialmente válidas
```

### Hallazgo 12

Exceso de administradores locales.

```text
superficie de privilegios excesiva
```

---

# G.2 · Altas, cambios y bajas

## Alta

```text
solicitud
↓
aprobación
↓
creación
↓
rol
↓
mínimo privilegio
↓
MFA
↓
registro
```

## Cambio

```text
cambio de puesto
↓
revisión de permisos
↓
retirar antiguos
↓
añadir nuevos
↓
registro
```

## Baja

```text
notificación
↓
deshabilitar cuenta
↓
revocar sesiones
↓
revocar tokens
↓
retirar permisos
↓
recuperar activos
↓
documentar
```

---

# G.3 · Privilegios

Una solución sólida:

```text
CUENTAS NORMALES
        +
CUENTAS ADMINISTRATIVAS SEPARADAS
        +
MFA
        +
PAM
        +
JUST-IN-TIME cuando sea viable
        +
REGISTRO
        +
REVISIÓN
```

Los administradores no deberían realizar navegación y correo cotidiano con una identidad privilegiada.

---

# G.4 · MFA / PAM / EDR / SIEM

### MFA

Protege autenticación.

### PAM

Controla y gobierna cuentas privilegiadas.

### EDR

Detecta y responde a actividad sospechosa en endpoints.

### SIEM

Centraliza y correlaciona eventos.

```text
MFA
→ identidad

PAM
→ privilegios

EDR
→ endpoint

SIEM
→ correlación
```

---

# 🚨 BLOQUE H · RESPUESTA AL INCIDENTE

## H.1 · ¿Es incidente?

Sí.

Aunque sea una prueba controlada, se ha demostrado una **debilidad de seguridad real**:

```text
GUEST
↓
DESCUBRIMIENTO
↓
LDAP
↓
SERVIDORES
↓
TRÁFICO SALIENTE
```

En un ejercicio autorizado, se clasificaría como:

```text
hallazgo de seguridad / incidente de prueba
```

y se documentaría.

---

# H.2 · Primeros 15 minutos

```text
1. Confirmar alcance de la prueba.

2. Identificar equipo origen.

3. Aislar el segmento GUEST si procede.

4. Bloquear comunicaciones innecesarias.

5. Preservar logs.

6. Revisar SIEM.

7. Identificar sistemas contactados.

8. Determinar si existe exfiltración real.

9. Informar al responsable de seguridad.

10. Evitar cambios destructivos.
```

---

# H.3 · Primera hora

```text
1. Reconstruir timeline.

2. Correlacionar SIEM.

3. Revisar EDR.

4. Revisar firewall.

5. Revisar LDAP.

6. Revisar DNS.

7. Identificar otros equipos.

8. Determinar alcance.

9. Corregir segmentación.

10. Revisar posible impacto RGPD.

11. Documentar decisiones.

12. Definir plan de remediación.
```

---

# H.4 · Evidencias

```text
SIEM
EDR
Firewall
LDAP
DNS
DHCP
VPN
Servidores
WAF
Proxy
```

Buscar:

```text
IP
MAC
usuario
hora
destino
puerto
proceso
volumen
acción
```

---

# H.5 · ¿Continúa activo?

Buscar:

```text
conexiones activas
+
nuevos IOC
+
nuevas alertas
+
nuevos equipos
+
nuevas cuentas
+
tráfico saliente
+
actividad LDAP
+
procesos sospechosos
```

---

# 🧪 BLOQUE I · FORENSE

Construcción de timeline:

```text
GUEST
 ↓
IP/MAC
 ↓
DNS
 ↓
LDAP
 ↓
SERVIDOR
 ↓
COLECCIÓN
 ↓
TRÁFICO SALIENTE
```

Cruzar:

```text
DHCP
+
DNS
+
Firewall
+
LDAP
+
EDR
+
SIEM
```

La meta es responder:

```text
QUIÉN
+
DESDE DÓNDE
+
CUÁNDO
+
QUÉ HIZO
+
A QUÉ ACCEDIÓ
+
QUÉ SALIÓ
```

---

# 💾 BLOQUE J · BACKUPS Y CONTINUIDAD

## J.1 · Estrategia

Una estrategia mejorada:

```text
BACKUP OPERATIVO
+
COPIA SECUNDARIA
+
COPIA FUERA DEL ENTORNO PRINCIPAL
+
INMUTABILIDAD
+
CIFRADO
+
CONTROL DE ACCESO
+
MONITORIZACIÓN
+
PRUEBAS DE RESTAURACIÓN
```

Concepto:

```text
3-2-1
```

complementado cuando sea posible con:

```text
inmutabilidad
+
aislamiento
```

---

# J.2 · Ejemplos RTO/RPO

No existe una única cifra correcta.

Una propuesta:

| Servicio | RTO | RPO | Justificación |
|---|---:|---:|---|
| Portal web | 4 h | 1 h | Servicio público importante |
| Aplicación interna | 8 h | 4 h | Impacto operativo |
| Base de datos | 4 h | 1 h | Datos críticos |
| Documentación | 24 h | 8 h | Menor criticidad |

Lo importante es:

```text
NEGOCIO
↓
CRITICIDAD
↓
RTO/RPO
```

y no inventar cifras sin análisis.

---

# J.3 · Prueba de restauración

```text
1. Seleccionar backup.

2. Verificar integridad.

3. Crear entorno de prueba.

4. Restaurar.

5. Validar aplicación.

6. Validar datos.

7. Medir tiempo.

8. Comparar con RTO.

9. Comparar pérdida con RPO.

10. Documentar resultado.

11. Corregir fallos.

12. Repetir periódicamente.
```

---

# 📊 BLOQUE K · LOGGING

## K.1 · Logs a centralizar

```text
Firewall
VPN
LDAP
DNS
DHCP
EDR
Servidores
DB
WAF
Proxy
Cloud
Sistemas críticos
```

---

# K.2 · Retención

La política interna establece:

```text
90 días
```

Por tanto el hallazgo 10 debe corregirse para alcanzar la política.

Pero la retención definitiva debe establecerse considerando:

```text
necesidades de seguridad
+
cumplimiento
+
capacidad
+
coste
+
tipo de información
```

---

# K.3 · Alertas

Al menos:

```text
1. Login imposible geográficamente.
2. Múltiples fallos MFA.
3. Inicio de sesión privilegiado anómalo.
4. Acceso VPN desde país inesperado.
5. Enumeración LDAP masiva.
6. Escaneo de red.
7. Movimiento lateral.
8. Gran volumen de tráfico saliente.
9. Acceso a backup.
10. Acceso al sistema de certificados.
11. Creación de cuentas.
12. Elevación de privilegios.
13. Desactivación de EDR.
14. PowerShell anómalo.
15. Office → PowerShell.
16. Comunicación con IOC.
17. Transferencia de archivos masiva.
18. Cambios en firewall.
19. Cambios en CA/PKI.
20. Acceso administrativo fuera de horario.
```

---

# 🧠 BLOQUE L · FORMACIÓN

Programa anual posible:

## Trimestre 1

```text
Phishing
Contraseñas
MFA
```

## Trimestre 2

```text
Ingeniería social
Cloud
USB
```

## Trimestre 3

```text
Móviles
Protección de datos
Trabajo remoto
```

## Trimestre 4

```text
Simulación de phishing
Repaso
Incidentes
```

Además:

```text
microformaciones
+
recordatorios
+
campañas
+
simulaciones
```

---

# 🚨 BLOQUE M · GESTIÓN DE INCIDENTES

## Tabletop

Simulación principalmente:

```text
DECISIONES
+
COMUNICACIÓN
+
ROLES
```

Sin necesidad de ejecutar técnicamente el ataque.

---

## Simulación técnica

Se prueba:

```text
detección
+
contención
+
herramientas
+
procedimientos
```

---

## Red Team / Purple Team

### Red Team

Busca:

```text
simular atacante
```

### Purple Team

Une:

```text
ATAQUE
+
DEFENSA
```

para mejorar detecciones y controles.

---

# 🏛️ BLOQUE N · GOBERNANZA

## N.1 · Actualizar

```text
Política de seguridad
+
Análisis de riesgos
+
Inventario
+
Arquitectura
+
Procedimientos
+
Continuidad
+
Incidentes
+
Cloud
+
Teletrabajo
+
Móviles
+
Ransomware
```

---

# N.2 · Periodicidad

No existe una única periodicidad universal.

Una propuesta:

| Elemento | Revisión |
|---|---|
| Política | Anual + ante cambios importantes |
| Riesgos | Anual + ante cambios importantes |
| Activos | Continua / revisión periódica |
| Procedimientos | Anual + después de incidentes |
| Permisos | Periódica + cambios de puesto |
| Certificados | Monitorización continua |
| Backups | Monitorización continua + pruebas periódicas |
| Incidentes | Después de cada incidente |
| Continuidad | Ejercicios periódicos |

---

# 🧠 BLOQUE O · PRIORIZACIÓN

Si solo podemos hacer cinco actuaciones inmediatas:

## 🥇 1. Eliminar DB expuesta

```text
ANY → DB
```

Riesgo crítico.

---

## 🥈 2. Segmentar GUEST

Actualmente:

```text
GUEST → LDAP/SERVERS
```

Esto contradice el principio de aislamiento.

---

## 🥉 3. Revisar cuentas antiguas

```text
14 cuentas
```

son identidades innecesarias.

---

## 4. Implantar backups inmutables

Porque:

```text
backup existente
≠
backup resistente a ataque
```

---

## 5. Revisar cloud personal

Especialmente porque contiene:

```text
datos personales
+
investigación
```

y está fuera del gobierno corporativo.

### ¿Y MFA?

Aquí ya existe MFA.

Por eso **no sería una de las cinco primeras actuaciones** frente a estos hallazgos, aunque debe mantenerse y mejorarse.

### ¿Y LDAP?

También sería candidato clarísimo a las cinco primeras:

```text
Internet → LDAP
```

En una situación real, puede desplazar a cualquiera de las anteriores según exposición y criticidad.

---

# 💰 BLOQUE P · ROADMAP

# 0-30 DÍAS

```text
Eliminar DB expuesta
Bloquear LDAP externo
Aislar GUEST
Eliminar cuentas antiguas
Revisar privilegios
Proteger clave privada
Revisar certificados críticos
Contener cloud personal
Revisar backups
Definir responsables
```

---

# 30-90 DÍAS

```text
Segmentación completa
VPN por roles
PAM
Inventario de certificados
Gestión formal PKI
Centralización de logs
Política de incidentes
Procedimiento RGPD
Revisión de riesgos
```

---

# 3-6 MESES

```text
Backups inmutables
Pruebas de restauración
EDR mejorado
SIEM afinado
WAF/IDS/IPS
Programa de formación
Tabletop
RTO/RPO
```

---

# 6-12 MESES

```text
Auditoría
Ejercicios avanzados
Purple Team
Revisión integral ENS
Revisión RGPD
Mejora continua
Automatización
Métricas de seguridad
```

---

# 📋 BLOQUE Q · PLAN DE ACCIÓN

Ejemplo:

| Hallazgo | Riesgo | Acción | Responsable | Prioridad | Plazo | Evidencia |
|---|---|---|---|---|---|---|
| 01 | DB expuesta | Eliminar regla | Redes | Crítica | 24 h | Config firewall |
| 02 | LDAP expuesto | Bloquear Internet | Redes | Crítica | 24 h | Regla + prueba |
| 03 | VPN excesiva | Segmentar por roles | Seguridad | Alta | 30 días | Matriz acceso |
| 05 | Clave expuesta | Revocar/renovar | PKI | Crítica | 24-72 h | Nuevo cert |
| 07 | Guest interno | Aislar VLAN | Redes | Alta | 7 días | Test segmentación |
| 09 | Backup débil | Inmutabilidad | Sistemas | Crítica | 30 días | Restauración |
| 10 | Logs cortos | Aumentar retención | Seguridad | Alta | 30 días | SIEM |
| 11 | Cuentas antiguas | Deshabilitar | IAM | Crítica | 24 h | Auditoría IAM |
| 12 | Exceso admin | Reducir privilegios | IAM | Alta | 30 días | Lista permisos |
| 13 | Cloud personal | Migrar a plataforma corporativa | DPO/IT | Crítica | 7-30 días | Inventario |
| 14 | ROPA desactualizado | Actualizar | DPO | Alta | 60 días | ROPA aprobado |
| 15 | Brechas sin proceso | Crear procedimiento | DPO/Sec | Alta | 30 días | Procedimiento |
| 17 | IR no probado | Tabletop | Seguridad | Alta | 90 días | Informe |
| 18 | Política ENS | Actualizar | Seguridad | Alta | 60 días | Política |
| 19 | Riesgos antiguos | Rehacer análisis | Seguridad | Alta | 60 días | Matriz |
| 20 | Sin RTO/RPO | Definir BIA + objetivos | Continuidad | Alta | 90 días | Plan |

---

# 🧠 BLOQUE R · RAZONAMIENTO

## R.1 · MFA + VPN = acceso a toda la red

❌ Incorrecto.

```text
MFA
→ AUTENTICACIÓN

SEGMENTACIÓN
→ ALCANCE

AUTORIZACIÓN
→ PERMISOS
```

Son controles diferentes.

---

## R.2 · Backups = continuidad

❌ Incorrecto.

Backups son una parte de la continuidad.

Continuidad también necesita:

```text
RTO
+
RPO
+
PERSONAS
+
PROCEDIMIENTOS
+
DEPENDENCIAS
+
COMUNICACIÓN
+
PRUEBAS
```

---

## R.3 · SIEM = monitorización resuelta

❌ Incorrecto.

SIEM proporciona una plataforma de:

```text
RECOGIDA
+
CORRELACIÓN
+
ALERTAS
+
ANÁLISIS
```

pero necesita:

```text
fuentes
+
casos de uso
+
reglas
+
personal
+
respuesta
```

---

## R.4 · CA interna = certificados seguros

❌ Incorrecto.

La CA proporciona confianza dentro del modelo establecido.

La seguridad depende también de:

```text
protección de claves
+
gestión
+
revocación
+
políticas
+
inventario
+
auditoría
```

---

## R.5 · Firewall bloquea Internet → DB

❌ No basta.

También hay que controlar:

```text
USUARIOS → DB
SERVIDORES → DB
GUEST → SERVIDORES
VPN → RED
SERVIDORES → INTERNET
```

La seguridad debe contemplar tráfico:

```text
NORTE-SUR
+
ESTE-OESTE
```

---

## R.6 · Política de hace dos años

❌ Incorrecto.

La política debe mantenerse alineada con:

```text
arquitectura
+
riesgos
+
amenazas
+
normativa
+
cambios organizativos
```

---

## R.7 · Riesgo bajo = ignorarlo para siempre

❌ Incorrecto.

Un riesgo bajo puede:

```text
aceptarse
+
mitigarse
+
transferirse
+
evitarse
```

pero debe:

```text
REGISTRARSE
+
REVISARSE
```

---

## R.8 · Seguridad = comprar herramientas

❌ Incorrecto.

La seguridad necesita:

```text
PERSONAS
+
PROCESOS
+
TECNOLOGÍA
```

Una organización puede tener:

```text
EDR
SIEM
WAF
FIREWALL
```

y seguir siendo insegura si:

```text
no revisa cuentas
+
no actualiza riesgos
+
no prueba backups
+
no forma usuarios
+
no ensaya incidentes
```

---

# 🧩 BLOQUE S · ARQUITECTURA OBJETIVO

Una solución:

```text
                           INTERNET
                               │
                       FIREWALL EXTERNO
                               │
                              DMZ
                        ┌──────┴──────┐
                       WEB            API
                        │              │
                        └──────┬───────┘
                               │
                       FIREWALL INTERNO
                               │
       ┌───────────┬──────────┼───────────┬──────────┐
       │           │          │           │          │
   USUARIOS     SERVERS       DB         ADMIN     BACKUP
       │           │                       │
       │       ┌───┴────┐                  │
       │      APP      FILES                │
       │                                   │
       ├── WIFI CORP                     MGMT
       │
       ├── GUEST ───────────────→ INTERNET
       │
       └── IOT ─────→ SOLO RECURSOS NECESARIOS
```

Capas transversales:

```text
VPN + MFA
PKI
SIEM
EDR
WAF
IDS/IPS
PAM
Backup
```

---

# 🏆 BLOQUE T · INFORME EJECUTIVO FINAL

## Respuesta de referencia

> La auditoría muestra que INVEGA dispone de numerosos controles tecnológicos, pero presenta debilidades importantes de configuración, gobierno, identidad, continuidad y gestión de datos. El principal problema no es la ausencia absoluta de herramientas, sino la falta de revisión sistemática y de integración entre personas, procesos y tecnología.
>
> Entre los riesgos prioritarios se encuentran la exposición directa de la base de datos y LDAP, la ausencia de segmentación adecuada para la red de invitados y la VPN, las cuentas de antiguos empleados, el exceso de privilegios administrativos, la existencia de una clave privada en una carpeta compartida, la debilidad de los backups y el almacenamiento de datos personales y de investigación en un servicio cloud personal no gobernado por la organización.
>
> Desde el punto de vista del ENS, deben actualizarse la política de seguridad, el análisis de riesgos, los procedimientos de gestión de incidentes, continuidad, control de acceso, monitorización y protección de sistemas. Deben existir evidencias de implantación, no únicamente documentos declarativos.
>
> Desde el punto de vista del RGPD, debe revisarse el registro de actividades de tratamiento, el uso del servicio cloud personal, las responsabilidades sobre los tratamientos y el procedimiento de gestión de brechas. Debe existir capacidad para evaluar rápidamente el riesgo de una violación de seguridad y adoptar las decisiones de notificación correspondientes.
>
> La PKI requiere un inventario completo, propietarios identificados, protección estricta de claves privadas, procedimientos de emisión, renovación y revocación y mecanismos de alerta ante expiraciones. La clave privada expuesta debe tratarse como potencialmente comprometida y sustituirse mediante un nuevo par de claves.
>
> La arquitectura debe adoptar una estrategia de mínimo privilegio y defensa en profundidad. El firewall debe aplicar deny by default, la DB y LDAP no deben estar expuestos innecesariamente, la red Guest debe estar aislada, la VPN debe segmentarse por roles y las conexiones de salida deben controlarse.
>
> En continuidad, INVEGA debe realizar un análisis de impacto, definir RTO y RPO por servicio, disponer de copias resistentes a ataques y probar periódicamente la restauración.
>
> Durante los próximos 12 meses debe ejecutarse un roadmap que combine correcciones urgentes, gobierno, segmentación, IAM/PAM, PKI, monitorización, backups, formación, ejercicios de incidentes y auditorías periódicas. El objetivo no es acumular herramientas, sino establecer un sistema de seguridad medible y sometido a mejora continua.

---

# 🧠 BLOQUE U · PREGUNTA FINAL DE OPOSICIÓN

Una respuesta excelente en 10 minutos podría estructurarse así:

## 1. Gobernanza

```text
política
roles
responsabilidades
```

## 2. Riesgos

```text
activos
amenazas
vulnerabilidades
impacto
probabilidad
```

## 3. ENS

```text
medidas organizativas
operacionales
protección
```

## 4. RGPD

```text
tratamientos
principios
responsabilidades
brechas
```

## 5. Identidad

```text
IAM
altas/cambios/bajas
```

## 6. Autenticación

```text
MFA
```

## 7. Autorización

```text
mínimo privilegio
RBAC
PAM
```

## 8. Redes

```text
segmentación
VLAN
DMZ
```

## 9. Firewall

```text
deny by default
```

## 10. PKI

```text
certificados
CA
claves
revocación
```

## 11. Endpoints

```text
EDR
hardening
parcheado
```

## 12. Monitorización

```text
SIEM
IDS/IPS
logs
```

## 13. Incidentes

```text
detectar
contener
investigar
erradicar
recuperar
```

## 14. Backups

```text
3-2-1
inmutabilidad
restauración
```

## 15. Continuidad

```text
RTO
RPO
BIA
```

## 16. Formación

```text
concienciación
phishing
ingeniería social
```

## 17. Auditoría

```text
revisión
pruebas
evidencias
```

## 18. Mejora continua

```text
MEDIR
↓
REVISAR
↓
CORREGIR
↓
VOLVER A MEDIR
```

---

# 🏁 BLOQUE V · AUTOEVALUACIÓN

Una interpretación de referencia:

```text
0-12
🔴 Necesita repaso importante

13-24
🟠 Base razonable

25-31
🟡 Buen nivel

32-36
🟢 Muy buen nivel

37-40
🔥 Nivel excelente
```

Pero hay una advertencia:

> La puntuación solo tiene valor si has respondido **sin consultar apuntes**.

Si has necesitado mirar el temario para responder una pregunta, esa pregunta debería marcarse como:

```text
1
```

aunque finalmente hayas dado una respuesta perfecta.

Eso convierte la autoevaluación en una herramienta de diagnóstico y no en un ejercicio de maquillaje académico. 🎯

---

# 🏆 BLOQUE W · RETO FINAL

La cadena:

```text
RIESGO
  ↓
GOBERNANZA
  ↓
ENS
  ↓
RGPD
  ↓
IDENTIDAD
  ↓
AUTENTICACIÓN
  ↓
AUTORIZACIÓN
  ↓
SEGMENTACIÓN
  ↓
FIREWALL
  ↓
PKI
  ↓
ENDPOINT
  ↓
MONITORIZACIÓN
  ↓
DETECCIÓN
  ↓
RESPUESTA
  ↓
RECUPERACIÓN
  ↓
CONTINUIDAD
  ↓
AUDITORÍA
  ↓
MEJORA
```

puede explicarse así:

```text
RIESGO
→ sabemos qué puede ocurrir.

GOBERNANZA
→ decidimos quién es responsable y cómo se gestiona.

ENS
→ establecemos el marco de seguridad aplicable al sector público.

RGPD
→ protegemos los tratamientos y derechos relacionados con datos personales.

IDENTIDAD
→ sabemos quién es el usuario.

AUTENTICACIÓN
→ verificamos su identidad.

AUTORIZACIÓN
→ decidimos qué puede hacer.

SEGMENTACIÓN
→ limitamos el alcance de un compromiso.

FIREWALL
→ controlamos las comunicaciones.

PKI
→ gestionamos confianza criptográfica.

ENDPOINT
→ protegemos los dispositivos.

MONITORIZACIÓN
→ observamos lo que ocurre.

DETECCIÓN
→ identificamos anomalías e incidentes.

RESPUESTA
→ contenemos y gestionamos el incidente.

RECUPERACIÓN
→ restauramos servicios seguros.

CONTINUIDAD
→ mantenemos la capacidad operativa.

AUDITORÍA
→ comprobamos que los controles funcionan.

MEJORA
→ corregimos y volvemos a evaluar.
```

---

# 🎯 LOS CONCEPTOS QUE DEBERÍAN QUEDARTE DEL BLOQUE 07

## ENS

```text
GOBERNANZA
+
RIESGO
+
MEDIDAS
+
EVIDENCIAS
```

## RGPD

```text
DATOS
+
RESPONSABILIDAD
+
SEGURIDAD
+
BRECHAS
+
DERECHOS
```

## CERTIFICADOS

```text
IDENTIDAD
+
CLAVE PÚBLICA
+
CA
+
PKI
```

## FIREWALL

```text
DENY BY DEFAULT
+
MÍNIMO PRIVILEGIO
+
SEGMENTACIÓN
```

## CIBERSEGURIDAD

```text
PREVENIR
+
DETECTAR
+
RESPONDER
+
RECUPERAR
```

---

# 🏁 MISIÓN 15 · CORREGIDA

## 🏆 BLOQUE 07 COMPLETADO

```text
┌──────────────────────────────┐
│        BLOQUE 07             │
│          SEGURIDAD            │
├──────────────────────────────┤
│ 7.1 ENS              ✅       │
│ 7.2 RGPD             ✅       │
│ 7.3 Certificados     ✅       │
│ 7.4 Firewalls        ✅       │
│ 7.5 Ciberseguridad   ✅       │
├──────────────────────────────┤
│ Misión 12            ✅       │
│ Misión 13            ✅       │
│ Misión 14            ✅       │
│ Misión 15            🏆       │
└──────────────────────────────┘
```

### 🧠 Idea final

La seguridad de un organismo público no se consigue con:

```text
FIREWALL
```

ni con:

```text
SIEM
```

ni con:

```text
MFA
```

ni siquiera con:

```text
ENS + RGPD + tecnología
```

por separado.

Se consigue cuando todos los elementos trabajan juntos:

```text
PERSONAS
   +
PROCESOS
   +
TECNOLOGÍA
   +
RIESGO
   +
CUMPLIMIENTO
   +
MONITORIZACIÓN
   +
RESPUESTA
   +
CONTINUIDAD
```

Ese es el concepto transversal que conecta **todo el Bloque 07**.

---

# 🎉 BLOQUE 07 · SEGURIDAD · FINALIZADO

```text
7.1 ENS                    ✅
7.2 RGPD                   ✅
7.3 Certificados           ✅
7.4 Firewalls              ✅
7.5 Ciberseguridad         ✅

MISIÓN 12                  ✅
MISIÓN 13                  ✅
MISIÓN 14                  ✅
MISIÓN 15                  🏆

SIMULACRO DEL BLOQUE       ⏳
```

**Bloque 07: completado.** 🔐🏆
