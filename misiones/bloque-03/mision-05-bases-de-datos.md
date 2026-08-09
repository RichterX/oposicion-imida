# 🎯 Misión Bloque 3 - Bases de Datos

## Objetivo

Esta misión tiene como objetivo comprobar la capacidad para **aplicar y relacionar** los conocimientos adquiridos en:

- **3.1 SQL**
- **3.2 PostgreSQL**
- **3.3 Oracle**
- **3.4 MySQL**
- **3.5 PL/SQL**
- **3.6 PostGIS**

No se pretende memorizar cada función o característica del temario, sino demostrar que se sabe **qué herramienta utilizar, cuándo utilizarla y por qué**.

> **Importante:** realizar la misión sin consultar el temario. Si una pregunta genera dudas, marcarla con `❓` y continuar. Las dudas serán especialmente útiles durante la corrección.

---

# 🟢 Nivel 1 - SQL Fundamental

## Misión 1 - Consultas básicas

Tenemos las siguientes tablas:

```text
clientes
---------
id
nombre
email
ciudad

pedidos
-------
id
cliente_id
fecha
total
estado

productos
---------
id
nombre
precio
categoria

detalle_pedido
--------------
pedido_id
producto_id
cantidad
precio
```

### 1.1

Obtener todos los clientes de la ciudad:

```text
Murcia
```

---

### 1.2

Obtener los pedidos cuyo total sea superior a:

```text
100 €
```

y cuyo estado sea:

```text
completado
```

---

### 1.3

Obtener:

```text
nombre del cliente
fecha del pedido
total
```

utilizando las tablas `clientes` y `pedidos`.

---

### 1.4

Obtener todos los clientes que **no tienen ningún pedido**.

> Hay varias formas de resolverlo. Utilizar la que se considere más apropiada.

---

### 1.5

Obtener el número de pedidos realizados por cada cliente.

El resultado debería tener:

```text
cliente
número_de_pedidos
```

Incluir también clientes que tengan:

```text
0 pedidos
```

---

# 🟢 Nivel 1 - Agrupaciones

## Misión 2 - GROUP BY y HAVING

### 2.1

Obtener el gasto total realizado por cada cliente.

Resultado:

```text
cliente
gasto_total
```

---

### 2.2

Obtener únicamente los clientes cuyo gasto total sea superior a:

```text
1.000 €
```

> Decidir dónde debe aplicarse la condición.

---

### 2.3

Obtener el precio medio de los productos de cada categoría.

Resultado:

```text
categoria
precio_medio
```

---

### 2.4

Explicar la diferencia conceptual entre:

```sql
WHERE
```

y:

```sql
HAVING
```

No utilizar únicamente una definición de memoria. Explicar la diferencia aplicada a esta misión.

---

# 🟡 Nivel 2 - SQL Intermedio

## Misión 3 - El producto estrella

Queremos encontrar:

> **El producto que ha generado mayor cantidad de ventas.**

Recordemos que `detalle_pedido` contiene:

```text
pedido_id
producto_id
cantidad
precio
```

Obtener:

```text
producto
cantidad_total_vendida
```

y determinar cuál es el producto más vendido.

Se pueden utilizar:

```text
GROUP BY
ORDER BY
LIMIT
```

o cualquier otra estrategia adecuada.

---

# 🟡 Nivel 2 - Clientes sin compras

## Misión 4 - Dos soluciones

Resolver de **dos maneras diferentes**:

> Obtener los clientes que no tienen ningún pedido.

Utilizar, por ejemplo:

1. `LEFT JOIN`
2. `NOT EXISTS`

Después explicar brevemente cuál de las dos soluciones se prefiere y por qué.

---

# 🟡 Nivel 2 - PostgreSQL

## Misión 5 - PostgreSQL

### 5.1 - JSONB

Tenemos:

```text
usuarios
---------
id
nombre
datos JSONB
```

El campo `datos` contiene:

```json
{
    "telefono": "600123456",
    "direccion": {
        "ciudad": "Murcia"
    }
}
```

Queremos obtener los usuarios cuya ciudad sea:

```text
Murcia
```

### Tarea

¿Qué característica de PostgreSQL utilizaríamos?

Escribir una consulta aproximada.

---

### 5.2 - Window Functions

Tenemos:

```text
ventas
---------
id
usuario_id
fecha
importe
```

Queremos obtener, para cada usuario:

```text
fecha
importe
importe acumulado
```

ordenado cronológicamente.

### Tarea

¿Qué característica de SQL/PostgreSQL utilizaríamos?

---

### 5.3 - CTE

Explicar qué problema podría resolver una:

```text
CTE
```

y escribir un ejemplo sencillo utilizando:

```sql
WITH ...
```

---

### 5.4 - EXPLAIN

Tenemos una consulta extremadamente lenta.

¿Qué herramienta de PostgreSQL utilizaríamos para investigar **cómo se está ejecutando realmente**?

Explicar también la diferencia entre:

```text
EXPLAIN
```

y:

```text
EXPLAIN ANALYZE
```

---

# 🟡 Nivel 2 - MySQL vs PostgreSQL

## Misión 6 - El detective de motores

Indicar si cada característica está asociada principalmente a:

- `PostgreSQL`
- `MySQL`
- `Ambos`

### 6.1

```text
JSONB
```

### 6.2

```text
InnoDB
```

### 6.3

```text
MVCC
```

### 6.4

```text
PL/pgSQL
```

### 6.5

```text
AUTO_INCREMENT
```

### 6.6

```text
GENERATED ALWAYS AS IDENTITY
```

### 6.7

```text
GiST
```

---

# 🟠 Nivel 3 - Oracle

## Misión 7 - Oracle

Explicar brevemente la función de:

```text
SEQUENCE
VIEW
MATERIALIZED VIEW
SYNONYM
TABLESPACE
```

Después responder:

> ¿Cuál de estos objetos utilizarías si necesitas almacenar físicamente el resultado de una consulta para poder reutilizarlo sin recalcularlo constantemente?

---

# 🟠 Nivel 3 - PL/SQL

## Misión 8 - Procedimiento

Tenemos:

```text
empleados
---------
id
nombre
salario
departamento_id
```

Queremos crear un procedimiento que reciba:

```text
id del empleado
porcentaje de incremento
```

y actualice su salario.

Escribir un procedimiento PL/SQL aproximado.

No es necesario que sea perfecto sintácticamente al milímetro. Se debe demostrar que se sabe estructurar:

```text
CREATE PROCEDURE
        ↓
parámetros
        ↓
BEGIN
        ↓
UPDATE
        ↓
EXCEPTION
        ↓
END
```

---

# 🟠 Nivel 3 - PL/SQL

## Misión 9 - Cursor

Queremos recorrer los empleados de un determinado departamento y realizar alguna operación sobre cada uno.

### Tareas

1. Explicar qué es un cursor en PL/SQL.
2. Explicar cuándo tendría sentido utilizarlo.
3. Escribir un pequeño ejemplo de cursor.

---

# 🔴 Nivel 4 - PostGIS

Aquí comienza el apartado espacial.

Tenemos:

```text
municipios
---------
id
nombre
geom

hospitales
----------
id
nombre
geom

carreteras
----------
id
nombre
geom
```

Suponemos que las geometrías están correctamente almacenadas y tienen un SRID válido.

---

# Misión 10 - ¿Dónde está el hospital?

Queremos saber:

> ¿En qué municipio está cada hospital?

Obtener:

```text
hospital
municipio
```

### Tarea

¿Qué relación espacial utilizaríamos?

---

# Misión 11 - Hospitales cercanos

Queremos obtener todos los hospitales situados a menos de:

```text
5 kilómetros
```

de un punto determinado.

### 11.1

¿Qué función utilizaríamos?

### 11.2

¿Qué tipo de dato podría resultar especialmente cómodo para trabajar directamente con distancias sobre la Tierra?

### 11.3

¿Qué índice espacial consideraríamos?

---

# 🔴 Nivel 4 - PostGIS

## Misión 12 - Carreteras municipales

Queremos encontrar:

> Las carreteras que atraviesan cada municipio.

Primero queremos saber **qué carreteras intersectan cada municipio**.

Después queremos obtener:

> **La parte de cada carretera que está dentro del municipio.**

### 12.1

¿Qué función utilizaríamos para saber si existe relación espacial?

### 12.2

¿Qué función utilizaríamos para obtener la geometría resultante?

### 12.3

¿Qué función utilizaríamos posteriormente para calcular la longitud de esa parte?

---

# 🔴 Nivel 4 - PostGIS

## Misión 13 - Buffer

Tenemos la ubicación de varios hospitales.

Queremos generar:

> Una zona de influencia de 1 km alrededor de cada hospital.

### Tareas

1. ¿Qué función utilizaríamos?
2. Explicar la diferencia entre:
   - Crear una zona de 1 km.
   - Preguntar si algo está a menos de 1 km.

---

# 🔴 Nivel 4 - PostGIS

## Misión 14 - CRS

Tenemos:

```text
geom = geometry(Point, 4326)
```

Un compañero propone:

```sql
ST_SetSRID(geom, 25830)
```

para convertir la geometría a:

```text
ETRS89 / UTM zona 30N
```

### Tareas

1. ¿Es correcto?
2. Si no lo es, ¿qué función deberíamos utilizar?
3. Explicar por qué.

---

# 🔴 Nivel 4 - PostGIS

## Misión 15 - Rendimiento

Tenemos:

```text
10 millones de geometrías
```

y una consulta espacial tarda muchísimo.

Actualmente tenemos:

```sql
SELECT *
FROM edificios
WHERE ST_DWithin(
    geom::geography,
    :punto::geography,
    1000
);
```

### 15.1

¿Qué tipo de índice espacial considerarías?

### 15.2

¿Qué herramienta utilizarías para investigar el plan de ejecución?

### 15.3

¿Qué diferencia hay entre:

```text
Seq Scan
```

y:

```text
Index Scan
```

---

# 🔥 Nivel Final - Caso Integrado

## Misión 16 - Sistema de centros públicos

Una administración quiere crear un sistema para analizar sus centros públicos.

Tenemos:

```text
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

---

### 16.1 - Clasificación espacial

Obtener todos los centros indicando:

```text
centro
municipio
```

---

### 16.2 - Incidencias

Contar cuántas incidencias tiene cada centro.

Deben aparecer también los centros:

```text
sin incidencias
```

---

### 16.3 - Filtrado por agrupación

Obtener los centros que tengan:

```text
más de 10 incidencias
```

---

### 16.4 - Proximidad

Obtener los centros situados a menos de:

```text
2 km
```

de un punto determinado.

---

### 16.5 - Rendimiento

La consulta espacial es muy lenta.

Proponer:

```text
índice
+
herramienta de diagnóstico
```

---

### 16.6 - GeoJSON

El frontend necesita recibir la geometría de los centros como:

```text
GeoJSON
```

¿Qué función de PostGIS utilizarías?

---

### 16.7 - Coordenadas

El frontend envía:

```text
latitude
longitude
```

¿Qué orden utilizarías al construir el `POINT`?

---

### 16.8 - Arquitectura

Explicar el flujo completo:

```text
Frontend
   ↓
API
   ↓
PostgreSQL/PostGIS
   ↓
consulta espacial
   ↓
resultado
   ↓
GeoJSON
   ↓
Frontend
```

utilizando las funciones y conceptos que se consideren apropiados.

---

# 🧠 Bonus - Las 10 parejas peligrosas

Sin consultar el temario, explicar la diferencia entre:

## 17.1

```text
WHERE
vs
HAVING
```

---

## 17.2

```text
DELETE
vs
TRUNCATE
vs
DROP
```

---

## 17.3

```text
PRIMARY KEY
vs
UNIQUE
```

---

## 17.4

```text
VIEW
vs
MATERIALIZED VIEW
```

---

## 17.5

```text
FUNCTION
vs
PROCEDURE
```

---

## 17.6

```text
ST_SetSRID
vs
ST_Transform
```

---

## 17.7

```text
ST_Intersects
vs
ST_Intersection
```

---

## 17.8

```text
ST_Distance
vs
ST_DWithin
```

---

## 17.9

```text
ST_Collect
vs
ST_Union
```

---

## 17.10

```text
ST_Centroid
vs
ST_PointOnSurface
```

---

# 🏁 Fin de la misión

## Recomendaciones

- Realizar la misión **sin consultar el temario**.
- Si una pregunta genera dudas, marcarla con `❓` y continuar.
- Para preguntas conceptuales, responder con **2-4 frases**.
- Para ejercicios SQL/PL/SQL, escribir la solución y explicar brevemente cuando se solicite.
- No es necesario utilizar exactamente la sintaxis mostrada en el enunciado si existe otra solución correcta.

El objetivo no es obtener una solución idéntica a la solución oficial, sino demostrar:

```text
Comprensión
    +
Capacidad de razonamiento
    +
Aplicación práctica
```

---

## Sistema de corrección

Durante la corrección, cada ejercicio será clasificado como:

| Resultado | Significado |
|---|---|
| ✅ Correcto | Solución correcta y suficientemente razonada |
| ⚠️ Correcto pero mejorable | La idea es correcta, pero existe algún detalle que conviene pulir |
| ❌ Incorrecto | El concepto o la solución necesita revisión |
| ❓ No respondido / duda | El concepto requiere refuerzo |

Además, se identificará el **concepto concreto que necesita repaso**, evitando volver a estudiar bloques completos innecesariamente.

### Objetivo final

Llegar al simulacro del Bloque 3 con un mapa claro de:

```text
🟢 Conceptos dominados
🟡 Conceptos que requieren repaso
🟠 Conceptos débiles
🔴 Conceptos que necesitan refuerzo
```

> **La misión no pretende cubrir las 13.000+ líneas del bloque. Pretende comprobar si somos capaces de utilizar sus conceptos fundamentales.**