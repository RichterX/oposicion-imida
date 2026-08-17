# 🏆 BLOQUE 07 · SEGURIDAD
# 🧪 MISIÓN 15 · AUDITORÍA INTEGRAL
## El jefe final · ENS + RGPD + Certificados + Firewalls + Ciberseguridad

> **Tipo:** misión final de bloque · caso integral  
> **Bloque:** 07 · Seguridad  
> **Ámbitos:** 7.1 ENS · 7.2 RGPD · 7.3 Certificados digitales · 7.4 Firewalls · 7.5 Ciberseguridad  
> **Dificultad:** 🔴🔴 Muy alta  
> **Modalidad:** individual, offline  
> **Objetivo:** resolver una auditoría integral de seguridad de un organismo público, identificar riesgos, priorizar actuaciones y diseñar un plan completo de mejora.

---

# 🎯 1. CONTEXTO

Después de las Misiones 12, 13 y 14, INVEGA ha mejorado considerablemente su seguridad.

Pero la dirección quiere saber una cosa:

> **"¿Estamos realmente preparados o simplemente hemos ido apagando incendios?"**

Por ese motivo se contrata una auditoría integral.

Tú formas parte del equipo auditor.

Tu trabajo no consiste únicamente en encontrar vulnerabilidades.

Debes determinar:

```text
¿QUÉ ESTÁ MAL?
      ↓
¿QUÉ RIESGO SUPONE?
      ↓
¿QUÉ NORMATIVA / CONTROL AFECTA?
      ↓
¿QUÉ DEBEMOS HACER?
      ↓
¿QUÉ ES PRIORITARIO?
      ↓
¿CÓMO SABREMOS QUE ESTÁ SOLUCIONADO?
```

---

# 🏢 2. ORGANIZACIÓN

INVEGA es un organismo público dedicado a:

```text
INVESTIGACIÓN
+
GESTIÓN ADMINISTRATIVA
+
PROYECTOS CIENTÍFICOS
+
SERVICIOS DIGITALES
```

Dispone de:

```text
420 empleados
38 investigadores
12 administradores TIC
6 administradores privilegiados
```

Gestiona:

```text
datos personales
datos de investigación
información administrativa
documentación contractual
credenciales
información institucional
```

---

# 🌐 3. INFRAESTRUCTURA

La arquitectura actual:

```text
                         INTERNET
                            │
                     ┌──────▼──────┐
                     │ FIREWALL EXT│
                     └──────┬──────┘
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
       ┌────────────┬──────┼──────┬────────────┐
       │            │      │      │            │
    USUARIOS     SERVERS    DB    ADMIN       BACKUP
       │
       ├── Wi-Fi corporativo
       ├── Wi-Fi invitados
       └── IoT
```

Además:

```text
VPN + MFA
EDR
SIEM
IDS/IPS
WAF
PKI
```

---

# 📋 4. HALLAZGOS DE AUDITORÍA

La auditoría descubre los siguientes hallazgos.

---

## 🔴 HALLAZGO 01 · FIREWALL

Existe:

```text
ANY → DB TCP/3306
```

La regla lleva:

> 4 años sin revisión.

---

## 🔴 HALLAZGO 02 · LDAP

Existe:

```text
INTERNET → LDAP TCP/389
```

aunque aparentemente no se utiliza.

---

## 🔴 HALLAZGO 03 · VPN

Todos los usuarios VPN pueden acceder a:

```text
TODA LA RED INTERNA
```

aunque existe MFA.

---

## 🟠 HALLAZGO 04 · ADMINISTRACIÓN

Los administradores utilizan sus equipos habituales para:

```text
correo
navegación
administración
```

La misma máquina puede utilizarse para:

```text
RDP
SSH
Firewall
Directorio
```

---

## 🟠 HALLAZGO 05 · CERTIFICADOS

Hay:

```text
17 certificados
```

sin propietario identificado.

Además:

```text
3 caducan en menos de 30 días
```

y uno tiene la clave privada en una carpeta compartida.

---

## 🔴 HALLAZGO 06 · CA

Existe una CA interna.

Pero:

```text
no existe documentación actualizada
no existe inventario completo
no existe procedimiento formal de revocación
```

---

## 🟠 HALLAZGO 07 · WI-FI

La red:

```text
GUEST
```

puede alcanzar:

```text
DNS
LDAP
algunos servidores
```

aunque no puede autenticarse.

---

## 🟠 HALLAZGO 08 · EGRESS

El firewall permite:

```text
SERVIDORES → INTERNET
```

sin restricciones importantes.

---

## 🔴 HALLAZGO 09 · BACKUPS

Existe:

```text
backup diario
```

pero:

```text
no hay copia inmutable
no se prueban restauraciones regularmente
```

---

## 🟠 HALLAZGO 10 · LOGS

Los logs se conservan:

```text
7 días
```

pero la política interna recomienda:

```text
90 días
```

---

## 🔴 HALLAZGO 11 · CUENTAS

Existen:

```text
14 cuentas
```

de antiguos empleados todavía activas.

---

## 🔴 HALLAZGO 12 · PRIVILEGIOS

Un grupo de:

```text
23 usuarios
```

tiene permisos de administración local.

Solo deberían tenerlos:

```text
12
```

---

## 🟠 HALLAZGO 13 · DATOS

Los investigadores almacenan:

```text
datos personales
+
resultados de investigación
```

en:

```text
servicio cloud personal
```

La organización no tiene contrato con ese proveedor.

---

## 🔴 HALLAZGO 14 · RGPD

El registro de actividades de tratamiento:

```text
no está actualizado
```

No se sabe con certeza:

```text
qué departamentos utilizan
qué datos
para qué finalidad
```

---

## 🟠 HALLAZGO 15 · BRECHAS

No existe un procedimiento formal para:

```text
detectar
registrar
evaluar
notificar
```

brechas de datos personales.

---

## 🟠 HALLAZGO 16 · FORMACIÓN

La formación anti-phishing se realizó:

> hace 3 años.

No existen campañas periódicas.

---

## 🔴 HALLAZGO 17 · INCIDENT RESPONSE

Existe un documento llamado:

```text
"Procedimiento de incidentes"
```

pero no se ha probado nunca mediante simulacro.

---

## 🟠 HALLAZGO 18 · ENS

Existe una política de seguridad.

Pero:

```text
no se ha revisado en 2 años
no refleja la arquitectura actual
```

---

## 🟠 HALLAZGO 19 · RIESGOS

Existe un análisis de riesgos.

Tiene:

```text
4 años
```

y no contempla:

```text
cloud
ransomware
teletrabajo
dispositivos móviles
```

---

## 🟠 HALLAZGO 20 · CONTINUIDAD

No están definidos formalmente:

```text
RTO
RPO
```

para los servicios críticos.

---

# 🚨 5. INCIDENTE SIMULADO

Durante la auditoría se realiza una prueba controlada.

A las:

```text
09:14
```

un equipo de pruebas obtiene acceso a:

```text
GUEST
```

Desde ahí descubre:

```text
LDAP
DNS
SERVIDORES
```

A las:

```text
09:21
```

un equipo de laboratorio comprometido realiza:

```text
enumeración LDAP
```

A las:

```text
09:29
```

se detecta:

```text
acceso a servidor de documentación
```

A las:

```text
09:36
```

se genera:

```text
tráfico saliente anómalo
```

El SIEM genera una alerta.

---

# 🧠 6. INFORMACIÓN ADICIONAL

El equipo auditor descubre además:

```text
• Una cuenta administrativa compartida.
• Un certificado sin inventariar.
• Un servidor con SSH expuesto internamente a toda la red.
• Un servidor que realiza conexiones salientes directas a Internet.
• Un dispositivo IoT en la VLAN de usuarios.
```

---

# 🏆 TU MISIÓN

Debes elaborar una **auditoría integral de seguridad de INVEGA**.

No queremos una lista de vulnerabilidades.

Queremos:

```text
HALLAZGO
   ↓
RIESGO
   ↓
IMPACTO
   ↓
PRIORIDAD
   ↓
MEDIDA
   ↓
RESPONSABLE
   ↓
PLAZO
   ↓
EVIDENCIA DE CIERRE
```

---

# 🔴 BLOQUE A · CLASIFICACIÓN DE HALLAZGOS

Clasifica los 20 hallazgos:

```text
CRÍTICO
ALTO
MEDIO
BAJO
```

Justifica al menos **10**.

---

# 🟠 BLOQUE B · MATRIZ DE RIESGOS

Selecciona los **10 riesgos más importantes**.

Crea una matriz:

| Riesgo | Activo | Amenaza | Vulnerabilidad | Impacto | Probabilidad | Nivel | Tratamiento |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

---

# 🟡 BLOQUE C · ENS

Para los hallazgos relacionados con ENS:

## C.1

Identifica:

```text
MARCO ORGANIZATIVO
MARCO OPERACIONAL
MEDIDAS DE PROTECCIÓN
```

---

## C.2

¿Qué medidas deberían implantarse?

---

## C.3

¿Qué documentación debería existir?

Considera:

```text
política
roles
riesgos
procedimientos
incidentes
continuidad
auditoría
```

---

## C.4

¿Cómo demostrarías que INVEGA cumple y no simplemente "dice cumplir"?

---

# 🟢 BLOQUE D · RGPD

Analiza:

```text
HALLAZGOS 13
14
15
```

y cualquier otro que tenga relación con datos personales.

---

## D.1

¿Qué principios del RGPD están potencialmente afectados?

---

## D.2

¿Qué documentación debería existir?

---

## D.3

¿Qué debe hacerse con el cloud personal?

---

## D.4

Diseña un procedimiento para:

```text
DETECCIÓN DE BRECHA
↓
EVALUACIÓN
↓
DECISIÓN
↓
NOTIFICACIÓN
↓
COMUNICACIÓN
↓
DOCUMENTACIÓN
```

---

# 🔵 BLOQUE E · CERTIFICADOS Y PKI

Analiza:

```text
HALLAZGOS 05 y 06
```

---

## E.1

¿Qué riesgos existen?

---

## E.2

Diseña una política de gestión de certificados.

Debe incluir:

```text
inventario
propietario
emisión
instalación
renovación
revocación
expiración
claves privadas
```

---

## E.3

¿Qué harías con el certificado cuya clave privada está en una carpeta compartida?

---

## E.4

¿Qué diferencia existe entre:

```text
CA
PKI
CERTIFICADO
CLAVE PRIVADA
```

?

---

# 🧱 BLOQUE F · FIREWALL Y SEGMENTACIÓN

Analiza:

```text
HALLAZGOS
01
02
03
07
08
```

---

## F.1

¿Qué reglas eliminarías?

---

## F.2

¿Qué reglas crearías?

---

## F.3

Diseña la segmentación definitiva:

```text
DMZ
USUARIOS
SERVIDORES
DB
ADMIN
BACKUP
GUEST
IOT
MANAGEMENT
```

---

## F.4

Explica cómo limitarías el movimiento lateral.

---

# 🔐 BLOQUE G · IDENTIDAD

Analiza:

```text
HALLAZGOS
04
11
12
```

---

## G.1

¿Qué problemas existen?

---

## G.2

Diseña una estrategia de:

```text
ALTAS
CAMBIOS
BAJAS
```

---

## G.3

Diseña una estrategia para cuentas privilegiadas.

---

## G.4

¿Qué papel tendría:

```text
MFA
PAM
EDR
SIEM
```

?

---

# 🚨 BLOQUE H · RESPUESTA AL INCIDENTE

Analiza el incidente simulado.

---

## H.1

¿Es un incidente?

---

## H.2

¿Qué haces durante los primeros:

```text
15 minutos
```

?

---

## H.3

¿Qué haces durante la:

```text
primera hora
```

?

---

## H.4

¿Qué evidencias conservarías?

---

## H.5

¿Cómo determinarías si el incidente continúa activo?

---

# 🧪 BLOQUE I · FORENSE

Diseña una investigación sobre:

```text
LDAP
DNS
SIEM
EDR
FIREWALL
SERVIDORES
```

Debes reconstruir:

```text
ORIGEN
↓
ACCESO
↓
DESCUBRIMIENTO
↓
MOVIMIENTO
↓
COLECCIÓN
↓
EXFILTRACIÓN
```

---

# 💾 BLOQUE J · BACKUPS Y CONTINUIDAD

Analiza:

```text
HALLAZGOS 09 y 20
```

---

## J.1

Diseña una estrategia de backups.

---

## J.2

Define ejemplos razonables de:

```text
RTO
RPO
```

para:

```text
Portal web
Aplicación interna
Base de datos
Documentación
```

No existe una única respuesta correcta. Justifica.

---

## J.3

Diseña un procedimiento de prueba de restauración.

---

# 📊 BLOQUE K · LOGGING Y MONITORIZACIÓN

Analiza:

```text
HALLAZGO 10
```

---

## K.1

¿Qué logs centralizarías?

---

## K.2

¿Qué retención establecerías?

---

## K.3

¿Qué alertas crearías?

Al menos:

```text
10
```

---

# 🧠 BLOQUE L · FORMACIÓN Y PERSONAS

Analiza:

```text
HALLAZGO 16
```

Diseña un programa anual de concienciación.

Debe incluir:

```text
phishing
contraseñas
MFA
cloud
USB
dispositivos móviles
ingeniería social
protección de datos
```

---

# 🚨 BLOQUE M · GESTIÓN DE INCIDENTES

Analiza:

```text
HALLAZGO 17
```

Diseña un programa de ejercicios:

```text
TABLETOP
↓
SIMULACIÓN TÉCNICA
↓
RED TEAM / PURPLE TEAM
↓
REVISIÓN
```

Explica qué objetivo tendría cada fase.

---

# 🏛️ BLOQUE N · GOBERNANZA

Analiza:

```text
HALLAZGOS 18 y 19
```

---

## N.1

¿Qué debería actualizarse?

---

## N.2

¿Con qué frecuencia revisarías:

```text
política de seguridad
análisis de riesgos
inventario de activos
procedimientos
permisos
certificados
```

No es necesario asignar la misma periodicidad a todo.

---

# 🧠 BLOQUE O · PRIORIZACIÓN

La dirección dispone de presupuesto para **solo cinco actuaciones inmediatas**.

Elige cinco.

Opciones:

```text
□ Eliminar DB expuesta.
□ Eliminar LDAP expuesto.
□ Segmentar GUEST.
□ Implantar MFA.
□ Comprar nuevos ordenadores.
□ Implementar backups inmutables.
□ Revisar cuentas antiguas.
□ Revisar certificados.
□ Crear CA nueva.
□ Implantar SIEM.
□ Contratar más personal.
□ Revisar cloud personal.
□ Actualizar política.
□ Formación.
□ Definir RTO/RPO.
```

Justifica tu selección.

---

# 💰 BLOQUE P · PLAN DE MEJORA

Diseña un roadmap:

```text
0-30 DÍAS
30-90 DÍAS
3-6 MESES
6-12 MESES
```

Incluye:

```text
personas
procesos
tecnología
cumplimiento
continuidad
```

---

# 📋 BLOQUE Q · PLAN DE ACCIÓN

Selecciona **15 hallazgos** y crea:

| Hallazgo | Riesgo | Acción | Responsable | Prioridad | Plazo | Evidencia de cierre |
|---|---|---|---|---|---|---|
| | | | | | | |

---

# 🧠 BLOQUE R · PREGUNTAS DE RAZONAMIENTO

## R.1

> "Como tenemos MFA, podemos dar acceso VPN a toda la red."

¿Correcto?

---

## R.2

> "Como tenemos backups, no necesitamos continuidad."

¿Correcto?

---

## R.3

> "Como tenemos SIEM, ya tenemos monitorización resuelta."

¿Correcto?

---

## R.4

> "Como utilizamos una CA interna, todos los certificados internos son seguros."

¿Correcto?

---

## R.5

> "Como el firewall bloquea Internet → DB, la base de datos está protegida."

¿Correcto?

---

## R.6

> "Una política de seguridad de hace dos años sigue siendo válida si nadie la ha incumplido."

¿Correcto?

---

## R.7

> "Un riesgo bajo puede ignorarse para siempre."

¿Correcto?

---

## R.8

> "La seguridad consiste principalmente en comprar herramientas."

¿Correcto?

---

# 🧩 BLOQUE S · ARQUITECTURA OBJETIVO

Diseña la arquitectura final de INVEGA.

Debe incluir:

```text
INTERNET
    │
FIREWALL EXTERNO
    │
   DMZ
    │
FIREWALL INTERNO
    │
 ┌──┼─────────────┬──────────────┐
 │  │             │              │
USUARIOS       SERVIDORES       ADMIN
 │                │              │
 │          ┌─────┼─────┐        │
 │          │     │     │        │
 │         APP    DB  FILES      │
 │
 ├── WIFI CORPORATIVO
 ├── GUEST
 └── IOT

BACKUP
MANAGEMENT
VPN
PKI
SIEM
EDR
WAF
IDS/IPS
```

---

# 🏆 BLOQUE T · INFORME EJECUTIVO FINAL

Redacta un informe de máximo:

> **1.000 palabras**

Debe responder:

1. ¿Cuál es el estado de seguridad de INVEGA?
2. ¿Cuáles son los cinco riesgos más graves?
3. ¿Qué incumplimientos o debilidades RGPD existen?
4. ¿Qué problemas relacionados con ENS existen?
5. ¿Qué cambios necesita la arquitectura?
6. ¿Qué debe hacerse con la PKI?
7. ¿Qué debe cambiar en el firewall?
8. ¿Cómo debe gestionarse la identidad?
9. ¿Qué estrategia de continuidad debe implantarse?
10. ¿Qué debe hacerse durante los próximos 12 meses?

---

# 🧠 BLOQUE U · PREGUNTA FINAL DE OPOSICIÓN

Imagina que el tribunal te pregunta:

> **"Explique cómo implantaría un sistema integral de seguridad en un organismo público como INVEGA."**

Tienes **10 minutos**.

Sin consultar apuntes, desarrolla una respuesta estructurada.

Debes intentar incluir:

```text
1. GOBERNANZA
2. RIESGOS
3. ENS
4. RGPD
5. IDENTIDAD
6. CONTROL DE ACCESO
7. REDES
8. FIREWALL
9. PKI
10. ENDPOINTS
11. MONITORIZACIÓN
12. INCIDENTES
13. BACKUPS
14. CONTINUIDAD
15. FORMACIÓN
16. AUDITORÍA
17. MEJORA CONTINUA
```

---

# 🏁 BLOQUE V · AUTOEVALUACIÓN

Al terminar, puntúate del 0 al 2:

```text
0 = No lo sé
1 = Lo entiendo pero necesito consultar
2 = Puedo explicarlo sin apuntes
```

| Área | 0-2 |
|---|---:|
| ENS | |
| RGPD | |
| Certificados | |
| PKI | |
| Firewalls | |
| Segmentación | |
| VPN | |
| MFA | |
| Identidad | |
| EDR | |
| SIEM | |
| Incidentes | |
| Forense | |
| Backups | |
| RTO/RPO | |
| Continuidad | |
| Gestión de riesgos | |
| Auditoría | |

### Interpretación

```text
0-12
🔴 Repaso importante

13-24
🟠 Base razonable

25-31
🟡 Buen nivel

32-36
🟢 Muy buen nivel

37-40
🔥 Nivel excelente
```

---

# 🏆 BLOQUE W · RETO FINAL DEL BLOQUE 07

Sin consultar las misiones anteriores, completa esta cadena:

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

Explica con tus propias palabras qué aporta cada etapa.

---

# 🎯 OBJETIVOS DE SUPERACIÓN

```text
□ Identificar riesgos críticos.

□ Priorizar correctamente.

□ Relacionar riesgo y control.

□ Aplicar ENS.

□ Aplicar RGPD.

□ Diseñar PKI.

□ Gestionar certificados.

□ Diseñar firewalls.

□ Diseñar segmentación.

□ Diseñar VPN.

□ Gestionar identidades.

□ Gestionar privilegios.

□ Diseñar monitorización.

□ Responder a incidentes.

□ Preservar evidencias.

□ Gestionar brechas.

□ Diseñar backups.

□ Definir RTO/RPO.

□ Diseñar continuidad.

□ Crear un roadmap.

□ Elaborar un plan de acción.

□ Explicar seguridad integral ante un tribunal.
```

---

# 🧭 REGLA DE ORO DEL BLOQUE 07

Durante todo el bloque hemos trabajado una misma idea:

```text
LA SEGURIDAD NO ES
UN PRODUCTO.

ES UN SISTEMA.
```

Ese sistema necesita:

```text
PERSONAS
   +
PROCESOS
   +
TECNOLOGÍA
   +
RIESGO
   +
NORMATIVA
   +
MONITORIZACIÓN
   +
RESPUESTA
   +
CONTINUIDAD
```

Y todos esos elementos deben estar conectados.

---

# 🏁 FIN DEL BLOQUE 07

## 🔐 SEGURIDAD

```text
7.1 ENS
   ↓
7.2 RGPD
   ↓
7.3 CERTIFICADOS
   ↓
7.4 FIREWALLS
   ↓
7.5 CIBERSEGURIDAD
   ↓
━━━━━━━━━━━━━━━━━━━━
   MISIÓN 15
   ↓
AUDITORÍA INTEGRAL
━━━━━━━━━━━━━━━━━━━━
```

### 🏆 MISIÓN FINAL

Esta misión **NO incluye las soluciones**.

Hazla como si fuese una prueba final real:

```text
SIN APUNTES
SIN INTERNET
SIN CONSULTAR LAS MISIONES
```

Puedes dividirla en varias sesiones si lo necesitas. No se trata de terminar rápido.

El objetivo es descubrir:

> **qué sabes realmente cuando desaparece el andamio de los apuntes.**

Cuando termines las respuestas, podrás compararlas con la corrección de referencia y utilizar los errores para preparar el **simulacro final del Bloque 07**.

---

# 🎉 BLOQUE 07 · SEGURIDAD · COMPLETADO

```text
          🔐 BLOQUE 07
               │
    ┌──────────┼──────────┐
    ↓          ↓          ↓
   ENS        RGPD       PKI
    │          │          │
    └──────┬───┴────┬─────┘
           ↓        ↓
        FIREWALL  IDENTIDAD
           │        │
           └───┬────┘
               ↓
        CIBERSEGURIDAD
               ↓
        INCIDENT RESPONSE
               ↓
          CONTINUIDAD
               ↓
        AUDITORÍA INTEGRAL
               ↓
          🏆 MISIÓN 15
```

**Misión 15 desbloqueada.**

**Bloque 07: terminado.** 🔐🏆
