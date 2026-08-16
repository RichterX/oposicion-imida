# 🧩 MISIÓN 10 · LA API
## «El nuevo lenguaje de GESTIONA»

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.9 JSON  
> **Tipo:** Misión práctica  
> **Dificultad:** 🟠 → 🔴  
> **Continuidad:** Misiones 7, 8 y 9 · GESTIONA

---

# 🎯 1. OBJETIVO

GESTIONA ha decidido abandonar progresivamente el sistema XML heredado.

El nuevo sistema utilizará:

```text
JSON
+
HTTP
+
API REST
+
JSON Schema
```

Y aquí aparece una ventaja para ti:

> Esta misión conecta directamente con conceptos que ya has utilizado trabajando con Laravel, APIs y Postman.

La misión no pretende convertirte en experto en diseño de APIs en una tarde.

Queremos que seas capaz de:

```text
entender JSON
        ↓
diseñar estructuras
        ↓
consumir una API
        ↓
interpretar HTTP
        ↓
diseñar endpoints REST
        ↓
validar JSON
        ↓
manejar errores
```

---

# 🏢 2. ESCENARIO

La nueva versión de GESTIONA tendrá un backend accesible mediante una API.

El frontend realizará peticiones HTTP como:

```text
GET    /api/equipos
GET    /api/equipos/EQ01
POST   /api/equipos
PUT    /api/equipos/EQ01
PATCH  /api/equipos/EQ01
DELETE /api/equipos/EQ01
```

Las respuestas utilizarán:

```text
application/json
```

---

# 📦 3. PARTE I · JSON BÁSICO

Representa este equipo mediante JSON:

```text
ID: EQ01
Tipo: ordenador
Marca: Dell
Modelo: OptiPlex 7090
Estado: activo
Usuario: E01
```

Debes crear un objeto JSON válido.

---

# 🧪 4. REGLAS JSON

Comprueba que tu documento respeta:

```text
□ Las claves utilizan comillas dobles.

□ Las cadenas utilizan comillas dobles.

□ No existen comas finales.

□ Los objetos utilizan { }.

□ Los arrays utilizan [ ].

□ null es válido.

□ true y false no llevan comillas.

□ Los números no llevan comillas si realmente son números.
```

---

# 🧩 5. TIPOS JSON

Explica y proporciona un ejemplo de:

```text
string
number
boolean
null
object
array
```

---

# 📚 6. ARRAY DE EQUIPOS

Crea un JSON que represente estos tres equipos:

```text
EQ01
Dell OptiPlex 7090
Ordenador
Activo

EQ02
LG UltraFine
Monitor
Activo

EQ03
HP LaserJet
Impresora
Averiado
```

El resultado debe ser un:

```text
array de objetos
```

---

# 👤 7. OBJETOS ANIDADOS

Ahora modifica el modelo.

En lugar de:

```json
{
    "usuario": "E01"
}
```

representa:

```text
usuario
├── id
├── nombre
└── email
```

Esto debe demostrar que comprendes que un objeto JSON puede contener otros objetos.

---

# 🔄 8. ARRAY ANIDADO

Representa un equipo que tenga:

```text
incidencias
```

con:

```text
I01
Impresora no responde
alta
abierta

I05
Cambio de tóner
baja
cerrada
```

La estructura debe contener:

```text
equipo
└── incidencias[]
```

---

# 🧠 9. JSON VS XML

Explica al menos cinco diferencias entre:

```text
JSON
```

y:

```text
XML
```

Considera:

```text
sintaxis
verbosidad
atributos
arrays
tipos de datos
namespaces
uso habitual
```

---

# 📄 10. PARTE II · HTTP

Ahora entra en escena HTTP.

Explica la diferencia entre:

```text
request
```

y:

```text
response
```

Una petición contiene conceptualmente:

```text
método
URL
headers
body
```

Una respuesta contiene:

```text
status code
headers
body
```

---

# 🚦 11. MÉTODOS HTTP

Relaciona:

```text
GET
POST
PUT
PATCH
DELETE
```

con su finalidad habitual.

---

# 🧠 12. IDEMPOTENCIA

Explica qué significa que una operación sea:

```text
idempotente
```

y razona si estos métodos son normalmente idempotentes:

```text
GET
PUT
PATCH
DELETE
POST
```

No basta con memorizar una tabla. Explica el concepto.

---

# 🔢 13. STATUS CODES

Explica el significado general de:

```text
200
201
204
400
401
403
404
409
422
429
500
```

Agrúpalos por:

```text
2xx
4xx
5xx
```

---

# 🧠 14. DIFERENCIA 401 / 403

Explica la diferencia entre:

```text
401 Unauthorized
```

y:

```text
403 Forbidden
```

Pista:

```text
autenticación
vs
autorización
```

---

# 🔎 15. DIFERENCIA 400 / 422

Explica una situación en la que utilizarías:

```text
400 Bad Request
```

y otra en la que utilizarías:

```text
422 Unprocessable Content
```

Ten en cuenta que las convenciones concretas pueden variar según la API.

---

# 🌐 16. PARTE III · DISEÑO REST

Diseña una API para GESTIONA.

Debe permitir:

```text
consultar equipos
consultar un equipo
crear equipos
modificar equipos
eliminar equipos

consultar incidencias
consultar una incidencia
crear incidencias
modificar incidencias
```

---

# 🛣️ 17. ENDPOINTS

Propón los endpoints.

Una posible estructura:

```text
GET    /api/equipos
GET    /api/equipos/{id}
POST   /api/equipos
PUT    /api/equipos/{id}
PATCH  /api/equipos/{id}
DELETE /api/equipos/{id}

GET    /api/incidencias
GET    /api/incidencias/{id}
POST   /api/incidencias
PATCH  /api/incidencias/{id}
```

Puedes proponer una variante si la justificas.

---

# 🚫 18. ANTI-PATRONES

Explica por qué estos endpoints son menos apropiados para una API REST:

```text
GET /api/getEquipos
POST /api/createEquipo
POST /api/deleteEquipo
GET /api/equipo?id=EQ01
```

No significa que una API no pueda funcionar así.

La pregunta es:

```text
¿por qué no expresan tan bien el recurso y la operación?
```

---

# 📦 19. PARTE IV · REQUEST JSON

Diseña el body JSON de:

```text
POST /api/equipos
```

Debe permitir crear:

```text
tipo
marca
modelo
estado
usuario
```

Decide qué campos deberían ser:

```text
obligatorios
opcionales
```

y justifica.

---

# 🧪 20. VALIDACIÓN

Supón que llega:

```json
{
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "",
    "estado": "banana"
}
```

Identifica los problemas.

---

# 🔒 21. REGLAS DE NEGOCIO

Define reglas para:

```text
tipo
estado
marca
modelo
usuario
```

Por ejemplo:

```text
tipo
→ ordenador
→ monitor
→ impresora
→ router
→ telefono

estado
→ activo
→ averiado
→ baja
```

Puedes proponer valores adicionales si están justificados.

---

# 🧠 22. PARTE V · JSON SCHEMA

Crea un JSON Schema que valide un equipo.

Debe contemplar:

```text
type
marca
modelo
estado
usuario
```

Utiliza como mínimo:

```text
type
properties
required
```

---

# 🔢 23. JSON SCHEMA · ENUM

Utiliza:

```text
enum
```

para restringir:

```text
tipo
```

y:

```text
estado
```

---

# 🔒 24. JSON SCHEMA · ADDITIONALPROPERTIES

Decide si quieres permitir:

```text
camello_volador
```

como propiedad adicional.

En este ejercicio:

```text
NO
```

Por tanto, utiliza:

```json
"additionalProperties": false
```

y explica qué efecto tiene.

---

# 🧪 25. VALIDACIÓN DE JSON

Determina si estos objetos son válidos respecto al esquema que hayas diseñado.

### A

```json
{
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "OptiPlex 7090",
    "estado": "activo",
    "usuario": "E01"
}
```

### B

```json
{
    "tipo": "platano",
    "marca": "Dell",
    "modelo": "X",
    "estado": "activo"
}
```

### C

```json
{
    "tipo": "monitor",
    "marca": "LG",
    "modelo": "UltraFine",
    "estado": "activo",
    "camello_volador": true
}
```

### D

```json
{
    "tipo": "monitor",
    "marca": "LG"
}
```

Justifica cada respuesta.

---

# 🔄 26. PARTE VI · RESPUESTAS DE API

Diseña una respuesta para:

```text
GET /api/equipos/EQ01
```

Debe incluir:

```text
id
tipo
marca
modelo
estado
usuario
```

---

# 📚 27. COLECCIONES

Diseña la respuesta de:

```text
GET /api/equipos
```

Debe representar:

```text
varios equipos
```

Puedes utilizar:

```text
array directo
```

o una estructura con metadatos:

```json
{
    "data": [],
    "meta": {}
}
```

Justifica tu decisión.

---

# 📄 28. PAGINACIÓN

La API debe devolver:

```text
1000 equipos
```

Explica por qué no es recomendable devolverlos todos en una única respuesta.

Diseña una solución mediante:

```text
?page=2&per_page=20
```

y decide qué información incluirías en:

```text
meta
```

---

# 🔎 29. FILTROS

Diseña peticiones para:

```text
equipos activos

equipos averiados

ordenadores

equipos de Dell

equipos asignados a E01
```

Por ejemplo:

```text
GET /api/equipos?estado=activo
```

---

# ↕️ 30. ORDENACIÓN

Diseña una forma de pedir:

```text
equipos ordenados por marca
```

y otra para:

```text
orden descendente
```

Explica tu convención.

---

# 🔍 31. BÚSQUEDA

Diseña una petición para buscar equipos cuyo:

```text
marca o modelo
```

contenga:

```text
Dell
```

Puedes utilizar:

```text
?q=Dell
```

o una convención alternativa.

---

# 🚨 32. PARTE VII · ERRORES DE API

Diseña una respuesta para:

```text
POST /api/equipos
```

cuando falta:

```text
marca
```

y:

```text
estado = banana
```

La respuesta debe contener:

```text
status code
mensaje general
errores por campo
```

---

# 🧠 33. FORMATO DE ERROR

Una posible estructura:

```json
{
    "message": "Los datos enviados no son válidos.",
    "errors": {
        "marca": [
            "El campo marca es obligatorio."
        ],
        "estado": [
            "El estado seleccionado no es válido."
        ]
    }
}
```

Puedes diseñar una estructura diferente si es consistente.

---

# 🔐 34. PARTE VIII · AUTENTICACIÓN

GESTIONA necesita proteger:

```text
POST
PUT
PATCH
DELETE
```

Explica la diferencia entre:

```text
autenticación
```

y:

```text
autorización
```

---

# 🎟️ 35. BEARER TOKEN

Supón que la API utiliza un token.

Construye el header:

```text
Authorization: Bearer <token>
```

Explica qué función tiene.

---

# 📦 36. CONTENT-TYPE

¿Qué significa:

```text
Content-Type: application/json
```

?

¿Y qué diferencia conceptual existe con:

```text
Accept: application/json
```

---

# 🧠 37. PARTE IX · POSTMAN

Simula que vas a probar:

```text
POST /api/incidencias
```

en Postman.

Define:

```text
URL
método
headers
body
```

El body debe incluir:

```text
titulo
descripcion
equipo
prioridad
estado
```

---

# 🧪 38. RAW VS FORM-DATA

Explica por qué una API JSON normalmente espera:

```text
raw JSON
```

cuando:

```text
Content-Type: application/json
```

y no:

```text
multipart/form-data
```

Explica también cuándo tendría sentido utilizar:

```text
multipart/form-data
```

---

# 🔄 39. PARTE X · HTTP + LARAVEL

Ahora conecta el ejercicio con tu experiencia.

Supón que tienes:

```text
POST /api/equipos
```

en Laravel.

Explica conceptualmente el recorrido:

```text
Cliente
  ↓
HTTP Request
  ↓
Router
  ↓
Controller
  ↓
Validation
  ↓
Service / lógica
  ↓
Model / Repository
  ↓
Database
  ↓
Response JSON
  ↓
Cliente
```

Indica qué responsabilidad tendría cada capa.

---

# 🧠 40. API RESOURCE

Explica para qué podría utilizarse en Laravel algo conceptualmente equivalente a:

```text
EquipoResource
```

y qué ventaja aporta frente a devolver directamente el modelo.

---

# 📄 41. PARTE XI · JSON VS SERIALIZACIÓN

Explica la diferencia entre:

```text
objeto PHP
```

y:

```text
JSON
```

y qué significa:

```text
serializar
```

---

# 🧪 42. DESAFÍO · PAGINACIÓN COMPLETA

Diseña una respuesta para:

```text
GET /api/equipos?page=2&per_page=20
```

que contenga:

```text
data
current_page
per_page
total
last_page
```

Puedes añadir:

```text
from
to
```

y enlaces si quieres.

---

# 🏆 43. DESAFÍO FINAL · DISEÑO COMPLETO

Diseña la API completa de:

```text
GESTIONA
```

para:

```text
equipos
empleados
departamentos
incidencias
```

Debes entregar:

```text
1. Endpoints

2. Métodos HTTP

3. Status codes

4. Ejemplos JSON

5. JSON Schema de al menos un recurso

6. Formato de errores

7. Paginación

8. Filtros

9. Autenticación

10. Justificación del diseño
```

---

# ⭐ 44. DESAFÍO EXTRA · DISEÑO DE UN RECURSO

Añade:

```text
GET /api/equipos/EQ01
```

y decide si la respuesta debe contener:

```json
{
    "id": "EQ01",
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "OptiPlex 7090",
    "usuario": {
        "id": "E01",
        "nombre": "Pedro"
    }
}
```

o:

```json
{
    "id": "EQ01",
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "OptiPlex 7090",
    "usuario_id": "E01"
}
```

Explica:

```text
ventajas
inconvenientes
```

de cada opción.

---

# 🧠 45. PREGUNTAS DE REFLEXIÓN

Responde sin consultar el temario:

### 1.

¿Qué diferencia hay entre JSON y JavaScript?

### 2.

¿Qué tipos de datos admite JSON?

### 3.

¿Qué diferencia existe entre objeto y array?

### 4.

¿Qué es HTTP?

### 5.

¿Qué diferencia hay entre request y response?

### 6.

¿Qué significa REST?

### 7.

¿Qué es un recurso?

### 8.

¿Qué diferencia hay entre PUT y PATCH?

### 9.

¿Qué significa idempotencia?

### 10.

¿Qué diferencia hay entre 401 y 403?

### 11.

¿Qué diferencia hay entre 404 y 422?

### 12.

¿Qué significa `Content-Type`?

### 13.

¿Qué significa `Accept`?

### 14.

¿Qué hace JSON Schema?

### 15.

¿Qué hace `additionalProperties: false`?

### 16.

¿Qué es paginación?

### 17.

¿Qué diferencia hay entre autenticación y autorización?

### 18.

¿Qué significa `Bearer`?

### 19.

¿Qué es serializar?

### 20.

¿Por qué una API debería devolver errores estructurados?

---

# 🧠 46. CHECKLIST

Antes de terminar:

```text
□ JSON
□ tipos JSON
□ objetos
□ arrays
□ objetos anidados
□ JSON vs XML
□ HTTP
□ request
□ response
□ GET
□ POST
□ PUT
□ PATCH
□ DELETE
□ idempotencia
□ status codes
□ REST
□ recursos
□ endpoints
□ filtros
□ búsqueda
□ ordenación
□ paginación
□ JSON Schema
□ required
□ enum
□ additionalProperties
□ errores
□ autenticación
□ autorización
□ Bearer
□ Content-Type
□ Accept
□ Postman
□ raw JSON
□ multipart/form-data
□ serialización
□ API Resource
□ integración con Laravel
```

---

# 📊 47. CRITERIOS DE EVALUACIÓN

| Área | Peso |
|---|---:|
| JSON y estructuras | 10% |
| HTTP y métodos | 15% |
| Status codes | 10% |
| Diseño REST | 15% |
| JSON Schema | 15% |
| Errores y validación | 10% |
| Autenticación / headers | 10% |
| Integración conceptual con Laravel | 10% |
| Justificación técnica | 5% |
| **TOTAL** | **100%** |

---

# 🏁 48. OBJETIVO FINAL

Al terminar esta misión deberías poder mirar una petición como:

```http
POST /api/equipos
Content-Type: application/json
Authorization: Bearer ...
```

con:

```json
{
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "OptiPlex 7090",
    "estado": "activo",
    "usuario": "E01"
}
```

y explicar mentalmente:

```text
HTTP
 ↓
POST
 ↓
recurso equipos
 ↓
JSON
 ↓
Content-Type
 ↓
autenticación
 ↓
validación
 ↓
lógica de aplicación
 ↓
persistencia
 ↓
JSON Response
 ↓
HTTP Status
```

Ese es el objetivo real de la misión.

---

# 🏁 49. CIERRE DEL BLOQUE DE MISIONES

Con esta misión terminamos la serie práctica del gran:

# BLOQUE 5 · PROGRAMACIÓN

Hemos recorrido:

```text
Python
Java
POO
UML
HTML
CSS
JavaScript
XML
JSON
```

y hemos intentado convertir el temario en algo más útil que una colección de definiciones:

```text
concepto
   ↓
ejercicio
   ↓
problema
   ↓
decisión técnica
   ↓
aplicación
```

---

# 🔮 SIGUIENTE PASO

Una vez terminadas las cuatro misiones:

```text
Misión 7
Misión 8
Misión 9
Misión 10
```

podrás entregármelas **una a una** para una corrección individual.

Después podremos hacer:

```text
CORRECCIÓN DE MISIONES
        ↓
REPASO DE ERRORES
        ↓
SIMULACRO GENERAL
        ↓
CORRECCIÓN
        ↓
REPASO FINAL DEL BLOQUE 5
```

Y ahí tendremos una visión bastante más fiable de qué partes del monstruo siguen intentando morder. 🐉

---

# 🏁 FIN DE MISIÓN 10
