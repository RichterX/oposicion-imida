# 📝 MISIÓN 10 · CORRECCIÓN
## «La API»

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.9 JSON  
> **Misión:** 10  
> **Objetivo:** Diseñar, consumir y razonar sobre APIs HTTP/REST que intercambian JSON.

---

# 1. CORRECCIÓN GENERAL

Esta misión admite distintas soluciones correctas, especialmente en:

```text
diseño REST
estructura de respuestas
paginación
formato de errores
modelado JSON
```

La solución de referencia sirve para comprobar que:

```text
✓ el JSON es válido
✓ HTTP está bien interpretado
✓ los recursos están bien modelados
✓ los métodos HTTP se utilizan con sentido
✓ los status codes son coherentes
✓ JSON Schema expresa las restricciones
✓ los errores son estructurados
✓ autenticación y autorización no se confunden
✓ el diseño está justificado
```

---

# 📦 2. PARTE I · JSON BÁSICO

Una solución válida para representar el equipo:

```json
{
    "id": "EQ01",
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "OptiPlex 7090",
    "estado": "activo",
    "usuario": "E01"
}
```

Todos los nombres de propiedad son cadenas.

---

# 🧠 3. TIPOS JSON

JSON dispone de seis categorías fundamentales de valores:

```text
string
number
object
array
boolean
null
```

Ejemplos:

```json
{
    "nombre": "Pedro",
    "edad": 30,
    "activo": true,
    "usuario": null,
    "direccion": {
        "ciudad": "Murcia"
    },
    "roles": [
        "admin",
        "tecnico"
    ]
}
```

---

# 📚 4. ARRAY DE EQUIPOS

Una solución:

```json
[
    {
        "id": "EQ01",
        "tipo": "ordenador",
        "marca": "Dell",
        "modelo": "OptiPlex 7090",
        "estado": "activo"
    },
    {
        "id": "EQ02",
        "tipo": "monitor",
        "marca": "LG",
        "modelo": "UltraFine",
        "estado": "activo"
    },
    {
        "id": "EQ03",
        "tipo": "impresora",
        "marca": "HP",
        "modelo": "LaserJet",
        "estado": "averiado"
    }
]
```

---

# 👤 5. OBJETOS ANIDADOS

Una representación válida:

```json
{
    "id": "EQ01",
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "OptiPlex 7090",
    "estado": "activo",
    "usuario": {
        "id": "E01",
        "nombre": "Pedro",
        "email": "pedro@example.com"
    }
}
```

---

# 🔄 6. ARRAY ANIDADO

Ejemplo:

```json
{
    "id": "EQ03",
    "tipo": "impresora",
    "marca": "HP",
    "modelo": "LaserJet",
    "estado": "averiado",
    "incidencias": [
        {
            "id": "I01",
            "titulo": "Impresora no responde",
            "prioridad": "alta",
            "estado": "abierta"
        },
        {
            "id": "I05",
            "titulo": "Cambio de tóner",
            "prioridad": "baja",
            "estado": "cerrada"
        }
    ]
}
```

---

# 🔍 7. JSON VS XML

Diferencias importantes:

| JSON | XML |
|---|---|
| Sintaxis generalmente más compacta | Más verboso |
| Arrays son una construcción nativa | Los arrays se modelan mediante elementos repetidos |
| Tipos básicos integrados | Tipado depende de mecanismos como XSD |
| Muy habitual en APIs web | Muy utilizado en sistemas documentales, integración y sistemas heredados |
| No utiliza atributos XML | Puede utilizar atributos |
| Namespaces no forman parte del modelo JSON | XML dispone de namespaces |

No debe concluirse que:

```text
JSON = mejor siempre
XML = obsoleto
```

Son tecnologías con características y contextos de uso diferentes.

---

# 🌐 8. PARTE II · HTTP

## Request

Una petición HTTP puede contener:

```text
método
URL
headers
body
```

Ejemplo:

```http
POST /api/equipos HTTP/1.1
Content-Type: application/json
Authorization: Bearer abc123
```

seguido de un body JSON.

---

## Response

Una respuesta puede contener:

```text
status code
headers
body
```

Ejemplo:

```http
HTTP/1.1 201 Created
Content-Type: application/json
```

seguido de un JSON.

---

# 🚦 9. MÉTODOS HTTP

| Método | Uso habitual |
|---|---|
| GET | Obtener/retrieval de recursos |
| POST | Crear/recurso o provocar una operación no idempotente |
| PUT | Crear/reemplazar una representación de un recurso en una URI conocida |
| PATCH | Modificación parcial |
| DELETE | Eliminar |

### Importante

Estas definiciones son semánticas de HTTP.

No debemos reducirlas simplemente a:

```text
GET = SELECT
POST = INSERT
PUT = UPDATE
DELETE = DELETE
```

porque HTTP no es SQL.

---

# 🧠 10. IDEMPOTENCIA

Una operación idempotente produce el mismo efecto sobre el estado del recurso cuando se repite varias veces con la misma petición.

Por especificación HTTP:

```text
GET
PUT
DELETE
```

son métodos idempotentes.

`POST` no lo es por defecto.

### ¿Y PATCH?

Aquí hay una sutileza importante:

```text
PATCH
```

**no está definido por HTTP como necesariamente idempotente**.

Una implementación concreta de PATCH puede diseñarse de forma idempotente, pero no debemos afirmar:

```text
PATCH siempre es idempotente
```

como regla general.

---

# 🔢 11. STATUS CODES

## 2xx · Éxito

### 200 OK

La petición se ha procesado correctamente.

### 201 Created

Se ha creado un recurso.

Muy apropiado para:

```text
POST /api/equipos
```

cuando se crea correctamente un equipo.

### 204 No Content

La petición se procesa correctamente pero no se devuelve contenido en el body.

Un ejemplo habitual:

```text
DELETE /api/equipos/EQ01
→ 204
```

---

# ⚠️ 12. 4xx · ERROR DEL CLIENTE

### 400 Bad Request

La petición es inválida o malformada en el sentido general.

### 401 Unauthorized

La petición necesita autenticación o las credenciales proporcionadas no permiten autenticar correctamente al cliente.

### 403 Forbidden

El servidor entiende la petición pero rechaza el acceso.

### 404 Not Found

El recurso solicitado no se encuentra.

### 409 Conflict

Existe un conflicto con el estado actual del recurso.

Ejemplo:

```text
intentar crear un equipo con un identificador
que ya está utilizado
```

### 422 Unprocessable Content

La petición tiene una estructura comprensible, pero el contenido no supera las reglas de validación/aplicación.

Por ejemplo:

```json
{
    "estado": "banana"
}
```

si `estado` solo admite ciertos valores.

### 429 Too Many Requests

El cliente ha realizado demasiadas peticiones en un periodo determinado.

---

# 🔥 13. 5xx · ERROR DEL SERVIDOR

### 500 Internal Server Error

Error interno no controlado o genérico del servidor.

---

# 🔐 14. 401 VS 403

La distinción fundamental:

```text
401
→ problema de autenticación

403
→ autenticado o identificado, pero sin permisos suficientes
```

Ejemplo:

```text
401
→ no has proporcionado credenciales válidas

403
→ eres un usuario válido, pero no puedes eliminar equipos
```

---

# 🧪 15. 400 VS 422

No existe una única convención universal utilizada por todas las APIs.

Una interpretación habitual:

```text
400
→ petición mal formada o inválida en términos generales

422
→ sintaxis entendible, pero datos que no cumplen
las reglas de validación
```

Por ejemplo:

```text
POST /api/equipos

{
    "tipo": "ordenador",
    "estado": "banana"
}
```

puede producir:

```text
422
```

si el formato JSON es correcto pero el valor viola una regla de validación.

---

# 🛣️ 16. PARTE III · DISEÑO REST

Una API razonable:

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

Esto modela recursos:

```text
equipos
incidencias
```

en lugar de convertir los verbos de las operaciones en nombres de URL.

---

# 🚫 17. ANTI-PATRONES REST

Ejemplo:

```text
GET /api/getEquipos
```

El verbo ya está expresado mediante:

```text
GET
```

Por tanto:

```text
/api/equipos
```

es una representación más orientada al recurso.

---

```text
POST /api/createEquipo
```

Mejor:

```text
POST /api/equipos
```

---

```text
POST /api/deleteEquipo
```

Mejor:

```text
DELETE /api/equipos/{id}
```

---

```text
GET /api/equipo?id=EQ01
```

Puede funcionar, pero si `EQ01` identifica un recurso concreto, una ruta más RESTful es:

```text
GET /api/equipos/EQ01
```

---

# 📦 18. PARTE IV · REQUEST JSON

Una solución:

```json
{
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "OptiPlex 7090",
    "estado": "activo",
    "usuario": "E01"
}
```

Una decisión razonable:

```text
tipo
→ obligatorio

marca
→ obligatorio

modelo
→ obligatorio

estado
→ obligatorio

usuario
→ opcional
```

La razón para `usuario` opcional es que un equipo puede existir sin estar asignado.

---

# 🧪 19. VALIDACIÓN

Tenemos:

```json
{
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "",
    "estado": "banana"
}
```

Problemas:

```text
modelo
→ vacío

estado
→ valor no permitido
```

Además:

```text
usuario
```

puede faltar si lo definimos como opcional.

---

# 🔒 20. REGLAS DE NEGOCIO

Una posible definición:

```text
tipo:
ordenador
monitor
impresora
router
telefono
```

```text
estado:
activo
averiado
baja
```

Y:

```text
marca
→ obligatoria

modelo
→ obligatorio

usuario
→ opcional
```

En una aplicación real podrían existir más reglas:

```text
un equipo dado de baja no debería poder asignarse
a un usuario

un equipo inexistente no puede aparecer
en una incidencia
```

Estas ya son reglas de negocio, no simplemente reglas de sintaxis JSON.

---

# 🧠 21. PARTE V · JSON SCHEMA

Una solución sencilla:

```json
{
    "$schema": "https://json-schema.org/draft/2020-12/schema",
    "title": "Equipo",
    "type": "object",
    "properties": {
        "tipo": {
            "type": "string",
            "enum": [
                "ordenador",
                "monitor",
                "impresora",
                "router",
                "telefono"
            ]
        },
        "marca": {
            "type": "string"
        },
        "modelo": {
            "type": "string"
        },
        "estado": {
            "type": "string",
            "enum": [
                "activo",
                "averiado",
                "baja"
            ]
        },
        "usuario": {
            "type": "string"
        }
    },
    "required": [
        "tipo",
        "marca",
        "modelo",
        "estado"
    ],
    "additionalProperties": false
}
```

---

# 🔢 22. `enum`

Permite restringir un valor a un conjunto determinado.

Ejemplo:

```json
"estado": {
    "type": "string",
    "enum": [
        "activo",
        "averiado",
        "baja"
    ]
}
```

Por tanto:

```text
activo
✓

averiado
✓

banana
✗
```

---

# 🔒 23. `additionalProperties`

Con:

```json
"additionalProperties": false
```

no permitimos propiedades que no estén definidas en:

```text
properties
```

Por tanto:

```json
{
    "tipo": "monitor",
    "marca": "LG",
    "modelo": "UltraFine",
    "estado": "activo",
    "camello_volador": true
}
```

es inválido respecto al esquema.

---

# 🧪 24. VALIDACIÓN DE A, B, C Y D

## A

```json
{
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "OptiPlex 7090",
    "estado": "activo",
    "usuario": "E01"
}
```

### Resultado:

```text
✓ Válido
```

---

## B

```json
{
    "tipo": "platano",
    "marca": "Dell",
    "modelo": "X",
    "estado": "activo"
}
```

### Resultado:

```text
✗ Inválido
```

Porque:

```text
tipo
```

no pertenece al `enum`.

---

## C

```json
{
    "tipo": "monitor",
    "marca": "LG",
    "modelo": "UltraFine",
    "estado": "activo",
    "camello_volador": true
}
```

### Resultado:

```text
✗ Inválido
```

porque:

```text
additionalProperties = false
```

---

## D

```json
{
    "tipo": "monitor",
    "marca": "LG"
}
```

### Resultado:

```text
✗ Inválido
```

porque faltan:

```text
modelo
estado
```

---

# 🔄 25. PARTE VI · RESPUESTA DE UN RECURSO

Una posible respuesta:

```json
{
    "id": "EQ01",
    "tipo": "ordenador",
    "marca": "Dell",
    "modelo": "OptiPlex 7090",
    "estado": "activo",
    "usuario": "E01"
}
```

Con:

```text
HTTP/1.1 200 OK
Content-Type: application/json
```

---

# 📚 26. COLECCIONES

Dos diseños razonables.

### Opción A

```json
[
    {
        "id": "EQ01",
        "tipo": "ordenador"
    },
    {
        "id": "EQ02",
        "tipo": "monitor"
    }
]
```

Ventaja:

```text
simple
```

---

### Opción B

```json
{
    "data": [
        {
            "id": "EQ01",
            "tipo": "ordenador"
        },
        {
            "id": "EQ02",
            "tipo": "monitor"
        }
    ],
    "meta": {
        "total": 2
    }
}
```

Ventaja:

```text
permite incorporar metadatos
```

Especialmente útil cuando existe:

```text
paginación
filtros
totales
enlaces
```

No existe una única estructura universal obligatoria.

---

# 📄 27. PAGINACIÓN

No es recomendable devolver:

```text
1000+
```

registros siempre en una respuesta porque puede aumentar:

```text
memoria
tiempo de procesamiento
tamaño de respuesta
latencia
```

Una petición:

```text
GET /api/equipos?page=2&per_page=20
```

podría producir:

```json
{
    "data": [
        ...
    ],
    "meta": {
        "current_page": 2,
        "per_page": 20,
        "total": 1000,
        "last_page": 50,
        "from": 21,
        "to": 40
    }
}
```

---

# 🔎 28. FILTROS

Ejemplos:

### Activos

```text
GET /api/equipos?estado=activo
```

### Averiados

```text
GET /api/equipos?estado=averiado
```

### Ordenadores

```text
GET /api/equipos?tipo=ordenador
```

### Dell

```text
GET /api/equipos?marca=Dell
```

### Asignados a E01

```text
GET /api/equipos?usuario=E01
```

---

# ↕️ 29. ORDENACIÓN

Una convención posible:

```text
GET /api/equipos?sort=marca
```

ascendente:

```text
sort=marca
```

descendente:

```text
sort=-marca
```

Otra convención válida podría ser:

```text
sort_by=marca&order=desc
```

Lo importante es definir una convención coherente.

---

# 🔍 30. BÚSQUEDA

Una solución:

```text
GET /api/equipos?q=Dell
```

La API podría interpretar:

```text
q
```

como búsqueda sobre:

```text
marca
+
modelo
```

---

# 🚨 31. PARTE VII · ERROR DE API

Una respuesta apropiada:

```http
HTTP/1.1 422 Unprocessable Content
Content-Type: application/json
```

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

Ventaja:

```text
mensaje general
+
errores específicos
```

Esto permite que un frontend pueda mostrar los errores junto a los campos correspondientes.

---

# 🔐 32. PARTE VIII · AUTENTICACIÓN

## Autenticación

Responde:

> ¿Quién eres?

Ejemplos:

```text
usuario + contraseña
token
certificado
```

---

## Autorización

Responde:

> ¿Qué puedes hacer?

Ejemplo:

```text
usuario autenticado
+
rol técnico
→ puede modificar incidencias

usuario autenticado
+
rol empleado
→ puede consultar sus equipos
```

---

# 🎟️ 33. BEARER TOKEN

Header:

```http
Authorization: Bearer abc123
```

Significa que se proporciona un token de acceso mediante el esquema:

```text
Bearer
```

El servidor utiliza ese token para identificar/autenticar la petición según el mecanismo de seguridad implementado.

---

# 📦 34. CONTENT-TYPE VS ACCEPT

## Content-Type

Indica el formato del contenido que se está enviando.

Ejemplo:

```http
Content-Type: application/json
```

significa:

```text
el body enviado es JSON
```

---

## Accept

Indica qué formato de respuesta desea recibir el cliente.

Ejemplo:

```http
Accept: application/json
```

significa:

```text
el cliente solicita una respuesta JSON
```

Por tanto:

```text
Content-Type
→ qué estoy enviando

Accept
→ qué quiero recibir
```

---

# 🧪 35. PARTE IX · POSTMAN

Para:

```text
POST /api/incidencias
```

podemos utilizar:

```text
Method:
POST

URL:
https://example.com/api/incidencias
```

Headers:

```text
Content-Type: application/json
Accept: application/json
Authorization: Bearer <token>
```

Body:

```json
{
    "titulo": "Impresora no responde",
    "descripcion": "La impresora no responde a las solicitudes.",
    "equipo": "EQ03",
    "prioridad": "alta",
    "estado": "abierta"
}
```

En Postman:

```text
Body
→ raw
→ JSON
```

---

# 🧪 36. RAW VS FORM-DATA

Cuando una API espera:

```http
Content-Type: application/json
```

el body debe contener un documento JSON.

Por ejemplo:

```json
{
    "marca": "Dell",
    "modelo": "OptiPlex"
}
```

`multipart/form-data` utiliza otro formato de codificación, especialmente útil cuando se envían:

```text
campos
+
archivos
```

Por ejemplo:

```text
imagen
+
nombre
+
descripción
```

No es que `form-data` sea "incorrecto" universalmente.

El servidor debe estar preparado para interpretar el `Content-Type` recibido.

---

# 🔄 37. PARTE X · HTTP + LARAVEL

Un recorrido conceptual:

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
Service / lógica de aplicación
   ↓
Model / Repository
   ↓
Database
   ↓
Response JSON
   ↓
Cliente
```

---

# 🧭 38. RESPONSABILIDADES

## Router

Determina qué código debe procesar:

```text
POST /api/equipos
```

---

## Controller

Recibe la petición y coordina el caso de uso.

No debería convertirse necesariamente en un lugar donde vive toda la lógica de negocio.

---

## Validation

Comprueba:

```text
required
tipo
estado
formatos
```

etc.

---

## Service

Puede contener la lógica de aplicación/caso de uso.

Por ejemplo:

```text
crearEquipo()
```

---

## Model / Repository

Gestiona la interacción con la persistencia según la arquitectura elegida.

---

## Response

Devuelve:

```text
JSON
+
status code
+
headers
```

---

# 🧠 39. API RESOURCE

Una capa de transformación tipo:

```text
EquipoResource
```

puede controlar qué representación pública recibe el cliente.

Por ejemplo, evita exponer automáticamente todos los atributos internos del modelo.

Puede transformar:

```text
Modelo interno
```

en:

```text
Representación API
```

Ventajas:

```text
control de campos
consistencia
separación entre modelo interno y contrato API
```

---

# 📄 40. PARTE XI · SERIALIZACIÓN

Un objeto PHP:

```php
$equipo
```

es una estructura/objeto del lenguaje.

JSON es una representación textual de datos.

La:

```text
serialización
```

consiste conceptualmente en convertir una estructura/objeto en una representación que pueda almacenarse o transmitirse.

Por ejemplo:

```text
Objeto PHP
    ↓
serialización
    ↓
JSON
```

Y al recibirlo:

```text
JSON
    ↓
deserialización / parsing
    ↓
estructura de datos
```

---

# 🧪 41. DESAFÍO · PAGINACIÓN COMPLETA

Una respuesta válida:

```json
{
    "data": [
        {
            "id": "EQ021",
            "tipo": "ordenador",
            "marca": "Dell"
        }
    ],
    "meta": {
        "current_page": 2,
        "per_page": 20,
        "total": 1000,
        "last_page": 50,
        "from": 21,
        "to": 40
    }
}
```

La cantidad real de elementos en `data` dependerá de la página concreta.

---

# 🏆 42. DESAFÍO FINAL · DISEÑO COMPLETO

Una API coherente podría ser:

## Equipos

```text
GET    /api/equipos
GET    /api/equipos/{id}
POST   /api/equipos
PUT    /api/equipos/{id}
PATCH  /api/equipos/{id}
DELETE /api/equipos/{id}
```

## Empleados

```text
GET    /api/empleados
GET    /api/empleados/{id}
POST   /api/empleados
PATCH  /api/empleados/{id}
```

## Departamentos

```text
GET    /api/departamentos
GET    /api/departamentos/{id}
POST   /api/departamentos
PATCH  /api/departamentos/{id}
```

## Incidencias

```text
GET    /api/incidencias
GET    /api/incidencias/{id}
POST   /api/incidencias
PATCH  /api/incidencias/{id}
```

Con:

```text
JSON
+
validación
+
status codes
+
errores estructurados
+
paginación
+
filtros
+
autenticación
```

---

# ⭐ 43. RECURSO ANIDADO VS ID

Dos respuestas posibles:

### Opción A

```json
{
    "id": "EQ01",
    "usuario": {
        "id": "E01",
        "nombre": "Pedro"
    }
}
```

Ventajas:

```text
respuesta cómoda para el cliente
menos necesidad de otra petición
```

Inconvenientes:

```text
respuesta más grande
posible duplicación
puede complicar consistencia
```

---

### Opción B

```json
{
    "id": "EQ01",
    "usuario_id": "E01"
}
```

Ventajas:

```text
respuesta pequeña
representación simple
menos duplicación
```

Inconvenientes:

```text
el cliente necesita más información
si necesita datos del usuario
```

No existe una única respuesta universalmente correcta.

Depende del contrato y necesidades del cliente.

---

# 🧠 44. RESPUESTAS DE REFLEXIÓN

## 1. JSON vs JavaScript

JSON es un formato de intercambio de datos.

JavaScript es un lenguaje de programación.

JSON utiliza una sintaxis relacionada con JavaScript, pero no es JavaScript.

---

## 2. Tipos JSON

```text
string
number
object
array
boolean
null
```

---

## 3. Objeto vs array

```text
object
→ pares clave/valor

array
→ colección ordenada de valores
```

---

## 4. HTTP

Protocolo utilizado para la comunicación entre clientes y servidores en la Web.

---

## 5. Request vs response

```text
request
→ cliente → servidor

response
→ servidor → cliente
```

---

## 6. REST

Estilo arquitectónico para diseñar servicios basados en recursos y las operaciones/semántica de HTTP.

---

## 7. Recurso

Una entidad o concepto identificable que la API expone mediante una representación.

Ejemplo:

```text
/equipos/EQ01
```

---

## 8. PUT vs PATCH

```text
PUT
→ reemplazo completo de una representación del recurso

PATCH
→ modificación parcial
```

---

## 9. Idempotencia

Repetir una misma petición produce el mismo efecto final sobre el recurso.

---

## 10. 401 vs 403

```text
401
→ autenticación necesaria/no válida

403
→ acceso prohibido
```

---

## 11. 404 vs 422

```text
404
→ recurso no encontrado

422
→ contenido entendible pero inválido
```

---

## 12. Content-Type

Indica el tipo de contenido que se está enviando.

---

## 13. Accept

Indica el formato de respuesta que el cliente acepta/preferiría.

---

## 14. JSON Schema

Permite describir y validar la estructura y restricciones de documentos JSON.

---

## 15. `additionalProperties: false`

Impide propiedades adicionales no definidas por el esquema.

---

## 16. Paginación

Divide un conjunto grande de resultados en páginas más pequeñas.

---

## 17. Autenticación vs autorización

```text
autenticación
→ quién eres

autorización
→ qué puedes hacer
```

---

## 18. Bearer

Esquema de autenticación/autorización mediante un token presentado en:

```http
Authorization: Bearer <token>
```

---

## 19. Serialización

Conversión de una estructura/objeto a una representación adecuada para almacenar o transmitir.

---

## 20. Errores estructurados

Permiten que los clientes puedan interpretar programáticamente:

```text
qué ha ocurrido
qué campos fallan
qué mensaje mostrar
```

---

# 🚨 45. ERRORES TÍPICOS

## Error 1

Pensar:

```text
JSON = JavaScript
```

No.

---

## Error 2

Confundir:

```text
Content-Type
```

con:

```text
Accept
```

---

## Error 3

Pensar:

```text
401 = no tienes permisos
```

No exactamente.

```text
401
→ autenticación

403
→ autorización/acceso
```

---

## Error 4

Pensar:

```text
PATCH siempre es idempotente
```

Incorrecto.

Puede serlo dependiendo de cómo se diseñe la operación, pero no es una propiedad general obligatoria de PATCH.

---

## Error 5

Confundir:

```text
PUT
```

con:

```text
PATCH
```

---

## Error 6

Crear endpoints como:

```text
/createEquipo
/deleteEquipo
```

sin una razón clara.

REST suele expresar:

```text
recurso
+
método HTTP
```

---

## Error 7

Devolver:

```text
500
```

para cualquier error de validación.

Los errores de validación son errores del cliente, no errores internos del servidor.

---

## Error 8

Devolver una cadena:

```text
"Error"
```

sin información estructurada.

Una API debería facilitar el tratamiento programático de los errores.

---

## Error 9

Pensar que `multipart/form-data` es siempre mejor que JSON.

Depende del contenido y del contrato de la API.

---

# 🧠 46. CONCEPTOS QUE DEBES DOMINAR

Al terminar deberías poder explicar sin apuntes:

```text
✓ JSON
✓ tipos JSON
✓ objetos
✓ arrays
✓ objetos anidados
✓ JSON vs XML
✓ HTTP
✓ request / response
✓ GET
✓ POST
✓ PUT
✓ PATCH
✓ DELETE
✓ idempotencia
✓ status codes
✓ REST
✓ recursos
✓ endpoints
✓ filtros
✓ búsqueda
✓ ordenación
✓ paginación
✓ JSON Schema
✓ required
✓ enum
✓ additionalProperties
✓ errores
✓ autenticación
✓ autorización
✓ Bearer
✓ Content-Type
✓ Accept
✓ serialización
✓ API Resource
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

# 🏁 48. CONCLUSIÓN

La misión completa puede resumirse:

```text
CLIENTE
   │
   │ HTTP Request
   ▼
┌──────────────────────┐
│        API           │
│                      │
│ Router               │
│ Validation           │
│ Business Logic       │
│ Persistence          │
└──────────┬───────────┘
           │
           │ JSON Response
           ▼
        CLIENTE
```

Y dentro de esa comunicación:

```text
HTTP
 ↓
método
 ↓
recurso
 ↓
headers
 ↓
JSON
 ↓
validación
 ↓
status code
 ↓
respuesta
```

Si puedes recorrer mentalmente todo ese camino, has cubierto el núcleo práctico del capítulo.

---

# 🏁 49. CIERRE DEL BLOQUE 5

Con esta misión termina nuestra serie de misiones prácticas del:

# BLOQUE 5 · PROGRAMACIÓN

Hemos trabajado:

```text
5.1 Python
5.2 Java
5.3 Programación Orientada a Objetos
5.4 UML
5.5 HTML
5.6 CSS
5.7 JavaScript
5.8 XML
5.9 JSON
```

Y las misiones prácticas:

```text
07 · POO + UML
08 · HTML + CSS
09 · XML
10 · JSON + API
```

El siguiente paso natural es:

```text
MISIÓN 7
     ↓
CORRECCIÓN
     ↓
MISIÓN 8
     ↓
CORRECCIÓN
     ↓
MISIÓN 9
     ↓
CORRECCIÓN
     ↓
MISIÓN 10
     ↓
CORRECCIÓN
     ↓
SIMULACRO GENERAL
     ↓
CORRECCIÓN DEL SIMULACRO
     ↓
REPASO DE ERRORES
```

---

# 🏁 FIN DE LA CORRECCIÓN · MISIÓN 10
# 🎉 FIN DE LAS MISIONES DEL BLOQUE 5
