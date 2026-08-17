<!-- encabezado-homogeneizado -->
# Bloque 03 - SIMULACRO
> **Bloque:** Bloque 03  
> **Documento:** Simulacro  
> **Preguntas de referencia:** 80  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# 🧪 Simulacro Tipo Test - Bloque 3

## Bases de Datos · SQL · PostgreSQL · MySQL · Oracle · PL/SQL · PostGIS

> **Simulacro orientado al formato de oposición**
>
> 80 preguntas · 4 opciones · 1 única respuesta correcta

---

# 📋 Instrucciones

- Lee cuidadosamente cada pregunta.
- Selecciona **una única respuesta**: A, B, C o D.
- No consultes el temario durante la primera realización.
- Las preguntas mezclan deliberadamente las distintas tecnologías del Bloque 3.
- Algunas preguntas contienen fragmentos de SQL.
- Hay distractores diseñados para parecer razonables.
- No se incluyen las soluciones en este documento.

## Baremo recomendado

Para una simulación de examen:

- ✅ Respuesta correcta: **+1 punto**
- ❌ Respuesta incorrecta: **0 puntos**
- ⬜ En blanco: **0 puntos**

> Si la convocatoria oficial utiliza penalización por respuestas incorrectas, aplica el baremo real de la convocatoria en lugar de este.

---

# 🧠 EXAMEN

## Pregunta 1

¿Cuál de las siguientes afirmaciones sobre una clave primaria es correcta?

A) Puede contener valores `NULL` siempre que no se repitan.  
B) Identifica de forma única cada fila y no admite `NULL`.  
C) Solo puede existir si también hay una clave foránea.  
D) Puede haber cualquier número de claves primarias independientes en una tabla.

---

## Pregunta 2

En SQL, ¿qué cláusula se utiliza para filtrar grupos después de aplicar una función de agregación?

A) `WHERE`  
B) `ORDER BY`  
C) `HAVING`  
D) `FILTER`

---

## Pregunta 3

Dadas las tablas:

```text
clientes
---------
id
nombre

pedidos
---------
id
cliente_id
total
```

¿Qué tipo de `JOIN` permite obtener todos los clientes, incluidos aquellos que no tienen pedidos?

A) `INNER JOIN`  
B) `LEFT JOIN`  
C) `CROSS JOIN`  
D) `SELF JOIN`

---

## Pregunta 4

¿Qué función SQL permite obtener el número de registros que cumplen una determinada consulta?

A) `SUM()`  
B) `COUNT()`  
C) `TOTAL()`  
D) `NUMBER()`

---

## Pregunta 5

¿Qué afirmación describe correctamente una transacción?

A) Es exclusivamente una consulta `SELECT`.  
B) Es un conjunto de operaciones tratado como una unidad lógica de trabajo.  
C) Solo puede contener operaciones de lectura.  
D) No puede deshacerse una vez iniciada.

---

## Pregunta 6

¿Qué instrucción confirma permanentemente, dentro del modelo transaccional correspondiente, las operaciones realizadas en una transacción?

A) `SAVE`  
B) `COMMIT`  
C) `CONFIRM`  
D) `PERSIST`

---

## Pregunta 7

¿Qué instrucción permite deshacer los cambios de una transacción que todavía no han sido confirmados?

A) `UNDO`  
B) `ROLLBACK`  
C) `REVERT`  
D) `CANCEL`

---

## Pregunta 8

¿Cuál de las siguientes afirmaciones sobre `DELETE`, `TRUNCATE` y `DROP` es correcta?

A) `DROP` elimina las filas pero conserva la tabla.  
B) `TRUNCATE` elimina la definición de la tabla.  
C) `DELETE` puede utilizar una cláusula `WHERE`.  
D) `DELETE` y `DROP` son equivalentes.

---

## Pregunta 9

¿Qué cláusula permite ordenar el resultado de una consulta?

A) `SORT BY`  
B) `ORDER BY`  
C) `GROUP BY`  
D) `ARRANGE BY`

---

## Pregunta 10

¿Qué ocurre conceptualmente al utilizar `GROUP BY`?

A) Se eliminan físicamente las filas originales.  
B) Se agrupan filas según una o varias expresiones para poder realizar operaciones agregadas.  
C) Se crea automáticamente un índice.  
D) Se convierte una tabla en una vista.

---

## Pregunta 11

¿Cuál de las siguientes operaciones devuelve normalmente un único valor agregado para un conjunto de filas?

A) `SUM()`  
B) `ORDER BY`  
C) `JOIN`  
D) `WHERE`

---

## Pregunta 12

¿Cuál es la principal finalidad de una `FOREIGN KEY`?

A) Garantizar que una columna contenga únicamente números.  
B) Garantizar unicidad absoluta de una columna.  
C) Establecer una relación referencial con otra tabla.  
D) Crear automáticamente una vista.

---

## Pregunta 13

¿Qué problema caracteriza al patrón N+1 en aplicaciones que utilizan bases de datos?

A) Una tabla contiene exactamente N+1 columnas.  
B) Se ejecuta una consulta inicial y después una consulta adicional por cada registro obtenido.  
C) Una consulta contiene N+1 condiciones `WHERE`.  
D) Se crean N+1 índices sobre una misma columna.

---

## Pregunta 14

¿Cuál de las siguientes afirmaciones sobre `UNIQUE` es correcta?

A) Su finalidad es garantizar que determinados valores no se repitan.  
B) Solo puede existir una restricción `UNIQUE` por tabla.  
C) Siempre sustituye a una clave primaria.  
D) Solo puede aplicarse a claves foráneas.

---

## Pregunta 15

¿Qué característica permite realizar un cálculo acumulado manteniendo las filas individuales en el resultado?

A) `GROUP BY`  
B) Window Function  
C) `DISTINCT`  
D) `UNION`

---

# 🟦 PostgreSQL

## Pregunta 16

¿Qué sistema gestor está asociado directamente con `PL/pgSQL`?

A) MySQL  
B) PostgreSQL  
C) Oracle  
D) SQL Server

---

## Pregunta 17

¿Qué tipo de dato de PostgreSQL está especialmente orientado a almacenar JSON en una representación binaria optimizada?

A) `XMLB`  
B) `JSONB`  
C) `TEXTJSON`  
D) `BJSON`

---

## Pregunta 18

Dado:

```sql
datos JSONB
```

¿qué expresión permite obtener el campo `ciudad` como texto desde:

```json
{
  "direccion": {
    "ciudad": "Murcia"
  }
}
```

?

A) `datos->'direccion'->>'ciudad'`  
B) `datos->>'direccion'->'ciudad'`  
C) `datos::text.ciudad`  
D) `datos['direccion']['ciudad']`

---

## Pregunta 19

¿Qué característica permite definir una consulta auxiliar reutilizable dentro de otra consulta?

A) Trigger  
B) CTE  
C) Sequence  
D) Cursor

---

## Pregunta 20

¿Cuál de las siguientes expresiones define correctamente una CTE?

A) `CREATE TEMP QUERY ...`  
B) `WITH nombre AS (...)`  
C) `TEMPORARY nombre AS (...)`  
D) `DECLARE QUERY nombre ...`

---

## Pregunta 21

¿Cuál es una característica de una Window Function?

A) Siempre reduce varias filas a una única fila.  
B) Permite realizar cálculos sobre un conjunto de filas relacionadas conservando las filas individuales.  
C) Solo puede utilizarse con `DELETE`.  
D) Sustituye obligatoriamente a `GROUP BY`.

---

## Pregunta 22

En:

```sql
SUM(importe) OVER (
    PARTITION BY usuario_id
    ORDER BY fecha
)
```

¿qué finalidad tiene `PARTITION BY usuario_id`?

A) Elimina los usuarios duplicados.  
B) Divide las filas en grupos lógicos para realizar el cálculo de ventana por usuario.  
C) Ordena los usuarios alfabéticamente.  
D) Crea un índice sobre `usuario_id`.

---

## Pregunta 23

¿Qué comando resulta especialmente útil para analizar el plan de ejecución real de una consulta PostgreSQL?

A) `DESCRIBE QUERY`  
B) `EXPLAIN ANALYZE`  
C) `SHOW EXECUTION`  
D) `ANALYZE QUERY ONLY`

---

## Pregunta 24

¿Cuál es la diferencia fundamental entre `EXPLAIN` y `EXPLAIN ANALYZE`?

A) `EXPLAIN` modifica los datos y `EXPLAIN ANALYZE` no.  
B) `EXPLAIN ANALYZE` ejecuta la consulta y proporciona información real de ejecución.  
C) `EXPLAIN` solo funciona con `SELECT`.  
D) No existe ninguna diferencia.

---

## Pregunta 25

¿Qué método de indexación se utiliza habitualmente para índices espaciales en PostGIS?

A) GiST  
B) HASH exclusivamente  
C) BTREE exclusivamente  
D) XML

---

## Pregunta 26

¿Qué significa MVCC?

A) Multi-Value Column Control  
B) Multi-Version Concurrency Control  
C) Multiple View Cache Configuration  
D) Managed Versioned Column Control

---

## Pregunta 27

¿Qué ventaja conceptual proporciona MVCC?

A) Impide que existan transacciones simultáneas.  
B) Facilita el control de concurrencia mediante diferentes versiones de los datos.  
C) Elimina la necesidad de índices.  
D) Convierte todas las consultas en operaciones de solo lectura.

---

# 🟩 MySQL

## Pregunta 28

¿Cuál de los siguientes es un motor de almacenamiento ampliamente asociado a MySQL y con soporte transaccional?

A) InnoDB  
B) GiST  
C) PL/pgSQL  
D) PostGIS

---

## Pregunta 29

¿Cuál de las siguientes características está tradicionalmente asociada a MySQL?

A) `AUTO_INCREMENT`  
B) `ST_Transform`  
C) `TABLESPACE` como concepto exclusivo de PostgreSQL  
D) `PL/SQL`

---

## Pregunta 30

¿Cuál de las siguientes afirmaciones sobre InnoDB es correcta?

A) Es un motor de almacenamiento de MySQL.  
B) Es una extensión espacial de PostgreSQL.  
C) Es un lenguaje procedural de Oracle.  
D) Es un formato GeoJSON.

---

## Pregunta 31

¿Cuál de las siguientes tecnologías está asociada a PostgreSQL y no constituye una característica propia de InnoDB?

A) MVCC  
B) Transacciones  
C) `JSONB`  
D) Índices

---

## Pregunta 32

¿Cuál de las siguientes afirmaciones es correcta?

A) PostgreSQL y MySQL son lenguajes SQL.  
B) PostgreSQL y MySQL son sistemas gestores de bases de datos que soportan SQL.  
C) MySQL es una extensión de PostgreSQL.  
D) PostgreSQL es un motor de almacenamiento de MySQL.

---

# 🟧 Oracle

## Pregunta 33

¿Qué objeto de Oracle permite generar una secuencia de valores numéricos?

A) View  
B) Sequence  
C) Synonym  
D) Tablespace

---

## Pregunta 34

¿Qué objeto proporciona una representación lógica basada en una consulta?

A) VIEW  
B) SEQUENCE  
C) TABLESPACE  
D) INDEX FILE

---

## Pregunta 35

¿Qué diferencia principal existe entre una `VIEW` y una `MATERIALIZED VIEW`?

A) Una VIEW solo puede contener una columna.  
B) Una MATERIALIZED VIEW almacena físicamente el resultado de una consulta.  
C) Una VIEW siempre almacena físicamente sus resultados.  
D) Una MATERIALIZED VIEW no puede contener consultas.

---

## Pregunta 36

¿Para qué sirve principalmente un `SYNONYM` en Oracle?

A) Para crear un índice espacial.  
B) Para proporcionar un nombre alternativo a un objeto.  
C) Para iniciar una transacción.  
D) Para almacenar datos JSON.

---

## Pregunta 37

¿Qué representa un `TABLESPACE` en Oracle?

A) Una estructura lógica relacionada con la organización del almacenamiento.  
B) Un lenguaje procedural.  
C) Una función espacial.  
D) Un tipo de índice JSON.

---

## Pregunta 38

¿Cuál de los siguientes elementos es característico de Oracle?

A) `PL/SQL`  
B) `PL/pgSQL`  
C) `InnoDB`  
D) `PostGIS`

---

# 🟨 PL/SQL

## Pregunta 39

¿Qué es PL/SQL?

A) Un motor de almacenamiento de MySQL.  
B) Una extensión procedural de SQL utilizada en Oracle.  
C) Un sistema de coordenadas geográficas.  
D) Un índice espacial.

---

## Pregunta 40

¿Cuál es la diferencia conceptual más adecuada entre una función y un procedimiento en PL/SQL?

A) Una función está orientada a devolver un valor, mientras un procedimiento está orientado a ejecutar una operación.  
B) Un procedimiento siempre devuelve una tabla.  
C) Una función no puede recibir parámetros.  
D) No existe ninguna diferencia.

---

## Pregunta 41

¿Qué sección de un bloque PL/SQL se utiliza para gestionar excepciones?

A) `CATCH`  
B) `ERROR`  
C) `EXCEPTION`  
D) `HANDLE`

---

## Pregunta 42

¿Qué estructura representa correctamente la organización básica de un bloque PL/SQL?

A) `BEGIN -> DECLARE -> END -> EXCEPTION`  
B) `DECLARE -> BEGIN -> EXCEPTION -> END`  
C) `EXCEPTION -> BEGIN -> DECLARE -> END`  
D) `START -> SQL -> END`

---

## Pregunta 43

¿Cuál es la finalidad de un cursor en PL/SQL?

A) Crear una tabla temporal automáticamente.  
B) Procesar un conjunto de filas de forma controlada.  
C) Transformar coordenadas.  
D) Crear una clave primaria.

---

## Pregunta 44

¿Cuál de las siguientes construcciones permite recorrer un cursor de forma sencilla en PL/SQL?

A) `FOR registro IN cursor LOOP`  
B) `FOREACH cursor AS registro`  
C) `LOOP cursor INTO registro FOR`  
D) `ITERATE cursor`

---

## Pregunta 45

¿Qué riesgo puede tener utilizar indiscriminadamente:

```sql
WHEN OTHERS THEN
```

?

A) Hace que Oracle deje de ejecutar SQL.  
B) Puede ocultar errores si no se realiza una gestión adecuada de la excepción.  
C) Convierte automáticamente todos los errores en advertencias.  
D) Solo funciona en PostgreSQL.

---

## Pregunta 46

Si un procedimiento recibe un identificador de empleado y un porcentaje de aumento salarial, ¿qué operación SQL sería la más directamente relacionada con la modificación del salario?

A) `UPDATE`  
B) `SELECT DISTINCT`  
C) `CREATE VIEW`  
D) `DROP`

---

# 🟥 PostGIS

## Pregunta 47

¿Qué añade PostGIS a PostgreSQL?

A) Funcionalidad para trabajar con datos espaciales y geográficos.  
B) Un motor de almacenamiento de MySQL.  
C) Un lenguaje procedural de Oracle.  
D) Un sistema operativo.

---

## Pregunta 48

¿Cuál de los siguientes tipos representa una geometría en PostGIS?

A) `geometry`  
B) `spatialtext`  
C) `geopointsql`  
D) `mapdata`

---

## Pregunta 49

¿Cuál es una diferencia conceptual entre `geometry` y `geography`?

A) `geometry` y `geography` son exactamente equivalentes en todos los aspectos.  
B) `geography` está orientado a coordenadas geográficas sobre la Tierra y facilita determinadas operaciones de distancia en unidades como metros.  
C) `geometry` solo puede almacenar puntos.  
D) `geography` solo puede almacenar polígonos.

---

## Pregunta 50

¿Qué función devuelve `TRUE` cuando una geometría está dentro de otra según la relación espacial correspondiente?

A) `ST_Within`  
B) `ST_Buffer`  
C) `ST_Length`  
D) `ST_AsGeoJSON`

---

## Pregunta 51

¿Cuál es la relación conceptual inversa de `ST_Within`?

A) `ST_Contains`  
B) `ST_Intersection`  
C) `ST_Distance`  
D) `ST_Collect`

---

## Pregunta 52

¿Qué función resulta especialmente adecuada para comprobar si dos geometrías están dentro de una distancia determinada?

A) `ST_DWithin`  
B) `ST_DistanceOnly`  
C) `ST_Near`  
D) `ST_Radius`

---

## Pregunta 53

¿Qué función calcula la distancia entre dos geometrías?

A) `ST_Distance`  
B) `ST_DWithin`  
C) `ST_DifferenceDistance`  
D) `ST_Measure`

---

## Pregunta 54

¿Cuál de las siguientes afirmaciones es correcta?

A) `ST_Distance` y `ST_DWithin` siempre devuelven exactamente el mismo tipo de resultado.  
B) `ST_Distance` calcula una distancia, mientras `ST_DWithin` comprueba si se cumple un umbral de distancia.  
C) `ST_DWithin` crea un buffer.  
D) `ST_Distance` crea un índice espacial.

---

## Pregunta 55

¿Qué función permite crear una zona alrededor de una geometría?

A) `ST_Buffer`  
B) `ST_Zone`  
C) `ST_Radius`  
D) `ST_ExpandOnly`

---

## Pregunta 56

¿Qué función permite comprobar si dos geometrías tienen una intersección espacial?

A) `ST_Intersects`  
B) `ST_Intersection`  
C) `ST_OverlapOnly`  
D) `ST_CrossCheck`

---

## Pregunta 57

¿Cuál es la diferencia principal entre `ST_Intersects` y `ST_Intersection`?

A) Ambas devuelven siempre una geometría.  
B) `ST_Intersects` devuelve una condición booleana, mientras `ST_Intersection` devuelve la geometría resultante.  
C) `ST_Intersection` devuelve siempre un booleano.  
D) No existe diferencia.

---

## Pregunta 58

¿Qué función permite obtener la parte común de dos geometrías?

A) `ST_Intersects`  
B) `ST_Intersection`  
C) `ST_Common`  
D) `ST_Shared`

---

## Pregunta 59

¿Qué función calcula una unión geométrica?

A) `ST_Union`  
B) `ST_Collect`  
C) `ST_MergeOnly`  
D) `ST_CombineText`

---

## Pregunta 60

¿Qué función agrupa geometrías en una colección sin realizar necesariamente una disolución geométrica?

A) `ST_Collect`  
B) `ST_Union`  
C) `ST_Dissolve`  
D) `ST_GroupGeometry`

---

## Pregunta 61

¿Qué afirmación sobre `ST_SetSRID` es correcta?

A) Transforma las coordenadas de una geometría.  
B) Asigna o modifica el SRID asociado a una geometría sin transformar sus coordenadas.  
C) Calcula la distancia entre dos puntos.  
D) Convierte siempre `geometry` en `geography`.

---

## Pregunta 62

¿Qué función se utiliza para transformar las coordenadas de una geometría a otro sistema de referencia?

A) `ST_SetSRID`  
B) `ST_Transform`  
C) `ST_ConvertCRS`  
D) `ST_ReprojectOnly`

---

## Pregunta 63

Una geometría está realmente en EPSG:4326 y queremos transformarla a EPSG:25830. ¿Cuál es la opción correcta?

A) `ST_SetSRID(geom, 25830)`  
B) `ST_Transform(geom, 25830)`  
C) `ST_AsGeoJSON(geom, 25830)`  
D) `ST_Buffer(geom, 25830)`

---

## Pregunta 64

¿Qué representan normalmente las coordenadas de un punto creado mediante:

```sql
ST_MakePoint(longitude, latitude)
```

?

A) X = latitude, Y = longitude.  
B) X = longitude, Y = latitude.  
C) X e Y representan siempre metros.  
D) El orden es irrelevante.

---

## Pregunta 65

¿Qué función permite convertir una geometría a GeoJSON?

A) `ST_AsGeoJSON`  
B) `ST_ToJSONGeometry`  
C) `ST_GeoJSON`  
D) `ST_ExportJSON`

---

## Pregunta 66

¿Qué función sería apropiada para calcular el centroide geométrico de un polígono?

A) `ST_Centroid`  
B) `ST_CenterPoint`  
C) `ST_PointOnSurface` exclusivamente  
D) `ST_Middle`

---

## Pregunta 67

¿Qué ventaja tiene `ST_PointOnSurface` frente a `ST_Centroid` para determinadas tareas cartográficas?

A) Garantiza un punto situado sobre la superficie correspondiente, útil para etiquetas.  
B) Siempre devuelve el centro geométrico exacto.  
C) Solo funciona con puntos.  
D) Convierte automáticamente el polígono a GeoJSON.

---

# 🟪 Rendimiento, índices e integración

## Pregunta 68

¿Qué tipo de índice se utiliza habitualmente en PostGIS para datos espaciales?

A) GiST  
B) XML  
C) JSONB exclusivamente  
D) Sequence

---

## Pregunta 69

Una tabla contiene millones de geometrías y una consulta espacial es lenta. ¿Cuál sería una actuación razonable?

A) Eliminar todos los índices.  
B) Utilizar `EXPLAIN ANALYZE` y comprobar el plan de ejecución.  
C) Cambiar todos los tipos a texto sin analizar nada.  
D) Ejecutar la misma consulta repetidamente esperando que mejore.

---

## Pregunta 70

¿Qué describe mejor un `Seq Scan`?

A) Acceso secuencial a las filas de una tabla.  
B) Acceso exclusivo mediante índice.  
C) Una consulta espacial.  
D) Una transacción.

---

## Pregunta 71

¿Es necesariamente incorrecto que PostgreSQL utilice un `Seq Scan`?

A) Sí, cualquier `Seq Scan` indica que falta un índice.  
B) No, PostgreSQL puede considerar que un recorrido secuencial es más barato.  
C) Sí, salvo en tablas temporales.  
D) Solo depende del número de columnas.

---

## Pregunta 72

Tenemos:

```sql
WHERE ST_DWithin(
    geom::geography,
    :punto::geography,
    1000
)
```

¿Qué opción puede ser relevante para mejorar el rendimiento?

A) Considerar un índice GiST apropiado para la expresión utilizada.  
B) Crear una `SEQUENCE`.  
C) Crear un `SYNONYM`.  
D) Convertir la geometría a texto antes de consultar.

---

## Pregunta 73

Una API recibe `latitude` y `longitude`. ¿Cuál es la construcción adecuada de un punto con SRID 4326?

A)

```sql
ST_SetSRID(
    ST_MakePoint(latitude, longitude),
    4326
)
```

B)

```sql
ST_SetSRID(
    ST_MakePoint(longitude, latitude),
    4326
)
```

C)

```sql
ST_Transform(
    ST_MakePoint(longitude, latitude),
    4326
)
```

D)

```sql
ST_AsGeoJSON(
    ST_MakePoint(longitude, latitude)
)
```

---

## Pregunta 74

¿Qué formato resulta especialmente habitual para devolver geometrías desde una API hacia una aplicación web cartográfica?

A) GeoJSON  
B) PL/SQL  
C) InnoDB  
D) TABLESPACE

---

## Pregunta 75

¿Qué función permite convertir una geometría PostGIS a GeoJSON?

A) `ST_AsGeoJSON`  
B) `ST_ToSQL`  
C) `ST_AsMap`  
D) `ST_GeoExport`

---

# 🔥 Preguntas de dificultad alta

## Pregunta 76

Tenemos una geometría con:

```text
SRID = 4326
```

Un desarrollador quiere asignarle EPSG:25830 y escribe:

```sql
ST_SetSRID(geom, 25830)
```

¿Qué problema existe?

A) Ninguno: `ST_SetSRID` siempre transforma las coordenadas.  
B) Se cambia la referencia declarada sin transformar las coordenadas, por lo que puede producir una interpretación incorrecta de la posición.  
C) `ST_SetSRID` solo funciona con EPSG:4326.  
D) EPSG:25830 no puede utilizarse en PostGIS.

---

## Pregunta 77

¿Cuál de las siguientes consultas expresa mejor una búsqueda de hospitales situados a menos de 5 km de un punto?

A)

```sql
WHERE ST_Distance(
    geom::geography,
    :punto::geography
) < 5000
```

B)

```sql
WHERE ST_DWithin(
    geom::geography,
    :punto::geography,
    5000
)
```

C)

```sql
WHERE ST_Buffer(
    geom::geography,
    5000
)
```

D)

```sql
WHERE ST_Within(
    geom::geography,
    :punto::geography
)
```

---

## Pregunta 78

¿Cuál de las siguientes afirmaciones sobre `ST_DWithin` es más adecuada?

A) Su única finalidad es crear geometrías circulares.  
B) Puede utilizarse para comprobar proximidad y, con una estrategia de indexación adecuada, resulta apropiada para búsquedas espaciales por distancia.  
C) Siempre devuelve la distancia exacta entre dos objetos.  
D) Solo funciona con polígonos.

---

## Pregunta 79

Queremos obtener la longitud de la parte de una carretera que queda dentro de un municipio. ¿Cuál de las siguientes secuencias conceptuales es la más adecuada?

A) `ST_Intersection` → `ST_Length`  
B) `ST_Buffer` → `ST_Centroid`  
C) `ST_Union` → `ST_AsGeoJSON`  
D) `ST_SetSRID` → `ST_Collect`

---

## Pregunta 80

Una consulta PostGIS sobre 20 millones de registros tarda varios segundos. ¿Cuál de las siguientes estrategias es la más completa?

A) Crear un índice cualquiera sin analizar la consulta.  
B) Ejecutar `EXPLAIN ANALYZE`, comprobar el plan, revisar la selectividad, verificar el CRS/tipo espacial y comprobar que existe un índice espacial adecuado para la operación realizada.  
C) Sustituir todas las geometrías por cadenas de texto.  
D) Utilizar siempre `ST_Buffer` antes de cualquier consulta espacial.

---

# 📝 HOJA DE RESPUESTAS

Marca únicamente una opción por pregunta.

| Nº | Respuesta | Nº | Respuesta | Nº | Respuesta | Nº | Respuesta |
|---:|:---:|---:|:---:|---:|:---:|---:|:---:|
| 1 | | 21 | | 41 | | 61 | |
| 2 | | 22 | | 42 | | 62 | |
| 3 | | 23 | | 43 | | 63 | |
| 4 | | 24 | | 44 | | 64 | |
| 5 | | 25 | | 45 | | 65 | |
| 6 | | 26 | | 46 | | 66 | |
| 7 | | 27 | | 47 | | 67 | |
| 8 | | 28 | | 48 | | 68 | |
| 9 | | 29 | | 49 | | 69 | |
| 10 | | 30 | | 50 | | 70 | |
| 11 | | 31 | | 51 | | 71 | |
| 12 | | 32 | | 52 | | 72 | |
| 13 | | 33 | | 53 | | 73 | |
| 14 | | 34 | | 54 | | 74 | |
| 15 | | 35 | | 55 | | 75 | |
| 16 | | 36 | | 56 | | 76 | |
| 17 | | 37 | | 57 | | 77 | |
| 18 | | 38 | | 58 | | 78 | |
| 19 | | 39 | | 59 | | 79 | |
| 20 | | 40 | | 60 | | 80 | |

---

# 📊 RESULTADO

## Puntuación

```text
Aciertos:      ____ / 80
Fallos:        ____
En blanco:     ____
Porcentaje:    ____ %
```

---

## Evaluación orientativa

| Resultado | Nivel |
|---:|---|
| 72-80 | 🟢 Excelente dominio |
| 64-71 | 🟢 Muy buen nivel |
| 56-63 | 🟡 Buen nivel, con puntos a reforzar |
| 48-55 | 🟠 Nivel intermedio |
| 40-47 | 🟠 Necesita repaso |
| < 40 | 🔴 Conviene volver a los fundamentos |

> Este baremo es únicamente orientativo. Para la oposición real deberá utilizarse el sistema de puntuación de la convocatoria.

---

# 🔍 ANÁLISIS POR ÁREAS

Después de corregir el examen, calcula:

```text
SQL:
____ / 15

PostgreSQL:
____ / 12

MySQL:
____ / 5

Oracle:
____ / 6

PL/SQL:
____ / 8

PostGIS:
____ / 21

Rendimiento e integración:
____ / 8

Alta dificultad:
____ / 5
```

> Las preguntas están diseñadas para que el resultado por áreas permita localizar los puntos débiles, no solo obtener una nota global.

---

# 🎯 OBJETIVO DEL SIMULACRO

La finalidad de este test no es demostrar que recuerdas literalmente las 13.000 líneas del capítulo de PostGIS ni las 9.000 de PL/SQL.

El objetivo es comprobar si puedes reconocer rápidamente conceptos como:

```text
WHERE        → filas
HAVING       → grupos
JOIN         → relaciones
GROUP BY     → agrupación
CTE          → consulta auxiliar
Window       → cálculo manteniendo filas
EXPLAIN      → plan
MVCC         → concurrencia
```

y:

```text
ST_Within       → dentro
ST_Contains     → contiene
ST_DWithin      → proximidad
ST_Distance     → distancia
ST_Buffer       → zona
ST_Intersects   → ¿intersectan?
ST_Intersection → geometría común
ST_Union        → unión
ST_Collect      → colección
```

y especialmente:

```text
ST_SetSRID
↓
Asignar referencia espacial

ST_Transform
↓
Transformar coordenadas
```

---

# 🏁 FIN DEL SIMULACRO

**No consultes las soluciones hasta haber terminado las 80 preguntas.**

---

# DESAFÍO EXTRA

**Puedes intentar [este ejercicio práctico](simulacro-practico-bloque-3.md) para afianzar conocimientos** 

### [Accede desde aquí a la plantilla de respuestas y explicaciones](plantilla-y-correcciones-simulacro-03.md)


