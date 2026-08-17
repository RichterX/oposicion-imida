<!-- encabezado-homogeneizado -->
# Bloque 05 - PLANTILLA Y CORRECCION
> **Bloque:** Bloque 05  
> **Documento:** Plantilla y correccion  
> **Preguntas de referencia:** 70  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# BLOQUE 5A - PLANTILLA Y CORRECCIÓN: PYTHON

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.1 - Python  
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

La puntuación se calcula mediante:

```text
Puntuación = aciertos - (errores × 0,33)
Porcentaje de aciertos = (aciertos / 70) × 100
```

---

# 🔑 2. PLANTILLA DE RESPUESTAS

| Nº | Correcta | Tu respuesta | Nº | Correcta | Tu respuesta | Nº | Correcta | Tu respuesta | Nº | Correcta | Tu respuesta |
|---:|:---:|:---:|---:|:---:|:---:|---:|:---:|:---:|---:|:---:|:---:|
| 1 | B | | 19 | A | | 37 | D | | 55 | D | |
| 2 | A | | 20 | B | | 38 | B | | 56 | B | |
| 3 | C | | 21 | C | | 39 | A | | 57 | A | |
| 4 | D | | 22 | D | | 40 | C | | 58 | C | |
| 5 | A | | 23 | A | | 41 | B | | 59 | B | |
| 6 | B | | 24 | B | | 42 | D | | 60 | A | |
| 7 | C | | 25 | C | | 43 | A | | 61 | D | |
| 8 | D | | 26 | A | | 44 | C | | 62 | B | |
| 9 | A | | 27 | D | | 45 | B | | 63 | C | |
| 10 | B | | 28 | B | | 46 | A | | 64 | A | |
| 11 | C | | 29 | A | | 47 | D | | 65 | B | |
| 12 | A | | 30 | C | | 48 | B | | 66 | D | |
| 13 | D | | 31 | B | | 49 | C | | 67 | C | |
| 14 | B | | 32 | D | | 50 | A | | 68 | A | |
| 15 | A | | 33 | A | | 51 | D | | 69 | B | |
| 16 | C | | 34 | B | | 52 | B | | 70 | D | |
| 17 | B | | 35 | C | | 53 | C | | | | |
| 18 | D | | 36 | A | | 54 | A | | | | |

---

# 📊 3. DIAGNÓSTICO POR ÁREAS

| Preguntas | Área | Aciertos |
|:---:|---|:---:|
| 1-12 | Fundamentos y control de flujo | /12 |
| 13-28 | Colecciones y funciones | /16 |
| 29-40 | Excepciones, módulos y archivos | /12 |
| 41-55 | POO, iteración y Python avanzado | /15 |
| 56-70 | Ecosistema, calidad y lectura de código | /15 |

Referencia orientativa:

- **60-70:** dominio muy sólido.
- **49-59:** buen nivel; conviene revisar los fallos concretos.
- **35-48:** base funcional con lagunas relevantes.
- **0-34:** recomendable repasar el capítulo 5.1 antes de repetirlo.

---

# 🧠 4. CORRECCIÓN RAZONADA

### Pregunta 1 · **B**

En Python el tipo pertenece al objeto, no al nombre. Un mismo nombre puede enlazarse durante la ejecución con objetos de tipos diferentes.

### Pregunta 2 · **A**

`//` realiza división entera o división suelo. Para operandos positivos, `7 // 2` produce `3`.

### Pregunta 3 · **C**

Las colecciones vacías son *falsy*. Por ello, `bool([])` es `False`.

### Pregunta 4 · **D**

`is` compara identidad; `==` compara igualdad de valores según la implementación del tipo.

### Pregunta 5 · **A**

Python permite encadenar comparaciones. La expresión equivale a `1 < x and x < 10`, que es verdadera para `x = 5`.

### Pregunta 6 · **B**

`range()` incluye el inicio y excluye el límite final. Partiendo de 2 y sumando 3 se obtienen 2, 5 y 8.

### Pregunta 7 · **C**

El `else` de un bucle se ejecuta cuando este termina normalmente. Una salida mediante `break` lo omite.

### Pregunta 8 · **D**

`continue` descarta las instrucciones restantes de la iteración actual y comienza la siguiente.

### Pregunta 9 · **A**

`range(3)` genera 0, 1 y 2. El argumento `end=" "` evita el salto de línea entre impresiones.

### Pregunta 10 · **B**

`enumerate()` produce pares índice-elemento. Con `start=1`, los índices son 1 y 2.

### Pregunta 11 · **C**

Por defecto, `zip()` termina cuando se agota el iterable más corto; no rellena los valores ausentes.

### Pregunta 12 · **A**

La expresión está entre corchetes, calcula `x ** 2` y filtra los valores cuyo resto al dividir por 2 es cero.

### Pregunta 13 · **D**

Una lista conserva el orden, es mutable y permite valores repetidos. Un conjunto elimina duplicados y una tupla no es mutable.

### Pregunta 14 · **B**

El *slice* comienza en el índice 1 y excluye el índice 3, por lo que contiene 20 y 30.

### Pregunta 15 · **A**

`append(iterable)` añade el iterable como un solo elemento; `extend(iterable)` añade uno a uno sus elementos.

### Pregunta 16 · **C**

Sin índice, `pop()` elimina y devuelve el último elemento. `remove()` busca por valor y no devuelve el elemento.

### Pregunta 17 · **B**

No puede reemplazarse un elemento de una tupla, pero uno de sus elementos sí puede ser, por ejemplo, una lista mutable.

### Pregunta 18 · **D**

`&` obtiene los elementos comunes. `|` es unión, `-` diferencia y `^` diferencia simétrica.

### Pregunta 19 · **A**

El acceso directo mediante corchetes requiere que la clave exista; de lo contrario se produce `KeyError`.

### Pregunta 20 · **B**

`dict.get(clave)` devuelve `None`, o el valor predeterminado indicado, cuando la clave no existe.

### Pregunta 21 · **C**

`lista` y `copia` apuntan al mismo objeto mutable. La modificación realizada mediante cualquiera de los nombres es visible desde el otro.

### Pregunta 22 · **D**

`sorted()` acepta un iterable y devuelve una lista nueva. `list.sort()` ordena la lista *in place* y devuelve `None`.

### Pregunta 23 · **A**

Toda función devuelve un valor. Si no se ejecuta un `return` con expresión, ese valor es `None`.

### Pregunta 24 · **B**

`*args` empaqueta los argumentos posicionales adicionales en una tupla dentro de la función.

### Pregunta 25 · **C**

`**kwargs` empaqueta los argumentos nombrados adicionales en un diccionario.

### Pregunta 26 · **A**

LEGB significa Local, Enclosing, Global y Built-in; ese es el orden de búsqueda de nombres.

### Pregunta 27 · **D**

`nonlocal` permite reasignar un nombre del ámbito de una función envolvente. No se refiere al ámbito global.

### Pregunta 28 · **B**

Una función `lambda` puede recibir varios argumentos, pero su cuerpo sintáctico se limita a una expresión.

### Pregunta 29 · **A**

El `else` asociado a `try` se ejecuta si el bloque `try` termina sin lanzar una excepción.

### Pregunta 30 · **C**

`finally` se reserva para limpieza y se ejecuta normalmente tanto si hubo excepción como si no, incluso ante muchos cambios de flujo.

### Pregunta 31 · **B**

Python utiliza `raise` para lanzar explícitamente una instancia o clase de excepción.

### Pregunta 32 · **D**

Las excepciones específicas deben capturarse antes que sus clases base; de otro modo, el bloque general las interceptaría primero.

### Pregunta 33 · **A**

Cuando el archivo actúa como programa principal, Python asigna `"__main__"` a `__name__`.

### Pregunta 34 · **B**

Un módulo es, en el caso habitual, un archivo `.py` cuyo código y nombres pueden importarse.

### Pregunta 35 · **C**

Un entorno virtual mantiene un conjunto de paquetes separado para evitar conflictos de versiones entre proyectos.

### Pregunta 36 · **A**

El gestor de contexto se encarga de cerrar el archivo al abandonar el bloque, incluso si se produce una excepción.

### Pregunta 37 · **D**

El modo `a` abre para escritura al final. Si el archivo no existe, normalmente lo crea.

### Pregunta 38 · **B**

El modo `w` crea el archivo o, si ya existe, elimina su contenido antes de comenzar la escritura.

### Pregunta 39 · **A**

`Path.exists()` devuelve un booleano que indica si la ruta representada existe.

### Pregunta 40 · **C**

`json.dump(objeto, archivo)` serializa hacia un archivo; `json.dumps(objeto)` devuelve el JSON como `str`.

### Pregunta 41 · **B**

Tras crear la instancia, `__init__` inicializa normalmente sus atributos. Técnicamente no es el método que crea el objeto.

### Pregunta 42 · **D**

`self` es el parámetro convencional que recibe la instancia. El nombre es convencional, aunque usarlo es la práctica universal.

### Pregunta 43 · **A**

`super()` crea un proxy que permite continuar la resolución de métodos conforme al MRO, útil también en herencia múltiple cooperativa.

### Pregunta 44 · **C**

`@property` permite acceder a un método sin paréntesis, como un atributo gestionado.

### Pregunta 45 · **B**

`__str__` proporciona la representación informal y legible. `__repr__` se orienta a una representación inequívoca o de depuración.

### Pregunta 46 · **A**

Un iterable puede entregar un iterador mediante `iter()`. El iterador mantiene el estado y entrega valores mediante `next()`.

### Pregunta 47 · **D**

Cuando ya no quedan elementos, `next()` provoca `StopIteration`; un bucle `for` gestiona internamente esa señal.

### Pregunta 48 · **B**

La presencia de `yield` hace que la llamada devuelva un generador. Cada iteración reanuda la ejecución desde el punto suspendido.

### Pregunta 49 · **C**

Una expresión generadora calcula cada elemento bajo demanda, lo que puede reducir mucho el uso de memoria.

### Pregunta 50 · **A**

Un decorador recibe el objeto decorado y devuelve el objeto que ocupará su lugar, normalmente una función envolvente.

### Pregunta 51 · **D**

`wraps` copia metadatos como `__name__` y `__doc__` a la función envolvente y establece `__wrapped__`.

### Pregunta 52 · **B**

Las anotaciones ayudan a herramientas, documentación y lectores. El intérprete no valida por defecto que los valores respeten esos tipos.

### Pregunta 53 · **C**

`Optional[int]` equivale conceptualmente a `int | None`; no significa que el argumento tenga valor predeterminado.

### Pregunta 54 · **A**

`@dataclass` puede generar `__init__`, `__repr__` y comparaciones a partir de los campos, según sus opciones.

### Pregunta 55 · **D**

Python 3.10 incorporó `match` y `case` para comparar la estructura de valores, no solo su igualdad simple.

### Pregunta 56 · **B**

`numpy.ndarray` es el array homogéneo multidimensional sobre el que se construye gran parte de NumPy.

### Pregunta 57 · **A**

`shape` es una tupla con la longitud de cada eje. `size` indica el total de elementos y `dtype` el tipo almacenado.

### Pregunta 58 · **C**

`DataFrame` representa datos tabulares bidimensionales con filas y columnas etiquetadas.

### Pregunta 59 · **B**

Requests proporciona una API de alto nivel para realizar solicitudes HTTP y trabajar con sus respuestas.

### Pregunta 60 · **A**

BeautifulSoup construye una estructura navegable a partir de HTML o XML y facilita localizar y extraer elementos.

### Pregunta 61 · **D**

En la interfaz `pyplot`, `plt.show()` presenta las figuras creadas.

### Pregunta 62 · **B**

PEP 8 reúne convenciones de formato y estilo destinadas a favorecer código Python legible y consistente.

### Pregunta 63 · **C**

El valor predeterminado mutable se crea una sola vez al definir la función. Las dos llamadas reutilizan la misma lista.

### Pregunta 64 · **A**

El índice `-1` se refiere al último elemento de una secuencia no vacía, que es 3.

### Pregunta 65 · **B**

El paso `-1` recorre la cadena de derecha a izquierda y produce `"nohtyp"`.

### Pregunta 66 · **D**

La copia superficial contiene los mismos valores, así que `==` es verdadero, pero es otro objeto y `is` es falso.

### Pregunta 67 · **C**

`int()` no interpreta directamente una cadena con notación decimal. Sería necesario convertir primero con `float()` si esa fuera la intención.

### Pregunta 68 · **A**

`filter()` conserva los elementos para los que el predicado devuelve un valor verdadero: los números pares 2 y 4.

### Pregunta 69 · **B**

La división lanza `ZeroDivisionError`, que captura el `except`. El bloque `else` no se ejecuta.

### Pregunta 70 · **D**

Un generador evita materializar toda la secuencia y mantiene en memoria solo el estado necesario para producir el siguiente elemento.

---

# ✅ CIERRE DE LA REVISIÓN

Anota para cada fallo si se debió a desconocimiento, confusión entre conceptos próximos o lectura apresurada de código. Repite únicamente las áreas por debajo del 70 % antes de volver a realizar el simulacro completo.
