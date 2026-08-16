# 📝 MISIÓN 7 · CORRECCIÓN
## «El plano de la máquina»

> **Bloque:** 5 - Programación  
> **Capítulos:** 5.3 POO + 5.4 UML  
> **Misión:** 7  
> **Objetivo:** Diseñar y modelar una aplicación orientada a objetos mediante UML.

---

# 1. CORRECCIÓN GENERAL

Esta misión no tiene una única solución completamente rígida.

En diseño orientado a objetos puede haber varias soluciones correctas si:

```text
✓ respetan los requisitos
✓ tienen responsabilidades coherentes
✓ mantienen buenas relaciones
✓ justifican las decisiones
✓ no introducen acoplamiento innecesario
```

Por tanto, esta corrección representa una **solución de referencia**.

No es necesario que tu diseño sea idéntico para considerarlo correcto.

---

# 2. PRIMER ERROR A DETECTAR

La tabla de evaluación original sumaba:

```text
110%
```

Debía sumar:

```text
100%
```

Una corrección sencilla es:

| Área | Peso |
|---|---:|
| Identificación de clases | 10% |
| Relaciones y multiplicidades | 15% |
| Herencia / polimorfismo | 10% |
| Encapsulación / responsabilidades | 10% |
| SOLID / diseño | 10% |
| Casos de uso | 10% |
| Diagrama de clases | 10% |
| Diagrama de secuencia | 10% |
| Diagrama de actividades | 5% |
| Justificación del diseño | 10% |
| **TOTAL** | **100%** |

No era necesario utilizar exactamente esta distribución. Lo importante era detectar y corregir el error.

---

# 🧩 3. PARTE I · CLASES

Una solución razonable identifica como mínimo:

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

También podría existir una clase:

```text
Usuario
```

como superclase de:

```text
Empleado
Tecnico
Administrador
```

si se considera apropiado.

---

# 4. CLASE EQUIPO

Una posible definición conceptual:

```text
<<abstract>>
Equipo
-------------------------
id
numeroSerie
marca
modelo
estado
fechaAlta
-------------------------
obtenerInformacionTecnica()
```

Los atributos exactos pueden variar.

La idea fundamental es que:

```text
Equipo
```

contenga aquello que es común a todos los tipos de equipo.

---

# 5. SUBCLASES

Una posible jerarquía:

```text
                 Equipo
                   ▲
       ┌───────────┼───────────┬──────────┬─────────┐
       │           │           │          │         │
   Ordenador    Monitor    Impresora   Router   Telefono
```

Cada subclase incorpora sus características específicas.

Ejemplo:

```text
Ordenador
-------------------------
procesador
ram
almacenamiento
sistemaOperativo
```

```text
Monitor
-------------------------
tamano
resolucion
tipoPanel
```

etc.

---

# 6. ¿DEBE EQUIPO SER ABSTRACTA?

Una buena solución es:

```text
Equipo = abstracta
```

porque conceptualmente representa una categoría general y los objetos concretos son:

```text
Ordenador
Monitor
Impresora
Router
Telefono
```

Pero esto **no es obligatorio**.

También sería válido que `Equipo` fuera una clase concreta si existen equipos genéricos en el dominio.

La decisión debe justificarse.

---

# 👥 7. EMPLEADO

Una posible clase:

```text
Empleado
-------------------------
id
nombre
apellidos
email
-------------------------
consultarEquipos()
crearIncidencia()
consultarIncidencias()
```

No es necesario que todos estos métodos aparezcan literalmente.

Lo importante es que las responsabilidades sean coherentes.

---

# 🏢 8. DEPARTAMENTO

```text
Departamento
-------------------------
id
nombre
-------------------------
consultarEmpleados()
consultarEquipos()
```

De nuevo, los métodos son orientativos.

---

# 🛠️ 9. TÉCNICO

```text
Tecnico
-------------------------
id
nombre
apellidos
email
-------------------------
consultarIncidencias()
asignarIncidencia()
actualizarIncidencia()
cerrarIncidencia()
```

---

# 🚨 10. INCIDENCIA

Una solución posible:

```text
Incidencia
-------------------------
id
titulo
descripcion
fechaCreacion
fechaCierre
estado
prioridad
-------------------------
asignarTecnico()
cambiarEstado()
cerrar()
```

Aquí aparece una cuestión importante:

```text
estado
```

no debería cambiarse arbitrariamente.

La propia clase puede controlar las transiciones válidas.

---

# 🔗 11. RELACIÓN DEPARTAMENTO - EMPLEADO

Los requisitos dicen:

```text
Un departamento puede tener varios empleados.

Cada empleado pertenece a un único departamento.
```

Por tanto:

```text
Departamento 1 ───────── 0..* Empleado
```

Desde el punto de vista conceptual:

```text
1 departamento
→ 0..* empleados

1 empleado
→ 1 departamento
```

---

# 🔗 12. RELACIÓN EMPLEADO - EQUIPO

Los requisitos dicen:

```text
Un empleado puede tener varios equipos.

Un equipo puede no estar asignado.
```

Por tanto:

```text
Empleado 0..1 ───────── 0..* Equipo
```

Interpretación:

```text
1 empleado
→ 0..* equipos

1 equipo
→ 0..1 empleado
```

Esto supone que cada equipo puede estar asignado como máximo a un empleado.

---

# 🔗 13. RELACIÓN EQUIPO - INCIDENCIA

Los requisitos establecen:

```text
Una incidencia pertenece a exactamente un equipo.
```

Pero no se establece un número máximo de incidencias por equipo.

Por tanto, una solución natural:

```text
Equipo 1 ───────── 0..* Incidencia
```

Interpretación:

```text
1 incidencia
→ exactamente 1 equipo

1 equipo
→ 0..* incidencias
```

---

# 🔗 14. RELACIÓN TÉCNICO - INCIDENCIA

Los requisitos dicen:

```text
Una incidencia puede estar sin técnico.

Un técnico puede tener múltiples incidencias.
```

Por tanto:

```text
Tecnico 0..1 ───────── 0..* Incidencia
```

Interpretación:

```text
1 incidencia
→ 0..1 técnico

1 técnico
→ 0..* incidencias
```

---

# 💡 15. ASOCIACIÓN, AGREGACIÓN O COMPOSICIÓN

Aquí lo importante es **no poner diamantes por decorar**.

La solución más conservadora sería modelar las relaciones como:

```text
asociaciones
```

porque el enunciado no establece claramente que una entidad sea propietaria del ciclo de vida de otra.

Por ejemplo:

```text
Departamento ─── Empleado
Empleado ─── Equipo
Equipo ─── Incidencia
Tecnico ─── Incidencia
```

son asociaciones perfectamente válidas.

---

# ⚠️ 16. ¿POR QUÉ NO COMPOSICIÓN?

Una composición implica una relación fuerte de pertenencia/ciclo de vida.

Por ejemplo:

```text
Casa ◆── Habitación
```

Si desaparece la casa, conceptualmente desaparecen sus habitaciones como partes de esa casa.

Pero en nuestro sistema:

```text
Departamento
→ Empleado
```

si eliminamos un departamento, no necesariamente queremos que el empleado deje de existir.

Igualmente:

```text
Equipo
→ Incidencia
```

si un equipo se da de baja, no necesariamente queremos destruir su historial de incidencias.

Por tanto:

```text
asociación
```

es una elección más segura con los requisitos proporcionados.

---

# 🎭 17. HERENCIA

Aquí sí existe una relación clara:

```text
Ordenador IS-A Equipo
Monitor IS-A Equipo
Impresora IS-A Equipo
Router IS-A Equipo
Telefono IS-A Equipo
```

Por tanto:

```text
Equipo
   ▲
   ├── Ordenador
   ├── Monitor
   ├── Impresora
   ├── Router
   └── Telefono
```

---

# 🔄 18. POLIMORFISMO

Podemos definir conceptualmente:

```text
Equipo
    +
obtenerInformacionTecnica()
```

y sobrescribirla:

```text
Ordenador
→ obtenerInformacionTecnica()

Monitor
→ obtenerInformacionTecnica()

Impresora
→ obtenerInformacionTecnica()
```

Entonces:

```text
Equipo equipo;
equipo.obtenerInformacionTecnica();
```

puede producir un comportamiento diferente según el objeto concreto.

Por ejemplo:

```text
Ordenador
→ CPU, RAM, almacenamiento...

Monitor
→ resolución, tamaño...

Impresora
→ tecnología, color...
```

Esto es polimorfismo.

---

# 🔐 19. ENCAPSULACIÓN

El estado de una incidencia no debería ser modificable libremente.

En lugar de:

```text
incidencia.estado = CERRADA
```

podemos tener:

```text
incidencia.cambiarEstado(...)
```

y que el propio objeto compruebe las reglas.

Por ejemplo:

```text
ABIERTA
   ↓
EN_PROGRESO
   ↓
RESUELTA
   ↓
CERRADA
```

Podemos impedir:

```text
ABIERTA
   ↓
CERRADA
```

directamente.

---

# 🧠 20. RESPONSABILIDADES

Una distribución razonable:

| Operación | Responsable |
|---|---|
| registrar equipo | servicio/controlador de gestión de equipos |
| modificar equipo | servicio/controlador de gestión de equipos |
| asignar equipo | servicio de gestión de asignaciones |
| crear incidencia | `Incidencia` + servicio de aplicación |
| cambiar estado | `Incidencia` |
| cerrar incidencia | `Incidencia` |
| consultar incidencias | servicio/repositorio/capa de aplicación |
| generar informe | servicio específico |

### ⚠️ Importante

No conviene meter todo en:

```text
SistemaGestiona
```

porque acabaríamos con una clase gigantesca.

---

# 🧱 21. SRP

El ejemplo:

```text
SistemaGestiona
├── registrarEquipo()
├── eliminarEquipo()
├── enviarEmail()
├── generarPDF()
├── conectarBaseDatos()
├── crearIncidencia()
└── cerrarIncidencia()
```

viola claramente el espíritu de:

```text
SRP
```

porque tiene demasiadas responsabilidades diferentes.

Podríamos separar:

```text
EquipoService
IncidenciaService
EmailService
PdfService
Repositorio
```

etc.

---

# 🔓 22. OCP

Supongamos que añadimos:

```text
Servidor
```

Si nuestro sistema está diseñado correctamente con una abstracción:

```text
Equipo
```

podemos añadir:

```text
Servidor extends Equipo
```

sin tener que modificar toda la lógica existente.

Esto encaja con:

```text
Open/Closed Principle
```

---

# 🧭 23. DIP

Una implementación mejor diseñada evitaría que las clases de alto nivel dependan directamente de implementaciones concretas.

Por ejemplo:

```text
IncidenciaService
       ↓
   Repositorio
```

podría depender de:

```text
EquipoRepositoryInterface
```

en lugar de:

```text
MySQLEquipoRepository
```

directamente.

Esto facilita:

```text
testing
cambio de implementación
mantenimiento
```

---

# 📐 24. CASOS DE USO

Actores:

```text
Administrador
Empleado
Tecnico
```

Casos de uso posibles:

```text
Gestionar equipos
Registrar equipo
Modificar equipo
Dar de baja equipo
Asignar equipo
Retirar equipo
Consultar equipos

Registrar incidencia
Consultar incidencia
Asignar técnico
Cambiar estado
Cerrar incidencia
```

---

# 🔗 25. INCLUDE

Un buen ejemplo sería:

```text
Registrar incidencia
        │
        │ <<include>>
        ↓
   Validar equipo
```

¿Por qué?

Porque para registrar correctamente una incidencia:

```text
hay que validar que el equipo existe
```

y esa comprobación forma parte obligatoria del proceso.

---

# 🔗 26. EXTEND

Un ejemplo razonable:

```text
Consultar equipo
        ▲
        │ <<extend>>
        │
Consultar historial de incidencias
```

La consulta del historial puede considerarse un comportamiento adicional que se realiza bajo una determinada condición/opción.

Otra modelización equivalente puede ser válida si se justifica correctamente.

---

# ⚠️ 27. INCLUDE VS EXTEND

Recordatorio:

```text
include
→ comportamiento reutilizado y obligatorio

extend
→ comportamiento adicional/opcional/condicionado
```

No debemos escoger uno u otro simplemente porque:

```text
"include es flecha"
"extend es otra flecha"
```

La diferencia es semántica.

---

# 📊 28. DIAGRAMA DE CLASES · REFERENCIA

Una representación simplificada:

```text
                         <<abstract>>
                            Equipo
                   ┌──────────┴──────────┐
                   │                     │
             ┌─────┴─────┐          ┌────┴─────┐
             │           │          │          │
        Ordenador     Monitor   Impresora    Router

                              └──── Telefono

Departamento 1 ───────── 0..* Empleado

Empleado 0..1 ───────── 0..* Equipo

Equipo 1 ────────────── 0..* Incidencia

Tecnico 0..1 ────────── 0..* Incidencia
```

El diagrama real debería representar también:

```text
atributos
métodos
visibilidad
```

según el nivel de detalle que hayas decidido.

---

# 🎬 29. DIAGRAMA DE SECUENCIA · REGISTRAR INCIDENCIA

Una solución conceptual:

```text
Empleado        Sistema       Equipo       Incidencia
   │               │             │              │
   │ registrar()   │             │              │
   ├──────────────>│             │              │
   │               │ buscar()    │              │
   │               ├────────────>│              │
   │               │             │              │
   │               │<────────────┤              │
   │               │             │              │
   │               │ crear()     │              │
   │               ├───────────────────────────>│
   │               │             │              │
   │               │             │       estado=ABIERTA
   │               │<───────────────────────────┤
   │<──────────────┤             │              │
   │ confirmación  │             │              │
```

---

# 🔀 30. FRAGMENTO `alt`

Debe existir una alternativa:

```text
              ┌──────────── alt ────────────┐
              │                             │
              │ [equipo existe]             │
Empleado ───> Sistema ───> crear incidencia │
              │                             │
              ├─────────────────────────────┤
              │                             │
              │ [equipo no existe]          │
Empleado ───> Sistema ───> devolver error   │
              │                             │
              └─────────────────────────────┘
```

Esto representa dos caminos alternativos.

---

# 🔄 31. DIAGRAMA DE ACTIVIDADES

Una solución posible:

```text
        ●
        │
        ▼
Consultar incidencia
        │
        ▼
   ¿Existe?
    /     \
  NO       SÍ
  │         │
  ▼         ▼
 Error    Asignar técnico
  │         │
  │         ▼
  │      Trabajar
  │         │
  │         ▼
  │     ¿Resuelta?
  │       /    \
  │     NO      SÍ
  │     │        │
  │     └───┐    ▼
  │         │  Cerrar
  │         │    │
  └─────────┴────┘
             │
             ▼
             ◎
```

---

# ⚡ 32. FORK / JOIN

No es necesario utilizar `fork/join` en este flujo.

De hecho, sería incorrecto introducir concurrencia artificial solamente para demostrar que conocemos el símbolo.

`fork/join` tendría sentido si existieran actividades realmente concurrentes.

Por ejemplo:

```text
Incidencia resuelta
       │
      fork
     /    \
Enviar    Actualizar
email     inventario
     \    /
      join
       │
       ▼
      Fin
```

Aquí sí existe una justificación.

---

# 🔍 33. REVISIÓN DEL DISEÑO

## ¿Hay una clase con demasiadas responsabilidades?

Si tenemos:

```text
SistemaGestiona
```

haciendo:

```text
PDF
email
BD
equipos
incidencias
```

sí.

Debe dividirse.

---

## ¿Existe alguna clase que debería heredar de Equipo?

Sí:

```text
Ordenador
Monitor
Impresora
Router
Telefono
```

---

## ¿Existe alguna herencia que debería ser composición?

No necesariamente.

No debemos crear herencia simplemente porque exista reutilización.

---

## ¿Existe acoplamiento innecesario?

Puede aparecer si:

```text
Incidencia
→ conoce directamente MySQL
```

Mejor:

```text
Incidencia
→ dominio

Repositorio/servicio
→ persistencia
```

---

# 🧠 34. EXTENSIBILIDAD

Añadir:

```text
Servidor
```

debería ser relativamente sencillo:

```text
Servidor extends Equipo
```

con:

```text
cpu
ram
almacenamiento
sistemaOperativo
numeroMaquinasVirtuales
```

Puede sobrescribir:

```text
obtenerInformacionTecnica()
```

si procede.

---

# 🏆 35. RESPUESTA AL DESAFÍO FINAL

Una respuesta completa:

### 1. Clase

```text
Servidor
```

### 2. Herencia

```text
Servidor extends Equipo
```

### 3. Atributos heredados

Por ejemplo:

```text
id
numeroSerie
marca
modelo
estado
fechaAlta
```

### 4. Propios

```text
cpu
ram
almacenamiento
sistemaOperativo
numeroMaquinasVirtuales
```

### 5. Métodos sobrescribibles

```text
obtenerInformacionTecnica()
```

### 6. UML

Añadir:

```text
Servidor
```

como nueva especialización de:

```text
Equipo
```

### 7. SOLID

Especialmente:

```text
OCP
```

porque queremos poder extender el sistema mediante nuevas especializaciones sin tener que modificar constantemente el código existente.

---

# ⭐ 36. NIVEL EXTRA · PERSISTENCIA

Una posible correspondencia:

```text
Departamento
→ departamentos

Empleado
→ empleados

Equipo
→ equipos

Incidencia
→ incidencias
```

Y para los tipos especializados podríamos utilizar diferentes estrategias de persistencia.

Por ejemplo:

```text
equipos
+
tipo
+
atributos específicos
```

o tablas especializadas:

```text
equipos
ordenadores
monitores
impresoras
routers
telefonos
```

La elección dependería de la estrategia de modelado y de las necesidades del sistema.

---

# 📊 37. ERRORES TÍPICOS QUE DEBERÍAS BUSCAR EN TU SOLUCIÓN

## Error 1

Crear:

```text
Ordenador
Monitor
Impresora
Router
Telefono
```

sin una abstracción común cuando claramente comparten concepto.

---

## Error 2

Hacer:

```text
Equipo
→ Incidencia
```

como composición sin justificar el ciclo de vida.

---

## Error 3

Confundir:

```text
include
```

con:

```text
extend
```

---

## Error 4

Crear una clase:

```text
SistemaGestiona
```

que haga absolutamente todo.

---

## Error 5

No indicar multiplicidades.

---

## Error 6

Confundir:

```text
IS-A
```

con:

```text
HAS-A
```

---

## Error 7

Usar herencia solamente para reutilizar código.

---

## Error 8

Permitir:

```text
ABIERTA → CERRADA
```

ignorando la regla de negocio.

---

## Error 9

Introducir `fork/join` sin que exista concurrencia real.

---

## Error 10

Hacer que el dominio conozca directamente:

```text
MySQL
PDF
SMTP
HTTP
```

sin una razón arquitectónica clara.

---

# 🧮 38. CRITERIOS DE CORRECCIÓN

La misión puede evaluarse así:

| Área | Peso |
|---|---:|
| Identificación de clases | 10% |
| Relaciones y multiplicidades | 15% |
| Herencia / polimorfismo | 10% |
| Encapsulación / responsabilidades | 10% |
| SOLID / diseño | 10% |
| Casos de uso | 10% |
| Diagrama de clases | 10% |
| Diagrama de secuencia | 10% |
| Diagrama de actividades | 5% |
| Justificación del diseño | 10% |
| **TOTAL** | **100%** |

### Interpretación

```text
90-100
→ Excelente dominio

75-89
→ Muy buen dominio

60-74
→ Aprobado, pero existen conceptos que revisar

50-59
→ Bastantes lagunas

<50
→ Conviene repasar POO/UML antes de continuar
```

---

# 🧠 39. QUÉ DEBERÍAS SER CAPAZ DE EXPLICAR SIN APUNTES

Al terminar esta misión deberías poder responder oralmente:

```text
¿Qué es una clase?

¿Qué es un objeto?

¿Qué diferencia hay entre encapsulación y abstracción?

¿Qué es polimorfismo?

¿Qué significa IS-A?

¿Qué significa HAS-A?

¿Qué diferencia hay entre asociación,
agregación y composición?

¿Qué es una multiplicidad?

¿Qué diferencia hay entre include y extend?

¿Qué representa un actor?

¿Qué representa un caso de uso?

¿Qué representa un diagrama de clases?

¿Qué representa un diagrama de secuencia?

¿Qué hace alt?

¿Qué hacen fork y join?

¿Qué significa SRP?

¿Qué significa OCP?

¿Por qué buscamos bajo acoplamiento?

¿Por qué buscamos alta cohesión?
```

Si puedes responderlas sin mirar el temario, esta misión ha hecho su trabajo.

---

# 🏁 40. CONCLUSIÓN

La idea central de esta misión es:

```text
POO
↓
pensar en objetos
↓
responsabilidades
↓
relaciones
↓
UML
↓
representar el diseño
```

No se trata de aprender a dibujar cajas y flechas.

Se trata de ser capaz de pasar de:

```text
"Necesito una aplicación para gestionar equipos"
```

a:

```text
"Estas son sus entidades,
estas son sus responsabilidades,
estas son sus relaciones,
estas son sus reglas,
y este es un modelo que otro programador
puede utilizar para construirla."
```

---

# 🏁 FIN DE LA CORRECCIÓN · MISIÓN 7
