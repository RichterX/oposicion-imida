# Tarjetas - Bloque 05 - 5.7 JavaScript

Formato:
P: Pregunta
R: Respuesta

---

## 5.7 JavaScript

P: Diferencia rapida entre == y ===?
R: == permite coercion; === compara tipo y valor estrictamente.

P: Que diferencia hay entre || y ??
R: || cae con falsy; ?? solo cae con null/undefined.

P: Que hace optional chaining (?.)?
R: Evita error de acceso/llamada cuando valor intermedio es nullish.

P: Diferencia entre map y forEach?
R: map devuelve nuevo array transformado; forEach itera para efectos secundarios.

P: Diferencia entre slice y splice?
R: slice no muta; splice muta el array original.

P: Que diferencia hay entre querySelector y querySelectorAll?
R: querySelector devuelve primer match; querySelectorAll devuelve NodeList de todos.

P: textContent o innerHTML para texto no confiable?
R: textContent, para evitar interpretar HTML y reducir riesgo XSS.

P: Diferencia entre preventDefault y stopPropagation?
R: preventDefault cancela accion por defecto; stopPropagation detiene propagacion.

P: Orden simplificado del event loop relevante para examen?
R: Sincrono -> microtasks (Promises) -> tasks (timers/eventos).

P: Que significa que async siempre devuelve Promise?
R: Incluso si hace return de valor simple, se envuelve en Promise resuelta.

P: fetch falla por 404 automaticamente?
R: No; hay que revisar response.ok o response.status.

P: Diferencia entre Promise.all y Promise.allSettled?
R: all falla si una rechaza; allSettled espera todas y reporta estado.

P: Que hace Promise.any si todas rechazan?
R: Rechaza con AggregateError.

P: Diferencia conceptual entre localStorage y sessionStorage?
R: localStorage persiste entre sesiones; sessionStorage vive en sesion de pestana/contexto.

P: XSS, CSRF y CORS son lo mismo?
R: No; son conceptos distintos de seguridad web.

---

## Tarjetas de repaso transversal (5.7)

P: Trampa de setTimeout(fn, 0)?
R: No ejecuta inmediatamente; agenda task para mas tarde.

P: Trampa target vs currentTarget?
R: target es origen del evento; currentTarget es nodo con listener en ejecucion.

P: Objetivo final de 5.7?
R: Dominar JS moderno, DOM, asincronia y seguridad para resolver preguntas teoricas y de codigo.
