# BLOQUE 5C - PLANTILLA Y CORRECCION: JAVASCRIPT

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.7 - JavaScript  
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
| 1 | B | | 19 | A | | 37 | D | | 55 | A | |
| 2 | D | | 20 | C | | 38 | B | | 56 | C | |
| 3 | A | | 21 | D | | 39 | A | | 57 | A | |
| 4 | C | | 22 | D | | 40 | C | | 58 | D | |
| 5 | B | | 23 | A | | 41 | D | | 59 | A | |
| 6 | D | | 24 | C | | 42 | B | | 60 | C | |
| 7 | A | | 25 | D | | 43 | A | | 61 | A | |
| 8 | C | | 26 | B | | 44 | D | | 62 | B | |
| 9 | B | | 27 | A | | 45 | B | | 63 | A | |
| 10 | D | | 28 | C | | 46 | D | | 64 | C | |
| 11 | A | | 29 | D | | 47 | A | | 65 | D | |
| 12 | C | | 30 | B | | 48 | C | | 66 | D | |
| 13 | D | | 31 | A | | 49 | A | | 67 | A | |
| 14 | D | | 32 | C | | 50 | D | | 68 | B | |
| 15 | A | | 33 | A | | 51 | D | | 69 | D | |
| 16 | C | | 34 | D | | 52 | C | | 70 | C | |
| 17 | D | | 35 | A | | 53 | A | | | | |
| 18 | B | | 36 | C | | 54 | D | | | | |

---

# 📊 3. DIAGNOSTICO POR AREAS

| Preguntas | Area | Aciertos |
|:---:|---|:---:|
| 1-12 | Fundamentos del lenguaje | /12 |
| 13-25 | Objetos, arrays y JSON | /13 |
| 26-40 | DOM y eventos | /15 |
| 41-54 | Asincronia, Promises y Fetch | /14 |
| 55-70 | Modulos, storage, seguridad y JS moderno | /16 |

Referencia orientativa:

- **60-70:** dominio muy solido.
- **49-59:** buen nivel, con margen de pulido.
- **35-48:** base util, pero con lagunas relevantes.
- **0-34:** recomendable repasar completo el capitulo 5.7.

---

# 🧠 4. CORRECCION RAZONADA

### Pregunta 1 · **B**
`const` impide reasignar la referencia; no impide mutar un objeto referenciado.

### Pregunta 2 · **D**
El hoisting procesa declaraciones antes de ejecutar, pero con comportamiento distinto segun tipo de declaracion.

### Pregunta 3 · **A**
`===` compara valor y tipo sin coercion implicita.

### Pregunta 4 · **C**
`typeof null` devuelve `"object"` por un comportamiento historico del lenguaje.

### Pregunta 5 · **B**
Un closure mantiene acceso al entorno lexico donde fue creado.

### Pregunta 6 · **D**
`||` usa el segundo operando cuando el primero es falsy; `0` es falsy.

### Pregunta 7 · **A**
`??` solo cae al alternativo con `null` o `undefined`; `0` se conserva.

### Pregunta 8 · **C**
Las arrow functions no crean `this` propio; capturan el del contexto exterior.

### Pregunta 9 · **B**
`NaN` pertenece al tipo numerico en JavaScript.

### Pregunta 10 · **D**
En strict mode, asignar a identificador no declarado produce error.

### Pregunta 11 · **A**
`for...of` recorre valores de iterables.

### Pregunta 12 · **C**
`for...in` recorre propiedades enumerables; en arrays suelen ser indices string.

### Pregunta 13 · **D**
`slice` no muta el original; `splice` si lo altera.

### Pregunta 14 · **D**
`map` transforma y devuelve nuevo array.

### Pregunta 15 · **A**
`filter` devuelve los elementos que cumplen el predicado.

### Pregunta 16 · **C**
`find` retorna `undefined` cuando no hay coincidencia.

### Pregunta 17 · **D**
`findIndex` devuelve `-1` si no encuentra elemento.

### Pregunta 18 · **B**
`some` verifica si al menos un elemento cumple.

### Pregunta 19 · **A**
`every` exige que todos cumplan.

### Pregunta 20 · **C**
`sort` ordena in place, modificando el array original.

### Pregunta 21 · **D**
`Set` modela valores unicos.

### Pregunta 22 · **D**
`Map` y `Set` usan propiedad `size`.

### Pregunta 23 · **A**
`JSON.stringify` serializa valor JS a string JSON.

### Pregunta 24 · **C**
`JSON.parse` deserializa string JSON valido a valor JS.

### Pregunta 25 · **D**
Spread en estructuras anidadas realiza copia superficial, no profunda.

### Pregunta 26 · **B**
`querySelector` devuelve el primer match o `null`.

### Pregunta 27 · **A**
`querySelectorAll` devuelve una `NodeList`.

### Pregunta 28 · **C**
`getElementsByClassName` devuelve `HTMLCollection` normalmente live.

### Pregunta 29 · **D**
`children` son elementos; `childNodes` incluye otros nodos como texto.

### Pregunta 30 · **B**
`textContent` trata el contenido como texto literal.

### Pregunta 31 · **A**
Inyectar contenido no confiable con `innerHTML` puede habilitar XSS.

### Pregunta 32 · **C**
`toggle` alterna presencia de una clase.

### Pregunta 33 · **A**
`target` es el origen del evento.

### Pregunta 34 · **D**
`currentTarget` es el nodo cuyo listener se esta ejecutando.

### Pregunta 35 · **A**
`preventDefault` cancela accion por defecto cuando el evento es cancelable.

### Pregunta 36 · **C**
`stopPropagation` detiene propagacion, no la accion por defecto.

### Pregunta 37 · **D**
La secuencia clasica es capturing -> target -> bubbling.

### Pregunta 38 · **B**
Delegacion: un listener en ancestro que discrimina objetivos descendientes.

### Pregunta 39 · **A**
`DOMContentLoaded` dispara cuando DOM esta construido.

### Pregunta 40 · **C**
`getComputedStyle` obtiene estilos finales calculados.

### Pregunta 41 · **D**
Call Stack sigue orden LIFO.

### Pregunta 42 · **B**
`setTimeout(..., 0)` no es inmediato; agenda tarea para mas adelante.

### Pregunta 43 · **A**
Handlers de Promise se ejecutan como microtasks.

### Pregunta 44 · **D**
Toda Promise inicia en `pending`.

### Pregunta 45 · **B**
`Promise.all` rechaza si cualquiera rechaza.

### Pregunta 46 · **D**
`allSettled` espera todas y devuelve estados individuales.

### Pregunta 47 · **A**
`Promise.any` se cumple con la primera fulfilled.

### Pregunta 48 · **C**
Si todas rechazan en `any`, rechaza con `AggregateError`.

### Pregunta 49 · **A**
Funcion `async` siempre retorna Promise.

### Pregunta 50 · **D**
`await` suspende esa funcion async, no bloquea toda la plataforma.

### Pregunta 51 · **D**
`fetch` no falla por 404/500 por si solo; revisar `ok`/`status`.

### Pregunta 52 · **C**
`response.json()` devuelve Promise de parseo.

### Pregunta 53 · **A**
`text()` lee cuerpo como texto.

### Pregunta 54 · **D**
`AbortController` permite cancelar fetch via `signal`.

### Pregunta 55 · **A**
El default export se importa sin llaves y con nombre a eleccion.

### Pregunta 56 · **C**
Los modulos tienen scope propio y strict mode implicito.

### Pregunta 57 · **A**
`getItem` devuelve `null` cuando no existe clave.

### Pregunta 58 · **D**
Web Storage persiste cadenas.

### Pregunta 59 · **A**
`sessionStorage` vive en sesion de pestana/contexto, no como persistencia larga.

### Pregunta 60 · **C**
`HttpOnly` evita acceso por JavaScript (`document.cookie`).

### Pregunta 61 · **A**
Optional chaining protege ante `null`/`undefined`.

### Pregunta 62 · **B**
Nullish coalescing solo actua con valores nullish.

### Pregunta 63 · **A**
`WeakMap` usa claves con referencia debil y no esta orientado a enumeracion total.

### Pregunta 64 · **C**
`WeakSet` mantiene objetos de forma debil y no ofrece enumeracion completa tipica.

### Pregunta 65 · **D**
XSS y CSRF son ataques distintos en objetivo y mecanica.

### Pregunta 66 · **D**
Validar en cliente ayuda UX, pero servidor debe validar seguridad y reglas.

### Pregunta 67 · **A**
`pushState` agrega entrada; `replaceState` sustituye la actual.

### Pregunta 68 · **B**
`URLSearchParams` simplifica operar parametros de query.

### Pregunta 69 · **D**
`location.replace` navega reemplazando entrada actual en historial.

### Pregunta 70 · **C**
Cookies HttpOnly y diseno de sesion pueden reducir exposicion a robo por JS, segun arquitectura.

---

# ✅ CIERRE DE REVISION

Clasifica cada fallo como desconocimiento, confusion entre conceptos cercanos o lectura apresurada de codigo. Refuerza primero los bloques con peor porcentaje antes de repetir el simulacro completo.