<!-- encabezado-homogeneizado -->
# Bloque 05 - SIMULACRO
> **Bloque:** Bloque 05  
> **Documento:** Simulacro  
> **Preguntas de referencia:** 70  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# BLOQUE 5A - SIMULACRO TIPO TEST: PYTHON

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.1 - Python (partes 1 a 12)  
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
- En las preguntas de código, presupón Python 3 y una ejecución independiente.

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

# 🐍 PREGUNTAS

## Fundamentos, tipos y control de flujo

### Pregunta 1

¿Qué afirmación describe mejor el tipado dinámico de Python?

**A.** Las variables deben declarar su tipo antes de usarse  
**B.** El tipo pertenece al objeto y un nombre puede referenciar objetos de tipos distintos  
**C.** Python convierte siempre tipos incompatibles automáticamente  
**D.** Los tipos solo se comprueban al instalar el intérprete

### Pregunta 2

¿Cuál es el resultado de `7 // 2`?

**A.** `3`  
**B.** `3.5`  
**C.** `4`  
**D.** `1`

### Pregunta 3

¿Qué valor produce `bool([])`?

**A.** `None`  
**B.** `True`  
**C.** `False`  
**D.** Lanza `TypeError`

### Pregunta 4

¿Qué operador compara la identidad de dos objetos?

**A.** `==`  
**B.** `=`  
**C.** `!=`  
**D.** `is`

### Pregunta 5

¿Qué imprime este código?

```python
x = 5
print(1 < x < 10)
```

**A.** `True`  
**B.** `False`  
**C.** `1`  
**D.** Produce un error de sintaxis

### Pregunta 6

¿Qué secuencia genera `range(2, 9, 3)`?

**A.** `2, 5, 8, 11`  
**B.** `2, 5, 8`  
**C.** `2, 3, 4, 5, 6, 7, 8`  
**D.** `3, 6, 9`

### Pregunta 7

En un bucle, ¿cuándo se ejecuta su bloque `else`?

**A.** Solo si el bucle no realiza ninguna iteración  
**B.** Siempre antes de la primera iteración  
**C.** Al terminar normalmente, sin haber salido mediante `break`  
**D.** Únicamente cuando se ejecuta `continue`

### Pregunta 8

¿Qué hace `continue` dentro de un bucle?

**A.** Finaliza el programa  
**B.** Reinicia el iterable  
**C.** Sale definitivamente del bucle  
**D.** Omite el resto de la iteración actual y pasa a la siguiente

### Pregunta 9

¿Qué imprime el siguiente código?

```python
for numero in range(3):
    print(numero, end=" ")
```

**A.** `0 1 2 `  
**B.** `1 2 3 `  
**C.** `0 1 2 3 `  
**D.** `3 `

### Pregunta 10

¿Qué devuelve `list(enumerate(["a", "b"], start=1))`?

**A.** `[(0, "a"), (1, "b")]`  
**B.** `[(1, "a"), (2, "b")]`  
**C.** `[("a", 1), ("b", 2)]`  
**D.** `[1, "a", 2, "b"]`

### Pregunta 11

¿Qué ocurre con `zip([1, 2, 3], ["a", "b"])` al convertirlo en lista?

**A.** Rellena con `None` la secuencia más corta  
**B.** Lanza una excepción por distinta longitud  
**C.** Se detiene al agotarse el iterable más corto  
**D.** Devuelve tres pares

### Pregunta 12

¿Cuál crea una lista con los cuadrados de los pares entre 0 y 5?

**A.** `[x ** 2 for x in range(6) if x % 2 == 0]`  
**B.** `[x for x ** 2 in range(6) if x % 2]`  
**C.** `{x ** 2 if x % 2 == 0 for x in range(6)}`  
**D.** `(x ** 2 for x in range(6) if x % 2 == 0)`

## Colecciones y funciones

### Pregunta 13

¿Qué estructura es ordenada, mutable y admite duplicados?

**A.** `frozenset`  
**B.** `tuple`  
**C.** `set`  
**D.** `list`

### Pregunta 14

¿Cuál es el resultado de `[10, 20, 30, 40][1:3]`?

**A.** `[10, 20, 30]`  
**B.** `[20, 30]`  
**C.** `[20, 30, 40]`  
**D.** `[10, 20]`

### Pregunta 15

¿Qué diferencia hay entre `append()` y `extend()` en una lista?

**A.** `append()` añade un elemento; `extend()` incorpora los elementos de un iterable  
**B.** `append()` ordena y `extend()` invierte  
**C.** `append()` devuelve una lista nueva y `extend()` una tupla  
**D.** No existe diferencia

### Pregunta 16

¿Qué método elimina y devuelve por defecto el último elemento de una lista?

**A.** `remove()`  
**B.** `clear()`  
**C.** `pop()`  
**D.** `discard()`

### Pregunta 17

¿Qué afirmación sobre las tuplas es correcta?

**A.** No pueden contener objetos mutables  
**B.** Son inmutables, aunque pueden contener referencias a objetos mutables  
**C.** No admiten indexación  
**D.** Eliminan automáticamente los duplicados

### Pregunta 18

¿Qué operación representa la intersección de los conjuntos `a` y `b`?

**A.** `a | b`  
**B.** `a - b`  
**C.** `a ^ b`  
**D.** `a & b`

### Pregunta 19

¿Qué ocurre al evaluar `datos["edad"]` si la clave no existe?

**A.** Se lanza `KeyError`  
**B.** Se devuelve `None` siempre  
**C.** Se crea la clave con valor cero  
**D.** Se lanza `IndexError`

### Pregunta 20

¿Qué método permite obtener una clave inexistente de un diccionario sin lanzar `KeyError`?

**A.** `index()`  
**B.** `get()`  
**C.** `find()`  
**D.** `fetch()`

### Pregunta 21

¿Qué imprime este código?

```python
lista = [1, 2]
copia = lista
copia.append(3)
print(lista)
```

**A.** `[1, 2]`  
**B.** `[3]`  
**C.** `[1, 2, 3]`  
**D.** Lanza `NameError`

### Pregunta 22

¿Cuál es la diferencia principal entre `sorted(datos)` y `datos.sort()` para una lista?

**A.** `sorted()` solo admite números  
**B.** `sort()` devuelve siempre una tupla  
**C.** Ambas modifican la lista y devuelven `None`  
**D.** `sorted()` devuelve una lista nueva; `sort()` modifica la original

### Pregunta 23

Si una función llega al final sin ejecutar `return`, ¿qué devuelve?

**A.** `None`  
**B.** `0`  
**C.** `False`  
**D.** Una cadena vacía

### Pregunta 24

En una definición de función, `*args` recoge:

**A.** Argumentos nombrados en un diccionario  
**B.** Argumentos posicionales adicionales en una tupla  
**C.** Solo argumentos de tipo cadena  
**D.** Excepciones pendientes

### Pregunta 25

En una definición de función, `**kwargs` recoge:

**A.** Argumentos posicionales en una lista  
**B.** Valores de retorno múltiples  
**C.** Argumentos nombrados adicionales en un diccionario  
**D.** Módulos importados

### Pregunta 26

Según la regla LEGB, ¿qué ámbito se busca primero al resolver un nombre dentro de una función?

**A.** Local  
**B.** Global  
**C.** Built-in  
**D.** Enclosing

### Pregunta 27

¿Para qué se utiliza `nonlocal`?

**A.** Para crear una constante  
**B.** Para importar un nombre de otro módulo  
**C.** Para convertir una variable local en global  
**D.** Para reasignar un nombre de un ámbito envolvente no global

### Pregunta 28

¿Cuál es una limitación sintáctica de `lambda`?

**A.** No puede recibir argumentos  
**B.** Su cuerpo es una única expresión  
**C.** Siempre devuelve `None`  
**D.** Solo puede operar con números

## Excepciones, módulos y archivos

### Pregunta 29

En `try/except/else/finally`, el bloque `else` se ejecuta cuando:

**A.** No se produce una excepción en el `try`  
**B.** Se produce cualquier excepción  
**C.** Se ejecuta `finally` con error  
**D.** El `except` vuelve a lanzar la excepción

### Pregunta 30

¿Qué caracteriza al bloque `finally`?

**A.** Solo se ejecuta si no hay error  
**B.** Sustituye a todos los bloques `except`  
**C.** Se ejecuta normalmente haya o no excepción  
**D.** Solo admite instrucciones `return`

### Pregunta 31

¿Qué instrucción lanza explícitamente una excepción?

**A.** `except`  
**B.** `raise`  
**C.** `assertion`  
**D.** `throw`

### Pregunta 32

Al ordenar varios bloques `except`, ¿cuál debe aparecer primero?

**A.** La excepción más general  
**B.** `BaseException` siempre  
**C.** El bloque sin tipo  
**D.** La excepción más específica

### Pregunta 33

¿Qué valor tiene normalmente `__name__` cuando un archivo se ejecuta directamente?

**A.** `"__main__"`  
**B.** `"__name__"`  
**C.** El nombre del intérprete  
**D.** `None`

### Pregunta 34

¿Qué es un módulo de Python?

**A.** Exclusivamente una carpeta con entorno virtual  
**B.** Un archivo de código Python importable  
**C.** Una función integrada  
**D.** Un paquete instalado obligatoriamente desde Internet

### Pregunta 35

¿Cuál es el objetivo principal de un entorno virtual?

**A.** Compilar Python a código máquina  
**B.** Sustituir el sistema operativo  
**C.** Aislar dependencias entre proyectos  
**D.** Cifrar el código fuente

### Pregunta 36

¿Qué ventaja principal ofrece `with open(...) as archivo`?

**A.** Gestiona el cierre del recurso aunque ocurra una excepción  
**B.** Convierte cualquier archivo a JSON  
**C.** Impide todos los errores de entrada/salida  
**D.** Abre siempre el archivo en modo binario

### Pregunta 37

¿Qué modo abre un archivo para añadir contenido al final?

**A.** `r`  
**B.** `x`  
**C.** `w`  
**D.** `a`

### Pregunta 38

¿Qué efecto tiene abrir un archivo existente con modo `w`?

**A.** Solo permite leerlo  
**B.** Trunca su contenido antes de escribir  
**C.** Añade al final sin modificar lo anterior  
**D.** Lanza siempre `FileExistsError`

### Pregunta 39

¿Qué método de `pathlib.Path` comprueba si una ruta existe?

**A.** `exists()`  
**B.** `isvalid()`  
**C.** `check()`  
**D.** `present()`

### Pregunta 40

¿Qué diferencia hay entre `json.dump()` y `json.dumps()`?

**A.** `dump()` decodifica y `dumps()` cifra  
**B.** Son alias exactos  
**C.** `dump()` escribe en un archivo; `dumps()` devuelve una cadena  
**D.** `dumps()` solo admite diccionarios

## Objetos, iteración y características avanzadas

### Pregunta 41

¿Cuál es la función habitual de `__init__`?

**A.** Destruir el objeto  
**B.** Inicializar el estado de una instancia recién creada  
**C.** Crear una clase abstracta  
**D.** Importar la superclase

### Pregunta 42

En un método de instancia, `self` representa:

**A.** La clase base  
**B.** El módulo actual  
**C.** Una palabra reservada obligatoria  
**D.** La instancia sobre la que se invoca el método

### Pregunta 43

¿Qué hace `super()` habitualmente en una subclase?

**A.** Permite delegar en implementaciones de la clase base según el MRO  
**B.** Convierte un método en estático  
**C.** Evita toda herencia múltiple  
**D.** Crea una copia profunda del objeto

### Pregunta 44

¿Qué decorador permite exponer un método como atributo calculado?

**A.** `@staticmethod`  
**B.** `@classmethod`  
**C.** `@property`  
**D.** `@abstract`

### Pregunta 45

¿Qué método especial se asocia con una representación legible para el usuario?

**A.** `__len__`  
**B.** `__str__`  
**C.** `__call__`  
**D.** `__iter__`

### Pregunta 46

¿Qué distingue a un iterable de un iterador?

**A.** El iterable puede proporcionar un iterador; el iterador produce elementos con `next()`  
**B.** Todo iterable implementa necesariamente `__next__()`  
**C.** Un iterador puede recorrerse infinitas veces desde el inicio  
**D.** Solo las listas son iterables

### Pregunta 47

¿Qué excepción señala el agotamiento de un iterador?

**A.** `EOFError`  
**B.** `IndexError`  
**C.** `GeneratorExit`  
**D.** `StopIteration`

### Pregunta 48

¿Qué efecto tiene `yield` en una función?

**A.** Finaliza el intérprete  
**B.** La convierte en una función generadora que conserva su estado entre reanudaciones  
**C.** Devuelve todos los valores en una lista  
**D.** Declara una excepción

### Pregunta 49

Frente a una lista por comprensión equivalente, una expresión generadora:

**A.** Evalúa todos los elementos al crearla  
**B.** No puede usarse en un `for`  
**C.** Produce valores de forma perezosa  
**D.** Siempre es más rápida en cualquier operación

### Pregunta 50

¿Qué es un decorador en Python?

**A.** Un callable que recibe y devuelve normalmente otro callable, modificando o ampliando su comportamiento  
**B.** Un comentario especial interpretado por PEP 8  
**C.** Un tipo de bucle  
**D.** Un módulo exclusivo de interfaces gráficas

### Pregunta 51

¿Para qué se usa `functools.wraps` al construir decoradores?

**A.** Para ejecutar la función en paralelo  
**B.** Para impedir argumentos nombrados  
**C.** Para memorizar cualquier resultado  
**D.** Para preservar metadatos de la función decorada

### Pregunta 52

¿Qué afirmación sobre las anotaciones de tipo es correcta?

**A.** Python las aplica siempre como restricciones en ejecución  
**B.** Sirven para documentación y análisis estático, pero normalmente no fuerzan tipos en ejecución  
**C.** Solo pueden usarse en atributos de clase  
**D.** Convierten Python en un lenguaje compilado

### Pregunta 53

En `typing`, `Optional[int]` expresa normalmente:

**A.** Solo `int`, pero con valor predeterminado  
**B.** Una lista opcional de enteros  
**C.** `int` o `None`  
**D.** Cualquier tipo salvo `int`

### Pregunta 54

¿Qué aporta principalmente `@dataclass`?

**A.** Genera métodos habituales a partir de campos declarados  
**B.** Hace inmutable toda clase obligatoriamente  
**C.** Impide la herencia  
**D.** Sustituye a todos los validadores

### Pregunta 55

¿Qué construcción introducida en Python 3.10 permite pattern matching estructural?

**A.** `switch/select`  
**B.** `when/then`  
**C.** `case/switch`  
**D.** `match/case`

## Ecosistema, calidad y lectura de código

### Pregunta 56

¿Qué objeto multidimensional constituye la estructura central de NumPy?

**A.** `DataFrame`  
**B.** `ndarray`  
**C.** `Series`  
**D.** `MatrixFrame`

### Pregunta 57

Para un array NumPy, ¿qué indica `shape`?

**A.** El tamaño de cada dimensión  
**B.** Solo el número total de bytes  
**C.** El tipo de dato  
**D.** La media de sus valores

### Pregunta 58

¿Cuál es la estructura tabular bidimensional principal de Pandas?

**A.** `ndarray`  
**B.** `Table`  
**C.** `DataFrame`  
**D.** `Panel2D`

### Pregunta 59

¿Qué biblioteca se utiliza habitualmente para realizar peticiones HTTP en Python?

**A.** BeautifulSoup  
**B.** Requests  
**C.** Matplotlib  
**D.** pathlib

### Pregunta 60

¿Cuál es el propósito principal de BeautifulSoup?

**A.** Analizar documentos HTML o XML para extraer información  
**B.** Dibujar gráficos vectoriales  
**C.** Crear arrays numéricos  
**D.** Gestionar procesos del sistema

### Pregunta 61

¿Qué función de Matplotlib se usa habitualmente para mostrar una figura?

**A.** `plt.render()`  
**B.** `plt.drawall()`  
**C.** `plt.open()`  
**D.** `plt.show()`

### Pregunta 62

¿Qué establece PEP 8 principalmente?

**A.** El protocolo de paquetes de red de Python  
**B.** Convenciones de estilo para código Python  
**C.** La licencia del intérprete  
**D.** Las reglas de gestión de memoria de CPython

### Pregunta 63

¿Qué imprime este código?

```python
def agregar(valor, destino=[]):
    destino.append(valor)
    return destino

print(agregar(1))
print(agregar(2))
```

**A.** `[1]` y después `[2]`  
**B.** Produce `TypeError` en la segunda llamada  
**C.** `[1]` y después `[1, 2]`  
**D.** `[]` y después `[]`

### Pregunta 64

¿Qué imprime este código?

```python
valores = [1, 2, 3]
print(valores[-1])
```

**A.** `3`  
**B.** `1`  
**C.** `-1`  
**D.** Lanza `IndexError`

### Pregunta 65

¿Qué resultado produce `"python"[::-1]`?

**A.** `"python"`  
**B.** `"nohtyp"`  
**C.** `"ython"`  
**D.** Una cadena vacía

### Pregunta 66

¿Qué imprime este código?

```python
a = [1, 2]
b = a.copy()
print(a == b, a is b)
```

**A.** `False False`  
**B.** `False True`  
**C.** `True True`  
**D.** `True False`

### Pregunta 67

¿Qué ocurre al ejecutar `int("3.5")`?

**A.** Devuelve `3`  
**B.** Devuelve `4`  
**C.** Lanza `ValueError`  
**D.** Devuelve `3.5`

### Pregunta 68

¿Qué imprime este código?

```python
numeros = [1, 2, 3, 4]
resultado = list(filter(lambda x: x % 2 == 0, numeros))
print(resultado)
```

**A.** `[2, 4]`  
**B.** `[1, 3]`  
**C.** `[False, True, False, True]`  
**D.** `6`

### Pregunta 69

¿Qué imprime este código?

```python
try:
    resultado = 10 / 0
except ZeroDivisionError:
    print("error")
else:
    print("ok")
```

**A.** `ok`  
**B.** `error`  
**C.** `error` y después `ok`  
**D.** Nada

### Pregunta 70

¿Qué práctica mejora normalmente la eficiencia de memoria al procesar una secuencia muy grande una sola vez?

**A.** Convertirla varias veces en lista  
**B.** Duplicarla mediante slicing  
**C.** Guardar cada resultado intermedio en un diccionario  
**D.** Utilizar un generador que produzca elementos bajo demanda

---

# 🏁 FIN DEL SIMULACRO

Revisa las preguntas en blanco antes de consultar la plantilla y la corrección.
