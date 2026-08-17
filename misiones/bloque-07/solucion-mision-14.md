# 🚨 BLOQUE 07 · SEGURIDAD
# 🧪 MISIÓN 14 · SOLUCIONES
## Incidente de ciberseguridad · Del primer indicador a la recuperación completa

> **Objetivo de la corrección:** ofrecer una respuesta de referencia para el incidente de INVEGA. En las preguntas abiertas existen distintas respuestas válidas. Lo importante es identificar correctamente el riesgo, priorizar, justificar las acciones y distinguir hechos confirmados de hipótesis.

---

# 🔴 BLOQUE A · CLASIFICACIÓN

## A.1 · ¿Evento, incidente, ataque y brecha?

La situación puede clasificarse como:

```text
EVENTOS
   ↓
INDICIOS DE COMPROMISO
   ↓
INCIDENTE DE SEGURIDAD
   ↓
ATAQUE EN CURSO
   ↓
POSIBLE VIOLACIÓN DE DATOS PERSONALES
```

### Evento

Cada registro individual es un evento:

```text
login VPN
ejecución de PowerShell
acceso a servidor
transferencia de datos
```

### Incidente

La correlación de esos eventos demuestra una situación que compromete o amenaza la seguridad de INVEGA.

### Ataque

Existe evidencia de actividad deliberada:

```text
enumeración
+
movimiento lateral
+
recopilación
+
exfiltración
```

Por tanto, ya no hablamos simplemente de una anomalía.

### Brecha de datos personales

Existe una **posible violación de la seguridad de los datos personales**, porque se confirma una transferencia de información y se descubre que parte de ella contiene datos personales.

La evaluación RGPD debe determinar:

```text
QUÉ DATOS
+
CUÁNTAS PERSONAS
+
QUÉ RIESGO
```

No es necesario esperar a conocer absolutamente todo para iniciar la evaluación.

---

# A.2 · "MFA funcionó, entonces fue María"

❌ No.

Que la autenticación MFA haya sido satisfactoria demuestra que el mecanismo de autenticación fue superado correctamente, pero no demuestra que la persona que utilizó la cuenta fuese María.

Posibilidades:

```text
CREDENCIALES ROBADAS
+
SESIÓN/TOKEN ROBADO
+
DISPOSITIVO COMPROMETIDO
+
APROBACIÓN FRAUDULENTA DEL MFA
+
OTRO MECANISMO DE COMPROMISO
```

Por tanto:

> **Autenticación válida ≠ usuario legítimo confirmado.**

---

# A.3 · Indicadores de compromiso

Al menos ocho:

```text
1. Login VPN desde IP extranjera.
2. Segundo login desde España solo dos minutos después.
3. Imposible desplazamiento geográfico.
4. Office → PowerShell.
5. Acceso a 47 servidores.
6. Enumeración de red.
7. Enumeración LDAP.
8. Acceso masivo a archivos.
9. Tráfico saliente anómalo.
10. 1,8 GB transferidos.
11. Intento de acceso a backup.
12. Intento de acceso al servidor de certificados.
13. Segundo equipo comunicándose con el mismo destino.
```

La combinación es mucho más importante que cualquiera de estos indicadores de forma aislada.

---

# 🟠 BLOQUE B · RECONSTRUCCIÓN

## B.1 · Línea temporal

Una reconstrucción razonable:

```text
08:41
VPN desde ubicación anómala
        ↓
08:43
Segundo acceso desde España
        ↓
08:51
Office → PowerShell
        ↓
09:02
Acceso aparentemente normal
        ↓
09:17
Acceso a 47 servidores
        ↓
09:24
Enumeración de red
        ↓
09:31
Enumeración LDAP
        ↓
09:44
Consulta de 2.843 archivos
        ↓
09:57
Gran volumen de tráfico saliente
        ↓
10:03
1,8 GB transferidos
        ↓
10:12
Intento de acceso a backup
        ↓
10:19
Intento de acceso a servidor de certificados
        ↓
10:25
Cuenta deshabilitada
        ↓
10:31
Endpoint aislado
        ↓
10:38
Segundo equipo → mismo destino
```

---

# B.2 · Relación con MITRE ATT&CK

No es necesario acertar el identificador exacto para demostrar comprensión.

| Acción | Concepto ATT&CK |
|---|---|
| Login VPN | Initial Access / Valid Accounts |
| Uso de credenciales legítimas | Credential Access / Valid Accounts |
| Office → PowerShell | Execution |
| Enumeración de red | Discovery |
| Enumeración LDAP | Account/Domain Discovery |
| Acceso a múltiples servidores | Lateral Movement / Discovery |
| Consulta masiva de archivos | Collection |
| Transferencia externa | Exfiltration |
| Intento de acceder a backup | Discovery / Collection / Impact potencial |
| Intento contra servidor de certificados | Discovery / Credential Access potencial |

Una respuesta excelente evita asignar tácticas que el escenario no demuestra.

---

# B.3 · Confirmado vs hipótesis

## Confirmado

```text
✔ Acceso VPN.
✔ Dos ubicaciones anómalas.
✔ PowerShell iniciado desde Office.
✔ Acceso a numerosos servidores.
✔ Enumeración de red.
✔ Enumeración LDAP.
✔ Consulta de 2.843 archivos.
✔ Transferencia de aproximadamente 1,8 GB.
✔ Intento contra backup.
✔ Intento contra servidor de certificados.
✔ Segundo equipo comunicándose con el mismo destino.
```

## Hipótesis

```text
? Robo de credenciales.
? Robo de sesión/token.
? Phishing previo.
? Persistencia.
? Compromiso de otro equipo.
? Exfiltración completa de los 1,8 GB.
? Modificación de datos.
? Compromiso de otros servidores.
? Compromiso de certificados.
? Mismo atacante en ambos equipos.
```

La investigación debe convertir las hipótesis en:

```text
CONFIRMADAS
o
DESCARTADAS
```

---

# 🟡 BLOQUE C · TRIAJE

## Orden recomendado

Una secuencia razonable sería:

```text
1. Aislar portátil.
2. Bloquear destino externo sospechoso.
3. Bloquear sesiones/tokens.
4. Deshabilitar o restringir la cuenta.
5. Preservar logs y evidencias.
6. Revisar otros equipos.
7. Analizar la cuenta.
8. Investigar datos exfiltrados.
9. Revisar persistencia.
10. Revisar backups.
11. Informar a dirección.
12. Coordinar respuesta RGPD.
```

### ¿Por qué no apagar toda la red?

Porque todavía necesitamos:

```text
EVIDENCIAS
+
SERVICIOS
+
COMUNICACIONES
+
CONTINUIDAD
```

Y porque el incidente parece estar parcialmente contenido.

La prioridad es:

> **contener el ataque con el menor impacto posible sin destruir evidencias.**

---

# 🟢 BLOQUE D · CONTENCIÓN

Al menos 12 medidas:

```text
1. Aislar el portátil de María mediante EDR.

2. Deshabilitar la cuenta comprometida.

3. Revocar sesiones activas.

4. Revocar tokens cuando sea posible.

5. Invalidar credenciales afectadas.

6. Bloquear el destino externo.

7. Buscar otros equipos comunicándose con ese destino.

8. Restringir temporalmente el acceso VPN de la cuenta.

9. Revisar cuentas relacionadas.

10. Bloquear indicadores de compromiso.

11. Restringir tráfico de salida sospechoso.

12. Revisar conexiones desde el endpoint comprometido.

13. Aumentar temporalmente la monitorización.

14. Proteger los sistemas críticos.

15. Revisar el acceso a backup.

16. Revisar el servidor de certificados.
```

### Importante

No debemos limitarnos a:

```text
CAMBIAR CONTRASEÑA
```

porque el atacante podría tener:

```text
SESIÓN ACTIVA
+
TOKEN
+
OTRA CREDENCIAL
+
PERSISTENCIA
```

---

# 🔵 BLOQUE E · "¿APAGAMOS TODO?"

## E.1

❌ No como primera reacción.

No existe información suficiente para concluir que toda la infraestructura esté comprometida.

---

## E.2 · Ventajas

Apagar sistemas podría:

```text
• detener procesos activos;
• limitar algunas acciones del atacante;
• impedir ciertas modificaciones;
• reducir temporalmente la superficie.
```

---

## E.3 · Riesgos

Puede:

```text
• destruir información volátil;
• perder conexiones activas;
• dificultar el análisis forense;
• provocar indisponibilidad;
• afectar servicios críticos;
• afectar investigación;
• interrumpir comunicaciones;
• complicar recuperación.
```

---

## E.4 · Alternativa

Aplicar:

```text
CONTENCIÓN SELECTIVA
```

por ejemplo:

```text
endpoint comprometido
+
cuenta
+
sesiones
+
destinos
+
segmentos
+
servidores afectados
```

y escalar el aislamiento si la evidencia demuestra una propagación mayor.

---

# 🟣 BLOQUE F · PRESERVACIÓN DE EVIDENCIAS

## F.1 · Fuentes

### EDR

Buscar:

```text
procesos
árboles de procesos
PowerShell
comandos
archivos
conexiones
persistencia
```

### SIEM

Buscar:

```text
eventos correlacionados
usuarios
horarios
IP
destinos
alertas
```

### VPN

```text
IP origen
hora
usuario
MFA
dispositivo
duración
```

### Firewall

```text
origen
destino
puerto
acción
volumen
```

### LDAP

```text
enumeración
consultas
cuentas
autenticaciones
cambios
```

### DNS

```text
resoluciones
dominios
horarios
equipos
```

### DHCP

Relacionar:

```text
IP
MAC
equipo
hora
```

### Correo

Buscar:

```text
mensajes
enlaces
adjuntos
reglas
accesos
```

### Endpoint

```text
memoria
procesos
archivos
logs
persistencia
credenciales
conexiones
```

### Servidores

```text
login
accesos
procesos
ficheros
cambios
```

### WAF / Proxy

```text
peticiones
orígenes
destinos
patrones anómalos
```

---

# F.2 · Sincronización de relojes

Si los sistemas tienen horas distintas:

```text
08:41
```

en un sistema podría corresponder a:

```text
08:37
```

en otro.

Eso dificulta reconstruir:

```text
QUÉ OCURRIÓ PRIMERO
```

Por eso es importante utilizar sincronización temporal coherente.

---

# F.3 · No destruir evidencias

Evitar:

```text
formatear inmediatamente
borrar logs
reiniciar innecesariamente
eliminar archivos
```

Primero:

```text
PRESERVAR
↓
ADQUIRIR
↓
ANALIZAR
```

La contención debe coordinarse con el equipo forense.

---

# 🧪 BLOQUE G · ANÁLISIS FORENSE

## G.1 · ¿Qué investigar primero?

Prioridad:

```text
Office
 ↓
PowerShell
 ↓
scripts
 ↓
conexiones
 ↓
persistencia
 ↓
credenciales
```

También:

```text
timeline
+
procesos
+
archivos
+
comunicaciones
```

---

# G.2 · Office → PowerShell

Es un patrón potencialmente sospechoso porque una aplicación de Office puede actuar como punto de ejecución de código que posteriormente lanza PowerShell.

No demuestra automáticamente malware.

Hay que investigar:

```text
¿QUÉ DOCUMENTO?
¿QUÉ MACRO/SCRIPT?
¿QUÉ COMANDO?
¿QUÉ PROCESO PADRE?
¿QUÉ CONEXIONES?
```

---

# G.3 · Credenciales almacenadas

Riesgos:

```text
robo de credenciales
+
movimiento lateral
+
acceso a otros servicios
+
persistencia
+
suplantación
```

---

# G.4 · Respuesta

```text
1. Identificar credenciales expuestas.

2. Revocarlas o rotarlas.

3. Invalidar sesiones asociadas.

4. Revisar reutilización.

5. Buscar usos posteriores.

6. Revisar cuentas privilegiadas relacionadas.

7. Determinar si el atacante pudo extraerlas.
```

No basta con cambiar la contraseña de María si también existían:

```text
tokens
credenciales de navegador
secretos
claves
```

---

# 🚨 BLOQUE H · SEGUNDO EQUIPO

## H.1 · Hipótesis

Al menos:

```text
1. Mismo atacante.
2. Misma infraestructura de C2/exfiltración.
3. Compromiso independiente.
4. Mismo malware o herramienta.
5. Uso de credenciales relacionadas.
6. Dispositivo infectado por el mismo vector.
```

---

## H.2 · Acción inmediata

```text
1. Identificar equipo.
2. Aislarlo si procede.
3. Preservar evidencias.
4. Revisar usuario.
5. Revisar conexiones.
6. Comparar timeline.
7. Comparar IOC.
8. Buscar el mismo patrón en toda la organización.
```

---

## H.3 · Determinar si es el mismo atacante

Correlacionar:

```text
IOC
+
TTP
+
horarios
+
infraestructura
+
dominios
+
IPs
+
herramientas
+
cuentas
+
patrones de comportamiento
```

Un único IOC no demuestra por sí mismo que sea el mismo actor.

---

# 🔐 BLOQUE I · IDENTIDAD

## I.1 · ¿Cómo puede ocurrir con MFA?

Posibilidades:

```text
CREDENCIALES ROBADAS
+
APROBACIÓN FRAUDULENTA
+
ROBO DE SESIÓN
+
TOKEN ROBADO
+
DISPOSITIVO COMPROMETIDO
+
FATIGA DE MFA
+
MÉTODO DE RECUPERACIÓN DÉBIL
```

La conclusión:

> MFA reduce mucho el riesgo, pero no convierte una identidad en infalible.

---

# I.2 · Controles adicionales

```text
ACCESO CONDICIONAL
+
DEVICE COMPLIANCE
+
EDR
+
ANÁLISIS DE COMPORTAMIENTO
+
GESTIÓN DE SESIONES
+
PAM
+
SEGMENTACIÓN
+
MÍNIMO PRIVILEGIO
+
MONITORIZACIÓN
```

---

# I.3 · Sesiones y tokens

Ante una sospecha seria:

```text
REVOCAR SESIONES
+
INVALIDAR TOKENS
+
FORZAR REAUTENTICACIÓN
+
ROTAR CREDENCIALES
```

No basta con cambiar la contraseña si una sesión válida sigue activa.

---

# 📊 BLOQUE J · DATOS Y RGPD

## J.1 · ¿Existe una posible brecha?

**Sí.**

Tenemos:

```text
DATOS PERSONALES
+
ACCESO NO AUTORIZADO
+
TRANSFERENCIA EXTERNA
```

Por tanto existe una posible violación de seguridad de datos personales que debe evaluarse.

---

# J.2 · Factores para evaluar el riesgo

Al menos:

```text
1. Naturaleza de los datos.
2. Sensibilidad.
3. Número de afectados.
4. Volumen de datos.
5. Categorías de interesados.
6. Posibilidad de identificación.
7. Posibles consecuencias.
8. Facilidad para causar daño.
9. Si existen categorías especiales.
10. Si existen datos financieros.
11. Si existen datos de menores.
12. Si existen credenciales.
13. Si los datos estaban cifrados.
14. Si el atacante pudo leerlos.
15. Si fueron realmente exfiltrados.
16. A quién fueron enviados.
17. Si pueden recuperarse.
18. Probabilidad de uso indebido.
19. Duración de la exposición.
20. Medidas adoptadas para mitigar el riesgo.
```

---

# J.3 · Departamentos

```text
SEGURIDAD
+
IT
+
DPO / DPD
+
JURÍDICO
+
DIRECCIÓN
+
RESPONSABLE DEL TRATAMIENTO
```

Según el incidente:

```text
RRHH
+
COMUNICACIÓN
+
RESPONSABLES DE INVESTIGACIÓN
+
PROVEEDORES
```

---

# J.4 · Notificación a la autoridad

Debe realizarse una evaluación documentada del riesgo para los derechos y libertades de las personas.

Si la brecha es susceptible de generar riesgo:

```text
→ NOTIFICACIÓN A LA AUTORIDAD DE CONTROL
```

Cuando proceda, el RGPD establece como referencia:

```text
SIN DILACIÓN INDEBIDA
Y, CUANDO SEA POSIBLE,
EN 72 HORAS DESDE QUE EL RESPONSABLE
TIENE CONSTANCIA DE LA BRECHA
```

No debemos esperar a completar absolutamente toda la investigación para empezar el análisis.

---

# J.5 · Comunicación a afectados

El criterio es más exigente:

```text
ALTO RIESGO
↓
COMUNICACIÓN A LOS AFECTADOS
```

Por tanto hay que valorar:

```text
GRAVEDAD
+
PROBABILIDAD
+
TIPO DE DATOS
+
CONSECUENCIAS
```

No toda brecha obliga automáticamente a comunicarla individualmente a todos los afectados.

---

# 🏛️ BLOQUE K · ENS

## K.1 · Dimensiones

### Confidencialidad

🔴 Claramente afectada.

```text
2.843 archivos
+
1,8 GB
+
datos personales
```

---

### Integridad

🟠 En riesgo.

No tenemos confirmación de modificación, pero el atacante ha tenido acceso amplio.

---

### Disponibilidad

🟡 En riesgo.

No existe evidencia de caída general, pero el atacante intentó acceder a backup y podría haber intentado causar impacto.

---

### Autenticidad

🟠 En riesgo.

La cuenta legítima de María está siendo utilizada de forma sospechosa.

---

### Trazabilidad

🟠 En riesgo, pero los sistemas de logging y SIEM ayudan a conservarla.

---

# K.2 · Medidas ENS

## Organizativas

```text
• Política de seguridad.
• Roles y responsabilidades.
• Gestión de incidentes.
• Gestión de riesgos.
• Formación.
• Coordinación.
```

## Operacionales

```text
• Gestión de incidentes.
• Monitorización.
• Gestión de vulnerabilidades.
• Gestión de cambios.
• Continuidad.
• Gestión de copias.
• Auditoría.
```

## Protección / técnicas

```text
• Control de acceso.
• MFA.
• Segmentación.
• EDR.
• Firewall.
• Protección de comunicaciones.
• Registro de actividad.
• Copias de seguridad.
• Protección de información.
```

---

# K.3 · Evidencias de correcta gestión

```text
TIMELINE
+
TICKETS
+
ALERTAS
+
LOGS
+
ACCIONES DE CONTENCIÓN
+
DECISIONES
+
RESPONSABLES
+
COMUNICACIONES
+
EVIDENCIAS FORENSES
+
EVALUACIÓN RGPD
+
INFORMES
+
PRUEBAS DE RECUPERACIÓN
```

La documentación es importante para demostrar:

```text
QUÉ SE HIZO
+
CUÁNDO
+
QUIÉN
+
POR QUÉ
```

---

# 🧹 BLOQUE L · ERRADICACIÓN

Si existe persistencia en dos servidores:

```text
1. Aislar servidores afectados.

2. Identificar mecanismo de persistencia.

3. Analizar cuentas creadas/modificadas.

4. Rotar credenciales.

5. Revisar tareas programadas.

6. Revisar servicios.

7. Revisar scripts.

8. Revisar claves y accesos remotos.

9. Eliminar software malicioso o no autorizado.

10. Parchear vulnerabilidades.

11. Corregir configuraciones.

12. Revisar otros servidores.

13. Validar que no existe persistencia adicional.

14. Documentar todas las acciones.
```

No debemos asumir:

> "Hemos borrado el archivo malicioso, ya está limpio."

La erradicación requiere confianza razonable en que el atacante ya no puede volver a entrar mediante el mecanismo identificado.

---

# 🔄 BLOQUE M · RECUPERACIÓN

## Fase 1 · Preparación

```text
Sistemas limpios
+
credenciales rotadas
+
vulnerabilidades corregidas
```

## Fase 2 · Restauración

```text
BACKUP CONFIABLE
↓
RESTAURAR
```

## Fase 3 · Validación

Comprobar:

```text
INTEGRIDAD
+
CONFIGURACIÓN
+
SEGURIDAD
+
FUNCIONALIDAD
```

## Fase 4 · Reincorporación

Devolver servicios progresivamente:

```text
CRÍTICOS
↓
IMPORTANTES
↓
RESTO
```

## Fase 5 · Monitorización reforzada

Durante un periodo definido:

```text
SIEM
+
EDR
+
FIREWALL
+
IDENTIDAD
```

con vigilancia reforzada.

---

# 💾 BLOQUE N · BACKUPS

## N.1 · ¿Qué comprobar?

```text
1. Intentos de acceso.
2. Cuentas utilizadas.
3. Logs.
4. Integridad.
5. Fecha de última copia.
6. Copias afectadas.
7. Inmutabilidad.
8. Aislamiento.
9. Accesos administrativos.
10. Posible manipulación.
```

---

# N.2 · ¿Son confiables?

Hay que comprobar:

```text
ORIGEN
+
INTEGRIDAD
+
FECHA
+
ESTADO
+
AUSENCIA DE COMPROMISO
+
PRUEBA DE RESTAURACIÓN
```

No basta con que:

```text
"el backup exista".
```

Debe ser:

```text
RESTAURABLE
+
ÍNTEGRO
+
NO COMPROMETIDO
```

---

# N.3 · RTO, RPO, 3-2-1 e inmutabilidad

### RTO

```text
Tiempo objetivo para recuperar
el servicio.
```

### RPO

```text
Cantidad máxima de información
que estamos dispuestos a perder.
```

### 3-2-1

Concepto clásico:

```text
3 COPIAS
2 MEDIOS
1 COPIA FUERA DEL ENTORNO PRINCIPAL
```

En una estrategia moderna puede complementarse con:

```text
INMUTABILIDAD
+
AISLAMIENTO
```

### Pruebas de restauración

Porque:

```text
BACKUP
≠
RECUPERACIÓN GARANTIZADA
```

---

# 🧠 BLOQUE O · THREAT INTELLIGENCE

## O.1 · Información a obtener

```text
IP
DOMINIOS
URL
CERTIFICADOS
DNS
WHOIS / REGISTROS DISPONIBLES
HISTORIAL
REPUTACIÓN
MALWARE RELACIONADO
TTP
OTROS IOC
```

También:

```text
¿qué otras organizaciones han observado
actividad relacionada?
```

---

# O.2 · IOC vs TTP

## IOC

**Indicator of Compromise**

Ejemplos:

```text
IP
HASH
DOMINIO
URL
EMAIL
NOMBRE DE ARCHIVO
CERTIFICADO
```

## TTP

**Tactics, Techniques and Procedures**

Describe:

```text
QUÉ OBJETIVO
+
QUÉ TÉCNICA
+
CÓMO OPERA
```

Ejemplo:

```text
PowerShell
+
enumeración
+
movimiento lateral
```

Un IOC puede cambiar rápidamente.

Las TTP pueden permanecer útiles aunque cambien:

```text
IP
dominio
hash
```

---

# O.3 · ¿Por qué bloquear solo la IP es insuficiente?

Porque el atacante puede:

```text
cambiar IP
+
usar otro dominio
+
usar otra infraestructura
+
usar servicios legítimos
+
usar otra cuenta
```

Por eso debemos detectar:

```text
IOC
+
TTP
+
COMPORTAMIENTO
```

---

# 🧩 BLOQUE P · PLAYBOOK

## Compromiso de cuenta + VPN + posible exfiltración

### 1. DETECCIÓN

```text
SIEM
↓
alerta
```

### 2. VALIDACIÓN

```text
correlacionar
+
confirmar
+
descartar falso positivo
```

### 3. CONTENCIÓN

```text
cuenta
+
sesiones
+
endpoint
+
red
+
destinos
```

### 4. INVESTIGACIÓN

```text
timeline
+
logs
+
EDR
+
identidad
+
datos
```

### 5. ERRADICACIÓN

```text
persistencia
+
vulnerabilidades
+
credenciales
+
software
```

### 6. RECUPERACIÓN

```text
restaurar
+
validar
+
monitorizar
```

### 7. COMUNICACIÓN

```text
dirección
+
seguridad
+
DPO
+
jurídico
+
autoridades/afectados
```

según corresponda.

### 8. LECCIONES APRENDIDAS

```text
causa raíz
+
fallos
+
controles
+
mejoras
```

---

# 🧠 BLOQUE Q · RAZONAMIENTO

## Q.1 · "MFA funcionó, no puede ser cuenta comprometida"

❌ Incorrecto.

```text
MFA
→ reduce riesgo
```

pero no demuestra:

```text
IDENTIDAD HUMANA
```

ni evita todos los escenarios de:

```text
TOKEN
SESIÓN
DISPOSITIVO
RECUPERACIÓN
ENGAÑO
```

---

## Q.2 · "Bloqueamos IP y solucionado"

❌ Incorrecto.

Una IP es solo un indicador.

Hay que investigar:

```text
persistencia
+
otras infraestructuras
+
otras cuentas
+
otros equipos
+
otros IOC
```

---

## Q.3 · "Aislamos y formateamos"

❌ Incorrecto como primera acción.

Podríamos destruir:

```text
memoria
+
procesos
+
artefactos
+
logs
+
evidencia
```

Primero:

```text
AISLAR
+
PRESERVAR
+
ADQUIRIR
```

y después limpiar o reconstruir.

---

## Q.4 · "Si no sabemos qué archivos salieron, no hay brecha"

❌ Incorrecto.

Ya existe:

```text
ACCESO NO AUTORIZADO
+
DATOS PERSONALES
+
TRANSFERENCIA EXTERNA
```

La incertidumbre sobre el alcance no elimina el incidente.

Precisamente obliga a:

```text
INVESTIGAR
+
EVALUAR RIESGO
```

---

## Q.5 · "No entraron al backup, no hay que revisarlo"

❌ Incorrecto.

El atacante:

```text
INTENTÓ
```

acceder.

Hay que comprobar:

```text
logs
+
cuentas
+
integridad
+
configuración
```

---

## Q.6 · "Primero erradicamos, luego investigamos"

❌ Incorrecto.

La investigación debe acompañar a la contención.

El orden conceptual es:

```text
CONTENER
+
PRESERVAR
+
INVESTIGAR
        ↓
ERRADICAR
```

---

# 🚨 BLOQUE R · COMUNICACIÓN

Una estructura razonable:

| Destinatario | Información |
|---|---|
| Dirección | Estado, impacto, decisiones |
| IT | Acciones técnicas |
| Seguridad | Indicadores, alcance, respuesta |
| DPO | Datos personales y riesgo |
| Jurídico | Obligaciones legales |
| Empleados | Instrucciones necesarias |
| Afectados | Información que corresponda |
| Autoridad | Información exigida cuando proceda |
| Proveedores | Acciones que deban ejecutar |

### Principio

```text
NECESIDAD DE SABER
+
INFORMACIÓN VERIFICADA
+
CANAL SEGURO
```

No se debe distribuir toda la información técnica a toda la organización.

---

# 🏆 BLOQUE S · ¿CUÁNDO TERMINA?

Al menos:

```text
1. Acceso atacante eliminado.

2. Persistencia eliminada.

3. Credenciales comprometidas rotadas.

4. Sesiones/tokens revocados.

5. Sistemas afectados corregidos.

6. Vulnerabilidades explotadas solucionadas.

7. No existen nuevos indicadores relevantes.

8. Servicios recuperados de forma segura.

9. Datos y backups validados.

10. Monitorización reforzada sin nuevos indicios.

11. Obligaciones regulatorias evaluadas.

12. Informe del incidente completado.
```

Importante:

> **"El atacante ya no está conectado" no significa necesariamente "incidente cerrado".**

---

# 🧠 BLOQUE T · LECCIONES APRENDIDAS

## Preventivas

```text
1. Mejorar MFA.
2. Revisar mínimo privilegio.
3. Segmentar.
4. Mejorar gestión de credenciales.
5. Formación.
```

## Detectivas

```text
1. SIEM.
2. EDR.
3. UEBA.
4. NDR.
5. Alertas de exfiltración.
```

## De respuesta

```text
1. Mejorar playbook.
2. Automatizar aislamiento.
3. Mejorar gestión de sesiones.
4. Mejorar coordinación.
5. Mejorar preservación de evidencias.
```

## De recuperación

```text
1. Backups inmutables.
2. Pruebas de restauración.
3. Definir RTO.
4. Definir RPO.
5. Plan de continuidad.
```

---

# 🔥 BLOQUE U · RETO FINAL

El atacante utiliza:

```text
CREDENCIALES VÁLIDAS
+
POWERSHELL
+
HERRAMIENTAS LEGÍTIMAS
```

Por tanto, detectar únicamente:

```text
MALWARE
```

no es suficiente.

## SIEM

Buscar:

```text
accesos anómalos
+
horarios
+
geolocalización
+
servidores
+
volumen
```

## EDR

Buscar:

```text
Office → PowerShell
PowerShell → red
procesos anómalos
scripts
```

## UEBA

Buscar:

```text
comportamiento diferente
al histórico del usuario
```

## NDR

Buscar:

```text
movimiento lateral
+
volumen
+
destinos
+
patrones
```

## Logs

Correlacionar:

```text
VPN
+
LDAP
+
DNS
+
Firewall
+
Servidores
```

## Identidad

Analizar:

```text
sesiones
+
tokens
+
dispositivos
+
MFA
+
ubicación
```

## Segmentación

Reducir:

```text
alcance
```

aunque las credenciales sean válidas.

---

# 🏆 BLOQUE V · INFORME FINAL

## Respuesta de referencia

> INVEGA ha sufrido un incidente de ciberseguridad que afecta a una cuenta de investigación utilizada para acceder a la VPN. Aunque la autenticación MFA fue superada correctamente, existen numerosos indicadores incompatibles con el comportamiento habitual de la usuaria, entre ellos accesos desde ubicaciones incompatibles, ejecución de PowerShell desde Office, enumeración de red y directorio, acceso a decenas de servidores y consulta masiva de documentación.
>
> El incidente evolucionó hacia una fase de recopilación y posible exfiltración, con aproximadamente 1,8 GB de tráfico transferido a un destino externo. Parte de la información contiene datos personales, resultados de investigación y documentación interna, por lo que debe tratarse como una posible violación de la seguridad de datos personales y someterse a una evaluación específica de riesgo conforme al RGPD.
>
> Las primeras medidas deben centrarse en el aislamiento del endpoint, deshabilitación de la cuenta, revocación de sesiones y tokens, bloqueo de indicadores, contención del tráfico externo y búsqueda de otros equipos comprometidos. Simultáneamente deben preservarse los logs y evidencias necesarias para reconstruir la actividad.
>
> La investigación debe determinar el vector de compromiso, el alcance, la posible persistencia, los datos consultados y exfiltrados y si existen otros sistemas afectados. Posteriormente deberán rotarse credenciales, eliminarse mecanismos de persistencia, corregirse vulnerabilidades y recuperarse los sistemas desde fuentes confiables.
>
> El cierre del incidente no debe producirse hasta comprobar razonablemente que el acceso atacante ha sido eliminado, que no existe persistencia conocida, que las credenciales han sido controladas, que los sistemas críticos son confiables y que se han completado las evaluaciones y obligaciones correspondientes.
>
> Como medidas posteriores deben reforzarse la gestión de identidades, el acceso condicional, la segmentación, la monitorización de comportamiento, la protección de credenciales, la estrategia de backups y los procedimientos de respuesta.

---

# 📊 BLOQUE W · MATRIZ FINAL

Una posible solución:

| Elemento | Situación |
|---|---|
| Activo inicial | Cuenta + endpoint de María |
| Cuenta afectada | `maria.garcia` |
| Vector de acceso | No confirmado |
| Persistencia | No confirmada inicialmente |
| Movimiento lateral | Confirmado por acceso a numerosos servidores |
| Datos afectados | Documentación + investigación + datos personales |
| Exfiltración | Aproximadamente 1,8 GB transferidos |
| Sistemas afectados | Endpoint + múltiples servidores potencialmente |
| Indicadores | VPN, PowerShell, LDAP, tráfico externo, etc. |
| Contención | Cuenta, endpoint, sesiones, destino, red |
| Erradicación | Pendiente de investigación |
| Recuperación | Tras validar sistemas y eliminar persistencia |
| Riesgo RGPD | Potencialmente significativo, debe evaluarse |
| Impacto ENS | Confidencialidad principalmente; integridad/disponibilidad/autenticidad/trazabilidad en riesgo |

---

# 🎯 LOS CINCO ERRORES QUE NO QUIERO QUE COMETAS EN EXAMEN

## ❌ 1. "MFA funcionó, así que era María"

No.

```text
AUTENTICACIÓN
≠
IDENTIDAD HUMANA CONFIRMADA
```

---

## ❌ 2. "Bloqueamos la IP"

No basta.

```text
IOC
≠
ATACANTE COMPLETO
```

---

## ❌ 3. "Formateamos el equipo"

No inmediatamente.

```text
PRESERVAR EVIDENCIA
```

es fundamental.

---

## ❌ 4. "No sabemos exactamente qué salió, así que no hay brecha"

Incorrecto.

La incertidumbre sobre el alcance **es precisamente algo que debe investigarse y evaluarse**.

---

## ❌ 5. "Ya no hay conexiones, incidente terminado"

Tampoco.

Primero hay que comprobar:

```text
ACCESO
PERSISTENCIA
CREDENCIALES
SISTEMAS
DATOS
BACKUPS
```

---

# 🧠 MAPA MENTAL FINAL

```text
                    INCIDENTE
                        │
             ┌──────────┴──────────┐
             ↓                     ↓
          IDENTIDAD               ENDPOINT
             │                     │
           VPN/MFA              EDR/PS
             │                     │
             └──────────┬──────────┘
                        ↓
                   MOVIMIENTO
                     LATERAL
                        ↓
                     DATOS
                        ↓
                   EXFILTRACIÓN
                        │
             ┌──────────┴──────────┐
             ↓                     ↓
            ENS                    RGPD
             │                     │
        Seguridad             Brecha/riesgo
             │                     │
             └──────────┬──────────┘
                        ↓
                    RESPUESTA
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

---

# 🏁 MISIÓN 14 · CORREGIDA

## La secuencia que debes recordar

```text
DETECTAR
   ↓
VALIDAR
   ↓
TRIAR
   ↓
CONTENER
   ↓
PRESERVAR
   ↓
INVESTIGAR
   ↓
ERRADICAR
   ↓
RECUPERAR
   ↓
COMUNICAR
   ↓
APRENDER
```

Y una última distinción que merece sitio propio:

```text
CONTENCIÓN
→ parar la propagación.

ERRADICACIÓN
→ eliminar la causa y persistencia.

RECUPERACIÓN
→ volver a operar de forma segura.

LECCIONES APRENDIDAS
→ mejorar para que el siguiente incidente
  encuentre una organización más preparada.
```

**Misión 14: completada.** 🚨🔐
