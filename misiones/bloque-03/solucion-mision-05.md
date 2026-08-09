# 🎯 Misión Bloque 3 - Soluciones

## Introducción

Estas son las soluciones propuestas para la misión del Bloque 3.

> **Nota:** En SQL y PL/SQL pueden existir varias soluciones correctas.
> Las mostradas son ejemplos válidos, no necesariamente las únicas
> respuestas posibles.

------------------------------------------------------------------------

# 🟢 Nivel 1 - SQL Fundamental

## Misión 1 - Consultas básicas

### 1.1 - Clientes de Murcia

``` sql
SELECT *
FROM clientes
WHERE ciudad = 'Murcia';
```

`WHERE` filtra las filas que cumplen una condición.

### 1.2 - Pedidos superiores a 100 € y completados

``` sql
SELECT *
FROM pedidos
WHERE total > 100
  AND estado = 'completado';
```

Ambas condiciones deben cumplirse.

### 1.3 - Cliente, fecha y total

``` sql
SELECT
    c.nombre,
    p.fecha,
    p.total
FROM clientes c
JOIN pedidos p
    ON p.cliente_id = c.id;
```

La relación es `clientes.id -> pedidos.cliente_id`.

### 1.4 - Clientes sin pedidos

``` sql
SELECT c.*
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id
WHERE p.id IS NULL;
```

El `LEFT JOIN` conserva también los clientes sin pedidos.

### 1.5 - Número de pedidos por cliente

``` sql
SELECT
    c.id,
    c.nombre,
    COUNT(p.id) AS numero_de_pedidos
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id
GROUP BY c.id, c.nombre;
```

`COUNT(p.id)` no cuenta los `NULL`, por lo que los clientes sin pedidos
obtienen `0`.

------------------------------------------------------------------------

# 🟢 Nivel 1 - Agrupaciones

## Misión 2 - GROUP BY y HAVING

### 2.1 - Gasto total por cliente

``` sql
SELECT
    c.id,
    c.nombre,
    SUM(p.total) AS gasto_total
FROM clientes c
JOIN pedidos p
    ON p.cliente_id = c.id
GROUP BY c.id, c.nombre;
```

### 2.2 - Clientes con más de 1.000 €

``` sql
SELECT
    c.id,
    c.nombre,
    SUM(p.total) AS gasto_total
FROM clientes c
JOIN pedidos p
    ON p.cliente_id = c.id
GROUP BY c.id, c.nombre
HAVING SUM(p.total) > 1000;
```

`HAVING` filtra grupos después de la agregación.

### 2.3 - Precio medio por categoría

``` sql
SELECT
    categoria,
    AVG(precio) AS precio_medio
FROM productos
GROUP BY categoria;
```

### 2.4 - WHERE vs HAVING

`WHERE` filtra filas antes de agrupar:

``` sql
SELECT *
FROM productos
WHERE precio > 100;
```

`HAVING` filtra grupos después de agrupar:

``` sql
SELECT
    categoria,
    AVG(precio) AS precio_medio
FROM productos
GROUP BY categoria
HAVING AVG(precio) > 100;
```

Regla:

``` text
WHERE  → filas
HAVING → grupos
```

------------------------------------------------------------------------

# 🟡 Nivel 2 - SQL Intermedio

## Misión 3 - El producto estrella

``` sql
SELECT
    p.id,
    p.nombre,
    SUM(dp.cantidad) AS cantidad_total_vendida
FROM productos p
JOIN detalle_pedido dp
    ON dp.producto_id = p.id
GROUP BY p.id, p.nombre
ORDER BY cantidad_total_vendida DESC
LIMIT 1;
```

`SUM` calcula las unidades vendidas, `ORDER BY ... DESC` ordena de mayor
a menor y `LIMIT 1` obtiene el primero.

------------------------------------------------------------------------

## Misión 4 - Clientes sin compras

### Con LEFT JOIN

``` sql
SELECT c.*
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id
WHERE p.id IS NULL;
```

### Con NOT EXISTS

``` sql
SELECT c.*
FROM clientes c
WHERE NOT EXISTS (
    SELECT 1
    FROM pedidos p
    WHERE p.cliente_id = c.id
);
```

Ambas son soluciones válidas. `NOT EXISTS` expresa de forma muy directa
la ausencia de registros relacionados. La elección final depende del
caso y del plan de ejecución.

------------------------------------------------------------------------

# 🟡 Nivel 2 - PostgreSQL

## Misión 5.1 - JSONB

``` sql
SELECT *
FROM usuarios
WHERE datos->'direccion'->>'ciudad' = 'Murcia';
```

`->` obtiene un objeto JSON y `->>` obtiene el valor como texto.

------------------------------------------------------------------------

## 5.2 - Window Functions

``` sql
SELECT
    usuario_id,
    fecha,
    importe,
    SUM(importe) OVER (
        PARTITION BY usuario_id
        ORDER BY fecha
        ROWS BETWEEN UNBOUNDED PRECEDING
             AND CURRENT ROW
    ) AS importe_acumulado
FROM ventas
ORDER BY usuario_id, fecha;
```

Las Window Functions permiten calcular sobre un conjunto de filas
relacionadas sin reducirlas a una sola fila mediante `GROUP BY`.

------------------------------------------------------------------------

## 5.3 - CTE

``` sql
WITH ventas_por_usuario AS (
    SELECT
        usuario_id,
        SUM(importe) AS total
    FROM ventas
    GROUP BY usuario_id
)
SELECT *
FROM ventas_por_usuario
WHERE total > 1000;
```

Una CTE mejora la legibilidad y permite dividir consultas complejas en
pasos. También existen CTE recursivas mediante `WITH RECURSIVE`.

------------------------------------------------------------------------

## 5.4 - EXPLAIN

``` sql
EXPLAIN ANALYZE
SELECT *
FROM ventas
WHERE usuario_id = 10;
```

``` text
EXPLAIN
↓
Plan estimado

EXPLAIN ANALYZE
↓
Ejecuta y muestra datos reales
```

------------------------------------------------------------------------

# 🟡 Nivel 2 - MySQL vs PostgreSQL

## Misión 6

  Característica                 Respuesta
  ------------------------------ -----------------------------------
  JSONB                          PostgreSQL
  InnoDB                         MySQL
  MVCC                           Ambos
  PL/pgSQL                       PostgreSQL
  AUTO_INCREMENT                 MySQL
  GENERATED ALWAYS AS IDENTITY   PostgreSQL / estándar SQL moderno
  GiST                           PostgreSQL

-   **JSONB:** característica especialmente asociada a PostgreSQL.
-   **InnoDB:** motor de almacenamiento transaccional de MySQL.
-   **MVCC:** mecanismo de control de concurrencia presente tanto en
    PostgreSQL como en InnoDB.
-   **PL/pgSQL:** lenguaje procedural de PostgreSQL.
-   **AUTO_INCREMENT:** característica tradicional de MySQL.
-   **GENERATED ALWAYS AS IDENTITY:** característica disponible en
    PostgreSQL y basada en SQL moderno.
-   **GiST:** método de indexación especialmente importante en
    PostgreSQL y utilizado por PostGIS.

------------------------------------------------------------------------

# 🟠 Nivel 3 - Oracle

## Misión 7 - Objetos Oracle

### SEQUENCE

Genera una secuencia de valores numéricos, habitualmente para
identificadores.

``` sql
CREATE SEQUENCE seq_empleados
START WITH 1
INCREMENT BY 1;
```

### VIEW

Consulta almacenada presentada como tabla virtual.

``` sql
CREATE VIEW empleados_activos AS
SELECT *
FROM empleados
WHERE activo = 1;
```

### MATERIALIZED VIEW

Almacena físicamente el resultado de una consulta y puede mejorar el
rendimiento de consultas complejas. Debe refrescarse cuando corresponda.

### SYNONYM

Proporciona un nombre alternativo para otro objeto de la base de datos.

### TABLESPACE

Estructura lógica de Oracle utilizada para organizar el almacenamiento
de objetos y administrar espacio.

**Respuesta:** `MATERIALIZED VIEW` almacena físicamente el resultado.

------------------------------------------------------------------------

# 🟠 Nivel 3 - PL/SQL

## Misión 8 - Procedimiento

``` sql
CREATE OR REPLACE PROCEDURE aumentar_salario(
    p_empleado_id IN empleados.id%TYPE,
    p_porcentaje  IN NUMBER
)
IS
BEGIN
    UPDATE empleados
    SET salario = salario * (1 + p_porcentaje / 100)
    WHERE id = p_empleado_id;

EXCEPTION
    WHEN OTHERS THEN
        RAISE;
END;
/
```

Uso:

``` sql
BEGIN
    aumentar_salario(10, 5);
END;
/
```

Aumenta el salario del empleado `10` un `5 %`.

En código real conviene gestionar las excepciones de forma específica
cuando sea posible.

------------------------------------------------------------------------

## Misión 9 - Cursor

Un cursor permite procesar un conjunto de filas de forma controlada
dentro de PL/SQL.

Ejemplo:

``` sql
DECLARE
    CURSOR c_empleados IS
        SELECT id, nombre, salario
        FROM empleados
        WHERE departamento_id = 10;

BEGIN
    FOR empleado IN c_empleados LOOP
        DBMS_OUTPUT.PUT_LINE(
            empleado.nombre || ': ' ||
            empleado.salario
        );
    END LOOP;
END;
/
```

------------------------------------------------------------------------

# 🔴 Nivel 4 - PostGIS

## Misión 10 - ¿Dónde está el hospital?

``` sql
SELECT
    h.nombre AS hospital,
    m.nombre AS municipio
FROM hospitales h
JOIN municipios m
    ON ST_Within(h.geom, m.geom);
```

También puede expresarse mediante:

``` sql
ST_Contains(m.geom, h.geom)
```

Conceptualmente:

``` text
ST_Within   → ¿está dentro?
ST_Contains → ¿contiene?
```

------------------------------------------------------------------------

# 🔴 Misión 11 - Hospitales cercanos

### 11.1

Utilizar `ST_DWithin`:

``` sql
SELECT *
FROM hospitales
WHERE ST_DWithin(
    geom::geography,
    :punto::geography,
    5000
);
```

### 11.2

`geography` resulta apropiado cuando queremos trabajar con coordenadas
geográficas y distancias sobre la Tierra utilizando metros.

### 11.3

Índice espacial GiST:

``` sql
CREATE INDEX idx_hospitales_geom
ON hospitales
USING GIST (geom);
```

Si se consulta específicamente `geom::geography`, puede estudiarse un
índice sobre esa expresión:

``` sql
CREATE INDEX idx_hospitales_geog
ON hospitales
USING GIST (geom::geography);
```

La elección debe verificarse con el plan de ejecución.

------------------------------------------------------------------------

# 🔴 Misión 12 - Carreteras municipales

### 12.1 - Comprobar relación

``` sql
ST_Intersects
```

Ejemplo:

``` sql
SELECT
    m.nombre AS municipio,
    c.nombre AS carretera
FROM municipios m
JOIN carreteras c
    ON ST_Intersects(m.geom, c.geom);
```

### 12.2 - Obtener geometría resultante

``` sql
ST_Intersection
```

``` sql
SELECT
    m.nombre AS municipio,
    c.nombre AS carretera,
    ST_Intersection(m.geom, c.geom) AS geometria
FROM municipios m
JOIN carreteras c
    ON ST_Intersects(m.geom, c.geom);
```

### 12.3 - Calcular longitud

``` sql
ST_Length
```

``` sql
SELECT
    m.nombre AS municipio,
    c.nombre AS carretera,
    ST_Length(
        ST_Intersection(m.geom, c.geom)
    ) AS longitud
FROM municipios m
JOIN carreteras c
    ON ST_Intersects(m.geom, c.geom);
```

Para obtener metros debemos utilizar un CRS apropiado o `geography`
cuando corresponda.

------------------------------------------------------------------------

# 🔴 Misión 13 - Buffer

### 13.1

Utilizar `ST_Buffer`:

``` sql
SELECT
    nombre,
    ST_Buffer(
        geom::geography,
        1000
    )
FROM hospitales;
```

`1000` representa 1000 metros.

### 13.2

``` text
ST_Buffer
↓
Crear una zona

ST_DWithin
↓
Preguntar si algo está dentro de una distancia
```

------------------------------------------------------------------------

# 🔴 Misión 14 - CRS

La propuesta:

``` sql
ST_SetSRID(geom, 25830)
```

es incorrecta si la geometría realmente está en EPSG:4326 y queremos
transformarla a EPSG:25830.

`ST_SetSRID()` no transforma las coordenadas. Asigna o modifica la
referencia espacial asociada.

Para transformar las coordenadas:

``` sql
ST_Transform(geom, 25830)
```

Regla fundamental:

``` text
ST_SetSRID
↓
Asignar referencia

ST_Transform
↓
Transformar coordenadas
```

------------------------------------------------------------------------

# 🔴 Misión 15 - Rendimiento

### 15.1 - Índice

GiST:

``` sql
CREATE INDEX idx_edificios_geom
ON edificios
USING GIST (geom);
```

Si la consulta utiliza `geom::geography`, puede considerarse:

``` sql
CREATE INDEX idx_edificios_geog
ON edificios
USING GIST (geom::geography);
```

### 15.2 - Diagnóstico

``` sql
EXPLAIN ANALYZE
SELECT *
FROM edificios
WHERE ST_DWithin(
    geom::geography,
    :punto::geography,
    1000
);
```

### 15.3 - Seq Scan vs Index Scan

`Seq Scan` recorre secuencialmente las filas de la tabla.

`Index Scan` utiliza un índice para localizar filas candidatas.

Un `Seq Scan` no implica automáticamente un problema: PostgreSQL puede
considerarlo más barato según tamaño, selectividad, estadísticas, coste
del índice y porcentaje de filas coincidentes.

------------------------------------------------------------------------

# 🔥 Nivel Final - Caso Integrado

## Misión 16 - Sistema de centros públicos

### 16.1 - Clasificación espacial

``` sql
SELECT
    c.nombre AS centro,
    m.nombre AS municipio
FROM centros c
JOIN municipios m
    ON ST_Within(c.geom, m.geom);
```

También:

``` sql
ON ST_Contains(m.geom, c.geom)
```

------------------------------------------------------------------------

### 16.2 - Número de incidencias

``` sql
SELECT
    c.id,
    c.nombre,
    COUNT(i.id) AS numero_incidencias
FROM centros c
LEFT JOIN incidencias i
    ON i.centro_id = c.id
GROUP BY c.id, c.nombre;
```

Se utiliza `LEFT JOIN` para conservar los centros sin incidencias.

------------------------------------------------------------------------

### 16.3 - Centros con más de 10 incidencias

``` sql
SELECT
    c.id,
    c.nombre,
    COUNT(i.id) AS numero_incidencias
FROM centros c
LEFT JOIN incidencias i
    ON i.centro_id = c.id
GROUP BY c.id, c.nombre
HAVING COUNT(i.id) > 10;
```

Se utiliza `HAVING` porque filtramos una agregación.

------------------------------------------------------------------------

### 16.4 - Centros a menos de 2 km

``` sql
SELECT *
FROM centros
WHERE ST_DWithin(
    geom::geography,
    :punto::geography,
    2000
);
```

`2000 metros = 2 kilómetros`.

------------------------------------------------------------------------

### 16.5 - Rendimiento

``` sql
CREATE INDEX idx_centros_geom
ON centros
USING GIST (geom);
```

Si se trabaja específicamente con `geography`, puede estudiarse un
índice sobre la expresión:

``` sql
CREATE INDEX idx_centros_geog
ON centros
USING GIST (geom::geography);
```

Diagnóstico:

``` sql
EXPLAIN ANALYZE
```

------------------------------------------------------------------------

### 16.6 - GeoJSON

Utilizar:

``` text
ST_AsGeoJSON
```

Ejemplo:

``` sql
SELECT
    id,
    nombre,
    ST_AsGeoJSON(geom) AS geometry
FROM centros;
```

La API puede utilizar posteriormente esta información para construir un
`Feature` o `FeatureCollection`.

------------------------------------------------------------------------

### 16.7 - Coordenadas

Si recibimos `latitude` y `longitude`:

``` text
X = longitude
Y = latitude
```

Ejemplo:

``` sql
ST_SetSRID(
    ST_MakePoint(
        :longitude,
        :latitude
    ),
    4326
)
```

------------------------------------------------------------------------

### 16.8 - Arquitectura

``` text
Frontend
   │
   │ latitude + longitude
   ▼
API
   │
   │ parámetros
   ▼
PostgreSQL + PostGIS
   │
   │ ST_MakePoint
   │ ST_SetSRID
   │ ST_DWithin
   ▼
Resultados
   │
   │ ST_AsGeoJSON
   ▼
API
   │
   ▼
Frontend
   │
   ▼
Mapa
```

Ejemplo:

``` sql
SELECT
    id,
    nombre,
    tipo,
    ST_AsGeoJSON(geom) AS geometry
FROM centros
WHERE ST_DWithin(
    geom::geography,
    ST_SetSRID(
        ST_MakePoint(
            :longitude,
            :latitude
        ),
        4326
    )::geography,
    :distance
);
```

------------------------------------------------------------------------

# 🧠 Bonus - Las 10 parejas peligrosas

## 17.1 - WHERE vs HAVING

``` text
WHERE
↓
Filtrar filas

HAVING
↓
Filtrar grupos
```

------------------------------------------------------------------------

## 17.2 - DELETE vs TRUNCATE vs DROP

``` text
DELETE
↓
Eliminar filas

TRUNCATE
↓
Vaciar tabla

DROP
↓
Eliminar objeto
```

------------------------------------------------------------------------

## 17.3 - PRIMARY KEY vs UNIQUE

``` text
PRIMARY KEY
↓
Identidad principal de la fila

UNIQUE
↓
Restricción de unicidad
```

Una clave primaria implica unicidad y no permite `NULL`.

------------------------------------------------------------------------

## 17.4 - VIEW vs MATERIALIZED VIEW

``` text
VIEW
↓
Consulta almacenada

MATERIALIZED VIEW
↓
Resultado almacenado físicamente
```

------------------------------------------------------------------------

## 17.5 - FUNCTION vs PROCEDURE

Una `FUNCTION` devuelve un valor y puede utilizarse dentro de
expresiones SQL según el sistema.

Un `PROCEDURE` está orientado a ejecutar acciones.

En Oracle:

``` text
FUNCTION
↓
Devuelve un valor

PROCEDURE
↓
Ejecuta una operación
```

------------------------------------------------------------------------

## 17.6 - ST_SetSRID vs ST_Transform

``` text
ST_SetSRID
↓
Asignar referencia espacial

ST_Transform
↓
Transformar coordenadas
```

------------------------------------------------------------------------

## 17.7 - ST_Intersects vs ST_Intersection

``` text
ST_Intersects
↓
Devuelve TRUE/FALSE

ST_Intersection
↓
Devuelve una geometría
```

------------------------------------------------------------------------

## 17.8 - ST_Distance vs ST_DWithin

``` text
ST_Distance
↓
¿Cuánto?

ST_DWithin
↓
¿Está dentro del límite?
```

Para búsquedas por proximidad, `ST_DWithin` suele ser preferible.

------------------------------------------------------------------------

## 17.9 - ST_Collect vs ST_Union

``` text
ST_Collect
↓
Agrupar geometrías

ST_Union
↓
Unir geométricamente
```

`ST_Union` puede disolver fronteras internas.

------------------------------------------------------------------------

## 17.10 - ST_Centroid vs ST_PointOnSurface

``` text
ST_Centroid
↓
Centro geométrico

ST_PointOnSurface
↓
Punto interior
```

El centroide no garantiza estar dentro del polígono, mientras que
`ST_PointOnSurface` está pensado para obtener un punto situado sobre la
superficie.

------------------------------------------------------------------------

# 🏁 Resumen de conceptos evaluados

## SQL

-   `SELECT`
-   `WHERE`
-   `JOIN`
-   `LEFT JOIN`
-   `GROUP BY`
-   `HAVING`
-   `COUNT`
-   `SUM`
-   `AVG`
-   `ORDER BY`
-   `LIMIT`
-   `NOT EXISTS`
-   Subconsultas

## PostgreSQL

-   `JSONB`
-   Operadores JSON
-   Window Functions
-   CTE
-   `EXPLAIN`
-   `EXPLAIN ANALYZE`
-   Índices
-   `MVCC`

## MySQL

-   InnoDB
-   `AUTO_INCREMENT`
-   MVCC
-   Diferencias con PostgreSQL

## Oracle

-   `SEQUENCE`
-   `VIEW`
-   `MATERIALIZED VIEW`
-   `SYNONYM`
-   `TABLESPACE`

## PL/SQL

-   Procedimientos
-   Parámetros
-   `UPDATE`
-   Excepciones
-   Cursores
-   Bucles

## PostGIS

-   Spatial Join
-   `ST_Within`
-   `ST_Contains`
-   `ST_DWithin`
-   `ST_Intersects`
-   `ST_Intersection`
-   `ST_Buffer`
-   `ST_Length`
-   `ST_SetSRID`
-   `ST_Transform`
-   `ST_AsGeoJSON`
-   `ST_MakePoint`
-   `geometry`
-   `geography`
-   SRID
-   GiST
-   `EXPLAIN ANALYZE`

------------------------------------------------------------------------

# 🎯 Conceptos especialmente importantes

``` text
WHERE
↓
Filtrar filas

HAVING
↓
Filtrar grupos
```

``` text
LEFT JOIN
↓
Conservar registros sin correspondencia
```

``` text
NOT EXISTS
↓
Comprobar ausencia de registros relacionados
```

``` text
EXPLAIN ANALYZE
↓
Analizar ejecución real
```

``` text
VIEW
↓
Consulta

MATERIALIZED VIEW
↓
Resultado almacenado
```

``` text
ST_SetSRID
↓
Asignar referencia

ST_Transform
↓
Transformar coordenadas
```

``` text
ST_Intersects
↓
Booleano

ST_Intersection
↓
Geometría
```

``` text
ST_Distance
↓
Distancia

ST_DWithin
↓
Proximidad
```

``` text
ST_Collect
↓
Agrupar

ST_Union
↓
Unión geométrica
```

``` text
ST_Centroid
↓
Centro

ST_PointOnSurface
↓
Punto interior
```

``` text
GiST
↓
Índice espacial
```

``` text
GeoJSON
↓
Intercambio habitual con aplicaciones web
```

------------------------------------------------------------------------

# 🏆 Fin de las soluciones
