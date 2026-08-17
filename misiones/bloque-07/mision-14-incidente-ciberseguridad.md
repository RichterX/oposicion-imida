# 🚨 BLOQUE 07 · SEGURIDAD
# 🧪 MISIÓN 14 · INCIDENTE DE CIBERSEGURIDAD
## Del primer indicador a la recuperación completa

> **Tipo:** misión práctica / respuesta a incidentes  
> **Bloque:** 07 · Seguridad  
> **Ámbitos:** 7.5 Ciberseguridad + integración de 7.1, 7.2, 7.3 y 7.4  
> **Dificultad:** 🔴 Alta  
> **Modalidad:** individual, offline  
> **Objetivo:** analizar, contener, investigar, erradicar y recuperar una organización durante un incidente de ciberseguridad.

---

# 🎯 1. CONTEXTO

Han pasado varias semanas desde la **Misión 13**.

INVEGA ya dispone de:

```text
✅ MFA
✅ Segmentación de red
✅ EDR
✅ SIEM
✅ Firewall interno
✅ WAF
✅ Backups mejorados
✅ Procedimientos de gestión de certificados
```

La organización considera que su postura de seguridad ha mejorado considerablemente.

Pero una mañana ocurre algo diferente.

No hay un correo de phishing evidente.

No aparece ningún ransomware.

No salta una alerta de antivirus tradicional.

Y, sin embargo...

> **Algo no encaja.**

---

# 🏢 2. INFRAESTRUCTURA

La arquitectura actual es:

```text
                         INTERNET
                            │
                     ┌──────▼──────┐
                     │  FIREWALL   │
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
       └── ENDPOINTS
```

Además:

```text
SIEM
EDR
VPN + MFA
PKI
WAF
IDS/IPS
```

---

# 👥 3. USUARIO AFECTADO

La cuenta:

```text
maria.garcia
```

pertenece a:

> Investigadora del departamento de biotecnología.

Sus permisos normales son:

```text
Correo
VPN
Aplicaciones de investigación
Servidor de documentación de su departamento
```

No debería tener:

```text
acceso administrativo
acceso directo a DB
acceso al sistema de backups
acceso a servidores de administración
```

---

# 🕘 4. LÍNEA TEMPORAL DEL INCIDENTE

## 08:41

El SIEM genera una alerta:

```text
LOGIN VPN
usuario: maria.garcia
origen: IP extranjera
```

La autenticación MFA fue correcta.

---

## 08:43

El mismo usuario inicia sesión desde:

```text
España
```

El sistema registra:

```text
DOS UBICACIONES
EN 2 MINUTOS
```

La segunda autenticación también supera MFA.

---

## 08:51

EDR detecta en el portátil de María:

```text
powershell.exe
```

ejecutándose desde un proceso de Microsoft Office.

No se detecta malware conocido.

---

## 09:02

El SIEM registra:

```text
maria.garcia
↓
acceso a servidor de documentación
```

Comportamiento aparentemente normal.

---

## 09:17

Se detecta:

```text
maria.garcia
↓
acceso a 47 servidores
```

La mayoría de esos servidores no habían sido utilizados anteriormente por esa cuenta.

---

## 09:24

El EDR detecta:

```text
powershell
↓
enumeración de red
```

---

## 09:31

Se registra:

```text
LDAP
↓
enumeración de usuarios
```

---

## 09:44

Se produce un acceso a:

```text
SERVIDOR DE FICHEROS
```

y se consultan:

```text
2.843 archivos
```

---

## 09:57

El SIEM detecta:

```text
gran volumen de tráfico saliente
```

destinado a:

```text
203.0.113.50
```

---

## 10:03

El firewall bloquea parte del tráfico.

Pero:

```text
███████████████████░░░
```

ya se han transferido aproximadamente:

> **1,8 GB**

---

## 10:07

El equipo de seguridad descubre que algunos archivos contienen:

```text
datos personales
+
resultados de investigación
+
documentación interna
```

---

## 10:12

El atacante intenta acceder a:

```text
BACKUP
```

El firewall bloquea la conexión.

---

## 10:19

Se detecta un intento de acceso:

```text
maria.garcia
↓
SERVIDOR DE CERTIFICADOS
```

El acceso es bloqueado.

---

## 10:25

La cuenta es deshabilitada.

---

## 10:31

El equipo EDR aísla el portátil.

---

## 10:38

Aparece una nueva alerta:

```text
OTRO EQUIPO
↓
mismo destino externo
```

El incidente parece ser mayor de lo esperado.

---

# 🚨 5. LA DIRECCIÓN PREGUNTA

A las 10:45 la dirección convoca al equipo técnico.

Pregunta:

> "¿Tenemos un incidente aislado o un ataque en curso?"

El responsable de protección de datos pregunta:

> "¿Tenemos una brecha de datos personales?"

El responsable de sistemas pregunta:

> "¿Podemos apagarlo todo?"

El responsable de investigación pregunta:

> "¿Podemos seguir trabajando?"

Y dirección añade:

> "¿Cuándo podemos decir que el incidente ha terminado?"

---

# 🧠 6. TU MISIÓN

Debes actuar como **responsable técnico de respuesta al incidente**.

Tu misión será:

```text
DETECTAR
   ↓
ANALIZAR
   ↓
PRIORIZAR
   ↓
CONTENER
   ↓
PRESERVAR EVIDENCIAS
   ↓
ERRADICAR
   ↓
RECUPERAR
   ↓
APRENDER
```

---

# 🔴 BLOQUE A · CLASIFICACIÓN

## A.1

Clasifica la situación:

```text
EVENTO
INCIDENTE
ATAQUE
BRECHA DE DATOS PERSONALES
```

Puedes utilizar varias categorías si son compatibles.

Justifica.

---

## A.2

¿La autenticación MFA correcta significa que:

> "María ha realizado realmente todos esos accesos"?

Explica.

---

## A.3

¿Qué indicios apuntan a que la cuenta puede estar comprometida?

Identifica al menos **8 indicadores**.

---

# 🟠 BLOQUE B · RECONSTRUCCIÓN

## B.1

Reconstruye la cadena de ataque a partir de los datos disponibles.

Utiliza:

```text
08:41
08:43
08:51
09:17
09:24
09:31
09:44
09:57
10:03
10:12
10:19
```

---

## B.2

Relaciona las acciones observadas con conceptos de:

```text
MITRE ATT&CK
```

No es necesario recordar códigos exactos.

---

## B.3

¿Qué acciones están:

```text
CONFIRMADAS
```

y cuáles son:

```text
HIPÓTESIS
```

?

Esta distinción es obligatoria.

---

# 🟡 BLOQUE C · TRIAJE

Debes decidir qué hacer primero.

Ordena estas acciones de mayor a menor prioridad:

```text
□ Cambiar contraseña de María.
□ Aislar portátil.
□ Revisar backup.
□ Bloquear destino externo.
□ Apagar toda la red.
□ Revisar otros equipos.
□ Preservar logs.
□ Analizar cuenta.
□ Notificar a dirección.
□ Investigar datos exfiltrados.
□ Bloquear sesiones.
□ Revisar persistencia.
```

Después justifica el orden.

---

# 🟢 BLOQUE D · CONTENCIÓN

Diseña una estrategia de contención inmediata.

Debes cubrir:

```text
CUENTA
ENDPOINT
RED
VPN
SERVIDORES
DATOS
DESTINOS EXTERNOS
OTROS EQUIPOS
```

Propón al menos **12 acciones**.

---

# 🔵 BLOQUE E · "¿APAGAMOS TODO?"

Dirección propone:

> "Apaguemos todos los servidores inmediatamente."

## E.1

¿Lo harías?

---

## E.2

¿Qué ventajas tendría?

---

## E.3

¿Qué riesgos tendría?

---

## E.4

¿Qué alternativa propondrías?

---

# 🟣 BLOQUE F · PRESERVACIÓN DE EVIDENCIAS

Debes diseñar una estrategia de adquisición y preservación de evidencias.

Considera:

```text
EDR
SIEM
VPN
FIREWALL
LDAP
DNS
DHCP
CORREO
ENDPOINT
SERVIDORES
FICHEROS
PROXY
WAF
```

---

## F.1

¿Qué información buscarías en cada fuente?

---

## F.2

¿Por qué es importante sincronizar relojes?

---

## F.3

¿Cómo evitarías destruir evidencias durante la contención?

---

# 🧪 BLOQUE G · ANÁLISIS FORENSE

El equipo forense encuentra en el portátil:

```text
powershell.exe
office.exe
winword.exe
```

y varias conexiones salientes.

Además encuentra:

```text
archivos temporales
scripts
credenciales almacenadas en navegador
```

## G.1

¿Qué investigarías primero?

---

## G.2

¿Qué relación podría existir entre:

```text
OFFICE
↓
POWERSHELL
```

?

---

## G.3

¿Qué riesgos presenta encontrar credenciales almacenadas?

---

## G.4

¿Qué acciones de respuesta tomarías respecto a esas credenciales?

---

# 🚨 BLOQUE H · SEGUNDO EQUIPO

A las 10:38 aparece:

```text
OTRO EQUIPO
↓
MISMO DESTINO EXTERNO
```

## H.1

¿Qué hipótesis plantearías?

---

## H.2

¿Qué harías inmediatamente?

---

## H.3

¿Cómo determinarías si:

```text
ES EL MISMO ATACANTE
```

?

---

# 🔐 BLOQUE I · IDENTIDAD

La cuenta de María superó MFA.

Analiza:

```text
MFA
VPN
SESIONES
TOKENS
CREDENCIALES
DISPOSITIVO
ACCESO CONDICIONAL
```

## I.1

¿Cómo puede producirse un acceso malicioso aunque MFA esté activo?

---

## I.2

¿Qué controles adicionales propondrías?

---

## I.3

¿Qué harías con las sesiones y tokens existentes?

---

# 📊 BLOQUE J · DATOS Y RGPD

Se han transferido aproximadamente:

```text
1,8 GB
```

Parte contiene:

```text
datos personales
```

## J.1

¿Existe una posible violación de seguridad de datos personales?

Justifica.

---

## J.2

¿Qué información necesitas conocer para evaluar el riesgo?

Identifica al menos **10 factores**.

---

## J.3

¿Qué departamentos deberían participar?

---

## J.4

¿Qué debe analizarse para determinar si procede notificación a la autoridad de control?

---

## J.5

¿Qué debe analizarse para determinar si procede comunicación a los afectados?

---

# 🏛️ BLOQUE K · ENS

## K.1

¿Qué dimensiones de seguridad están afectadas o en riesgo?

Analiza:

```text
CONFIDENCIALIDAD
INTEGRIDAD
DISPONIBILIDAD
AUTENTICIDAD
TRAZABILIDAD
```

---

## K.2

¿Qué medidas del ENS deberían intervenir durante la respuesta?

Agrupa:

```text
ORGANIZATIVAS
OPERACIONALES
PROTECCIÓN / TÉCNICAS
```

---

## K.3

¿Qué evidencias necesitarías para demostrar que el incidente se gestionó correctamente?

---

# 🧹 BLOQUE L · ERRADICACIÓN

Supón que la investigación confirma:

```text
PERSISTENCIA
```

en dos servidores.

Diseña el proceso de erradicación.

Incluye:

```text
cuentas
credenciales
persistencia
software
vulnerabilidades
configuración
servidores
endpoints
```

---

# 🔄 BLOQUE M · RECUPERACIÓN

Diseña una recuperación por fases.

```text
FASE 1
FASE 2
FASE 3
FASE 4
FASE 5
```

Debes explicar qué condiciones deben cumplirse antes de avanzar.

---

# 💾 BLOQUE N · BACKUPS

El atacante intentó acceder al sistema de backup pero fue bloqueado.

## N.1

¿Qué comprobarías?

---

## N.2

¿Cómo determinarías si los backups son confiables?

---

## N.3

¿Qué papel tienen:

```text
RTO
RPO
3-2-1
INMUTABILIDAD
PRUEBAS DE RESTAURACIÓN
```

?

---

# 🧠 BLOQUE O · THREAT INTELLIGENCE

El destino:

```text
203.0.113.50
```

aparece en varios sistemas de monitorización.

## O.1

¿Qué información intentarías obtener?

---

## O.2

¿Qué diferencia existe entre:

```text
IOC
```

y:

```text
TTP
```

?

---

## O.3

¿Por qué bloquear únicamente la IP puede ser insuficiente?

---

# 🧩 BLOQUE P · PLAYBOOK

Diseña un pequeño playbook para:

> **Compromiso de cuenta + acceso VPN + posible exfiltración**

Debe contener:

```text
1. DETECCIÓN
2. VALIDACIÓN
3. CONTENCIÓN
4. INVESTIGACIÓN
5. ERRADICACIÓN
6. RECUPERACIÓN
7. COMUNICACIÓN
8. LECCIONES APRENDIDAS
```

---

# 🧠 BLOQUE Q · PREGUNTAS DE RAZONAMIENTO

## Q.1

> "Como MFA funcionó, no puede ser una cuenta comprometida."

¿Correcto?

---

## Q.2

> "Bloqueamos la IP y el incidente está solucionado."

¿Correcto?

---

## Q.3

> "Si aislamos el ordenador, podemos borrarlo inmediatamente."

¿Correcto?

---

## Q.4

> "Si no sabemos exactamente qué archivos fueron robados, no podemos considerar que exista brecha."

¿Correcto?

---

## Q.5

> "El atacante no accedió al backup, así que no necesitamos revisarlo."

¿Correcto?

---

## Q.6

> "Tenemos que erradicar el ataque antes de empezar a investigar."

¿Correcto?

---

# 🚨 BLOQUE R · COMUNICACIÓN

Diseña un esquema de comunicación durante el incidente.

Debes decidir:

```text
¿QUIÉN INFORMA?
¿A QUIÉN?
¿CUÁNDO?
¿QUÉ INFORMACIÓN?
¿POR QUÉ CANAL?
```

Incluye:

```text
DIRECCIÓN
IT
SEGURIDAD
DPO
JURÍDICO
EMPLEADOS
USUARIOS AFECTADOS
AUTORIDADES
PROVEEDORES
```

No todos tienen que recibir la misma información.

---

# 🏆 BLOQUE S · ¿CUÁNDO TERMINA EL INCIDENTE?

Dirección pregunta:

> "¿Cuándo podemos decir que el incidente ha terminado?"

Define al menos **8 criterios**.

Por ejemplo:

```text
□ No existe acceso atacante conocido.
□ Persistencia eliminada.
...
```

---

# 🧠 BLOQUE T · LECCIONES APRENDIDAS

Una vez cerrado el incidente, identifica al menos:

```text
5 medidas preventivas
5 medidas detectivas
5 medidas de respuesta
5 medidas de recuperación
```

---

# 🔥 BLOQUE U · RETO FINAL

Ahora imagina que el atacante **no utilizó malware**.

Utilizó:

```text
credenciales válidas
PowerShell
herramientas administrativas
servicios legítimos
```

y eliminó parte de sus rastros.

Diseña una estrategia de detección.

Debes utilizar:

```text
SIEM
EDR
UEBA
NDR
logs
identidad
segmentación
```

---

# 🏆 BLOQUE V · INFORME FINAL

Redacta un informe ejecutivo de máximo **750 palabras**.

Debe responder:

1. ¿Qué ocurrió?
2. ¿Cómo entró el atacante?
3. ¿Qué sistemas afectó?
4. ¿Qué información pudo salir?
5. ¿Qué acciones se realizaron?
6. ¿Qué riesgos quedan?
7. ¿Qué obligaciones RGPD deben analizarse?
8. ¿Qué medidas ENS son relevantes?
9. ¿Cuándo puede recuperarse la actividad?
10. ¿Qué debe cambiar después?

---

# 📊 BLOQUE W · MATRIZ FINAL DEL INCIDENTE

Completa:

| Elemento | Situación |
|---|---|
| Activo inicial | |
| Cuenta afectada | |
| Vector de acceso | |
| Persistencia | |
| Movimiento lateral | |
| Datos afectados | |
| Exfiltración | |
| Sistemas afectados | |
| Indicadores | |
| Contención | |
| Erradicación | |
| Recuperación | |
| Riesgo RGPD | |
| Impacto ENS | |

---

# 🎯 OBJETIVOS DE SUPERACIÓN

```text
□ Diferenciar evento e incidente.

□ Reconocer una cuenta comprometida aunque MFA funcione.

□ Reconstruir una línea temporal.

□ Distinguir hechos de hipótesis.

□ Realizar triaje.

□ Diseñar contención.

□ Preservar evidencias.

□ Comprender análisis forense.

□ Identificar persistencia.

□ Analizar movimiento lateral.

□ Gestionar credenciales y sesiones.

□ Analizar una posible brecha RGPD.

□ Relacionar el incidente con ENS.

□ Diseñar erradicación.

□ Diseñar recuperación.

□ Utilizar RTO/RPO.

□ Evaluar backups.

□ Utilizar IOC y TTP.

□ Diseñar un playbook.

□ Diseñar comunicación.

□ Determinar criterios de cierre.

□ Proponer lecciones aprendidas.
```

---

# 🧭 REGLA DE ORO

Durante un incidente:

```text
NO ADIVINES
   ↓
OBSERVA
   ↓
REGISTRA
   ↓
CORRELACIONA
   ↓
PRIORIZA
   ↓
ACTÚA
   ↓
DOCUMENTA
```

Y recuerda:

```text
CONTENCIÓN
→ impedir que siga avanzando

ERRADICACIÓN
→ eliminar la causa y persistencia

RECUPERACIÓN
→ volver a operar de forma segura

LECCIONES APRENDIDAS
→ evitar que vuelva a ocurrir
```

---

# 🏁 FIN DE LA MISIÓN 14

## INCIDENTE DE CIBERSEGURIDAD

```text
              INCIDENTE
                  │
          ┌───────┴───────┐
          ↓               ↓
       IDENTIDAD         RED
          │               │
          └───────┬───────┘
                  ↓
              DETECCIÓN
                  ↓
                TRIAJE
                  ↓
              CONTENCIÓN
                  ↓
          INVESTIGACIÓN
                  ↓
             ERRADICACIÓN
                  ↓
              RECUPERACIÓN
                  ↓
          MEJORA CONTINUA
```

### 🚨 IMPORTANTE

**Esta misión NO incluye las soluciones.**

Resuélvela offline.

Cuando la termines, puedes pasarme tus respuestas y haremos la corrección completa, punto por punto.

La siguiente será la **Misión 15**, la gran misión final del Bloque 7, donde mezclaremos:

```text
ENS
+
RGPD
+
CERTIFICADOS
+
FIREWALLS
+
CIBERSEGURIDAD
```

en un único escenario.

**Misión 14 desbloqueada.** 🚨🔐
