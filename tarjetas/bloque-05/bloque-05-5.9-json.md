# Tarjetas - Bloque 05 - 5.9 JSON

Formato:
P: Pregunta
R: Respuesta

---

## 5.9 JSON

P: Que significa JSON?
R: JavaScript Object Notation.

P: Que tipos basicos admite JSON?
R: object, array, string, number, boolean y null.

P: JSON admite comentarios?
R: No, en JSON estandar no se admiten comentarios.

P: Como deben ir los nombres de propiedades en JSON?
R: Entre comillas dobles.

P: Diferencia entre objeto JS y string JSON?
R: Objeto JS es estructura en memoria; JSON es texto serializado.

P: Que hace JSON.parse()?
R: Convierte string JSON valido a valor JavaScript.

P: Que hace JSON.stringify()?
R: Convierte valor JavaScript serializable a string JSON.

P: Que ocurre con undefined, funciones o Symbol al serializar?
R: No tienen representacion JSON directa y pueden omitirse/transformarse segun contexto.

P: Por que JSON es tan usado en APIs?
R: Es ligero, legible y ampliamente soportado en clientes/servidores.

P: Riesgo habitual al parsear entrada externa?
R: Suponer estructura correcta sin validar campos obligatorios y tipos.

P: Que es un schema JSON (conceptualmente)?
R: Contrato de validacion para estructura y restricciones de documentos JSON.

P: Diferencia entre null y clave ausente en JSON?
R: null es valor explicito; ausencia implica que la propiedad no existe.

P: Que ventaja aporta versionar contratos JSON en APIs?
R: Permite evolucionar sin romper consumidores existentes.

P: Error comun en examen?
R: Confundir JSON valido con objeto literal JS no serializado.

---

## Tarjetas de repaso transversal (5.9)

P: Regla minima al consumir JSON de terceros?
R: Parsear, validar y manejar errores de forma defensiva.

P: Regla minima al publicar JSON?
R: Definir contrato estable y documentar campos, tipos y errores.

P: Objetivo final de 5.9?
R: Manejar intercambio de datos fiable entre frontend, backend e integraciones.
