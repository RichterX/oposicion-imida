<!-- encabezado-homogeneizado -->
# Bloque 03 - SIMULACRO
> **Bloque:** Bloque 03  
> **Documento:** Simulacro  
> **Preguntas de referencia:** 99  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# 🧪 Simulacro Bloque 3 - Bases de Datos

> **Simulacro global del Bloque 3**
>
> SQL · PostgreSQL · Oracle · MySQL · PL/SQL · PostGIS

------------------------------------------------------------------------

# 📋 Instrucciones

Este simulacro está diseñado para comprobar la comprensión global del
Bloque 3.

A diferencia de la misión, aquí los conceptos aparecen **mezclados**. No
se indica expresamente qué tecnología debe utilizarse en cada pregunta.

El objetivo es aproximarse a una situación de examen real.

## Reglas

-   No consultar el temario durante la primera vuelta.
-   No consultar las soluciones.
-   Responder primero las preguntas que resulten más claras.
-   Marcar las dudas con `❓`.
-   Si una pregunta parece especialmente difícil, continuar y volver a
    ella posteriormente.
-   En preguntas SQL se aceptan soluciones equivalentes.
-   En preguntas conceptuales importa especialmente el razonamiento.

------------------------------------------------------------------------

# 🎯 Estructura

  Bloque   Área                                  Preguntas
  -------- ----------------------------------- -----------
  A        SQL y bases de datos relacionales          1-10
  B        PostgreSQL y MySQL                        11-18
  C        Oracle y PL/SQL                           19-26
  D        PostGIS                                   27-38
  E        Rendimiento y arquitectura                39-44
  F        Caso práctico integrado                   45-50

**Total: 50 preguntas**

------------------------------------------------------------------------

# 🟢 BLOQUE A - SQL Y BASES DE DATOS RELACIONALES

## Pregunta 1

Explica la diferencia entre:

``` text
PRIMARY KEY
FOREIGN KEY
UNIQUE
```

Indica qué problema resuelve cada una.

------------------------------------------------------------------------

## Pregunta 2

Tenemos:

``` text
clientes
---------
id
nombre

pedidos
-------
id
cliente_id
total
```

Obtener el nombre de cada cliente y el número de pedidos que ha
realizado.

Deben aparecer también los clientes que nunca hayan realizado un pedido.

------------------------------------------------------------------------

## Pregunta 3

Tenemos:

``` text
productos
---------
id
nombre
categoria
precio
```

Obtener las categorías cuyo precio medio sea superior a:

``` text
100 €
```

------------------------------------------------------------------------

## Pregunta 4

Explica la diferencia entre:

``` sql
WHERE
```

y:

``` sql
HAVING
```

Incluye un ejemplo de cada uno.

------------------------------------------------------------------------

## Pregunta 5

Explica las diferencias fundamentales entre:

``` text
INNER JOIN
LEFT JOIN
RIGHT JOIN
FULL OUTER JOIN
```

------------------------------------------------------------------------

## Pregunta 6

Tenemos:

``` text
empleados
---------
id
nombre
departamento_id
salario
```

Obtener el empleado con el salario más alto.

Después explica cómo obtendrías **el salario máximo de cada
departamento**.

------------------------------------------------------------------------

## Pregunta 7

Explica qué problema puede producir una consulta que contenga:

``` text
N+1 consultas
```

y cómo puede evitarse desde la aplicación.

------------------------------------------------------------------------

## Pregunta 8

Explica la diferencia entre:

``` text
DELETE
TRUNCATE
DROP
```

------------------------------------------------------------------------

## Pregunta 9

Tenemos:

``` text
ventas
---------
id
usuario_id
fecha
importe
```

Obtener para cada usuario:

``` text
fecha
importe
importe acumulado
```

ordenado cronológicamente.

¿Qué característica de SQL utilizarías?

------------------------------------------------------------------------

## Pregunta 10

Explica qué es una transacción y qué significan:

``` text
COMMIT
ROLLBACK
```

Relaciona la respuesta con las propiedades ACID.

------------------------------------------------------------------------

# 🟡 BLOQUE B - POSTGRESQL Y MYSQL

## Pregunta 11

¿Qué diferencia fundamental existe entre:

``` text
PostgreSQL
MySQL
```

como sistemas gestores de bases de datos?

No se busca una lista de características. Explica qué significa que
ambos sean SGBD relacionales y qué diferencias relevantes pueden
aparecer en su funcionamiento y sintaxis.

------------------------------------------------------------------------

## Pregunta 12

¿Qué es:

``` text
JSONB
```

en PostgreSQL?

Explica una ventaja frente a almacenar simplemente texto JSON.

------------------------------------------------------------------------

## Pregunta 13

Tenemos:

``` sql
usuarios
---------
id
nombre
datos JSONB
```

Y:

``` json
{
    "direccion": {
        "ciudad": "Murcia"
    }
}
```

Escribe una consulta para obtener los usuarios cuya ciudad sea Murcia.

------------------------------------------------------------------------

## Pregunta 14

¿Qué es una:

``` text
CTE
```

?

Explica para qué sirve y escribe un ejemplo sencillo.

------------------------------------------------------------------------

## Pregunta 15

¿Qué es una Window Function?

Explica la diferencia conceptual entre:

``` text
GROUP BY
```

y:

``` text
Window Function
```

------------------------------------------------------------------------

## Pregunta 16

¿Qué herramienta de PostgreSQL utilizarías para analizar una consulta
lenta?

Explica la diferencia entre:

``` text
EXPLAIN
EXPLAIN ANALYZE
```

------------------------------------------------------------------------

## Pregunta 17

Relaciona cada concepto con el sistema más característico:

``` text
InnoDB
JSONB
PL/pgSQL
AUTO_INCREMENT
GiST
```

------------------------------------------------------------------------

## Pregunta 18

Explica qué es:

``` text
MVCC
```

y por qué resulta importante cuando varias transacciones trabajan
simultáneamente.

------------------------------------------------------------------------

# 🟠 BLOQUE C - ORACLE Y PL/SQL

## Pregunta 19

Explica la finalidad de:

``` text
SEQUENCE
VIEW
MATERIALIZED VIEW
SYNONYM
TABLESPACE
```

------------------------------------------------------------------------

## Pregunta 20

¿Cuál es la diferencia conceptual entre una:

``` text
VIEW
```

y una:

``` text
MATERIALIZED VIEW
```

¿En qué situación podría interesar utilizar la segunda?

------------------------------------------------------------------------

## Pregunta 21

¿Qué es PL/SQL y qué relación tiene con SQL?

------------------------------------------------------------------------

## Pregunta 22

Explica la diferencia entre:

``` text
FUNCTION
PROCEDURE
```

en PL/SQL.

------------------------------------------------------------------------

## Pregunta 23

Tenemos:

``` text
empleados
---------
id
nombre
salario
```

Escribe un procedimiento PL/SQL que reciba:

``` text
id_empleado
porcentaje
```

y aumente el salario del empleado.

------------------------------------------------------------------------

## Pregunta 24

¿Qué es un cursor en PL/SQL?

¿En qué situación podría utilizarse?

------------------------------------------------------------------------

## Pregunta 25

Explica la finalidad de la sección:

``` text
EXCEPTION
```

en PL/SQL.

¿Qué problema puede tener utilizar indiscriminadamente:

``` sql
WHEN OTHERS
```

?

------------------------------------------------------------------------

## Pregunta 26

Explica qué ocurre conceptualmente en:

``` text
DECLARE
   ↓
BEGIN
   ↓
EXCEPTION
   ↓
END
```

------------------------------------------------------------------------

# 🔴 BLOQUE D - POSTGIS

## Pregunta 27

¿Qué añade PostGIS a PostgreSQL?

Explica qué tipo de información permite almacenar y consultar.

------------------------------------------------------------------------

## Pregunta 28

Explica la diferencia entre:

``` text
geometry
geography
```

------------------------------------------------------------------------

## Pregunta 29

Tenemos:

``` text
hospitales
----------
id
nombre
geom

municipios
----------
id
nombre
geom
```

Queremos saber en qué municipio está cada hospital.

¿Qué relación espacial utilizarías?

------------------------------------------------------------------------

## Pregunta 30

Explica la diferencia entre:

``` text
ST_Within
ST_Contains
```

------------------------------------------------------------------------

## Pregunta 31

Queremos encontrar todos los hospitales situados a menos de:

``` text
5 km
```

de un punto.

¿Qué función utilizarías?

Escribe una consulta aproximada.

------------------------------------------------------------------------

## Pregunta 32

Explica la diferencia entre:

``` text
ST_Distance
ST_DWithin
```

¿Por qué `ST_DWithin` suele resultar especialmente interesante para
búsquedas de proximidad?

------------------------------------------------------------------------

## Pregunta 33

Queremos crear una zona de influencia de:

``` text
1 km
```

alrededor de cada hospital.

¿Qué función utilizaríamos?

------------------------------------------------------------------------

## Pregunta 34

Tenemos:

``` text
geom geometry(Point, 4326)
```

y queremos trabajar en:

``` text
EPSG:25830
```

Un compañero propone:

``` sql
ST_SetSRID(geom, 25830)
```

¿Es correcto?

Explica por qué.

------------------------------------------------------------------------

## Pregunta 35

Explica con tus propias palabras la diferencia entre:

``` text
ST_SetSRID
ST_Transform
```

Esta pregunta es especialmente importante.

------------------------------------------------------------------------

## Pregunta 36

Tenemos municipios y carreteras.

Queremos saber:

1.  Qué carreteras atraviesan cada municipio.
2.  Qué geometría de cada carretera queda dentro del municipio.
3.  Cuántos metros de carretera hay dentro de cada municipio.

Indica qué función utilizarías en cada paso.

------------------------------------------------------------------------

## Pregunta 37

Explica la diferencia entre:

``` text
ST_Intersects
ST_Intersection
```

------------------------------------------------------------------------

## Pregunta 38

Explica la diferencia entre:

``` text
ST_Centroid
ST_PointOnSurface
```

¿Por qué podría ser preferible `ST_PointOnSurface` para colocar una
etiqueta dentro de un polígono?

------------------------------------------------------------------------

# 🔵 BLOQUE E - RENDIMIENTO Y ARQUITECTURA

## Pregunta 39

Tenemos una tabla PostGIS con:

``` text
10 millones de geometrías
```

Una consulta espacial tarda varios segundos.

¿Qué tres cosas investigarías inicialmente?

------------------------------------------------------------------------

## Pregunta 40

¿Qué es un índice espacial?

¿Qué tipo de índice se utiliza habitualmente en PostGIS?

------------------------------------------------------------------------

## Pregunta 41

Explica la diferencia entre:

``` text
Seq Scan
Index Scan
```

¿Un `Seq Scan` significa necesariamente que existe un problema?

------------------------------------------------------------------------

## Pregunta 42

Tenemos esta consulta:

``` sql
SELECT *
FROM edificios
WHERE ST_DWithin(
    geom::geography,
    :punto::geography,
    1000
);
```

La tabla contiene millones de registros.

¿Qué índice considerarías?

------------------------------------------------------------------------

## Pregunta 43

Una API recibe:

``` text
latitude
longitude
```

y debe consultar PostGIS.

¿Qué orden deben ocupar estas coordenadas al construir un `POINT`?

Escribe una expresión utilizando:

``` text
ST_MakePoint
ST_SetSRID
```

------------------------------------------------------------------------

## Pregunta 44

El frontend necesita representar los resultados espaciales sobre un
mapa.

¿Qué formato podrías utilizar para transportar las geometrías desde la
API?

¿Qué función de PostGIS permite convertir una geometría a ese formato?

------------------------------------------------------------------------

# 🔥 BLOQUE F - CASO PRÁCTICO INTEGRADO

## Pregunta 45 - Diseño

Una administración quiere gestionar centros públicos.

Tenemos:

``` text
centros
-------
id
nombre
tipo
geom

municipios
----------
id
nombre
geom

incidencias
-----------
id
centro_id
fecha
estado
```

Explica las relaciones principales entre las tablas.

------------------------------------------------------------------------

## Pregunta 46 - SQL

Obtener:

``` text
centro
número de incidencias
```

Deben aparecer también los centros sin incidencias.

Escribe la consulta.

------------------------------------------------------------------------

## Pregunta 47 - SQL + agregación

Modificar la consulta anterior para obtener únicamente los centros que
tengan:

``` text
más de 10 incidencias
```

------------------------------------------------------------------------

## Pregunta 48 - PostGIS

Obtener:

``` text
centro
municipio
```

indicando en qué municipio se encuentra cada centro.

Escribe la consulta espacial.

------------------------------------------------------------------------

## Pregunta 49 - PostGIS + API

La API recibe:

``` text
latitude
longitude
radius
```

y debe devolver todos los centros situados dentro de ese radio.

Además, la geometría debe devolverse en GeoJSON.

Escribe una consulta que combine:

``` text
ST_MakePoint
ST_SetSRID
ST_DWithin
ST_AsGeoJSON
```

------------------------------------------------------------------------

## Pregunta 50 - Pregunta final

La consulta anterior funciona correctamente, pero la tabla contiene:

``` text
20 millones de centros
```

y comienza a tardar demasiado.

Describe un plan razonable de diagnóstico y optimización.

Debes mencionar como mínimo:

-   Índice espacial.
-   `EXPLAIN ANALYZE`.
-   `geometry` / `geography`.
-   Selectividad.
-   Posibles problemas derivados del uso de expresiones como
    `geom::geography`.

------------------------------------------------------------------------

# 🏆 BLOQUE EXTRA - PREGUNTAS DE ALTA DIFICULTAD

Estas preguntas son opcionales.

Si el simulacro principal ya ha sido suficientemente exigente, pueden
realizarse después.

------------------------------------------------------------------------

## Pregunta 51

¿Por qué esta consulta puede ser problemática?

``` sql
SELECT *
FROM pedidos p
JOIN clientes c
    ON p.cliente_id = c.id
WHERE c.nombre LIKE '%garcia%';
```

¿Qué factores podrían afectar a su rendimiento?

------------------------------------------------------------------------

## Pregunta 52

Explica por qué esta consulta:

``` sql
SELECT *
FROM hospitales
WHERE ST_Distance(
    geom::geography,
    :punto::geography
) < 5000;
```

podría no ser la primera opción para una búsqueda de proximidad.

¿Qué alternativa considerarías?

------------------------------------------------------------------------

## Pregunta 53

Tenemos:

``` text
EPSG:4326
```

y queremos realizar cálculos de distancia precisos en metros.

Explica qué alternativas considerarías y qué papel tienen:

``` text
geometry
geography
CRS proyectado
```

------------------------------------------------------------------------

## Pregunta 54

Explica por qué no siempre es buena idea utilizar cursores para procesar
miles o millones de registros en PL/SQL.

¿Qué alternativa SQL intentarías antes?

------------------------------------------------------------------------

## Pregunta 55

Una consulta devuelve:

``` text
Seq Scan
```

y el desarrollador afirma:

> "Hay que crear un índice porque PostgreSQL no está usando ninguno."

¿Es necesariamente correcto?

Explica qué comprobarías antes de tomar esa decisión.

------------------------------------------------------------------------

# 🧠 HOJA DE RESPUESTAS

Utiliza esta sección para registrar únicamente tus respuestas finales.

## Bloque A

### 1.

Respuesta:

### 2.

Respuesta:

### 3.

Respuesta:

### 4.

Respuesta:

### 5.

Respuesta:

### 6.

Respuesta:

### 7.

Respuesta:

### 8.

Respuesta:

### 9.

Respuesta:

### 10.

Respuesta:

------------------------------------------------------------------------

## Bloque B

### 11.

Respuesta:

### 12.

Respuesta:

### 13.

Respuesta:

### 14.

Respuesta:

### 15.

Respuesta:

### 16.

Respuesta:

### 17.

Respuesta:

### 18.

Respuesta:

------------------------------------------------------------------------

## Bloque C

### 19.

Respuesta:

### 20.

Respuesta:

### 21.

Respuesta:

### 22.

Respuesta:

### 23.

Respuesta:

### 24.

Respuesta:

### 25.

Respuesta:

### 26.

Respuesta:

------------------------------------------------------------------------

## Bloque D

### 27.

Respuesta:

### 28.

Respuesta:

### 29.

Respuesta:

### 30.

Respuesta:

### 31.

Respuesta:

### 32.

Respuesta:

### 33.

Respuesta:

### 34.

Respuesta:

### 35.

Respuesta:

### 36.

Respuesta:

### 37.

Respuesta:

### 38.

Respuesta:

------------------------------------------------------------------------

## Bloque E

### 39.

Respuesta:

### 40.

Respuesta:

### 41.

Respuesta:

### 42.

Respuesta:

### 43.

Respuesta:

### 44.

Respuesta:

------------------------------------------------------------------------

## Bloque F

### 45.

Respuesta:

### 46.

Respuesta:

### 47.

Respuesta:

### 48.

Respuesta:

### 49.

Respuesta:

### 50.

Respuesta:

------------------------------------------------------------------------

# 📊 AUTOEVALUACIÓN

Cuando termines, clasifica cada pregunta:

  Símbolo   Resultado
  --------- -------------------------
  🟢        Correcta y razonada
  🟡        Correcta pero con dudas
  🟠        Parcialmente correcta
  🔴        Incorrecta
  ⚪        No respondida

## Resultado

``` text
🟢 Dominadas:
🟡 Con dudas:
🟠 Parciales:
🔴 Incorrectas:
⚪ No respondidas:
```

------------------------------------------------------------------------

# 🎯 INTERPRETACIÓN

No utilizar únicamente el número de aciertos.

Un resultado especialmente útil sería algo como:

``` text
SQL              🟢🟢🟢🟢🟡
PostgreSQL       🟢🟢🟡🟠🟡
MySQL            🟢🟢🟢
Oracle           🟡🟠🟡
PL/SQL           🟠🟠🟡
PostGIS          🟢🟡🟢🟠🟡
Rendimiento      🟡🟠🟡
```

Esto permite detectar **qué partes necesitan repaso** sin volver a
estudiar las 13.000 líneas completas.

------------------------------------------------------------------------

# 🧭 CRITERIO DE CORRECCIÓN

La corrección tendrá en cuenta cuatro dimensiones:

### 1. Conocimiento

¿Se conoce el concepto?

### 2. Aplicación

¿Se sabe utilizar en un caso práctico?

### 3. Razonamiento

¿Se entiende por qué se utiliza esa solución?

### 4. Precisión

¿Se conocen las diferencias importantes entre conceptos parecidos?

------------------------------------------------------------------------

# 🏁 FIN DEL SIMULACRO

> **No se trata de recordar 13.000 líneas.**
>
> Se trata de demostrar que, ante un problema, sabes identificar la
> herramienta adecuada, utilizarla y explicar por qué.

