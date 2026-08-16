# 🧠 SOLUCIONES · MISIÓN 11
# Bloque 06 · Gestión TIC
## El proyecto que nadie sabe gestionar

> **Documento de corrección**
>
> Estas soluciones están pensadas para revisar la misión offline. En las preguntas abiertas puede haber formulaciones diferentes que sean igualmente válidas si mantienen el concepto correcto.

---

# 🧩 PARTE 1 · IDENTIFICA EL MARCO

## 1.1

**Situación:** buenas prácticas para gestionar incidentes, problemas, peticiones y niveles de servicio.

**Respuesta:**

> **ITIL**

### Explicación

ITIL proporciona un conjunto de buenas prácticas para la gestión de servicios, incluyendo prácticas relacionadas con:

```text
incidentes
problemas
peticiones
niveles de servicio
mejora continua
```

---

## 1.2

**Situación:** requisitos formales para un Sistema de Gestión de Servicios.

**Respuesta:**

> **ISO/IEC 20000-1**

### Explicación

ISO/IEC 20000-1 establece requisitos para establecer, implementar, mantener y mejorar un:

```text
Service Management System
(SMS)
```

---

## 1.3

**Situación:** gobernar un proyecto temporal con presupuesto, plazos, riesgos, productos y responsabilidades.

**Respuesta:**

> **PRINCE2**

### Explicación

PRINCE2 es un método de gestión de proyectos y proporciona conceptos como:

```text
Business Case
etapas
tolerancias
roles/responsabilidades
productos
riesgos
gestión por excepción
```

---

## 1.4

**Situación:** desarrollo iterativo, feedback frecuente y adaptación.

**Respuesta:**

> **Scrum**

### Explicación

Scrum es un framework para abordar productos y problemas complejos mediante un enfoque empírico, iterativo e incremental.

---

## 1.5

**Situación:** comprobar si el sistema de gestión de servicios cumple una norma internacional.

**Respuesta:**

> **ISO/IEC 20000-1**

### Explicación

La norma establece requisitos que pueden utilizarse como base para evaluar la conformidad del Sistema de Gestión de Servicios.

---

## 1.6

**Situación:** organizar el trabajo en Sprints.

**Respuesta:**

> **Scrum**

---

## 1.7

**Situación:** gestionar los servicios una vez que la plataforma esté operativa.

**Respuesta:**

> **ITIL**

### Explicación

Aquí ya no estamos principalmente desarrollando el producto ni gestionando el proyecto de implantación, sino gestionando el servicio en operación.

---

## 1.8

**Situación:** controlar un proyecto desde su inicio hasta su cierre mediante etapas y tolerancias.

**Respuesta:**

> **PRINCE2**

---

# 🏗️ PARTE 2 · CONSTRUYE EL PROYECTO

## 2.1

### Respuesta orientativa

NEXUS es un proyecto porque tiene características propias de una iniciativa temporal:

```text
1. Tiene un comienzo y un final.
2. Persigue un objetivo concreto.
3. Debe producir productos definidos.
4. Dispone de recursos limitados.
5. Implica cambios en la organización.
6. Tiene riesgos, costes y plazos que gestionar.
```

No es simplemente una operación habitual porque la organización está creando una nueva capacidad y realizando un cambio temporalmente organizado.

---

## 2.2

### Respuesta

> **Business Case**

El Business Case permite responder:

> "¿Por qué merece la pena realizar NEXUS?"

Debería considerar aspectos como:

```text
beneficios
desbeneficios
costes
riesgos
viabilidad
deseabilidad
```

Además, PRINCE2 exige que la justificación empresarial continúe siendo válida durante el proyecto.

### Idea clave

```text
Business Case
→ ¿Por qué hacemos el proyecto?
```

---

## 2.3

### Respuesta

El **Project Board** está formado por:

```text
Executive
Senior User
Senior Supplier
```

### Executive

Representa principalmente el interés empresarial.

Se preocupa de que:

```text
el proyecto siga justificándose
+
los recursos estén adecuadamente dirigidos
+
se obtengan los beneficios previstos
```

### Senior User

Representa los intereses de:

```text
usuarios
+
beneficiarios
```

Se preocupa especialmente de:

```text
necesidades
+
beneficios
+
aceptación
```

### Senior Supplier

Representa los intereses relacionados con:

```text
diseño
+
construcción
+
suministro
+
conocimientos técnicos
```

### Memoriza

```text
Executive
→ negocio

Senior User
→ usuarios

Senior Supplier
→ proveedor/técnico
```

---

## 2.4

Tenemos:

```text
Tolerancia de tiempo:
±10 días

Tolerancia de coste:
±20.000 €
```

La previsión es:

```text
+4 días
+8.000 €
```

### Respuesta

No es necesario escalar inmediatamente al Project Board.

La previsión está:

```text
dentro de las tolerancias
```

Por tanto, el Project Manager puede gestionar la situación dentro de su autoridad.

Esto representa:

> **Manage by exception**

mientras la situación permanezca dentro de los límites acordados.

---

## 2.5

Ahora tenemos:

```text
+25 días
+45.000 €
```

Las tolerancias eran:

```text
±10 días
±20.000 €
```

Por tanto:

```text
25 > 10
45.000 > 20.000
```

### Respuesta

Se ha producido una:

> **excepción**

El Project Manager debe escalar la situación siguiendo el mecanismo de gobierno establecido.

El nivel superior deberá decidir qué hacer con la desviación.

### Concepto clave

```text
Tolerancia superada
        ↓
Excepción
        ↓
Escalado
        ↓
Decisión
```

---

# 🧠 PARTE 3 · LOS PRODUCTOS

## 3.1

### Respuesta

PRINCE2 utiliza un enfoque basado en productos.

Primero debemos determinar:

```text
qué productos necesitamos
+
qué características deben tener
+
qué criterios de calidad deben cumplir
```

y posteriormente determinar:

```text
qué trabajo
```

es necesario para producirlos.

Esto ayuda a evitar que el proyecto se centre exclusivamente en actividades sin tener claro cuál será el resultado final.

### Idea clave

```text
¿QUÉ ENTREGAMOS?
        ↓
PRODUCTOS
        ↓
¿QUÉ TRABAJO NECESITAMOS?
```

---

## 3.2

### Ejemplo de Product Description

Producto elegido:

> **P4. Sistema de gestión de incidencias**

### Nombre

```text
Sistema de gestión de incidencias
```

### Propósito

Permitir registrar, clasificar, priorizar, asignar, resolver y cerrar incidencias relacionadas con los servicios TIC.

### Composición

Podría incluir:

```text
formulario de registro
base de datos de incidencias
clasificación
priorización
asignación
seguimiento
historial
notificaciones
```

### Criterios de calidad

Por ejemplo:

```text
Debe permitir registrar una incidencia.
Debe conservar trazabilidad.
Debe controlar permisos de acceso.
Debe permitir consultar el estado.
Debe cumplir los niveles de disponibilidad establecidos.
```

### Método de calidad

Por ejemplo:

```text
pruebas funcionales
pruebas de permisos
pruebas de rendimiento
revisión
pruebas de aceptación
```

> No existe una única respuesta correcta. Lo importante es demostrar que una Product Description define claramente qué es el producto y cómo se comprobará su calidad.

---

## 3.3

### Respuesta

> **Work Package**

Es una forma de acordar y controlar el trabajo que se autoriza a un Team Manager o equipo.

Puede establecer:

```text
productos a entregar
+
tolerancias
+
restricciones
+
métodos
+
información necesaria
```

---

# 🏃 PARTE 4 · AHORA ENTRA SCRUM

## 4.1

### Respuesta

> **Product Owner**

Es responsable de maximizar el valor del producto.

También es responsable de la gestión efectiva del Product Backlog, incluyendo:

```text
desarrollar y comunicar Product Goal
+
crear/comunicar elementos
+
ordenar elementos
+
hacer que el backlog sea transparente,
visible y comprendido
```

Puede delegar determinadas tareas, pero sigue siendo responsable.

---

## 4.2

### Respuesta

> **Sprint Planning**

Es el evento que inicia el Sprint.

Responde esencialmente a:

```text
¿Por qué?
→ Sprint Goal

¿Qué?
→ selección de Product Backlog items

¿Cómo?
→ plan de trabajo
```

El resultado fundamental incluye:

```text
Sprint Goal
+
selección de Product Backlog items
+
plan de trabajo
```

que conforman el Sprint Backlog.

---

## 4.3

### Respuesta

> **Daily Scrum**

Tiene una duración de:

```text
15 minutos
```

Su propósito es:

> inspeccionar el progreso hacia el Sprint Goal y adaptar el Sprint Backlog según sea necesario.

No es una reunión destinada simplemente a informar al Scrum Master.

---

## 4.4

### Respuesta

Las tres preguntas:

```text
¿Qué hice ayer?
¿Qué haré hoy?
¿Qué impedimentos tengo?
```

pueden utilizarse como técnica para realizar el Daily Scrum.

Pero:

> **NO son obligatorias en Scrum.**

Lo importante es que el Daily Scrum permita a los Developers inspeccionar el progreso hacia el:

```text
Sprint Goal
```

y adaptar su plan.

---

## 4.5

### Respuesta

> **Sprint Review**

Se inspecciona principalmente:

```text
resultado del Sprint
+
Increment
+
progreso hacia Product Goal
```

y se obtiene feedback de los stakeholders relevantes.

Como consecuencia, el Product Backlog puede adaptarse.

### Regla mental

```text
Review
→ producto
→ resultado
→ feedback
```

---

## 4.6

### Respuesta

> **Sprint Retrospective**

Se inspecciona la forma de trabajar del equipo:

```text
personas
+
interacciones
+
procesos
+
herramientas
+
Definition of Done
```

para identificar mejoras.

### Regla mental

```text
Review
→ ¿qué hemos construido?

Retro
→ ¿cómo estamos trabajando?
```

---

# 📦 PARTE 5 · LOS TRES ARTEFACTOS

| Artefacto | Compromiso |
|---|---|
| Product Backlog | **Product Goal** |
| Sprint Backlog | **Sprint Goal** |
| Increment | **Definition of Done** |

## Diferencias

### Product Goal

Objetivo a largo plazo del producto.

```text
¿Hacia dónde queremos llevar el producto?
```

### Sprint Goal

Objetivo único del Sprint.

```text
¿Qué queremos conseguir en este Sprint?
```

### Definition of Done

Descripción formal del estado que debe cumplir un Increment para considerarse terminado conforme a las medidas de calidad requeridas.

```text
¿Qué significa "terminado"?
```

---

# 🚨 PARTE 6 · INCIDENTE, PROBLEMA O PETICIÓN

## 6.1

> "No puedo acceder al portal de servicios."

### Respuesta

> **INCIDENTE**

Existe una interrupción o reducción de la calidad del servicio que requiere restauración.

---

## 6.2

> "Quiero solicitar acceso al catálogo de servicios."

### Respuesta

> **SERVICE REQUEST / PETICIÓN DE SERVICIO**

Es una solicitud del usuario de algo que forma parte de la prestación normal del servicio.

---

## 6.3

> "La aplicación deja de responder todos los lunes por la mañana."

### Respuesta

> **PROBLEMA**

La recurrencia indica que debemos investigar la causa subyacente o potencial de los incidentes.

Puede existir además un incidente activo, pero la investigación de la causa recurrente pertenece a Problem Management.

---

## 6.4

> "Necesito que me instalen una aplicación autorizada."

### Respuesta

> **SERVICE REQUEST / PETICIÓN DE SERVICIO**

Es una solicitud estándar del usuario.

---

## 6.5

> "Se ha descubierto que un componente defectuoso provoca repetidamente las caídas."

### Respuesta

> **PROBLEMA**

Aquí se ha identificado una causa real o potencial de uno o más incidentes.

---

## 6.6

### Incident Management

Busca:

> restaurar el servicio normal lo antes posible y minimizar el impacto sobre los usuarios.

```text
INCIDENTE
→ restaurar servicio
```

### Problem Management

Busca:

```text
identificar causas
+
reducir probabilidad/impacto
+
prevenir recurrencias
```

```text
PROBLEMA
→ entender/reducir causa
```

### Service Request Management

Gestiona:

```text
peticiones estándar
```

como:

```text
accesos
información
instalaciones autorizadas
```

### Resumen

```text
INCIDENT
→ algo ha fallado

PROBLEM
→ ¿por qué ocurre / podría ocurrir?

SERVICE REQUEST
→ el usuario solicita algo estándar
```

---

# 📊 PARTE 7 · ITIL ENTRA EN JUEGO

## 7.1 Service Desk

### Respuesta

Debe actuar como punto de contacto entre:

```text
usuarios
+
proveedor/organización de servicios
```

Puede:

```text
recibir incidencias
+
recibir peticiones
+
comunicar información
+
coordinar escalados
+
mantener comunicación con usuarios
```

---

## 7.2 Service Catalogue

### Respuesta

Debe proporcionar información sobre los servicios disponibles, por ejemplo:

```text
nombre del servicio
descripción
usuarios
condiciones
horarios
niveles de servicio
cómo solicitarlo
```

El catálogo permite que los usuarios sepan:

> **qué servicios existen y cómo acceder a ellos.**

---

## 7.3 Service Level Management

### Respuesta

Debe gestionar los niveles de servicio acordados, incluyendo:

```text
requisitos
+
objetivos
+
medición
+
seguimiento
+
revisión
+
mejora
```

Puede incluir indicadores como:

```text
disponibilidad
tiempos de respuesta
tiempos de resolución
cumplimiento de SLA
```

---

## 7.4 Continual Improvement

### Respuesta

La organización debe establecer un ciclo continuo de:

```text
medición
↓
análisis
↓
identificación de oportunidades
↓
mejoras
↓
medición
```

Puede utilizar:

```text
indicadores
+
feedback
+
incidentes
+
problemas
+
auditorías
+
revisiones
```

El objetivo es evitar que NEXUS quede implantado y posteriormente se convierta en un sistema estático.

---

# ⚖️ PARTE 8 · ITIL VS ISO/IEC 20000

La afirmación:

> "Ya tenemos ITIL. Por tanto, ya cumplimos ISO/IEC 20000."

es:

> ❌ **INCORRECTA**

### ITIL

Es un:

> **framework de buenas prácticas**

que proporciona orientación para la gestión de servicios.

### ISO/IEC 20000-1

Es una:

> **norma que establece requisitos para un Sistema de Gestión de Servicios.**

### SMS

Es el:

> **Service Management System**

que permite dirigir y controlar las actividades de gestión de servicios.

### Relación

```text
ITIL
→ buenas prácticas
       ↓
pueden ayudar a implementar
       ↓
SMS
       ↓
ISO/IEC 20000-1
→ requisitos
```

Utilizar ITIL no significa automáticamente cumplir todos los requisitos de ISO/IEC 20000-1.

---

# 🏛️ PARTE 9 · CONSTRUYENDO EL SMS

| Situación | Cláusula |
|---|---:|
| 9.1 Definir alcance | **4 · Contexto** |
| 9.2 Política | **5 · Liderazgo** |
| 9.3 Riesgos y oportunidades | **6 · Planificación** |
| 9.4 Recursos, competencia, concienciación | **7 · Apoyo** |
| 9.5 Servicios, cambios, incidentes y problemas | **8 · Operación** |
| 9.6 Auditorías e indicadores | **9 · Evaluación del desempeño** |
| 9.7 No conformidades y acciones correctivas | **10 · Mejora** |

### Regla de memoria

```text
4 → CONTEXTO
5 → LIDERAZGO
6 → PLAN
7 → APOYO
8 → OPERACIÓN
9 → EVALUACIÓN
10 → MEJORA
```

---

# 🔄 PARTE 10 · EL CICLO COMPLETO

Una respuesta posible:

## 1. Se decide crear una nueva plataforma.

> **PRINCE2**

Se plantea y justifica el proyecto.

---

## 2. Se justifica económicamente.

> **PRINCE2 → Business Case**

Se comprueba la justificación continua del proyecto.

---

## 3. Se organiza el proyecto.

> **PRINCE2**

Se definen:

```text
roles
+
responsabilidades
+
planes
+
tolerancias
+
controles
```

---

## 4. Se desarrolla la plataforma.

> **Scrum**

El desarrollo puede organizarse mediante:

```text
Sprints
+
Product Backlog
+
Sprint Goals
+
Increments
```

---

## 5. Se entrega una primera versión.

> **Scrum**

Se produce un:

```text
Increment
```

que cumple la:

```text
Definition of Done
```

---

## 6. La plataforma pasa a producción.

Aquí pueden intervenir:

```text
ITIL
+
ISO/IEC 20000
```

La transición y puesta en servicio deben realizarse de forma controlada dentro del modelo de gestión de servicios.

---

## 7. Los usuarios comienzan a utilizarla.

> **ITIL**

Empiezan a gestionarse:

```text
incidentes
+
peticiones
+
niveles de servicio
```

---

## 8. Se gestionan incidentes y peticiones.

> **ITIL**

Por ejemplo:

```text
Incident Management
Service Request Management
```

---

## 9. Se miden los niveles de servicio.

> **ITIL + ISO/IEC 20000**

ITIL aporta prácticas de gestión y medición del servicio.

ISO/IEC 20000-1 establece requisitos para el SMS.

---

## 10. Se audita y mejora el sistema.

> **ISO/IEC 20000 + ITIL**

ISO/IEC 20000 contempla:

```text
evaluación
+
auditoría
+
mejora
```

ITIL aporta prácticas de mejora continua.

---

# 🧨 PARTE 11 · CASOS TRAMPA

## 11.1

> "Como utilizamos Scrum, no necesitamos gestionar riesgos."

### Respuesta

❌ **Incorrecto.**

Scrum permite inspección y adaptación, pero eso no significa que elimine la necesidad de gestionar riesgos.

Si NEXUS se encuentra dentro de un proyecto PRINCE2, la gestión de riesgos continúa siendo una práctica fundamental de PRINCE2.

Además, Scrum e inspección/adaptación no sustituyen automáticamente todas las prácticas de gestión necesarias en una organización.

---

## 11.2

> "Como soy responsable del Product Backlog, puedo decidir quién realiza cada tarea."

### Respuesta

❌ **Incorrecto.**

El Product Owner es responsable de la gestión efectiva del Product Backlog y de maximizar el valor del producto.

Los Developers son responsables de:

```text
planificar
+
adaptar
+
gestionar
```

su propio trabajo.

Scrum Team:

```text
autogestionado
```

---

## 11.3

> "Un incidente y un problema son lo mismo."

### Respuesta

❌ **Incorrecto.**

```text
INCIDENTE
→ interrupción o reducción de calidad del servicio
→ objetivo: restaurarlo

PROBLEMA
→ causa real o potencial de uno o más incidentes
→ objetivo: reducir causas/recurrencia
```

Un mismo contexto puede contener ambos.

---

## 11.4

> "ISO/IEC 20000 nos dice exactamente cómo implementar Scrum."

### Respuesta

❌ **Incorrecto.**

ISO/IEC 20000-1 establece requisitos para el:

```text
Sistema de Gestión de Servicios
```

No prescribe Scrum como método obligatorio de desarrollo.

Una organización puede utilizar Scrum dentro de su modelo de gestión de servicios, pero son conceptos diferentes.

---

## 11.5

> "Si estoy dentro de las tolerancias, el Project Board no debería necesitar recibir ningún tipo de información."

### Respuesta

⚠️ **Incorrecto como afirmación absoluta.**

La gestión por excepción permite que el Project Manager gestione dentro de sus tolerancias sin escalar cada desviación.

Pero eso no significa que:

```text
no exista información
+
no existan informes
+
el Project Board quede completamente al margen
```

La dirección y gobernanza del proyecto siguen existiendo.

La clave es:

> **dentro de tolerancia → gestión delegada**

> **fuera de tolerancia → excepción y escalado**

---

## 11.6

> "La certificación ISO/IEC 20000 significa que todos los servicios son perfectos."

### Respuesta

❌ **Incorrecto.**

La conformidad con una norma no significa:

```text
perfección
+
cero incidentes
+
cero problemas
```

Significa que el sistema de gestión debe cumplir los requisitos aplicables y mantenerse y mejorarse adecuadamente.

La gestión de servicios sigue requiriendo:

```text
medición
+
evaluación
+
mejora
```

---

# 🧠 PARTE 12 · PREGUNTAS DE CONEXIÓN

## 12.1 PRINCE2 vs Scrum

### Respuesta modelo

```text
PRINCE2 es un método de gestión de proyectos.

Se ocupa de aspectos como:
justificación,
gobierno,
etapas,
tolerancias,
roles,
riesgos y control.

Scrum es un framework para abordar productos
y problemas complejos mediante empirismo,
iteración e incrementos.

PRINCE2 puede gobernar un proyecto
dentro del cual el desarrollo del producto
se realice utilizando Scrum.
```

### Idea clave

```text
PRINCE2
→ proyecto

Scrum
→ producto/desarrollo
```

---

## 12.2 ITIL vs ISO/IEC 20000

### Respuesta modelo

```text
ITIL es un framework de buenas prácticas
para la gestión de servicios.

ISO/IEC 20000-1 es una norma que establece
requisitos para un Sistema de Gestión de Servicios.

ITIL puede utilizarse como fuente de buenas
prácticas para diseñar y mejorar procesos.

Pero utilizar ITIL no significa automáticamente
cumplir ISO/IEC 20000-1.
```

---

## 12.3 ¿Pueden coexistir los cuatro?

### Respuesta

> **Sí.**

Y NEXUS es precisamente un buen ejemplo.

```text
PRINCE2
→ gobierna/gestiona el proyecto

Scrum
→ organiza el desarrollo del producto

ITIL
→ gestiona los servicios

ISO/IEC 20000
→ establece requisitos para el SMS
```

No compiten necesariamente.

Resuelven problemas diferentes.

---

## 12.4 PROYECTO · PRODUCTO · SERVICIO · SISTEMA

| Concepto | Marco |
|---|---|
| **Proyecto** | PRINCE2 |
| **Producto** | Scrum |
| **Servicio** | ITIL |
| **Sistema de gestión** | ISO/IEC 20000 |

### La cadena completa

```text
PRINCE2
gestiona el proyecto
       ↓
SCRUM
ayuda a desarrollar el producto
       ↓
producto pasa a servicio
       ↓
ITIL
ayuda a gestionar el servicio
       ↓
ISO/IEC 20000
establece requisitos para el
sistema de gestión de servicios
```

Esta es probablemente **la idea más importante de toda la misión**.

---

# 🧪 PARTE 13 · SIMULACIÓN DE EXAMEN

## 13.1

**Respuesta: B**

> Gestionar por excepción.

---

## 13.2

**Respuesta: C**

> Definition of Done.

---

## 13.3

**Respuesta: B**

> Restaurar el servicio normal lo antes posible.

---

## 13.4

**Respuesta: A**

> Un conjunto de requisitos para un SMS.

---

## 13.5

**Respuesta: C**

> Product Owner.

---

## 13.6

**Respuesta: C**

> Cláusula 8.

---

## 13.7

**Respuesta: B**

> Manage by exception.

---

## 13.8

**Respuesta: B**

> Sprint Review.

---

## 13.9

**Respuesta: B**

> ITIL es un framework de buenas prácticas e ISO/IEC 20000 establece requisitos.

---

## 13.10

**Respuesta: B**

> Una causa real o potencial de uno o más incidentes.

---

# 🏆 PARTE 14 · RETO FINAL

### Respuesta modelo

No necesitamos elegir entre los cuatro porque no resuelven exactamente el mismo problema. **PRINCE2** puede utilizarse para gobernar y gestionar el proyecto NEXUS, controlando su justificación, etapas, riesgos, tolerancias y responsabilidades. **Scrum** puede utilizarse por el equipo de desarrollo para construir la plataforma de forma iterativa e incremental. Una vez que la plataforma se convierte en un servicio operativo, **ITIL** proporciona prácticas para gestionar incidentes, peticiones, niveles de servicio y mejora continua. Finalmente, **ISO/IEC 20000-1** puede proporcionar los requisitos para establecer y mantener un Sistema de Gestión de Servicios. Los cuatro pueden coexistir porque actúan sobre niveles diferentes del mismo ecosistema.

### En una frase

```text
PRINCE2
→ gestiona el PROYECTO

SCRUM
→ desarrolla el PRODUCTO

ITIL
→ gestiona el SERVICIO

ISO/IEC 20000
→ estructura el SISTEMA DE GESTIÓN
```

---

# 🎯 PARTE 15 · CHECKLIST DE DOMINIO

```text
✓ Sé qué problema resuelve ITIL.

✓ Sé qué problema resuelve Scrum.

✓ Sé qué problema resuelve PRINCE2.

✓ Sé qué problema resuelve ISO/IEC 20000.

✓ Sé distinguir framework y norma.

✓ Sé distinguir proyecto, producto y servicio.

✓ Sé distinguir incidente, problema y petición.

✓ Sé explicar gestión por excepción.

✓ Sé explicar tolerancias.

✓ Sé identificar el Project Board.

✓ Sé distinguir Product Owner y Scrum Master.

✓ Sé identificar los tres artefactos Scrum.

✓ Sé identificar sus tres compromisos.

✓ Sé explicar Sprint Review y Retrospective.

✓ Sé explicar las cláusulas 4-10 de ISO/IEC 20000-1.

✓ Sé explicar qué es un SMS.

✓ Sé explicar cómo pueden coexistir los cuatro marcos.

✓ Soy capaz de resolver un caso sin memorizar literalmente la definición.
```

---

# 🏁 FIN DE LA CORRECCIÓN

## 🧠 LA IDEA QUE DEBES LLEVARTE DEL BLOQUE 06

```text
                    NEXUS
                      │
                      ▼
              ┌───────────────┐
              │   PROYECTO    │
              └───────┬───────┘
                      │
                   PRINCE2
                      │
                      ▼
              ┌───────────────┐
              │   PRODUCTO    │
              └───────┬───────┘
                      │
                    SCRUM
                      │
                      ▼
              ┌───────────────┐
              │    SERVICIO   │
              └───────┬───────┘
                      │
                    ITIL
                      │
                      ▼
              ┌───────────────┐
              │      SMS      │
              └───────┬───────┘
                      │
               ISO/IEC 20000
```

> **Si ves un proyecto → piensa PRINCE2.**
>
> **Si ves desarrollo iterativo de producto → piensa Scrum.**
>
> **Si ves gestión de servicios → piensa ITIL.**
>
> **Si ves requisitos formales de un sistema de gestión de servicios → piensa ISO/IEC 20000.**

# 🏆 BLOQUE 06 · MISIÓN 11 CORREGIDA
