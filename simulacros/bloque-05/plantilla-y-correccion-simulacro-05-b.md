# BLOQUE 5B - PLANTILLA Y CORRECCIÓN: JAVA

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.2 - Java  
> **Simulacro:** 70 preguntas  
> **Puntuación:** +1 acierto · 0 en blanco · -0,33 error

---

# 📋 1. DATOS DEL EXAMEN

```text
Fecha:
Tiempo empleado:
Aciertos:
Errores:
En blanco:
Puntuación:
Porcentaje de aciertos:
```

```text
Puntuación = aciertos - (errores × 0,33)
Porcentaje de aciertos = (aciertos / 70) × 100
```

---

# 🔑 2. PLANTILLA DE RESPUESTAS

| Nº | Correcta | Tu respuesta | Nº | Correcta | Tu respuesta | Nº | Correcta | Tu respuesta | Nº | Correcta | Tu respuesta |
|---:|:---:|:---:|---:|:---:|:---:|---:|:---:|:---:|---:|:---:|:---:|
| 1 | B | | 19 | C | | 37 | A | | 55 | C | |
| 2 | D | | 20 | B | | 38 | D | | 56 | B | |
| 3 | C | | 21 | A | | 39 | C | | 57 | A | |
| 4 | D | | 22 | B | | 40 | D | | 58 | B | |
| 5 | C | | 23 | A | | 41 | C | | 59 | A | |
| 6 | B | | 24 | D | | 42 | B | | 60 | D | |
| 7 | C | | 25 | A | | 43 | C | | 61 | A | |
| 8 | B | | 26 | D | | 44 | B | | 62 | D | |
| 9 | A | | 27 | C | | 45 | A | | 63 | C | |
| 10 | B | | 28 | D | | 46 | B | | 64 | D | |
| 11 | A | | 29 | C | | 47 | A | | 65 | C | |
| 12 | D | | 30 | B | | 48 | D | | 66 | B | |
| 13 | A | | 31 | C | | 49 | A | | 67 | C | |
| 14 | D | | 32 | B | | 50 | D | | 68 | B | |
| 15 | C | | 33 | A | | 51 | C | | 69 | A | |
| 16 | D | | 34 | B | | 52 | D | | 70 | B | |
| 17 | C | | 35 | A | | 53 | C | | | | |
| 18 | B | | 36 | D | | 54 | B | | | | |

---

# 📊 3. DIAGNÓSTICO POR ÁREAS

| Preguntas | Área | Aciertos |
|:---:|---|:---:|
| 1-12 | Fundamentos, sintaxis y control | /12 |
| 13-24 | POO, encapsulación y herencia | /12 |
| 25-36 | Interfaces, lambdas y colecciones | /12 |
| 37-48 | Excepciones, genéricos, Stream y Optional | /12 |
| 49-59 | Cadenas, fechas, regex, NIO y serialización | /11 |
| 60-70 | Concurrencia, reflexión y módulos | /11 |

Referencia orientativa:

- **60-70:** dominio muy sólido.
- **49-59:** buen nivel; conviene revisar los fallos concretos.
- **35-48:** base funcional con lagunas relevantes.
- **0-34:** recomendable repasar el capítulo 5.2 antes de repetirlo.

---

# 🧠 4. CORRECCIÓN RAZONADA

### Pregunta 1 · **B**

La JVM carga y ejecuta bytecode, aportando una capa común sobre sistemas y arquitecturas compatibles.

### Pregunta 2 · **D**

El JDK incorpora herramientas de desarrollo, entre ellas `javac`, además de los componentes necesarios para ejecutar aplicaciones.

### Pregunta 3 · **C**

`javac` compila el fuente a bytecode almacenado normalmente en archivos `.class`, que después ejecuta la JVM.

### Pregunta 4 · **D**

La JVM busca el método `public static void main(String[] args)` como punto de entrada convencional de una aplicación.

### Pregunta 5 · **C**

`int` es uno de los ocho tipos primitivos. `Integer`, `String` y `BigDecimal` son clases.

### Pregunta 6 · **B**

Las variables locales no reciben un valor predeterminado utilizable; el análisis de asignación definida impide leerlas sin inicializar.

### Pregunta 7 · **C**

Ambos operandos son enteros, por lo que la parte fraccionaria se descarta y el resultado es 3.

### Pregunta 8 · **B**

`&&` no evalúa el operando derecho cuando el izquierdo ya es falso. `&` evalúa ambos operandos booleanos.

### Pregunta 9 · **A**

El postincremento devuelve primero el valor 5 y después incrementa `x` a 6.

### Pregunta 10 · **B**

Las expresiones `switch` modernas pueden asignar o devolver un resultado y la sintaxis `case ... ->` evita la caída accidental.

### Pregunta 11 · **A**

`do-while` evalúa su condición después del cuerpo, de modo que este se ejecuta al menos una vez.

### Pregunta 12 · **D**

`length` es un campo de los arrays y contiene su número de posiciones; no es un método ni el último índice.

### Pregunta 13 · **A**

Un constructor comparte nombre con la clase y no declara tipo de retorno, ni siquiera `void`.

### Pregunta 14 · **D**

`this` referencia la instancia actual y permite, por ejemplo, distinguir campos de parámetros con el mismo nombre.

### Pregunta 15 · **C**

Un miembro `private` solo es accesible directamente desde el cuerpo de la clase que lo declara.

### Pregunta 16 · **D**

Los miembros `static` están asociados a la clase y se comparten, en lugar de formar parte independiente de cada instancia.

### Pregunta 17 · **C**

`final` impide cambiar la referencia tras asignarla, pero no congela el estado interno del objeto referenciado.

### Pregunta 18 · **B**

Una clase hereda de otra mediante `extends`. Una clase implementa interfaces mediante `implements`.

### Pregunta 19 · **C**

`super(...)` invoca un constructor de la clase padre y debe ser la primera instrucción explícita del constructor.

### Pregunta 20 · **B**

Hay sobrescritura cuando el subtipo proporciona una implementación con firma y retorno compatibles para un método heredado.

### Pregunta 21 · **A**

`@Override` hace que el compilador avise si el método no sobrescribe realmente, evitando errores de firma.

### Pregunta 22 · **B**

La sobrecarga reúne métodos del mismo nombre cuyas listas de parámetros difieren. No depende solo del tipo de retorno.

### Pregunta 23 · **A**

El método de instancia sobrescrito se selecciona según el tipo real del objeto, aunque la referencia tenga un supertipo.

### Pregunta 24 · **D**

Una clase abstracta no se instancia directamente, pero puede tener estado, constructores y métodos tanto abstractos como implementados.

### Pregunta 25 · **A**

Una clase declara las interfaces que adopta tras `implements`; puede implementar más de una.

### Pregunta 26 · **D**

Un método `default` aporta una implementación en la interfaz y facilita evolucionar contratos sin romper todas sus implementaciones.

### Pregunta 27 · **C**

Una interfaz funcional posee un solo método abstracto funcional; puede contener métodos `default` y `static` adicionales.

### Pregunta 28 · **D**

`Predicate<T>` recibe un `T` y devuelve un booleano, por ejemplo para filtrar un stream.

### Pregunta 29 · **C**

Una lambda implementa el único método abstracto de una interfaz funcional sin declarar una clase anónima de forma explícita.

### Pregunta 30 · **B**

La variable local capturada no puede reasignarse: debe ser `final` o mantenerse efectivamente final.

### Pregunta 31 · **C**

`List` conserva una posición para cada elemento y admite repetidos. `Map` es quien relaciona claves y valores.

### Pregunta 32 · **B**

`ArrayList` se apoya en un array redimensionable y permite acceso por índice normalmente en tiempo constante.

### Pregunta 33 · **A**

Un `Set` evita duplicados conforme a igualdad y ordenación, según la implementación; no todos garantizan orden.

### Pregunta 34 · **B**

`LinkedHashSet` combina unicidad con orden de inserción predecible. `HashSet` no promete ese orden.

### Pregunta 35 · **A**

`Map<K,V>` asocia claves únicas con valores. No hereda de `Collection`.

### Pregunta 36 · **D**

Tras obtener un elemento con el iterador, `Iterator.remove()` coordina la eliminación con el estado de iteración cuando está soportado.

### Pregunta 37 · **A**

Las excepciones checked deben capturarse o figurar en `throws`; las subclases de `RuntimeException` son unchecked.

### Pregunta 38 · **D**

`throws` forma parte de la declaración del método. `throw` es la instrucción que lanza una excepción concreta.

### Pregunta 39 · **C**

`throw new MiExcepcion()` lanza el objeto de excepción. `throws` solo declara posibles propagaciones.

### Pregunta 40 · **D**

Los recursos declarados en *try-with-resources* se cierran automáticamente en orden inverso al finalizar el bloque.

### Pregunta 41 · **C**

*Multi-catch* comparte un manejador para tipos alternativos; las alternativas no pueden tener una relación de subtipo redundante.

### Pregunta 42 · **B**

Los genéricos permiten expresar restricciones de tipos en compilación y reducen errores y conversiones manuales.

### Pregunta 43 · **C**

El tipo concreto es desconocido, pero está acotado superiormente por `Number`. Es seguro leer como `Number`, no añadir cualquier número.

### Pregunta 44 · **B**

PECS resume *Producer Extends, Consumer Super*. Para introducir `Integer`, `? super Integer` es la cota adecuada.

### Pregunta 45 · **A**

Operaciones como `filter()` y `map()` construyen perezosamente una tubería y no trabajan hasta una operación terminal.

### Pregunta 46 · **B**

`collect()` consume el stream y materializa un resultado. `filter()`, `map()` y `distinct()` son intermedias.

### Pregunta 47 · **A**

`flatMap()` aplica una función que produce streams y combina sus elementos en un único flujo plano.

### Pregunta 48 · **D**

`Optional` modela cero o un valor y ofrece operaciones explícitas para transformarlo, filtrarlo o proporcionar alternativas.

### Pregunta 49 · **A**

Un `String` no cambia tras crearse. Operaciones como concatenar generan un nuevo objeto o resultado.

### Pregunta 50 · **D**

`StringBuilder` es mutable y evita crear numerosas cadenas intermedias; en un solo hilo no necesita la sincronización de `StringBuffer`.

### Pregunta 51 · **C**

`StringBuffer` sincroniza sus métodos principales. Esa seguridad tiene un coste y no suele ser necesaria en uso local a un hilo.

### Pregunta 52 · **D**

Entre referencias, `==` comprueba si apuntan al mismo objeto. `equals()` expresa igualdad lógica cuando la clase la implementa.

### Pregunta 53 · **C**

El autoboxing permite convertir implícitamente, por ejemplo, un `int` en un `Integer`; el unboxing realiza el camino inverso.

### Pregunta 54 · **B**

`LocalDate` contiene año, mes y día sin hora ni zona. `Instant` representa un punto temporal global.

### Pregunta 55 · **C**

`Instant` representa un instante en la línea temporal con relación al origen UTC, con precisión de segundos y nanosegundos.

### Pregunta 56 · **B**

`matches()` exige que toda la región coincida. `find()` busca la siguiente subsecuencia coincidente.

### Pregunta 57 · **A**

`Path` modela una ruta de forma abstracta; las operaciones reales de lectura, copia o borrado suelen realizarse mediante `Files`.

### Pregunta 58 · **B**

`Files.readAllLines(path)` carga las líneas en una lista. Para lectura perezosa existe `Files.lines(path)`.

### Pregunta 59 · **A**

Un campo `transient` se excluye del mecanismo de serialización estándar por defecto y recupera su valor predeterminado al deserializar.

### Pregunta 60 · **D**

`Runnable` representa la tarea separadamente del hilo que la ejecuta y permite que la clase extienda otra superclase.

### Pregunta 61 · **A**

`Callable<V>.call()` devuelve un `V` y puede declarar excepciones checked; `Runnable.run()` devuelve `void`.

### Pregunta 62 · **D**

Un `Future` es un manejador del resultado pendiente: permite consultar finalización, cancelar y obtener el valor, posiblemente bloqueando.

### Pregunta 63 · **C**

`ExecutorService` desacopla envío y ejecución, administra hilos y ofrece un ciclo de cierre controlado.

### Pregunta 64 · **D**

Solo un hilo puede poseer un monitor dado, y liberar/adquirir ese monitor establece relaciones de visibilidad de memoria.

### Pregunta 65 · **C**

`volatile` hace visibles las escrituras y limita reordenamientos, pero `contador++` sigue siendo una operación compuesta no atómica.

### Pregunta 66 · **B**

Existe carrera cuando accesos concurrentes sin coordinación hacen que el resultado dependa del orden impredecible de ejecución.

### Pregunta 67 · **C**

En un deadlock, cada hilo espera un recurso que otro miembro del ciclo retiene, de modo que ninguno puede avanzar.

### Pregunta 68 · **B**

`CompletableFuture` permite encadenar, combinar y manejar errores de etapas asíncronas sin reducir todo el diseño a llamadas bloqueantes.

### Pregunta 69 · **A**

La API de reflexión inspecciona clases, constructores, métodos, campos y anotaciones durante la ejecución, sujeta a acceso y módulos.

### Pregunta 70 · **B**

`module-info.java` declara el nombre del módulo y directivas como `requires`, `exports`, `opens`, `uses` y `provides`.

---

# ✅ CIERRE DE LA REVISIÓN

Clasifica cada fallo como desconocimiento, confusión conceptual o lectura apresurada. Repasa las áreas por debajo del 70 % y vuelve a realizar el simulacro sin consultar esta clave.