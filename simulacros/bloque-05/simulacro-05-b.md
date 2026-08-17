<!-- encabezado-homogeneizado -->
# Bloque 05 - SIMULACRO
> **Bloque:** Bloque 05  
> **Documento:** Simulacro  
> **Preguntas de referencia:** 70  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# BLOQUE 5B - SIMULACRO TIPO TEST: JAVA

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.2 - Java (partes 1 a 6)  
> **Formato:** Tipo test  
> **Preguntas:** 70  
> **Opciones:** 4 por pregunta  
> **Respuestas correctas:** 1 por pregunta  
> **Nivel:** ⭐⭐⭐⭐⭐  
> **Tiempo recomendado:** 90 minutos  
> **Puntuación recomendada:** +1 por acierto, 0 en blanco, -0,33 por error

---

# 📋 INSTRUCCIONES

- Marca una única respuesta (`A`, `B`, `C` o `D`) por pregunta.
- No consultes el manual durante el examen.
- Puedes dejar preguntas en blanco y volver a ellas al final.
- En las preguntas de código, presupón una versión moderna de Java y una ejecución independiente.

---

# 🧮 HOJA DE RESPUESTAS

| Nº | Resp. | Nº | Resp. | Nº | Resp. | Nº | Resp. | Nº | Resp. |
|---:|:---:|---:|:---:|---:|:---:|---:|:---:|---:|:---:|
| 1 | | 15 | | 29 | | 43 | | 57 | |
| 2 | | 16 | | 30 | | 44 | | 58 | |
| 3 | | 17 | | 31 | | 45 | | 59 | |
| 4 | | 18 | | 32 | | 46 | | 60 | |
| 5 | | 19 | | 33 | | 47 | | 61 | |
| 6 | | 20 | | 34 | | 48 | | 62 | |
| 7 | | 21 | | 35 | | 49 | | 63 | |
| 8 | | 22 | | 36 | | 50 | | 64 | |
| 9 | | 23 | | 37 | | 51 | | 65 | |
| 10 | | 24 | | 38 | | 52 | | 66 | |
| 11 | | 25 | | 39 | | 53 | | 67 | |
| 12 | | 26 | | 40 | | 54 | | 68 | |
| 13 | | 27 | | 41 | | 55 | | 69 | |
| 14 | | 28 | | 42 | | 56 | | 70 | |

---

# ☕ PREGUNTAS

## Fundamentos, sintaxis y control de flujo

### Pregunta 1

¿Cuál es la función principal de la JVM?

**A.** Editar código fuente Java  
**B.** Ejecutar bytecode Java y abstraer la plataforma subyacente  
**C.** Sustituir al sistema operativo  
**D.** Gestionar exclusivamente bases de datos

### Pregunta 2

¿Qué incluye el JDK que lo diferencia conceptualmente del entorno necesario solo para ejecutar?

**A.** Solo el recolector de basura  
**B.** Únicamente la biblioteca `java.lang`  
**C.** Un servidor web obligatorio  
**D.** Herramientas de desarrollo como el compilador `javac`

### Pregunta 3

¿Qué genera normalmente `javac Programa.java`?

**A.** Código fuente Python  
**B.** Un ejecutable nativo idéntico para todos los procesadores  
**C.** Bytecode en uno o varios archivos `.class`  
**D.** Un archivo `.jar` firmado automáticamente

### Pregunta 4

¿Cuál es el punto de entrada habitual de una aplicación Java?

**A.** `public void start()`  
**B.** `static int main()`  
**C.** `public Main()`  
**D.** `public static void main(String[] args)`

### Pregunta 5

¿Cuál de los siguientes es un tipo primitivo?

**A.** `Integer`  
**B.** `String`  
**C.** `int`  
**D.** `BigDecimal`

### Pregunta 6

¿Qué ocurre con una variable local si se intenta leer antes de inicializarla?

**A.** Toma siempre el valor cero  
**B.** Se produce un error de compilación  
**C.** Toma el valor `null`  
**D.** La JVM elige un valor aleatorio

### Pregunta 7

¿Qué resultado produce la división entera `7 / 2`?

**A.** `3.5`  
**B.** `4`  
**C.** `3`  
**D.** Lanza `ArithmeticException`

### Pregunta 8

¿Qué operador lógico realiza cortocircuito?

**A.** `&` exclusivamente  
**B.** `&&`  
**C.** `!`  
**D.** `^`

### Pregunta 9

¿Qué imprime este código?

```java
int x = 5;
System.out.println(x++);
```

**A.** `5`  
**B.** `6`  
**C.** `4`  
**D.** No compila

### Pregunta 10

¿Qué afirmación sobre `switch` moderno es correcta?

**A.** Solo admite valores `boolean`  
**B.** Puede utilizar sintaxis de expresión y producir un valor  
**C.** Obliga siempre a usar `break` con `case ->`  
**D.** Solo admite dos casos

### Pregunta 11

¿Qué bucle garantiza al menos una ejecución de su cuerpo?

**A.** `do-while`  
**B.** `while`  
**C.** `for`  
**D.** `for-each`

### Pregunta 12

En un array Java, ¿qué representa `array.length`?

**A.** Un método que cambia el tamaño  
**B.** El último índice válido  
**C.** La memoria ocupada en bytes  
**D.** El número de elementos del array

## Clases, encapsulación, herencia y polimorfismo

### Pregunta 13

¿Qué describe mejor a un constructor?

**A.** Tiene el nombre de la clase y no declara tipo de retorno  
**B.** Debe devolver la instancia con `return`  
**C.** Solo puede ser `private`  
**D.** Se hereda como cualquier método

### Pregunta 14

¿Qué referencia representa el objeto actual dentro de un método de instancia?

**A.** `super`  
**B.** `current`  
**C.** `self`  
**D.** `this`

### Pregunta 15

¿Qué modificador restringe un miembro a la propia clase?

**A.** `public`  
**B.** `protected`  
**C.** `private`  
**D.** Sin modificador

### Pregunta 16

Un miembro declarado `static` pertenece principalmente:

**A.** A cada objeto con una copia independiente obligatoria  
**B.** Al constructor más reciente  
**C.** Al paquete  
**D.** A la clase

### Pregunta 17

¿Qué implica `final` aplicado a una variable de referencia?

**A.** La referencia pasa a ser `static`  
**B.** El objeto se vuelve profundamente inmutable  
**C.** La referencia no puede reasignarse, aunque el objeto podría seguir siendo mutable  
**D.** La variable puede reasignarse una vez por método

### Pregunta 18

¿Qué palabra clave establece herencia entre clases?

**A.** `implements`  
**B.** `extends`  
**C.** `inherits`  
**D.** `super`

### Pregunta 19

¿Qué permite `super(...)` en un constructor?

**A.** Invocar cualquier método privado de la clase hija  
**B.** Crear una interfaz  
**C.** Invocar un constructor de la superclase  
**D.** Evitar la inicialización heredada

### Pregunta 20

¿Qué requisito define la sobrescritura de un método?

**A.** Mismo nombre pero parámetros necesariamente distintos  
**B.** Una subclase proporciona una implementación compatible del método heredado  
**C.** Cambio obligatorio del tipo de retorno  
**D.** Método siempre `static`

### Pregunta 21

¿Qué anotación ayuda al compilador a comprobar que se pretende sobrescribir?

**A.** `@Override`  
**B.** `@Overload`  
**C.** `@InheritedMethod`  
**D.** `@Replace`

### Pregunta 22

¿Qué es la sobrecarga de métodos?

**A.** Repetir exactamente la misma firma en la misma clase  
**B.** Usar el mismo nombre con listas de parámetros diferentes  
**C.** Sobrescribir un método final  
**D.** Ejecutar un método en varios hilos

### Pregunta 23

¿Qué demuestra el polimorfismo dinámico?

**A.** Una referencia de supertipo puede invocar la implementación sobrescrita del subtipo  
**B.** Los métodos `static` se resuelven por el objeto  
**C.** Una variable solo puede apuntar a su tipo exacto  
**D.** Todo *cast* es seguro

### Pregunta 24

¿Cuál es una propiedad de una clase abstracta?

**A.** No puede contener métodos implementados  
**B.** Debe ser `final`  
**C.** Solo puede tener miembros `static`  
**D.** No puede instanciarse directamente

## Interfaces, lambdas y colecciones

### Pregunta 25

¿Qué palabra clave usa una clase para adoptar una interfaz?

**A.** `implements`  
**B.** `extends` obligatoriamente  
**C.** `interface`  
**D.** `uses`

### Pregunta 26

¿Qué permite un método `default` en una interfaz?

**A.** Ser privado y abstracto simultáneamente  
**B.** Evitar que la interfaz se implemente  
**C.** Modificar campos de instancia de la interfaz  
**D.** Aportar una implementación heredable

### Pregunta 27

Una interfaz funcional tiene:

**A.** Exactamente un método total, contando los de `Object`  
**B.** Solo métodos `static`  
**C.** Un único método abstracto funcional  
**D.** Obligatoriamente la anotación `@FunctionalInterface` para compilar

### Pregunta 28

¿Qué interfaz funcional representa una operación que recibe un valor y devuelve un `boolean`?

**A.** `Supplier<T>`  
**B.** `Consumer<T>`  
**C.** `Function<T, R>`  
**D.** `Predicate<T>`

### Pregunta 29

¿Qué caracteriza a una expresión lambda?

**A.** No puede capturar variables locales  
**B.** Declara una nueva clase pública en archivo propio  
**C.** Proporciona una implementación para el método de una interfaz funcional  
**D.** Solo puede usarse con hilos

### Pregunta 30

¿Qué restricción se aplica a una variable local capturada por una lambda?

**A.** Debe ser `static`  
**B.** Debe ser final o efectivamente final  
**C.** Debe valer `null`  
**D.** Debe ser un tipo primitivo

### Pregunta 31

¿Qué propiedad define a `List`?

**A.** Prohíbe duplicados siempre  
**B.** No conserva posición  
**C.** Es una colección ordenada por posición que admite duplicados  
**D.** Asocia obligatoriamente claves con valores

### Pregunta 32

¿Qué implementación suele ofrecer acceso posicional eficiente?

**A.** `LinkedHashSet`  
**B.** `ArrayList`  
**C.** `ArrayDeque`  
**D.** `TreeMap`

### Pregunta 33

¿Qué característica básica tiene un `Set`?

**A.** No admite elementos duplicados según su criterio de igualdad  
**B.** Mantiene cada elemento con una clave separada  
**C.** Solo almacena números  
**D.** Garantiza siempre orden natural

### Pregunta 34

¿Qué implementación de `Set` mantiene normalmente el orden de inserción?

**A.** `HashSet`  
**B.** `LinkedHashSet`  
**C.** `TreeSet`  
**D.** `EnumMap`

### Pregunta 35

¿Qué estructura almacena asociaciones clave-valor?

**A.** `Map`  
**B.** `Set`  
**C.** `Queue`  
**D.** `Iterator`

### Pregunta 36

¿Cuál es la forma segura de eliminar elementos durante una iteración explícita?

**A.** Llamar siempre a `coleccion.clear()`  
**B.** Crear un hilo por elemento  
**C.** Modificar directamente la colección en un `for-each`  
**D.** Usar `Iterator.remove()` cuando el iterador lo soporte

## Excepciones, genéricos, Stream y Optional

### Pregunta 37

¿Qué distingue a una *checked exception*?

**A.** El compilador exige capturarla o declararla  
**B.** Hereda necesariamente de `RuntimeException`  
**C.** Nunca puede capturarse  
**D.** Solo aparece al compilar

### Pregunta 38

¿Qué cláusula declara que un método puede propagar una excepción?

**A.** `throw`  
**B.** `finally`  
**C.** `catch`  
**D.** `throws`

### Pregunta 39

¿Qué instrucción lanza una excepción concreta?

**A.** `throws new`  
**B.** `raise`  
**C.** `throw`  
**D.** `exception`

### Pregunta 40

¿Qué ventaja ofrece *try-with-resources*?

**A.** Convierte excepciones checked en unchecked  
**B.** Evita declarar recursos  
**C.** Ejecuta cada recurso en un hilo distinto  
**D.** Cierra automáticamente recursos compatibles con `AutoCloseable`

### Pregunta 41

¿Qué efecto tiene la inferencia *multi-catch* `catch (A | B e)`?

**A.** Vuelve opcional el bloque `try`  
**B.** Captura simultáneamente dos objetos de excepción  
**C.** Un mismo bloque maneja excepciones alternativas no relacionadas por subtipado directo  
**D.** Solo funciona con `RuntimeException`

### Pregunta 42

¿Qué problema resuelven principalmente los genéricos?

**A.** Ejecución paralela automática  
**B.** Seguridad de tipos reutilizable y reducción de conversiones explícitas  
**C.** Serialización obligatoria  
**D.** Herencia múltiple de clases

### Pregunta 43

¿Qué expresa `List<? extends Number>`?

**A.** Una lista que acepta añadir cualquier `Number`  
**B.** Solo una `List<Number>` exacta  
**C.** Una lista de algún tipo desconocido que es `Number` o subtipo  
**D.** Una lista de supertipos de `Number`

### Pregunta 44

Según PECS, si una estructura consume valores de tipo `Integer`, suele ser apropiado:

**A.** `? extends Integer`  
**B.** `? super Integer`  
**C.** `? implements Integer`  
**D.** `? equals Integer`

### Pregunta 45

¿Qué caracteriza a las operaciones intermedias de un `Stream`?

**A.** Son normalmente perezosas y devuelven otro stream  
**B.** Cierran siempre el programa  
**C.** Producen obligatoriamente un número  
**D.** Modifican siempre la colección origen

### Pregunta 46

¿Cuál es una operación terminal de Stream?

**A.** `filter()`  
**B.** `collect()`  
**C.** `map()`  
**D.** `distinct()`

### Pregunta 47

¿Qué hace `flatMap()`?

**A.** Transforma elementos en streams y aplana sus resultados  
**B.** Elimina el tipado genérico  
**C.** Ordena siempre en sentido descendente  
**D.** Convierte un stream en paralelo obligatoriamente

### Pregunta 48

¿Cuál es el propósito de `Optional<T>`?

**A.** Sustituir todas las excepciones  
**B.** Almacenar varios valores  
**C.** Hacer mutable una constante  
**D.** Representar explícitamente la posible presencia o ausencia de un valor

## Cadenas, fechas, regex, NIO y serialización

### Pregunta 49

¿Qué afirmación sobre `String` es correcta?

**A.** Es inmutable  
**B.** Cada concatenación modifica el mismo objeto  
**C.** Es un tipo primitivo  
**D.** No implementa `equals()`

### Pregunta 50

Para concatenaciones repetidas en un único hilo, suele preferirse:

**A.** `StringBuffer` en todos los casos  
**B.** `IntegerBuilder`  
**C.** Un array de `char` inmutable  
**D.** `StringBuilder`

### Pregunta 51

¿Qué diferencia principal presenta `StringBuffer` frente a `StringBuilder`?

**A.** `StringBuffer` es inmutable  
**B.** `StringBuilder` solo admite números  
**C.** `StringBuffer` sincroniza sus operaciones principales  
**D.** `StringBuffer` no permite `append()`

### Pregunta 52

Para objetos, ¿qué compara `==`?

**A.** Siempre el contenido textual  
**B.** El resultado de `hashCode()`  
**C.** El orden natural  
**D.** La identidad de las referencias

### Pregunta 53

¿Qué es *autoboxing*?

**A.** Reserva manual de memoria  
**B.** Serialización automática de objetos  
**C.** Conversión automática de un primitivo a su clase wrapper  
**D.** Conversión de cualquier objeto a `String`

### Pregunta 54

¿Qué clase representa una fecha sin hora ni zona?

**A.** `Instant`  
**B.** `LocalDate`  
**C.** `Duration`  
**D.** `ZonedDateTime`

### Pregunta 55

¿Qué representa `Instant`?

**A.** Un formato de fecha localizado  
**B.** Una cantidad en meses y años  
**C.** Un punto en la línea temporal  
**D.** Una zona horaria sin fecha

### Pregunta 56

En expresiones regulares, `Matcher.matches()` intenta:

**A.** Encontrar solo la primera letra  
**B.** Hacer coincidir la región completa con el patrón  
**C.** Compilar el patrón  
**D.** Reemplazar todas las coincidencias

### Pregunta 57

¿Qué representa `Path` en NIO.2?

**A.** Una ruta abstracta a un archivo o directorio  
**B.** Un flujo de bytes ya abierto  
**C.** Un hilo de entrada/salida  
**D.** Un archivo serializado en memoria

### Pregunta 58

¿Qué método de `Files` lee todas las líneas de un archivo de texto en una lista?

**A.** `Files.linesToList()`  
**B.** `Files.readAllLines()`  
**C.** `Files.openLines()`  
**D.** `Files.scan()`

### Pregunta 59

¿Qué indica `transient` en un campo durante la serialización estándar?

**A.** Que el campo no debe formar parte del estado serializado por defecto  
**B.** Que el campo se guarda dos veces  
**C.** Que el campo es siempre público  
**D.** Que el campo es una constante de compilación

## Concurrencia, reflexión y módulos

### Pregunta 60

¿Qué ventaja ofrece implementar `Runnable` frente a extender `Thread`?

**A.** Garantiza ausencia de condiciones de carrera  
**B.** Devuelve directamente un resultado genérico  
**C.** Ejecuta sin necesidad de hilo  
**D.** Separa la tarea del mecanismo de ejecución y deja libre la herencia de clase

### Pregunta 61

¿Qué aporta `Callable<V>` frente a `Runnable`?

**A.** Puede devolver un valor y lanzar excepciones comprobadas  
**B.** Es siempre síncrono  
**C.** No puede ejecutarse en un executor  
**D.** Impide cancelar la tarea

### Pregunta 62

¿Qué representa habitualmente un `Future<V>`?

**A.** Un hilo que nunca comienza  
**B.** Una colección concurrente  
**C.** Un bloqueo intrínseco  
**D.** El resultado pendiente de una tarea asíncrona

### Pregunta 63

¿Qué responsabilidad tiene `ExecutorService`?

**A.** Compilar clases en paralelo  
**B.** Serializar tareas  
**C.** Gestionar la ejecución de tareas, normalmente mediante un conjunto de hilos  
**D.** Sustituir todos los bloqueos

### Pregunta 64

¿Qué garantiza un bloque `synchronized` respecto al mismo monitor?

**A.** Que todos los hilos ejecuten el bloque a la vez  
**B.** Que no pueda producirse ningún deadlock en el programa  
**C.** Que la operación sea distribuida entre máquinas  
**D.** Exclusión mutua y efectos de visibilidad asociados al monitor

### Pregunta 65

¿Qué garantiza principalmente `volatile` sobre un campo?

**A.** Inmutabilidad profunda  
**B.** Atomicidad de cualquier incremento  
**C.** Visibilidad de sus escrituras entre hilos, pero no atomicidad de operaciones compuestas  
**D.** Ausencia absoluta de bloqueos

### Pregunta 66

¿Qué es una condición de carrera?

**A.** Una tarea que siempre termina primero  
**B.** Un resultado que depende de la intercalación no controlada de accesos concurrentes  
**C.** Una excepción obligatoria de la JVM  
**D.** Un algoritmo de ordenación

### Pregunta 67

¿Qué caracteriza a un *deadlock*?

**A.** Un hilo finaliza antes de tiempo  
**B.** Dos tareas leen datos inmutables  
**C.** Varios hilos esperan indefinidamente recursos retenidos entre sí  
**D.** Un executor rechaza una tarea tras cerrarse

### Pregunta 68

¿Qué facilita `CompletableFuture`?

**A.** Solo bloquear mediante `get()`  
**B.** Componer etapas asíncronas y gestionar sus resultados  
**C.** Acceder a campos privados sin reflexión  
**D.** Declarar módulos

### Pregunta 69

¿Qué permite la reflexión?

**A.** Inspeccionar y, con las restricciones aplicables, manipular clases y miembros en ejecución  
**B.** Eliminar el tipado estático del lenguaje  
**C.** Evitar cargar clases  
**D.** Compilar sin JDK

### Pregunta 70

¿Qué descriptor declara un módulo Java explícito?

**A.** `package-info.java`  
**B.** `module-info.java`  
**C.** `manifest.java`  
**D.** `classpath-info.java`

---

# 🏁 FIN DEL SIMULACRO

Revisa las preguntas en blanco antes de consultar la plantilla y la corrección.
