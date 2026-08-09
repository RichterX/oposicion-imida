# 📝 Plantilla de Corrección - Simulacro Bloque 3

## Bases de Datos · SQL · PostgreSQL · MySQL · Oracle · PL/SQL · PostGIS

> **Documento de corrección del simulacro tipo test de 80 preguntas.**
>
> Utilizar después de completar el examen.

---

# 📋 Criterio de corrección

## Baremo base

- ✅ Respuesta correcta: **+1 punto**
- ❌ Respuesta incorrecta: **0 puntos**
- ⬜ En blanco: **0 puntos**

**Puntuación máxima: 80 puntos**

> Para la oposición real debe aplicarse el sistema de penalización establecido en la convocatoria. Este simulacro utiliza un baremo sencillo para facilitar el análisis del aprendizaje.

---

# 🗝️ Plantilla de respuestas correctas

| Nº | Correcta | Nº | Correcta | Nº | Correcta | Nº | Correcta |
|---:|:---:|---:|:---:|---:|:---:|---:|:---:|
| 1 | B | 21 | B | 41 | C | 61 | B |
| 2 | C | 22 | B | 42 | B | 62 | B |
| 3 | B | 23 | B | 43 | B | 63 | B |
| 4 | B | 24 | B | 44 | A | 64 | B |
| 5 | B | 25 | A | 45 | B | 65 | A |
| 6 | B | 26 | B | 46 | A | 66 | A |
| 7 | B | 27 | B | 47 | A | 67 | A |
| 8 | C | 28 | A | 48 | A | 68 | A |
| 9 | B | 29 | A | 49 | B | 69 | B |
| 10 | B | 30 | A | 50 | A | 70 | A |
| 11 | A | 31 | C | 51 | A | 71 | B |
| 12 | C | 32 | B | 52 | A | 72 | A |
| 13 | B | 33 | B | 53 | A | 73 | B |
| 14 | A | 34 | A | 54 | B | 74 | A |
| 15 | B | 35 | B | 55 | A | 75 | A |
| 16 | B | 36 | B | 56 | A | 76 | B |
| 17 | B | 37 | A | 57 | B | 77 | B |
| 18 | A | 38 | A | 58 | B | 78 | B |
| 19 | B | 39 | B | 59 | A | 79 | A |
| 20 | B | 40 | A | 60 | A | 80 | B |

---

# 🧠 Corrección razonada

## 🟢 Preguntas 1-15 - SQL y fundamentos

### 1. **B** ✔️

La clave primaria identifica de forma única cada fila y no admite valores `NULL`.

---

### 2. **C** ✔️

`HAVING` permite filtrar grupos después de aplicar funciones de agregación.

```sql
GROUP BY ...
HAVING COUNT(*) > 10
```

Regla:

```text
WHERE
↓
filtra filas

HAVING
↓
filtra grupos
```

---

### 3. **B** ✔️

`LEFT JOIN` conserva todas las filas de la tabla situada a la izquierda, aunque no exista una fila relacionada a la derecha.

---

### 4. **B** ✔️

`COUNT()` permite contar filas o valores no nulos, dependiendo de la expresión utilizada.

---

### 5. **B** ✔️

Una transacción agrupa operaciones que deben tratarse como una unidad lógica de trabajo.

---

### 6. **B** ✔️

`COMMIT` confirma los cambios de la transacción.

---

### 7. **B** ✔️

`ROLLBACK` deshace los cambios no confirmados de la transacción, dentro del comportamiento transaccional correspondiente.

---

### 8. **C** ✔️

`DELETE` permite utilizar `WHERE`:

```sql
DELETE FROM empleados
WHERE id = 10;
```

En cambio, `TRUNCATE` vacía la tabla y `DROP` elimina el objeto.

---

### 9. **B** ✔️

`ORDER BY` controla el orden del conjunto de resultados.

---

### 10. **B** ✔️

`GROUP BY` agrupa filas según una o varias expresiones, permitiendo realizar agregaciones por grupo.

---

### 11. **A** ✔️

`SUM()` es una función de agregación que calcula la suma de un conjunto de valores.

---

### 12. **C** ✔️

Una `FOREIGN KEY` establece una relación referencial con otra tabla.

---

### 13. **B** ✔️

El patrón N+1 aparece cuando se realiza una consulta inicial y después una consulta adicional por cada elemento obtenido.

Ejemplo conceptual:

```text
1 consulta
+
N consultas
=
N+1
```

Es un problema habitual en aplicaciones que acceden a relaciones de forma ineficiente.

---

### 14. **A** ✔️

`UNIQUE` garantiza que los valores afectados por la restricción no se repitan.

---

### 15. **B** ✔️

Una Window Function permite calcular información relacionada con un conjunto de filas sin eliminar las filas individuales del resultado.

---

# 🟦 Preguntas 16-27 - PostgreSQL

### 16. **B** ✔️

`PL/pgSQL` es el lenguaje procedural asociado a PostgreSQL.

---

### 17. **B** ✔️

`JSONB` almacena datos JSON en una representación binaria optimizada y permite utilizar operadores e índices específicos.

---

### 18. **A** ✔️

La expresión:

```sql
datos->'direccion'->>'ciudad'
```

accede al objeto `direccion` y posteriormente obtiene `ciudad` como texto.

---

### 19. **B** ✔️

Una CTE permite definir una consulta auxiliar dentro de otra consulta.

---

### 20. **B** ✔️

La sintaxis característica es:

```sql
WITH nombre AS (
    ...
)
SELECT ...
```

---

### 21. **B** ✔️

Las Window Functions realizan cálculos sobre filas relacionadas conservando las filas individuales.

---

### 22. **B** ✔️

`PARTITION BY usuario_id` divide lógicamente las filas en particiones para realizar el cálculo de ventana independientemente por usuario.

---

### 23. **B** ✔️

`EXPLAIN ANALYZE` permite analizar la ejecución real de una consulta.

---

### 24. **B** ✔️

`EXPLAIN` muestra el plan estimado.

`EXPLAIN ANALYZE` ejecuta la consulta y añade información observada durante su ejecución.

---

### 25. **A** ✔️

`GiST` es un método de indexación utilizado habitualmente para índices espaciales en PostgreSQL/PostGIS.

---

### 26. **B** ✔️

MVCC significa:

```text
Multi-Version Concurrency Control
```

---

### 27. **B** ✔️

MVCC permite gestionar concurrencia utilizando diferentes versiones de los datos, reduciendo determinados conflictos entre lecturas y escrituras.

---

# 🟩 Preguntas 28-32 - MySQL

### 28. **A** ✔️

`InnoDB` es un motor de almacenamiento de MySQL con soporte para transacciones y otras características relevantes para aplicaciones transaccionales.

---

### 29. **A** ✔️

`AUTO_INCREMENT` es una característica tradicionalmente asociada a MySQL para generar valores incrementales.

---

### 30. **A** ✔️

InnoDB es un motor de almacenamiento de MySQL.

---

### 31. **C** ✔️

`JSONB` es una característica propia de PostgreSQL, mientras que MVCC, transacciones e índices también aparecen en InnoDB.

---

### 32. **B** ✔️

PostgreSQL y MySQL son sistemas gestores de bases de datos que soportan SQL.

---

# 🟧 Preguntas 33-38 - Oracle

### 33. **B** ✔️

Una `SEQUENCE` genera una secuencia de valores numéricos.

---

### 34. **A** ✔️

Una `VIEW` proporciona una representación lógica basada en una consulta.

---

### 35. **B** ✔️

Una `MATERIALIZED VIEW` almacena físicamente el resultado de una consulta.

---

### 36. **B** ✔️

Un `SYNONYM` proporciona un nombre alternativo para un objeto.

---

### 37. **A** ✔️

Un `TABLESPACE` es una estructura lógica relacionada con la organización del almacenamiento de Oracle.

---

### 38. **A** ✔️

`PL/SQL` es el lenguaje procedural asociado a Oracle.

---

# 🟨 Preguntas 39-46 - PL/SQL

### 39. **B** ✔️

PL/SQL es una extensión procedural de SQL utilizada en Oracle.

---

### 40. **A** ✔️

Una función está orientada a devolver un valor, mientras que un procedimiento está orientado a ejecutar una operación.

---

### 41. **C** ✔️

La sección:

```sql
EXCEPTION
```

se utiliza para gestionar excepciones en un bloque PL/SQL.

---

### 42. **B** ✔️

La estructura conceptual básica es:

```text
DECLARE
   ↓
BEGIN
   ↓
EXCEPTION
   ↓
END
```

La sección `DECLARE` es opcional, pero cuando aparece ocupa esa posición.

---

### 43. **B** ✔️

Un cursor permite recorrer y procesar un conjunto de filas de forma controlada.

---

### 44. **A** ✔️

La construcción:

```sql
FOR registro IN cursor LOOP
```

permite recorrer cómodamente las filas de un cursor.

---

### 45. **B** ✔️

`WHEN OTHERS` puede capturar excepciones no tratadas específicamente. Si se utiliza sin una gestión adecuada, puede ocultar información importante sobre los errores.

---

### 46. **A** ✔️

Modificar el salario de un empleado implica normalmente un:

```sql
UPDATE
```

---

# 🟥 Preguntas 47-67 - PostGIS

### 47. **A** ✔️

PostGIS añade capacidades espaciales y geográficas a PostgreSQL.

---

### 48. **A** ✔️

`geometry` es uno de los tipos fundamentales de PostGIS.

---

### 49. **B** ✔️

`geography` está orientado a coordenadas geográficas sobre la Tierra y proporciona operaciones específicas que resultan especialmente útiles para distancias geográficas.

---

### 50. **A** ✔️

`ST_Within(A, B)` comprueba si A está dentro de B según la relación espacial definida.

---

### 51. **A** ✔️

`ST_Contains(A, B)` expresa la relación inversa conceptual:

```text
A contiene B
```

---

### 52. **A** ✔️

`ST_DWithin` permite comprobar si dos geometrías están dentro de una distancia determinada.

---

### 53. **A** ✔️

`ST_Distance` calcula la distancia entre dos geometrías.

---

### 54. **B** ✔️

```text
ST_Distance
↓
¿Cuánto?

ST_DWithin
↓
¿Está dentro del límite?
```

---

### 55. **A** ✔️

`ST_Buffer` crea una zona alrededor de una geometría.

---

### 56. **A** ✔️

`ST_Intersects` devuelve una condición booleana indicando si existe intersección espacial.

---

### 57. **B** ✔️

```text
ST_Intersects
↓
TRUE / FALSE

ST_Intersection
↓
Geometría resultante
```

---

### 58. **B** ✔️

`ST_Intersection` obtiene la geometría correspondiente a la parte común de las dos geometrías.

---

### 59. **A** ✔️

`ST_Union` realiza una unión geométrica.

---

### 60. **A** ✔️

`ST_Collect` agrupa geometrías en una colección sin realizar necesariamente la disolución geométrica que puede producir `ST_Union`.

---

### 61. **B** ✔️

`ST_SetSRID` asigna o modifica el SRID asociado. No transforma las coordenadas.

---

### 62. **B** ✔️

`ST_Transform` transforma las coordenadas entre sistemas de referencia.

---

### 63. **B** ✔️

Si las coordenadas están realmente en EPSG:4326 y queremos transformarlas a EPSG:25830:

```sql
ST_Transform(geom, 25830)
```

---

### 64. **B** ✔️

En:

```sql
ST_MakePoint(longitude, latitude)
```

el orden es:

```text
X = longitude
Y = latitude
```

---

### 65. **A** ✔️

`ST_AsGeoJSON` convierte una geometría a GeoJSON.

---

### 66. **A** ✔️

`ST_Centroid` calcula el centroide geométrico.

---

### 67. **A** ✔️

`ST_PointOnSurface` está diseñado para devolver un punto situado sobre la superficie correspondiente y resulta útil para determinadas tareas cartográficas, como etiquetar polígonos.

---

# 🟪 Preguntas 68-75 - Rendimiento e integración

### 68. **A** ✔️

`GiST` es un método de indexación habitual para datos espaciales en PostGIS.

---

### 69. **B** ✔️

Antes de optimizar conviene analizar el comportamiento real:

```sql
EXPLAIN ANALYZE
```

---

### 70. **A** ✔️

`Seq Scan` significa `Sequential Scan`: PostgreSQL recorre secuencialmente las filas.

---

### 71. **B** ✔️

Un `Seq Scan` no significa automáticamente que falte un índice.

El optimizador puede determinar que recorrer secuencialmente la tabla es más barato.

---

### 72. **A** ✔️

Cuando la consulta utiliza:

```sql
geom::geography
```

puede ser relevante estudiar un índice GiST adecuado para la expresión utilizada y comprobar el plan mediante `EXPLAIN ANALYZE`.

---

### 73. **B** ✔️

La construcción correcta es:

```sql
ST_SetSRID(
    ST_MakePoint(longitude, latitude),
    4326
)
```

El orden de las coordenadas es fundamental.

---

### 74. **A** ✔️

GeoJSON es un formato habitual para transportar geometrías hacia aplicaciones web cartográficas.

---

### 75. **A** ✔️

La función es:

```sql
ST_AsGeoJSON
```

---

# 🔥 Preguntas 76-80 - Alta dificultad

### 76. **B** ✔️

`ST_SetSRID(geom, 25830)` no transforma las coordenadas.

Si las coordenadas siguen siendo las de EPSG:4326 pero se etiquetan como EPSG:25830, la posición puede interpretarse incorrectamente.

---

### 77. **B** ✔️

Para una consulta de proximidad es especialmente apropiado:

```sql
ST_DWithin(
    geom::geography,
    :punto::geography,
    5000
)
```

---

### 78. **B** ✔️

`ST_DWithin` permite realizar comprobaciones de proximidad y resulta especialmente interesante para búsquedas espaciales cuando se combina con una estrategia de indexación adecuada.

---

### 79. **A** ✔️

Primero obtenemos la parte de la carretera que está dentro del municipio:

```sql
ST_Intersection
```

y después calculamos su longitud:

```sql
ST_Length
```

Por tanto:

```text
ST_Intersection
       ↓
ST_Length
```

---

### 80. **B** ✔️

Una estrategia de diagnóstico razonable debe combinar:

```text
EXPLAIN ANALYZE
       ↓
Plan real
       ↓
Selectividad
       ↓
CRS / geometry / geography
       ↓
Índice espacial
       ↓
Coste real
```

No debemos crear índices a ciegas.

---

# 📊 HOJA DE RESULTADOS

## Puntuación global

```text
Aciertos:       ____ / 80
Fallos:         ____
En blanco:      ____
Porcentaje:     ____ %
```

---

# 🧭 RESULTADO POR ÁREA

| Área | Preguntas | Aciertos | Porcentaje |
|---|---:|---:|---:|
| SQL y fundamentos | 1-15 | ____ / 15 | ____ % |
| PostgreSQL | 16-27 | ____ / 12 | ____ % |
| MySQL | 28-32 | ____ / 5 | ____ % |
| Oracle | 33-38 | ____ / 6 | ____ % |
| PL/SQL | 39-46 | ____ / 8 | ____ % |
| PostGIS | 47-67 | ____ / 21 | ____ % |
| Rendimiento e integración | 68-75 | ____ / 8 | ____ % |
| Alta dificultad | 76-80 | ____ / 5 | ____ % |
| **TOTAL** | **1-80** | **____ / 80** | **____ %** |

---

# 🎯 INTERPRETACIÓN

| Resultado | Interpretación |
|---:|---|
| 72-80 | 🟢 Excelente |
| 64-71 | 🟢 Muy buen dominio |
| 56-63 | 🟡 Buen nivel |
| 48-55 | 🟠 Nivel intermedio |
| 40-47 | 🟠 Necesita repaso |
| < 40 | 🔴 Repasar fundamentos |

> La nota global no es suficiente. Un 70/80 con un 40% en PL/SQL puede ser más preocupante que un 65/80 equilibrado.

---

# 🔎 REGISTRO DE ERRORES

Para cada pregunta fallada, registrar:

| Pregunta | Tu respuesta | Correcta | Motivo del fallo | ¿Repasar? |
|---:|:---:|:---:|---|:---:|
| | | | | |
| | | | | |
| | | | | |
| | | | | |
| | | | | |
| | | | | |
| | | | | |
| | | | | |
| | | | | |
| | | | | |

---

# 🧠 CLASIFICACIÓN DE LOS FALLOS

No todos los errores significan lo mismo.

## 🟢 Error de memoria

> "Lo sabía, pero no recordaba el nombre."

Ejemplo:

```text
Confundir GiST con otro tipo de índice.
```

### Acción

Repaso rápido + tarjeta Anki.

---

## 🟡 Error de concepto

> "Conocía los términos, pero no entendía bien la diferencia."

Ejemplo:

```text
ST_SetSRID
vs
ST_Transform
```

### Acción

Volver al concepto y realizar ejemplos prácticos.

---

## 🟠 Error de aplicación

> "Conozco el concepto, pero no sé utilizarlo en una consulta."

Ejemplo:

```text
ST_DWithin
```

### Acción

Practicar consultas.

---

## 🔴 Error de confusión

> "Dos conceptos se me mezclan completamente."

Ejemplos:

```text
WHERE vs HAVING
```

```text
ST_Intersects vs ST_Intersection
```

```text
VIEW vs MATERIALIZED VIEW
```

### Acción

Crear una comparación directa y repetir posteriormente.

---

# 🏆 CONCEPTOS QUE DEBERÍAS DOMINAR SIN DUDAR

## SQL

```text
WHERE
HAVING
GROUP BY
JOIN
LEFT JOIN
PRIMARY KEY
FOREIGN KEY
UNIQUE
COMMIT
ROLLBACK
```

## PostgreSQL

```text
JSONB
CTE
Window Functions
EXPLAIN
EXPLAIN ANALYZE
MVCC
GiST
```

## MySQL

```text
InnoDB
AUTO_INCREMENT
MVCC
```

## Oracle

```text
SEQUENCE
VIEW
MATERIALIZED VIEW
SYNONYM
TABLESPACE
```

## PL/SQL

```text
FUNCTION
PROCEDURE
CURSOR
EXCEPTION
WHEN OTHERS
DECLARE / BEGIN / EXCEPTION / END
```

## PostGIS

```text
geometry
geography
SRID
ST_Within
ST_Contains
ST_DWithin
ST_Distance
ST_Buffer
ST_Intersects
ST_Intersection
ST_Union
ST_Collect
ST_SetSRID
ST_Transform
ST_Centroid
ST_PointOnSurface
ST_AsGeoJSON
ST_MakePoint
```

---

# 🧩 LAS 10 TRAMPAS DEL SIMULACRO

Si fallas alguna de estas, merece especial atención:

```text
1. WHERE vs HAVING
2. LEFT JOIN
3. GROUP BY vs Window Functions
4. EXPLAIN vs EXPLAIN ANALYZE
5. JSONB
6. VIEW vs MATERIALIZED VIEW
7. ST_DWithin vs ST_Distance
8. ST_Intersects vs ST_Intersection
9. ST_SetSRID vs ST_Transform
10. longitude vs latitude
```

---

# 🏁 FIN DE LA CORRECCIÓN

> **La nota importa.**
>
> Pero para preparar una oposición, importa todavía más saber **por qué fallaste**.
>
> Un error bien analizado vale más que diez respuestas acertadas por intuición.
