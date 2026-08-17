<!-- encabezado-homogeneizado -->
# Bloque 05 - SIMULACRO
> **Bloque:** Bloque 05  
> **Documento:** Simulacro  
> **Preguntas de referencia:** 70  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# BLOQUE 5C - SIMULACRO TIPO TEST: JAVASCRIPT

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.7 - JavaScript (partes 1 a 6)  
> **Formato:** Tipo test  
> **Preguntas:** 70  
> **Opciones:** 4 por pregunta  
> **Respuestas correctas:** 1 por pregunta  
> **Nivel:** ⭐⭐⭐⭐⭐  
> **Tiempo recomendado:** 90 minutos  
> **Puntuación recomendada:** +1 por acierto, 0 en blanco, -0,33 por error

---

# 📋 INSTRUCCIONES

- Marca una unica respuesta (`A`, `B`, `C` o `D`) por pregunta.
- No consultes el manual durante la realizacion.
- Puedes dejar preguntas en blanco y volver al final.
- En preguntas de codigo, presupón JavaScript moderno en navegador.

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

# 🟨 PREGUNTAS

## Fundamentos del lenguaje

### Pregunta 1
¿Que afirmacion sobre `let` y `const` es correcta?

**A.** `let` y `const` se pueden redeclarar siempre en el mismo bloque  
**B.** `const` no permite reasignar la referencia, aunque un objeto referenciado pueda mutar  
**C.** `let` es siempre global  
**D.** `const` obliga a usar valores primitivos

### Pregunta 2
¿Que describe mejor el hoisting?

**A.** Los valores de variables se inicializan antes de cualquier declaracion  
**B.** Solo afecta a funciones flecha  
**C.** El motor transpila automaticamente a TypeScript  
**D.** Declaraciones se procesan antes de ejecutar, con reglas distintas segun `var`, `let`, `const` y funciones

### Pregunta 3
En comparaciones, ¿que operador exige igualdad de tipo y valor?

**A.** `===`  
**B.** `==`  
**C.** `=`  
**D.** `!=`

### Pregunta 4
¿Que valor imprime?

```javascript
console.log(typeof null);
```

**A.** `null`  
**B.** `undefined`  
**C.** `object`  
**D.** `boolean`

### Pregunta 5
¿Que es un closure?

**A.** Una funcion que no puede devolver valores  
**B.** Una funcion que conserva acceso a variables de su entorno lexico  
**C.** Un objeto sellado  
**D.** Una promesa rechazada

### Pregunta 6
¿Que resultado produce?

```javascript
const x = 0;
console.log(x || 10);
```

**A.** `0`  
**B.** `undefined`  
**C.** `null`  
**D.** `10`

### Pregunta 7
¿Que resultado produce?

```javascript
const x = 0;
console.log(x ?? 10);
```

**A.** `0`  
**B.** `10`  
**C.** `false`  
**D.** error

### Pregunta 8
En una arrow function, `this`:

**A.** Siempre apunta al objeto global  
**B.** Se calcula igual que en una funcion metodo tradicional  
**C.** Es lexico y no crea su propio `this`  
**D.** Siempre es `undefined`

### Pregunta 9
¿Que devuelve `typeof NaN`?

**A.** `nan`  
**B.** `number`  
**C.** `undefined`  
**D.** `object`

### Pregunta 10
En modo estricto, la asignacion `x = 10;` sin declaracion previa:

**A.** Crea una global implicita sin avisar  
**B.** Se ignora silenciosamente  
**C.** Devuelve `false`  
**D.** Lanza error

### Pregunta 11
¿Que recorre `for...of` sobre un array?

**A.** Valores  
**B.** Propiedades heredadas  
**C.** Solo claves string  
**D.** Solo indices pares

### Pregunta 12
¿Que recorre `for...in` sobre un array normalmente?

**A.** Valores numericos  
**B.** Objetos internos  
**C.** Propiedades enumerables, habitualmente indices como strings  
**D.** Nada, produce error

## Objetos, arrays y JSON

### Pregunta 13
¿Que diferencia principal hay entre `slice()` y `splice()`?

**A.** `slice()` modifica y `splice()` no  
**B.** Ambas no modifican nunca  
**C.** Ambas modifican siempre  
**D.** `slice()` no modifica el original, `splice()` si lo modifica

### Pregunta 14
¿Que metodo transforma cada elemento y devuelve un nuevo array?

**A.** `forEach()`  
**B.** `filter()`  
**C.** `reduce()`  
**D.** `map()`

### Pregunta 15
¿Que metodo devuelve solo elementos que cumplen condicion?

**A.** `filter()`  
**B.** `findIndex()`  
**C.** `sort()`  
**D.** `join()`

### Pregunta 16
¿Que devuelve `find()` si no encuentra coincidencia?

**A.** `-1`  
**B.** `null`  
**C.** `undefined`  
**D.** `false`

### Pregunta 17
¿Que devuelve `findIndex()` si no encuentra coincidencia?

**A.** `undefined`  
**B.** `null`  
**C.** `false`  
**D.** `-1`

### Pregunta 18
¿Que comprueba `some()`?

**A.** Que todos cumplan condicion  
**B.** Que al menos uno cumpla condicion  
**C.** Que no haya duplicados  
**D.** Que el array este ordenado

### Pregunta 19
¿Que comprueba `every()`?

**A.** Que todos cumplan condicion  
**B.** Que exista alguno  
**C.** Que el array tenga longitud par  
**D.** Que no haya `null`

### Pregunta 20
¿Que afirmacion sobre `sort()` es correcta?

**A.** Siempre ordena numericamente sin comparador  
**B.** Devuelve un array nuevo sin tocar el original  
**C.** Modifica el array original  
**D.** Solo funciona con strings

### Pregunta 21
¿Que estructura representa mejor una coleccion de valores unicos?

**A.** `Map`  
**B.** `Object`  
**C.** `Array`  
**D.** `Set`

### Pregunta 22
En `Set` y `Map`, la cantidad de elementos se consulta con:

**A.** `length`  
**B.** `count`  
**C.** `size()`  
**D.** `size`

### Pregunta 23
¿Que hace `JSON.stringify(valor)`?

**A.** Convierte valor JS en cadena JSON  
**B.** Convierte JSON en objeto JS  
**C.** Valida schema JSON automaticamente  
**D.** Convierte un objeto en `Map`

### Pregunta 24
¿Que hace `JSON.parse(texto)`?

**A.** Convierte objeto a JSON string  
**B.** Comprime JSON  
**C.** Convierte JSON valido a valor JS  
**D.** Lee cookies

### Pregunta 25
Sobre spread en objetos/arrays anidados, ¿que es correcto?

**A.** Siempre hace copia profunda  
**B.** Solo funciona con arrays  
**C.** Clona funciones en bytecode  
**D.** Hace copia superficial

## DOM y eventos

### Pregunta 26
¿Que devuelve `querySelector()`?

**A.** Todos los elementos coincidentes  
**B.** El primer elemento coincidente o `null`  
**C.** Siempre un `HTMLCollection`  
**D.** Siempre una `NodeList`

### Pregunta 27
¿Que devuelve `querySelectorAll()`?

**A.** Una `NodeList`  
**B.** Un unico elemento  
**C.** Un `Map`  
**D.** Un array mutable live

### Pregunta 28
¿Cual suele ser una coleccion live?

**A.** `querySelectorAll()`  
**B.** `NodeList` de `querySelectorAll()`  
**C.** `HTMLCollection` de `getElementsByClassName()`  
**D.** Ninguna, todas son estaticas

### Pregunta 29
Diferencia correcta entre `children` y `childNodes`:

**A.** Ambas devuelven solo elementos HTML  
**B.** `children` incluye comentarios y texto  
**C.** `childNodes` excluye nodos de texto  
**D.** `children` devuelve elementos; `childNodes` devuelve nodos

### Pregunta 30
¿Que propiedad trata siempre como texto literal?

**A.** `innerHTML`  
**B.** `textContent`  
**C.** `outerHTML`  
**D.** `dataset`

### Pregunta 31
¿Que riesgo aumenta al insertar contenido no confiable con `innerHTML`?

**A.** XSS  
**B.** CSRF  
**C.** CORS  
**D.** SQL injection local

### Pregunta 32
¿Que hace `classList.toggle("activo")`?

**A.** Solo añade la clase  
**B.** Solo elimina la clase  
**C.** La añade o elimina segun estado previo  
**D.** Reemplaza todas las clases

### Pregunta 33
`event.target` representa:

**A.** El elemento donde se origino el evento  
**B.** Siempre el documento  
**C.** Siempre el mismo valor que `currentTarget`  
**D.** El ultimo ancestro

### Pregunta 34
`event.currentTarget` representa:

**A.** Siempre el nodo hijo clicado  
**B.** El origen fisico del puntero  
**C.** El elemento con foco  
**D.** El elemento cuyo listener esta ejecutandose

### Pregunta 35
`preventDefault()`:

**A.** Evita la accion por defecto del evento cancelable  
**B.** Detiene siempre toda propagacion  
**C.** Elimina todos los listeners  
**D.** Impide cualquier evento futuro

### Pregunta 36
`stopPropagation()`:

**A.** Cancela el submit automaticamente  
**B.** Impide la accion por defecto  
**C.** Detiene la propagacion del evento  
**D.** Detiene solo microtareas

### Pregunta 37
Orden correcto de fases de propagacion:

**A.** bubbling -> target -> capturing  
**B.** target -> capturing -> bubbling  
**C.** target -> bubbling -> capturing  
**D.** capturing -> target -> bubbling

### Pregunta 38
La delegacion de eventos consiste en:

**A.** Registrar listeners en cada hijo obligatoriamente  
**B.** Registrar un listener en ancestro y discriminar por `event.target`/`closest`  
**C.** Desactivar bubbling  
**D.** Usar solo `onclick` inline

### Pregunta 39
¿Que evento indica DOM construido sin esperar todos los recursos?

**A.** `DOMContentLoaded`  
**B.** `load`  
**C.** `readyStateComplete`  
**D.** `beforeload`

### Pregunta 40
`getComputedStyle(elemento)` devuelve:

**A.** Solo estilos inline  
**B.** Solo variables CSS  
**C.** Estilos calculados finales  
**D.** Un booleano de visibilidad

## Asincronia, Promises y Fetch

### Pregunta 41
El Call Stack funciona tipicamente como:

**A.** FIFO  
**B.** Cola circular  
**C.** Pila de prioridad  
**D.** LIFO

### Pregunta 42
`setTimeout(fn, 0)` significa:

**A.** Ejecutar `fn` inmediatamente antes del siguiente `console.log`  
**B.** Programar una tarea para ejecutarse no antes de ese umbral, cuando toque ciclo/event loop  
**C.** Forzar microtask  
**D.** Bloquear el hilo 0 ms exactos

### Pregunta 43
Los callbacks de `then/catch/finally` se encolan como:

**A.** Microtasks  
**B.** Macrotasks de timer  
**C.** Eventos DOM synchronos  
**D.** Hilos separados

### Pregunta 44
Estado inicial de una Promise:

**A.** `fulfilled`  
**B.** `resolved`  
**C.** `rejected`  
**D.** `pending`

### Pregunta 45
`Promise.all([...])`:

**A.** Ignora rechazos  
**B.** Rechaza si cualquiera rechaza  
**C.** Devuelve primer fulfilled  
**D.** Siempre devuelve `AggregateError`

### Pregunta 46
`Promise.allSettled([...])`:

**A.** Falla al primer rechazo  
**B.** Se resuelve con el primero que cumpla  
**C.** Es alias de `race`  
**D.** Espera a todas e informa estado de cada una

### Pregunta 47
`Promise.any([...])`:

**A.** Se cumple con la primera Promise que se cumpla  
**B.** Se rechaza al primer rechazo  
**C.** Es igual que `all`  
**D.** No admite arrays

### Pregunta 48
Si todas las Promises en `Promise.any()` rechazan:

**A.** Devuelve `null`  
**B.** Queda pendiente  
**C.** Rechaza con `AggregateError`  
**D.** Devuelve array vacio

### Pregunta 49
Una funcion `async` devuelve:

**A.** Siempre una Promise  
**B.** Siempre `undefined`  
**C.** Siempre callback  
**D.** Valor plano sin Promise

### Pregunta 50
`await` dentro de una funcion `async`:

**A.** Bloquea totalmente navegador y event loop  
**B.** Solo sirve para `fetch`  
**C.** Solo funciona con `setTimeout`  
**D.** Suspende esa funcion hasta resolucion/rechazo de la Promise

### Pregunta 51
Sobre `fetch`, ¿que afirmacion es correcta?

**A.** Rechaza automaticamente por cualquier 404/500  
**B.** Nunca rechaza en errores de red  
**C.** Solo funciona con GET  
**D.** Conviene comprobar `response.ok`/`status` para errores HTTP

### Pregunta 52
`response.json()`:

**A.** Devuelve directamente un objeto sincrono  
**B.** Devuelve string JSON plano  
**C.** Devuelve una Promise con el parseo JSON  
**D.** Solo funciona si status es 201

### Pregunta 53
¿Que metodo de `Response` leeria contenido textual?

**A.** `text()`  
**B.** `stringify()`  
**C.** `plain()`  
**D.** `toText()`

### Pregunta 54
`AbortController` en Fetch se usa para:

**A.** Evitar CORS  
**B.** Convertir POST en GET  
**C.** Reintentar automaticamente  
**D.** Cancelar solicitudes asociadas al `signal`

## Modulos, storage, seguridad y JS moderno

### Pregunta 55
En ES modules, `export default` se importa tipicamente:

**A.** Sin llaves, con nombre elegido por quien importa  
**B.** Solo con `import * as`  
**C.** Solo con llaves obligatorias  
**D.** No puede coexistir con exports nombrados

### Pregunta 56
Una caracteristica de scripts `type="module"` es:

**A.** Desactivar strict mode  
**B.** Convertir todo en global `window`  
**C.** Scope propio y strict mode implicito  
**D.** Impedir imports relativos

### Pregunta 57
`localStorage.getItem("clave")` cuando no existe clave devuelve:

**A.** `null`  
**B.** `undefined`  
**C.** `false`  
**D.** `""`

### Pregunta 58
Web Storage (`localStorage`/`sessionStorage`) guarda valores como:

**A.** Binario  
**B.** Objetos profundos  
**C.** Numbers puros  
**D.** Strings

### Pregunta 59
`sessionStorage` se asocia tipicamente a:

**A.** Sesion de la pestaña/contexto, no persistencia larga como localStorage  
**B.** Persistencia indefinida entre equipos  
**C.** Cookie HttpOnly  
**D.** Cache del service worker

### Pregunta 60
Una cookie con atributo `HttpOnly`:

**A.** Se envia solo por HTTP plano  
**B.** Se borra al cerrar pestana siempre  
**C.** No es accesible desde `document.cookie` por JavaScript  
**D.** Desactiva `SameSite`

### Pregunta 61
`?.` (optional chaining) evita error de acceso cuando el operando es:

**A.** `null` o `undefined`  
**B.** `0`  
**C.** `""`  
**D.** `false`

### Pregunta 62
`valor ?? "x"` usa el valor alternativo solo cuando `valor` es:

**A.** Falsy cualquiera  
**B.** `null` o `undefined`  
**C.** Menor que cero  
**D.** String vacio

### Pregunta 63
`WeakMap` se diferencia de `Map` en que:

**A.** Mantiene referencias debiles en claves y no esta orientado a enumeracion completa  
**B.** Acepta solo claves string  
**C.** Tiene propiedad `length`  
**D.** Permite `for...of` sobre todas sus entradas siempre

### Pregunta 64
`WeakSet`:

**A.** Es igual que `Set` con `size` y enumeracion completa  
**B.** Permite primitvos y objetos por igual  
**C.** Guarda referencias debiles a objetos y no esta disenado para enumerar todo  
**D.** Almacena pares clave-valor

### Pregunta 65
¿Que diferencia conceptual es correcta?

**A.** CORS y CSRF son el mismo problema  
**B.** XSS es equivalente a CORS  
**C.** CSRF es inyeccion de script en DOM  
**D.** XSS es ejecucion de contenido/script no confiable; CSRF busca solicitudes no deseadas

### Pregunta 66
¿Que afirmacion sobre validacion cliente/servidor es correcta?

**A.** La validacion cliente sustituye por completo la del servidor  
**B.** Nunca hay que validar en cliente  
**C.** Solo valida quien tenga HTTPS  
**D.** La validacion en cliente mejora UX, pero la seguridad/reglas finales deben validarse en servidor

### Pregunta 67
En History API, `pushState()` frente a `replaceState()`:

**A.** `pushState` añade entrada; `replaceState` reemplaza la actual  
**B.** Ambos recargan siempre  
**C.** Ambos son identicos  
**D.** `replaceState` añade y `pushState` borra

### Pregunta 68
`URLSearchParams` sirve para:

**A.** Parsear HTML  
**B.** Gestionar parametros de consulta (`get`, `set`, `has`, `delete`)  
**C.** Serializar cookies HttpOnly  
**D.** Reemplazar Fetch

### Pregunta 69
`location.replace("/login")`:

**A.** Agrega una nueva entrada al historial como `assign`  
**B.** No navega realmente  
**C.** Es equivalente a `history.back()`  
**D.** Navega reemplazando la entrada actual del historial

### Pregunta 70
¿Que afirmacion sobre seguridad y storage es mas correcta?

**A.** Guardar secretos sensibles en localStorage reduce el impacto de XSS  
**B.** localStorage es inaccesible desde JavaScript  
**C.** Cookies HttpOnly y estrategia de sesion pueden reducir superficie frente a robo por JS, segun arquitectura  
**D.** CORS elimina por completo ataques XSS

---

# 🏁 FIN DEL SIMULACRO

Revisa respuestas en blanco antes de consultar plantilla y correccion.
