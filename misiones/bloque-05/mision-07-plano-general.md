# 🧩 MISIÓN 7 · EL PLANO DE LA MÁQUINA

> **Bloque:** 5 - Programación  
> **Capítulos:** 5.3 POO + 5.4 UML  
> **Tipo:** Misión práctica  
> **Dificultad:** 🟢 → 🟠  
> **Objetivo:** Diseñar y modelar una aplicación antes de programarla.

---

# 🎯 1. OBJETIVO DE LA MISIÓN

Hasta ahora has estudiado:

```text
Programación Orientada a Objetos
+
UML
```

Ahora toca demostrar que sabes utilizarlos juntos.

La misión consiste en diseñar, desde cero, el modelo de una aplicación.

No queremos todavía construirla.

Primero debemos responder:

> **¿Qué objetos existen, qué responsabilidades tienen y cómo se relacionan?**

La misión tendrá dos grandes productos:

```text
PRODUCTO 1
→ modelo orientado a objetos

PRODUCTO 2
→ modelos UML que representen ese diseño
```

---

# 📖 2. EL ESCENARIO

Una organización quiere crear una plataforma llamada:

# 🏢 **GESTIONA**

La aplicación permitirá gestionar los recursos tecnológicos de una organización.

Actualmente, la organización tiene un inventario descontrolado de:

```text
ordenadores
monitores
impresoras
routers
teléfonos
```

Los equipos están repartidos entre diferentes departamentos y empleados.

La organización quiere saber:

```text
qué equipos existen
dónde están
quién los utiliza
qué departamento los posee
qué estado tienen
qué incidencias han sufrido
```

Además, cuando un equipo deja de funcionar, debe poder registrarse una incidencia y asignarla a un técnico.

---

# 🧑‍💼 3. ACTORES DEL SISTEMA

De momento conocemos estos actores:

## Administrador

Puede:

```text
gestionar usuarios
gestionar departamentos
registrar equipos
asignar equipos
consultar inventario
```

---

## Empleado

Puede:

```text
consultar sus equipos asignados
consultar información de un equipo
crear incidencias sobre sus equipos
consultar sus incidencias
```

---

## Técnico

Puede:

```text
consultar incidencias
asumir incidencias
actualizar incidencias
cerrar incidencias
```

---

# 📦 4. REQUISITOS FUNCIONALES

El sistema debe permitir:

### RF01

Registrar un equipo.

### RF02

Modificar los datos de un equipo.

### RF03

Dar de baja un equipo.

### RF04

Asignar un equipo a un empleado.

### RF05

Retirar un equipo de un empleado.

### RF06

Consultar los equipos de un departamento.

### RF07

Consultar los equipos asignados a un empleado.

### RF08

Registrar una incidencia.

### RF09

Asignar una incidencia a un técnico.

### RF10

Cambiar el estado de una incidencia.

### RF11

Consultar el historial de incidencias de un equipo.

### RF12

Cerrar una incidencia.

---

# 🧱 5. TIPOS DE EQUIPO

El sistema debe distinguir al menos:

```text
Ordenador
Monitor
Impresora
Router
Teléfono
```

Todos son:

```text
Equipo
```

Pero cada tipo puede tener características específicas.

Por ejemplo:

### Ordenador

```text
procesador
memoria RAM
almacenamiento
sistema operativo
```

### Monitor

```text
tamaño
resolución
tipo de panel
```

### Impresora

```text
tecnología
color
conectividad
```

### Router

```text
número de puertos
velocidad
wifi
```

### Teléfono

```text
modelo
sistema operativo
número
```

---

# 👥 6. EMPLEADOS

Cada empleado tendrá como mínimo:

```text
id
nombre
apellidos
email
```

Además, pertenece a un departamento.

---

# 🏢 7. DEPARTAMENTOS

Cada departamento tendrá:

```text
id
nombre
```

Un departamento puede tener:

```text
muchos empleados
```

pero cada empleado pertenece a:

```text
un departamento
```

---

# 🛠️ 8. INCIDENCIAS

Una incidencia tendrá:

```text
id
título
descripción
fecha de creación
fecha de cierre
estado
prioridad
```

Estados posibles:

```text
ABIERTA
EN_PROGRESO
RESUELTA
CERRADA
```

Prioridades:

```text
BAJA
MEDIA
ALTA
CRÍTICA
```

Una incidencia:

```text
pertenece a un equipo
```

y puede:

```text
ser asignada a un técnico
```

---

# 🔗 9. REGLAS DE NEGOCIO

Aquí empieza la parte importante.

## RN01

Un empleado pertenece a un único departamento.

## RN02

Un departamento puede tener varios empleados.

## RN03

Un equipo puede estar asignado a un empleado.

## RN04

Un empleado puede tener varios equipos.

## RN05

Un equipo puede no estar asignado a ningún empleado.

## RN06

Una incidencia pertenece a exactamente un equipo.

## RN07

Una incidencia puede estar sin técnico asignado.

## RN08

Un técnico puede tener múltiples incidencias asignadas.

## RN09

Una incidencia cerrada debe tener fecha de cierre.

## RN10

Una incidencia no puede pasar directamente de:

```text
ABIERTA
```

a:

```text
CERRADA
```

Debe pasar previamente por:

```text
EN_PROGRESO
```

o:

```text
RESUELTA
```

---

# 🧠 10. PARTE I · IDENTIFICAR LAS CLASES

Tu primera tarea consiste en identificar las clases principales.

Como mínimo deberían aparecer conceptos equivalentes a:

```text
???
???
???
???
???
???
```

### Tu misión

Determina:

1. Qué clases necesita el sistema.
2. Qué clases son abstractas, si consideras que alguna debe serlo.
3. Qué atributos tiene cada clase.
4. Qué métodos/responsabilidades debería tener cada clase.

---

# 🧪 11. PARTE II · ENCONTRAR HERENCIA

Recuerda:

```text
IS-A
```

Tenemos:

```text
Ordenador IS-A Equipo
Monitor IS-A Equipo
Impresora IS-A Equipo
Router IS-A Equipo
Teléfono IS-A Equipo
```

### Tu misión

Determina:

```text
¿Debe existir una clase Equipo?

¿Debe ser abstracta?

¿Qué atributos deberían estar en Equipo?

¿Qué atributos deberían estar solamente
en cada subtipo?
```

---

# 🔗 12. PARTE III · RELACIONES

Ahora debes identificar las relaciones.

Piensa especialmente en:

```text
Departamento
Empleado

Empleado
Equipo

Equipo
Incidencia

Técnico
Incidencia
```

Para cada relación indica:

```text
tipo de relación
multiplicidad
navegabilidad, si procede
```

---

# 🧠 13. PREGUNTA CLAVE

Compara:

```text
Departamento
→ Empleado
```

con:

```text
Equipo
→ Incidencia
```

¿Son exactamente el mismo tipo de relación?

No respondas simplemente:

```text
"ambas tienen muchos"
```

Analiza:

```text
¿es composición?
¿agregación?
¿asociación?
¿qué multiplicidades existen?
```

---

# 🧩 14. PARTE IV · COMPOSICIÓN O AGREGACIÓN

Debes decidir si alguna relación debe modelarse como:

```text
composición
```

o:

```text
agregación
```

o simplemente:

```text
asociación
```

### Justifica cada decisión.

No buscamos solamente que dibujes un diamante.

Queremos saber:

> **¿Por qué existe esa relación y qué implica para el ciclo de vida de los objetos?**

---

# 🎭 15. PARTE V · POLIMORFISMO

Tenemos:

```text
Equipo
├── Ordenador
├── Monitor
├── Impresora
├── Router
└── Teléfono
```

Imagina que necesitamos una operación:

```text
obtenerInformacionTecnica()
```

Cada tipo de equipo puede proporcionar información diferente.

### Tu misión

Explica cómo aplicarías:

```text
herencia
+
polimorfismo
```

para resolverlo.

No necesitas escribir código completo.

Puedes utilizar pseudocódigo.

---

# 🧱 16. PARTE VI · ENCAPSULACIÓN

Supongamos que una incidencia tiene:

```text
estado
```

No queremos permitir que cualquier parte del programa haga:

```text
incidencia.estado = CERRADA
```

sin comprobar las reglas del negocio.

### Tu misión

Explica cómo aplicarías encapsulación para impedir cambios de estado inválidos.

Piensa en:

```text
atributos
métodos
visibilidad
reglas de negocio
```

---

# 🧠 17. PARTE VII · RESPONSABILIDADES

Ahora analiza estas posibles responsabilidades:

```text
registrarEquipo()
asignarEquipo()
crearIncidencia()
cerrarIncidencia()
cambiarEstado()
generarInforme()
```

Indica:

```text
¿qué clase debería ser responsable de cada operación?
```

Y explica brevemente por qué.

---

# 🧪 18. PARTE VIII · SOLID

Analiza este supuesto:

```text
class SistemaGestiona
{
    registrarEquipo()
    eliminarEquipo()
    enviarEmail()
    generarPDF()
    conectarBaseDatos()
    crearIncidencia()
    cerrarIncidencia()
}
```

### Pregunta

¿Qué principio o principios de diseño podrían estar siendo incumplidos?

Piensa especialmente en:

```text
SRP
OCP
DIP
```

Explica qué problema observas.

---

# 📐 19. PARTE IX · DIAGRAMA DE CASOS DE USO

Ahora pasamos a UML.

Debes crear un:

```text
DIAGRAMA DE CASOS DE USO
```

Incluye como mínimo:

```text
Administrador
Empleado
Técnico
```

Y casos de uso equivalentes a:

```text
Gestionar equipos
Asignar equipo
Consultar equipos
Registrar incidencia
Gestionar incidencia
Cerrar incidencia
```

---

# 🔗 20. INCLUDE VS EXTEND

Busca al menos:

```text
1 relación <<include>>
1 relación <<extend>>
```

entre los casos de uso.

### ⚠️

No los coloques simplemente porque "hay que poner alguno".

Debes explicar:

```text
¿Por qué es include?

¿Por qué es extend?
```

---

# 📐 21. PARTE X · DIAGRAMA DE CLASES

Ahora construye el:

```text
DIAGRAMA DE CLASES
```

Debe mostrar:

```text
clases
atributos
métodos
herencia
asociaciones
multiplicidades
```

Como mínimo:

```text
Equipo
Ordenador
Monitor
Impresora
Router
Telefono
Empleado
Departamento
Tecnico
Incidencia
```

---

# 🔢 22. MULTIPLICIDADES

No olvides indicar las multiplicidades.

Por ejemplo:

```text
Departamento 1 ─────── 0..* Empleado
```

Pero debes determinar tú las demás.

Utiliza notación UML:

```text
1
0..1
*
0..*
1..*
```

---

# 📐 23. PARTE XI · DIAGRAMA DE SECUENCIA

Ahora vamos a representar una operación concreta:

# «Registrar una incidencia»

El escenario:

```text
Empleado
    ↓
Sistema
    ↓
Equipo
    ↓
Incidencia
```

Construye un diagrama de secuencia que represente:

```text
1. El empleado solicita registrar una incidencia.
2. El sistema comprueba que el equipo existe.
3. El sistema crea la incidencia.
4. La incidencia queda en estado ABIERTA.
5. El sistema devuelve confirmación.
```

---

# 🎭 24. ALTERNATIVA

Añade una alternativa:

```text
alt
```

para representar:

```text
Equipo existe
```

frente a:

```text
Equipo no existe
```

---

# 🧪 25. PARTE XII · DIAGRAMA DE ACTIVIDADES

Representa el proceso:

```text
Gestionar una incidencia
```

Debe incluir al menos:

```text
inicio
↓
consultar incidencia
↓
¿existe?
├── NO → error
└── SÍ
      ↓
   asignar técnico
      ↓
   trabajar incidencia
      ↓
   ¿resuelta?
   ├── NO → continuar
   └── SÍ
         ↓
       cerrar
         ↓
        fin
```

Utiliza correctamente:

```text
decisiones
flujos
```

y, si procede:

```text
fork / join
```

---

# 🧠 26. PARTE XIII · REVISIÓN DEL DISEÑO

Ahora debes revisar tu propio diseño.

Responde:

### 1.

¿Existe alguna clase que tenga demasiadas responsabilidades?

### 2.

¿Existe alguna relación que debería ser herencia?

### 3.

¿Existe alguna herencia que realmente debería ser composición?

### 4.

¿Hay acoplamiento innecesario?

### 5.

¿Las clases tienen responsabilidades coherentes?

### 6.

¿Se podría extender el sistema fácilmente para añadir:

```text
Tablet
Servidor
SmartTV
```

sin modificar demasiado código?

---

# 🏆 27. DESAFÍO FINAL

Imagina que mañana la organización pide:

> «Queremos añadir un nuevo tipo de equipo llamado Servidor.»

Debe tener:

```text
CPU
RAM
almacenamiento
sistema operativo
número de máquinas virtuales
```

### Tu misión

Explica:

```text
1. Qué clase crearías.
2. De qué clase heredaría.
3. Qué atributos heredaría.
4. Qué atributos propios tendría.
5. Qué métodos podría sobrescribir.
6. Qué cambios serían necesarios en UML.
7. Qué principio SOLID te ayuda a minimizar modificaciones.
```

---

# ⭐ 28. NIVEL EXTRA · PERSISTENCIA

Si quieres subir la dificultad:

Imagina que los objetos deben persistirse en una base de datos.

Propón qué entidades/tablas necesitarías:

```text
empleados
departamentos
equipos
incidencias
...
```

No es necesario diseñar SQL.

Solo:

```text
entidad
→ tabla
→ relación
```

---

# 🧠 29. CHECKLIST DE LA MISIÓN

Antes de dar la misión por terminada comprueba:

```text
□ He identificado las clases principales.

□ He identificado atributos.

□ He identificado responsabilidades.

□ He identificado herencia.

□ He explicado IS-A.

□ He identificado asociaciones.

□ He determinado multiplicidades.

□ He analizado composición/agregación.

□ He aplicado encapsulación.

□ He explicado polimorfismo.

□ He detectado problemas SOLID.

□ He creado un diagrama de casos de uso.

□ He utilizado include correctamente.

□ He utilizado extend correctamente.

□ He creado un diagrama de clases.

□ He incluido multiplicidades.

□ He creado un diagrama de secuencia.

□ He utilizado alt.

□ He creado un diagrama de actividades.

□ He revisado cohesión y acoplamiento.

□ He pensado cómo ampliar el sistema.
```

---

# 🏅 30. CRITERIOS DE EVALUACIÓN

La misión no se evalúa únicamente por:

```text
"el diagrama está bonito"
```

Se valorará:

| Área | Peso |
|---|---:|
| Identificación de clases | 15% |
| Relaciones y multiplicidades | 15% |
| Herencia / polimorfismo | 15% |
| Encapsulación / responsabilidades | 10% |
| SOLID / diseño | 10% |
| Casos de uso | 10% |
| Diagrama de clases | 10% |
| Diagrama de secuencia | 10% |
| Diagrama de actividades | 5% |
| Justificación del diseño | 10% |
| **TOTAL** | **110%** |

### ⚠️ Corrección

La tabla anterior suma 110% deliberadamente por error de diseño. 😈

Tu primera tarea antes de empezar la misión es:

> **Detectar el fallo y corregir la ponderación para que sume exactamente 100%.**

No es una pregunta de UML.

Es una pequeña prueba de que estás despierto.

---

# 🧭 31. ENTREGA

Puedes realizar la misión en:

```text
Markdown
```

y utilizar:

```text
Mermaid
PlantUML
draw.io
Lucidchart
papel
```

para los diagramas.

Si utilizas Markdown + Mermaid, puedes mantener todo dentro del repositorio.

---

# 🎁 32. BONIFICACIÓN

Si quieres completar la misión como si fuera un pequeño proyecto real, crea una estructura:

```text
mission-07/
│
├── README.md
│
├── analysis/
│   └── requirements.md
│
├── uml/
│   ├── use-cases.md
│   ├── class-diagram.md
│   ├── sequence.md
│   └── activity.md
│
└── design/
    └── decisions.md
```

En:

```text
decisions.md
```

explica las decisiones de diseño más importantes.

---

# 🏁 33. FINAL DE LA MISIÓN

Al terminar deberías poder mirar tu trabajo y responder:

> **¿Podría otro programador empezar a construir GESTIONA a partir de mi diseño?**

Si la respuesta es:

```text
SÍ
```

entonces la misión ha cumplido su objetivo.

---

# 🔓 PRÓXIMA MISIÓN

## Misión 8 · «La interfaz»

Después de diseñar:

```text
POO + UML
```

utilizaremos ese mismo sistema para construir su interfaz con:

```text
HTML
+
CSS
```

La misión será práctica y visual.

---

# 🏁 FIN DE MISIÓN 7
