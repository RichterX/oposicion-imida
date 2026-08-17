# 🔐 BLOQUE 07 · SEGURIDAD
# 🧪 MISIÓN 12 · ENS + RGPD
## Auditoría de seguridad y protección de datos de un organismo público

> **Tipo:** misión práctica  
> **Bloque:** 07 · Seguridad  
> **Ámbitos:** 7.1 ENS + 7.2 RGPD  
> **Dificultad:** 🟡 Media / Alta  
> **Modalidad:** individual, offline  
> **Objetivo:** aplicar los conceptos estudiados a un escenario realista de administración pública, justificando las decisiones tomadas.

---

# 🎯 1. OBJETIVO DE LA MISIÓN

Hasta ahora has estudiado por separado:

```text
ENS
↓
seguridad de sistemas públicos

RGPD
↓
protección de datos personales
```

Ahora toca juntarlos.

En esta misión vas a asumir el papel de:

> **Técnico responsable de seguridad y sistemas de un organismo público.**

Tu trabajo será analizar una situación, detectar problemas y proponer medidas.

⚠️ **No se busca que memorices artículos literalmente.**

Se busca que seas capaz de responder:

```text
¿Qué problema existe?
        ↓
¿Qué principio / requisito se ve afectado?
        ↓
¿Qué riesgo genera?
        ↓
¿Qué medida propondrías?
        ↓
¿Por qué?
```

---

# 🏢 2. EL ESCENARIO

El organismo ficticio **INVEGA** es una entidad pública dedicada a la investigación y gestión de proyectos científicos.

Dispone de:

```text
150 empleados
20 investigadores
10 técnicos de laboratorio
8 administrativos
5 responsables de dirección
7 técnicos informáticos
```

Su infraestructura incluye:

```text
PORTAL WEB PÚBLICO
APLICACIÓN INTERNA
SERVIDOR DE FICHEROS
BASE DE DATOS
SERVIDOR DE CORREO
VPN
DIRECTORIO CORPORATIVO
COPIAS DE SEGURIDAD
```

Además, INVEGA gestiona:

```text
datos de empleados
datos de proveedores
datos de investigadores
datos de participantes en estudios
datos de contacto
información económica
documentación administrativa
resultados de investigación
```

---

# 🌐 3. INFRAESTRUCTURA

La arquitectura simplificada es:

```text
                         INTERNET
                            │
                            ▼
                     ┌─────────────┐
                     │   FIREWALL  │
                     └──────┬──────┘
                            │
                 ┌──────────┴──────────┐
                 │                     │
                 ▼                     ▼
                DMZ                RED INTERNA
                 │                     │
          ┌──────┴──────┐       ┌──────┴────────┐
          │             │       │               │
         WEB           API    USUARIOS       SERVIDORES
                                      │           │
                                      │      ┌────┴─────┐
                                      │      │          │
                                      │      DB      FICHEROS
                                      │
                                      ▼
                                   BACKUPS
```

La VPN permite acceder desde fuera de la organización.

---

# 👤 4. USUARIOS

Actualmente:

- Los empleados utilizan usuario y contraseña.
- No existe MFA para el acceso a la VPN.
- Algunos administradores comparten una cuenta administrativa.
- Existen cuentas de antiguos empleados que no siempre se desactivan inmediatamente.
- Algunos investigadores tienen permisos de lectura y escritura sobre más carpetas de las necesarias.
- Los usuarios pueden instalar determinados programas sin intervención del departamento IT.

---

# 🔑 5. CONTRASEÑAS

La política actual establece:

```text
MÍNIMO 8 CARACTERES
CAMBIO CADA 12 MESES
```

No se exige MFA.

Además:

> Algunos usuarios reutilizan sus contraseñas corporativas en servicios externos.

---

# 💾 6. COPIAS DE SEGURIDAD

INVEGA realiza:

```text
backup diario
```

de los servidores principales.

Sin embargo:

- Las copias están conectadas permanentemente a la infraestructura.
- No se realizan pruebas periódicas completas de restauración.
- No existe una copia inmutable.
- La organización no ha definido formalmente RTO y RPO para todos los servicios críticos.

---

# 📊 7. REGISTROS Y MONITORIZACIÓN

Los sistemas generan logs.

Sin embargo:

```text
NO EXISTE SIEM
```

Los logs se almacenan en cada sistema por separado.

Además:

- No todos los administradores revisan los registros.
- Algunos sistemas tienen periodos de retención diferentes.
- No existe una política centralizada de monitorización.
- Los relojes de algunos servidores no están perfectamente sincronizados.

---

# 📧 8. CORREO ELECTRÓNICO

El sistema de correo dispone de filtros antispam básicos.

No existe una solución específica avanzada de protección frente a phishing.

Los empleados reciben periódicamente:

```text
correos externos
enlaces
documentos adjuntos
```

No se realizan campañas periódicas de concienciación sobre phishing.

---

# 🧪 9. DATOS DE INVESTIGACIÓN

Uno de los departamentos mantiene una base de datos con información de participantes en proyectos científicos.

La base contiene:

```text
nombre
apellidos
correo electrónico
fecha de nacimiento
información relacionada con el proyecto
```

Algunos investigadores exportan datos a hojas de cálculo para trabajar desde sus equipos.

Estas hojas pueden almacenarse:

```text
en el ordenador local
en unidades USB
en servicios cloud personales
```

No existe una política clara que prohíba estas prácticas.

---

# ☁️ 10. SERVICIO CLOUD

Un investigador utiliza una cuenta personal de almacenamiento cloud para compartir temporalmente documentos con colaboradores externos.

Los documentos pueden contener:

```text
datos personales
resultados de investigación
documentación interna
```

El servicio no ha sido aprobado formalmente por INVEGA.

---

# 📱 11. DISPOSITIVOS MÓVILES

Los empleados pueden acceder al correo corporativo desde sus teléfonos.

No todos los dispositivos están gestionados mediante MDM.

No existe una política uniforme sobre:

```text
bloqueo
cifrado
borrado remoto
actualizaciones
```

---

# 🌐 12. PORTAL WEB

El portal público permite:

```text
consultar información
enviar formularios
descargar documentación
```

Los formularios recogen:

```text
nombre
correo electrónico
teléfono
```

El portal no muestra claramente en todos los formularios:

```text
información sobre privacidad
finalidad del tratamiento
```

---

# 📋 13. PROTECCIÓN DE DATOS

INVEGA tiene un documento interno llamado:

```text
"Política de Privacidad"
```

pero no todos los departamentos utilizan los mismos procedimientos.

Además:

- No existe un inventario completamente actualizado de tratamientos.
- Algunos departamentos desconocen qué datos personales manejan otros departamentos.
- No existe un procedimiento único para responder a solicitudes de derechos.
- No todos los empleados han recibido formación específica en protección de datos.
- No está claramente documentado quién debe comunicar internamente una posible brecha de datos personales.

---

# 🚨 14. EL INCIDENTE

Un viernes a las 09:15 ocurre lo siguiente.

Una empleada recibe un correo:

> **"Actualización urgente del sistema de nóminas"**

El mensaje contiene un enlace.

La empleada accede y proporciona:

```text
usuario
contraseña
```

La página era falsa.

---

## 09:40

El atacante utiliza las credenciales para acceder a la VPN.

Como no existe MFA:

```text
CREDENCIALES
+
VPN
=
ACCESO
```

---

## 09:55

El atacante accede al equipo de la empleada.

---

## 10:20

Se detectan conexiones hacia otros servidores.

---

## 10:45

El atacante consigue acceder a una carpeta compartida con documentación de investigación.

---

## 11:10

Se detecta una gran transferencia de archivos hacia un sistema externo.

---

## 11:30

El departamento IT descubre que parte de los documentos contienen:

```text
datos personales
```

---

## 12:00

La dirección pregunta:

> "¿Tenemos un incidente de seguridad ENS?"

Y el responsable jurídico pregunta:

> "¿Tenemos también una posible brecha de datos personales?"

---

# 🧠 15. TU MISIÓN

Debes elaborar un **informe de análisis y actuación**.

No necesitas responder con frases extremadamente largas.

Lo importante es:

```text
IDENTIFICAR
JUSTIFICAR
PROPONER
```

---

# 🔴 BLOQUE A · IDENTIFICACIÓN DEL INCIDENTE

## A.1

¿Estamos ante:

- un evento?
- un incidente?
- una brecha de seguridad?
- una brecha de datos personales?

Explica tu respuesta.

---

## A.2

Identifica los activos afectados o potencialmente afectados.

Puedes clasificarlos:

```text
SISTEMAS
DATOS
USUARIOS
CREDENCIALES
RED
SERVICIOS
```

---

## A.3

¿Qué propiedades de la tríada CIA pueden verse afectadas?

Analiza:

```text
CONFIDENCIALIDAD
INTEGRIDAD
DISPONIBILIDAD
```

No te limites a indicar una palabra. Justifica cada una.

---

# 🔵 BLOQUE B · ANÁLISIS DEL ATAQUE

## B.1

Identifica las principales fases del ataque utilizando los conceptos estudiados en 7.5.

Por ejemplo:

```text
PHISHING
↓
...
↓
...
```

---

## B.2

Relaciona el incidente con MITRE ATT&CK.

Identifica, al menos:

```text
Initial Access
Credential Access
Discovery
Lateral Movement
Collection
Exfiltration
```

No es necesario indicar códigos de técnicas si no los recuerdas.

---

## B.3

¿Qué vulnerabilidades o debilidades organizativas facilitaron el ataque?

Debes identificar al menos **8**.

---

# 🟢 BLOQUE C · ENS

## C.1

¿En qué sentido puede afectar este incidente al cumplimiento del ENS?

Explica la relación entre:

```text
SEGURIDAD
+
SISTEMAS DE INFORMACIÓN
+
SERVICIOS PÚBLICOS
```

---

## C.2

Identifica medidas de seguridad que propondrías para reducir el riesgo.

Agrúpalas:

```text
ORGANIZATIVAS
OPERACIONALES
TÉCNICAS
```

Intenta proponer al menos:

```text
4 organizativas
4 operacionales
6 técnicas
```

---

## C.3

¿Qué papel tendría el control de acceso?

Propón medidas relacionadas con:

```text
MÍNIMO PRIVILEGIO
CUENTAS
ADMINISTRADORES
MFA
BAJAS DE USUARIOS
PERMISOS
```

---

## C.4

¿Qué papel tendría la monitorización?

Explica cómo utilizarías:

```text
LOGS
SIEM
EDR
FIREWALL
```

para detectar y analizar este incidente.

---

## C.5

¿Qué medidas propondrías respecto a las copias de seguridad?

Incluye:

```text
3-2-1
INMUTABILIDAD
RTO
RPO
PRUEBAS DE RESTAURACIÓN
```

---

# 🟣 BLOQUE D · RGPD

## D.1

En el incidente se han visto afectados datos personales.

¿Podría existir una:

> **violación de la seguridad de los datos personales?**

Justifica.

---

## D.2

¿Qué principios del RGPD podrían verse comprometidos?

Analiza, cuando corresponda:

```text
LICITUD
LEALTAD
TRANSPARENCIA
LIMITACIÓN DE LA FINALIDAD
MINIMIZACIÓN
EXACTITUD
LIMITACIÓN DEL PLAZO DE CONSERVACIÓN
INTEGRIDAD Y CONFIDENCIALIDAD
RESPONSABILIDAD PROACTIVA
```

⚠️ No es necesario afirmar que todos están incumplidos. Determina cuáles tienen relación real con el escenario.

---

## D.3

¿Quién debería participar internamente en la gestión del incidente?

Considera:

```text
IT
SEGURIDAD
DPO / DELEGADO DE PROTECCIÓN DE DATOS
DIRECCIÓN
ÁREA JURÍDICA
RESPONSABLE DEL TRATAMIENTO
```

---

## D.4

¿Qué debería analizarse para determinar si existe obligación de notificar la brecha a la autoridad de control?

Explica el criterio general.

---

## D.5

¿Y qué debería analizarse para determinar si también debe comunicarse a los afectados?

No respondas simplemente "sí" o "no".

Explica qué factor determina la obligación.

---

# 🟠 BLOQUE E · RESPUESTA AL INCIDENTE

Diseña un procedimiento desde las 12:00.

## E.1 Contención

Propón al menos **8 acciones inmediatas**.

Ejemplos de áreas:

```text
CUENTA
VPN
ENDPOINT
RED
SERVIDORES
CREDENCIALES
DATOS
COMUNICACIONES
```

---

## E.2 Preservación de evidencias

¿Qué evidencias intentarías conservar?

Por ejemplo:

```text
LOGS
EDR
VPN
FIREWALL
CORREO
EQUIPO AFECTADO
CUENTA
TRÁFICO
```

Explica por qué.

---

## E.3 Erradicación

¿Qué habría que eliminar o corregir antes de considerar controlado el incidente?

---

## E.4 Recuperación

Diseña una recuperación ordenada.

```text
1.
2.
3.
4.
5.
6.
```

---

# 🟡 BLOQUE F · MEJORA POSTERIOR

Una vez recuperada la organización:

## F.1

Identifica al menos **10 medidas de mejora**.

Puedes clasificarlas:

```text
PERSONAS
PROCESOS
TECNOLOGÍA
DATOS
INFRAESTRUCTURA
```

---

## F.2

¿Qué cambiarías para evitar que un atacante que robe una contraseña pueda entrar directamente por VPN?

---

## F.3

¿Qué cambiarías para reducir el movimiento lateral?

---

## F.4

¿Qué cambiarías para reducir la posibilidad de exfiltración?

---

## F.5

¿Qué cambiarías para mejorar la detección?

---

# 🔥 BLOQUE G · AUDITORÍA RÁPIDA

Además del incidente, debes detectar **10 debilidades adicionales** presentes en INVEGA que no dependan directamente del phishing.

Para cada una:

```text
DEBILIDAD
↓
RIESGO
↓
MEDIDA
```

Ejemplo:

```text
CUENTAS DE ANTIGUOS EMPLEADOS
↓
ACCESO NO AUTORIZADO
↓
PROCEDIMIENTO DE BAJA + REVISIÓN DE CUENTAS
```

---

# 🧠 BLOQUE H · PREGUNTAS DE RAZONAMIENTO

## H.1

INVEGA dice:

> "Tenemos antivirus, firewall y copias de seguridad, por lo que el riesgo de ransomware es muy bajo."

¿Estás de acuerdo?

Razona.

---

## H.2

Un responsable propone:

> "Vamos a cambiar las contraseñas cada 30 días y solucionamos el problema."

¿Por qué esta medida, por sí sola, sería insuficiente?

---

## H.3

Un administrador propone:

> "Para simplificar la gestión, todos los administradores deberían utilizar una única cuenta administrativa."

Explica por qué esta propuesta es problemática.

---

## H.4

Un investigador afirma:

> "Como el servicio cloud tiene contraseña, podemos utilizarlo para guardar datos de investigación."

¿Es suficiente?

---

## H.5

La dirección pregunta:

> "Si no hemos detectado pruebas de que los datos hayan sido publicados, ¿podemos considerar que no existe problema de confidencialidad?"

Razona.

---

# 🧪 BLOQUE I · DISEÑO FINAL

Debes diseñar una **arquitectura de seguridad mejorada** para INVEGA.

Puedes realizarla en texto, Markdown o incluso dibujarla.

Como mínimo debería incluir:

```text
INTERNET
   ↓
FIREWALL
   ↓
DMZ
   ↓
RED INTERNA
   ↓
SEGMENTACIÓN
   ↓
USUARIOS / SERVIDORES / DATOS
```

Añade:

```text
MFA
EDR
SIEM
BACKUPS
DLP
WAF
VPN
CONTROL DE ACCESO
MONITORIZACIÓN
```

No es necesario utilizar todos los elementos si justificas por qué alguno no sería adecuado.

---

# 🏆 BLOQUE J · INFORME EJECUTIVO

Imagina que debes presentar el resultado a la dirección.

Redacta un resumen de **máximo 500 palabras** que responda:

1. ¿Qué ocurrió?
2. ¿Qué impacto tiene?
3. ¿Qué riesgos existen?
4. ¿Qué acciones deben realizarse inmediatamente?
5. ¿Qué medidas deben implantarse a medio plazo?
6. ¿Qué riesgos no se han podido descartar?

---

# 📊 16. MATRIZ FINAL DE RIESGO

Completa al menos cinco riesgos:

| Riesgo | Activo | Amenaza | Vulnerabilidad | Impacto | Probabilidad | Nivel | Medida |
|---|---|---|---|---|---|---|---|
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |

Puedes utilizar:

```text
Probabilidad:
BAJA / MEDIA / ALTA

Impacto:
BAJO / MEDIO / ALTO

Nivel:
BAJO / MEDIO / ALTO / CRÍTICO
```

No existe una única clasificación correcta si justificas adecuadamente tu criterio.

---

# 🧠 17. RETO EXTRA

Si quieres subir la dificultad:

Imagina que el atacante:

```text
NO UTILIZÓ MALWARE
```

y que únicamente utilizó:

```text
CREDENCIALES VÁLIDAS
+
HERRAMIENTAS LEGÍTIMAS
+
SERVICIOS AUTORIZADOS
```

Explica cómo podría detectarse el ataque.

Debes proponer al menos:

```text
5 indicadores
+
5 controles
```

---

# 🎯 18. OBJETIVOS DE SUPERACIÓN

Considera la misión superada si puedes:

```text
□ Identificar el incidente.

□ Identificar los activos afectados.

□ Analizar CIA.

□ Reconstruir el ataque.

□ Utilizar correctamente MITRE ATT&CK.

□ Detectar debilidades ENS.

□ Proponer controles ENS.

□ Diferenciar seguridad y protección de datos.

□ Identificar principios RGPD relacionados.

□ Explicar qué debe analizarse ante una brecha de datos personales.

□ Diseñar una estrategia de contención.

□ Diseñar una estrategia de erradicación.

□ Diseñar una recuperación.

□ Utilizar correctamente RTO y RPO.

□ Proponer medidas de detección.

□ Identificar evidencias forenses.

□ Diseñar mejoras posteriores.

□ Priorizar riesgos.

□ Explicar las decisiones a dirección.
```

---

# 🧭 19. REGLA DE ORO

No intentes responder esta misión pensando:

> "¿Qué definición tengo que escribir?"

Piensa:

```text
¿QUÉ ESTÁ PASANDO?
        ↓
¿QUÉ RIESGO GENERA?
        ↓
¿QUÉ NORMA / PRINCIPIO / CONTROL APLICA?
        ↓
¿QUÉ HARÍA YO?
        ↓
¿POR QUÉ?
```

Ese razonamiento es precisamente el que queremos entrenar.

---

# 🏁 FIN DE LA MISIÓN 12

## 🔐 ENS + RGPD

```text
BLOQUE 07
   │
   ├── 7.1 ENS
   ├── 7.2 RGPD
   │
   └── MISIÓN 12
          ↓
      CASO INTEGRAL
          ↓
     INCIDENTE REALISTA
          ↓
     ENS + RGPD + CIA
          ↓
     RESPUESTA + RIESGO
```

### 🚨 IMPORTANTE

**Esta misión NO incluye las soluciones.**

Primero resuélvela offline.

Cuando termines, puedes pasarme tus respuestas y haremos una **corrección completa punto por punto**, igual que con las misiones anteriores, distinguiendo entre:

```text
🟢 CORRECTO
🟡 PARCIAL
🔴 INCORRECTO

+
💡 EXPLICACIÓN
+
📚 CONCEPTO A REPASAR
+
🎯 RESPUESTA IDEAL DE EXAMEN
```

**Misión 12 desbloqueada.** 🔐
