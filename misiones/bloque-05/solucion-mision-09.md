# 📝 MISIÓN 9 · CORRECCIÓN
## «El archivo heredado»

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.8 XML  
> **Misión:** 9  
> **Objetivo:** Validar, consultar, transformar y procesar documentos XML.

---

# 1. CORRECCIÓN GENERAL

Esta misión tiene varias partes donde puede haber más de una expresión o diseño correcto.

Especialmente:

```text
DTD
XSD
XPath
XSLT
```

No es necesario que tu solución coincida literalmente con esta corrección.

Se considera correcta si:

```text
✓ respeta la sintaxis
✓ produce el resultado solicitado
✓ maneja correctamente los namespaces
✓ las restricciones son coherentes
✓ la elección técnica está justificada
```

---

# 2. PARTE I · XML BIEN FORMADO

El documento proporcionado es **bien formado**.

Presenta:

```text
✓ un único elemento raíz
✓ elementos correctamente cerrados
✓ elementos correctamente anidados
✓ atributos entre comillas
✓ atributos sin duplicar dentro del mismo elemento
```

Por tanto:

```text
inventario.xml
→ bien formado
```

### ⚠️ Pero eso no significa automáticamente:

```text
→ válido
```

La validez depende de que cumpla una DTD o XSD que establezca las reglas estructurales correspondientes.

---

# 3. BIEN FORMADO VS VÁLIDO

## XML bien formado

Significa que el documento cumple las reglas sintácticas básicas de XML.

Por ejemplo:

```xml
<empleado>
    <nombre>Pedro</nombre>
</empleado>
```

es sintácticamente correcto.

---

## XML válido

Significa que además cumple las restricciones definidas por un esquema, por ejemplo:

```text
DTD
```

o:

```text
XSD
```

Por tanto:

```text
Bien formado
→ sintaxis XML correcta

Válido
→ bien formado + cumple un esquema
```

Un documento XML válido debe ser bien formado.

---

# 📐 4. PARTE II · NAMESPACES

El documento utiliza:

```xml
xmlns="https://example.com/gestiona"
xmlns:t="https://example.com/gestiona/equipos"
```

Por tanto existen:

```text
namespace por defecto:
https://example.com/gestiona

namespace t:
https://example.com/gestiona/equipos
```

---

# 🔎 5. NAMESPACE DE LOS ELEMENTOS

Los elementos sin prefijo dentro del ámbito del namespace por defecto pertenecen a:

```text
https://example.com/gestiona
```

Por ejemplo:

```text
gestiona
departamentos
departamento
nombre
empleados
empleado
incidencias
incidencia
titulo
descripcion
prioridad
estado
```

Los elementos con `t:` pertenecen a:

```text
https://example.com/gestiona/equipos
```

Por ejemplo:

```text
t:equipos
t:equipo
t:marca
t:modelo
t:estado
t:usuario
```

### Importante

El atributo:

```text
tipo
```

de:

```xml
<t:equipo tipo="ordenador">
```

no pertenece automáticamente al namespace por defecto ni al namespace `t`.

Los atributos sin prefijo tienen un tratamiento distinto de los elementos respecto a namespaces.

---

# 🧠 6. ¿PARA QUÉ SIRVEN LOS NAMESPACES?

Permiten distinguir vocabularios diferentes que podrían utilizar nombres iguales.

Por ejemplo:

```text
gestiona:estado
```

podría representar el estado de una incidencia.

Mientras:

```text
equipos:estado
```

podría representar el estado de un equipo.

Los namespaces evitan colisiones de nombres.

---

# 📄 7. PARTE III · DTD

Una DTD simplificada compatible con la estructura planteada podría ser:

```dtd
<!ELEMENT gestiona (departamentos, incidencias)>

<!ELEMENT departamentos (departamento*)>

<!ELEMENT departamento (nombre, empleados)>
<!ATTLIST departamento
    id ID #REQUIRED
>

<!ELEMENT nombre (#PCDATA)>

<!ELEMENT empleados (empleado*)>

<!ELEMENT empleado (nombre, apellidos, email)>
<!ATTLIST empleado
    id ID #REQUIRED
>

<!ELEMENT apellidos (#PCDATA)>

<!ELEMENT email (#PCDATA)>

<!ELEMENT incidencias (incidencia*)>

<!ELEMENT incidencia (titulo, descripcion, prioridad, estado)>
<!ATTLIST incidencia
    id ID #REQUIRED
    equipo IDREF #REQUIRED
>

<!ELEMENT titulo (#PCDATA)>
<!ELEMENT descripcion (#PCDATA)>
<!ELEMENT prioridad (#PCDATA)>
<!ELEMENT estado (#PCDATA)>
```

### Nota

Esta DTD describe la estructura simplificada solicitada.

El XML original contiene además:

```text
t:equipos
```

y una DTD completa tendría que contemplar correctamente ese vocabulario si quisiéramos validar **todo** el documento original con namespaces.

---

# 🔢 8. DTD · `?`, `*`, `+`

Recordatorio:

```text
?
→ cero o una vez

*
→ cero o más veces

+
→ una o más veces
```

En nuestra estructura:

```text
departamento*
```

permite:

```text
0..*
```

departamentos.

```text
empleado*
```

permite:

```text
0..*
```

empleados.

```text
incidencia*
```

permite:

```text
0..*
```

incidencias.

---

# 🧠 9. ¿POR QUÉ `*` Y NO `+`?

El enunciado decía:

```text
puede contener 0..*
```

Por tanto:

```text
*
```

es la representación adecuada.

Si utilizáramos:

```text
+
```

estaríamos obligando a que existiera al menos uno.

---

# 📐 10. PARTE IV · XSD

Una solución simplificada podría comenzar así:

```xml
<?xml version="1.0" encoding="UTF-8"?>

<xs:schema
    xmlns:xs="http://www.w3.org/2001/XMLSchema"
    targetNamespace="https://example.com/gestiona"
    xmlns="https://example.com/gestiona"
    elementFormDefault="qualified">

    ...

</xs:schema>
```

La solución completa puede organizarse de diferentes maneras:

```text
xs:sequence
xs:complexType
xs:simpleType
xs:restriction
```

---

# 🔢 11. XSD · OCURRENCIAS

Ejemplo:

```xml
<xs:element
    name="departamento"
    minOccurs="0"
    maxOccurs="unbounded">
```

significa:

```text
0..*
```

Para un empleado:

```xml
<xs:element
    name="empleado"
    minOccurs="0"
    maxOccurs="unbounded">
```

Para una incidencia:

```xml
<xs:element
    name="incidencia"
    minOccurs="0"
    maxOccurs="unbounded">
```

---

# 🔒 12. XSD · ENUMERACIÓN

Una posible definición para prioridad:

```xml
<xs:simpleType name="PrioridadType">

    <xs:restriction base="xs:string">

        <xs:enumeration value="baja"/>
        <xs:enumeration value="media"/>
        <xs:enumeration value="alta"/>
        <xs:enumeration value="critica"/>

    </xs:restriction>

</xs:simpleType>
```

Y para estado:

```xml
<xs:simpleType name="EstadoType">

    <xs:restriction base="xs:string">

        <xs:enumeration value="abierta"/>
        <xs:enumeration value="en_progreso"/>
        <xs:enumeration value="resuelta"/>
        <xs:enumeration value="cerrada"/>

    </xs:restriction>

</xs:simpleType>
```

---

# 🧠 13. DTD VS XSD

Cinco diferencias importantes:

| DTD | XSD |
|---|---|
| Sintaxis propia | Sintaxis basada en XML |
| Tipado más limitado | Tipos de datos más ricos |
| Soporte de namespaces limitado frente a XSD | Soporte de namespaces |
| Menos expresivo para restricciones | Mayor capacidad de restricción |
| Menor extensibilidad | Mayor capacidad de modelado |

Ejemplo:

DTD:

```dtd
<!ELEMENT edad (#PCDATA)>
```

XSD:

```xml
<xs:element
    name="edad"
    type="xs:integer">
```

XSD puede expresar que realmente esperamos un entero.

---

# 🔎 14. PARTE V · XPATH

Aquí hay una cuestión importante:

El documento utiliza un namespace por defecto y otro para equipos.

Por ello, **las expresiones XPath deben tener en cuenta namespaces** cuando se ejecutan desde una API o herramienta que requiere prefijos.

En una herramienta donde se hayan registrado:

```text
g → https://example.com/gestiona

t → https://example.com/gestiona/equipos
```

podríamos escribir:

### 1. Todos los departamentos

```xpath
/g:gestiona/g:departamentos/g:departamento
```

### 2. Todos los empleados

```xpath
//g:empleado
```

### 3. Empleado E01

```xpath
//g:empleado[@id='E01']
```

### 4. Todos los equipos

```xpath
//t:equipo
```

### 5. Equipos averiados

```xpath
//t:equipo[t:estado='averiado']
```

### 6. Incidencias abiertas

```xpath
//g:incidencia[g:estado='abierta']
```

### 7. Incidencias de prioridad alta

```xpath
//g:incidencia[g:prioridad='alta']
```

### 8. IDs de las incidencias

```xpath
//g:incidencia/@id
```

---

# ⚠️ 15. NAMESPACES EN XPATH

Esta es una de las trampas importantes.

No debemos asumir que:

```xpath
//equipo
```

encuentra:

```xml
<t:equipo>
```

porque ese elemento pertenece al namespace:

```text
https://example.com/gestiona/equipos
```

Debemos utilizar un prefijo asociado al namespace en el contexto XPath:

```xpath
//t:equipo
```

si:

```text
t
→ https://example.com/gestiona/equipos
```

---

# 🧪 16. PREDICADOS

### Empleados llamados Pedro

```xpath
//g:empleado[g:nombre='Pedro']
```

### Ordenadores

```xpath
//t:equipo[@tipo='ordenador']
```

### Equipos activos

```xpath
//t:equipo[t:estado='activo']
```

### Incidencias abiertas

```xpath
//g:incidencia[g:estado='abierta']
```

### Incidencias de prioridad alta

```xpath
//g:incidencia[g:prioridad='alta']
```

---

# 🧭 17. EJES / EXPRESIONES BÁSICAS

## `.`

Nodo/contexto actual.

Ejemplo:

```xpath
.
```

---

## `..`

Nodo padre.

Ejemplo:

```xpath
../nombre
```

---

## `/`

Separador de pasos de ubicación.

Ejemplo:

```xpath
/g:gestiona/g:departamentos
```

---

## `//`

Selección descendiente a cualquier profundidad desde el contexto correspondiente.

Ejemplo:

```xpath
//g:empleado
```

---

## `@`

Atributo.

Ejemplo:

```xpath
//g:empleado/@id
```

---

# 🔎 18. PARTE VI · CONSULTAS COMBINADAS

### Incidencia cuyo equipo es EQ03

```xpath
//g:incidencia[@equipo='EQ03']
```

### Equipo asignado a E01

```xpath
//t:equipo[t:usuario='E01']
```

---

# 📄 19. PARTE VII · XSLT

La transformación debe utilizar:

```text
XSLT
→ transformar XML
```

a:

```text
HTML
```

Una estructura simplificada:

```xml
<xsl:stylesheet
    version="1.0"
    xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
    xmlns:g="https://example.com/gestiona"
    xmlns:t="https://example.com/gestiona/equipos"
    exclude-result-prefixes="g t">

    <xsl:template match="/">

        <html>

            <head>
                <title>GESTIONA</title>
            </head>

            <body>

                <h1>Inventario de equipos</h1>

                ...

            </body>

        </html>

    </xsl:template>

</xsl:stylesheet>
```

---

# 🔄 20. XSLT · `xsl:for-each`

Para recorrer equipos:

```xml
<xsl:for-each select="//t:equipo">

    ...

</xsl:for-each>
```

La expresión:

```xpath
//t:equipo
```

selecciona los elementos `equipo` del namespace correspondiente.

---

# 🎯 21. XSLT · `xsl:value-of`

Ejemplo:

```xml
<td>
    <xsl:value-of select="@id"/>
</td>

<td>
    <xsl:value-of select="@tipo"/>
</td>

<td>
    <xsl:value-of select="t:marca"/>
</td>

<td>
    <xsl:value-of select="t:modelo"/>
</td>

<td>
    <xsl:value-of select="t:estado"/>
</td>
```

---

# 🔀 22. XSLT · CONDICIONALES

Una posibilidad:

```xml
<xsl:choose>

    <xsl:when test="t:estado='activo'">

        <span class="active">
            Activo
        </span>

    </xsl:when>

    <xsl:otherwise>

        <span class="broken">
            Averiado
        </span>

    </xsl:otherwise>

</xsl:choose>
```

---

# 📊 23. XSLT · ORDENACIÓN

Para ordenar por marca:

```xml
<xsl:for-each select="//t:equipo">

    <xsl:sort
        select="t:marca"
        data-type="text"
        order="ascending"
    />

    ...

</xsl:for-each>
```

---

# 🚨 24. XSLT · INCIDENCIAS ABIERTAS

Podemos seleccionar directamente:

```xml
<xsl:for-each
    select="//g:incidencia[g:estado='abierta']">

    ...

</xsl:for-each>
```

Esto genera una iteración únicamente sobre las incidencias abiertas.

---

# 🌳 25. PARTE VIII · DOM

DOM representa el documento como un árbol de nodos.

Conceptualmente:

```text
XML
 ↓
DOM
 ↓
árbol completo
 ↓
memoria
```

Esto permite:

```text
navegar
buscar
modificar
añadir
eliminar
```

nodos.

---

# 🌳 26. ÁRBOL DOM

Una representación simplificada:

```text
gestiona
├── departamentos
│   ├── departamento
│   │   ├── nombre
│   │   └── empleados
│   │       ├── empleado
│   │       └── empleado
│   └── departamento
│       └── ...
│
├── t:equipos
│   ├── t:equipo
│   ├── t:equipo
│   └── t:equipo
│
└── incidencias
    ├── incidencia
    └── incidencia
```

---

# ⚖️ 27. VENTAJAS DOM

Tres ventajas:

```text
1. Permite navegar libremente por el árbol.

2. Permite acceder repetidamente a diferentes nodos.

3. Permite modificar el documento en memoria.
```

---

# ⚠️ 28. DESVENTAJAS DOM

Tres inconvenientes:

```text
1. Puede consumir mucha memoria.

2. No es ideal para documentos XML gigantes.

3. Construir el árbol completo implica un coste inicial.
```

---

# ⚡ 29. PARTE IX · SAX

Con:

```text
5 GB
```

DOM puede ser problemático porque intenta mantener una representación completa del documento en memoria.

SAX resulta apropiado cuando:

```text
procesamos secuencialmente
+
no necesitamos mantener todo el documento
```

---

# 🔔 30. SAX · PUSH

SAX utiliza un modelo orientado a eventos.

El parser va generando eventos y el código responde a ellos.

Conceptualmente:

```text
Parser
  │
  ├── startDocument()
  ├── startElement()
  ├── characters()
  ├── endElement()
  └── endDocument()
```

El parser controla el flujo.

Por eso hablamos de:

```text
PUSH
```

---

# 🔄 31. DOM VS SAX

| Característica | DOM | SAX |
|---|---|---|
| Modelo | Árbol | Eventos |
| Memoria | Mayor | Menor |
| Acceso aleatorio | Sí | No |
| Modificación | Sí | No como árbol en memoria |
| Documentos grandes | Menos apropiado | Apropiado |
| Flujo | En memoria | Secuencial |

---

# 🎛️ 32. PARTE X · StAX

StAX utiliza un modelo:

```text
pull
```

El código controla cuándo solicita el siguiente evento.

Conceptualmente:

```text
while (parser.hasNext()) {
    event = parser.nextEvent();
}
```

A diferencia de SAX:

```text
SAX
→ parser empuja eventos

StAX
→ aplicación solicita eventos
```

---

# 🧠 33. DOM / SAX / StAX

### Escenario A

XML relativamente pequeño y necesitamos modificarlo y navegar libremente:

```text
DOM
```

### Escenario B

XML enorme y procesamiento secuencial basado en eventos:

```text
SAX
```

### Escenario C

XML grande y queremos controlar explícitamente el flujo de lectura:

```text
StAX
```

---

# 🧪 34. PARTE XI · DETECTAR ERRORES

## Fragmento A

```xml
<empleado>
    <nombre>Pedro</apellidos>
</empleado>
```

### Error

Las etiquetas no coinciden:

```text
<nombre>
```

se cierra como:

```text
</apellidos>
```

Es un:

```text
error de XML bien formado
```

---

# 35. FRAGMENTO B

```xml
<empleado id=E01>
```

### Error

El atributo no está entre comillas.

Debería ser:

```xml
<empleado id="E01">
```

Es un:

```text
error de XML bien formado
```

---

# 36. FRAGMENTO C

```xml
<empleado>
    <nombre>Pedro</nombre>
    <nombre>Ana</nombre>
</empleado>
```

Sintácticamente puede ser XML bien formado.

Pero si el esquema exige:

```text
exactamente un nombre
```

entonces es:

```text
bien formado
pero inválido respecto al esquema
```

---

# 37. FRAGMENTO D

```xml
<empleado>
    <nombre>Pedro</nombre>
</empleado>

<empleado>
    <nombre>Ana</nombre>
</empleado>
```

Hay dos elementos raíz.

XML requiere:

```text
un único elemento raíz
```

Por tanto es:

```text
error de XML bien formado
```

---

# 🧠 38. TABLA DE DIAGNÓSTICO

| Fragmento | Bien formado | Válido | Problema |
|---|---|---|---|
| A | ❌ | ❌ | Etiquetas mal cerradas |
| B | ❌ | ❌ | Atributo sin comillas |
| C | ✅ | ❌* | Repetición no permitida por esquema |
| D | ❌ | ❌ | Múltiples raíces |

`*` Siempre que el esquema realmente exija exactamente un `nombre`.

---

# 🏆 39. PARTE XII · MIGRACIÓN

Una estrategia razonable:

```text
inventario.xml
       ↓
validación XSD
       ↓
XPath
       ↓
XSLT
       ↓
HTML
```

### Paso 1 · Validación

```text
XSD
```

Comprueba que los datos respetan la estructura y restricciones.

### Paso 2 · Consulta

```text
XPath
```

Permite localizar los datos que necesitamos.

### Paso 3 · Transformación

```text
XSLT
```

Convierte el XML en otra representación, por ejemplo:

```text
HTML
```

---

# ⭐ 40. DESAFÍO EXTRA · 20 GB

Para:

```text
20 GB
```

y únicamente localizar:

```text
incidencias críticas
```

evitaría:

```text
DOM
```

porque mantener el árbol completo puede requerir demasiada memoria.

Una solución adecuada:

```text
SAX
```

si queremos procesar secuencialmente reaccionando a eventos.

También puede ser apropiado:

```text
StAX
```

si queremos controlar desde el código cuándo consumir el siguiente evento.

---

# 🧠 41. RESPUESTAS DE REFLEXIÓN

### 1. Bien formado vs válido

```text
Bien formado
→ cumple sintaxis XML.

Válido
→ cumple además un DTD/XSD.
```

---

### 2. Namespaces

Evitan colisiones entre vocabularios y permiten identificar de forma inequívoca elementos pertenecientes a diferentes espacios de nombres.

---

### 3. DTD vs XSD

XSD:

```text
usa XML
+
tipos de datos
+
restricciones más avanzadas
+
namespaces
```

DTD tiene una sintaxis diferente y menor capacidad de tipado.

---

### 4. `*`

```text
0..*
```

---

### 5. `maxOccurs="unbounded"`

No establece un máximo finito.

Junto con:

```text
minOccurs="0"
```

representa:

```text
0..*
```

---

### 6. `@id`

Selecciona el atributo:

```text
id
```

---

### 7. `..`

Selecciona el nodo padre.

---

### 8. `/` vs `//`

```text
/
→ navegación mediante pasos concretos

//
→ búsqueda de descendientes a cualquier profundidad
```

---

### 9. XSLT

Permite transformar documentos XML en otras representaciones.

Por ejemplo:

```text
XML → HTML
```

---

### 10. DOM vs SAX

```text
DOM
→ árbol en memoria

SAX
→ eventos secuenciales
```

---

### 11. ¿Por qué DOM consume memoria?

Porque construye y mantiene una representación del documento en memoria.

---

### 12. SAX push

El parser genera los eventos y los entrega al código.

---

### 13. StAX pull

El código controla cuándo obtiene el siguiente evento.

---

# 📊 42. CRITERIOS DE EVALUACIÓN

| Área | Peso |
|---|---:|
| XML bien formado y conceptos básicos | 10% |
| Namespaces | 10% |
| DTD | 10% |
| XSD | 15% |
| XPath | 15% |
| XSLT | 15% |
| DOM / SAX / StAX | 15% |
| Diagnóstico de errores | 5% |
| Justificación técnica | 5% |
| **TOTAL** | **100%** |

---

# 🚨 43. ERRORES TÍPICOS

## Error 1

Pensar:

```text
bien formado = válido
```

Incorrecto.

---

## Error 2

Olvidar namespaces en XPath.

```xpath
//equipo
```

no equivale automáticamente a:

```xpath
//t:equipo
```

---

## Error 3

Confundir:

```text
*
```

con:

```text
+
```

---

## Error 4

Confundir:

```text
minOccurs
```

con:

```text
maxOccurs
```

---

## Error 5

Pensar que DOM es un parser basado en eventos.

No.

```text
DOM
→ árbol
```

---

## Error 6

Confundir:

```text
SAX = pull
```

Incorrecto:

```text
SAX = push
StAX = pull
```

---

## Error 7

Pensar que XPath transforma XML.

No.

```text
XPath
→ selecciona/localiza

XSLT
→ transforma
```

---

# 🧠 44. CONCEPTOS QUE DEBES DOMINAR

Al terminar deberías poder explicar sin apuntes:

```text
✓ XML bien formado
✓ XML válido
✓ DTD
✓ XSD
✓ Namespaces
✓ XPath
✓ Predicados
✓ XSLT
✓ DOM
✓ SAX
✓ StAX
✓ push
✓ pull
✓ minOccurs
✓ maxOccurs
✓ ? * +
```

Y, sobre todo, deberías poder responder:

> Si mañana te dan un XML de 10 GB, ¿qué tecnología utilizarías para procesarlo y por qué?

La respuesta no debería salir de memoria mecánica, sino del problema:

```text
¿Necesito todo el árbol?
→ DOM

¿Necesito procesamiento secuencial basado en eventos?
→ SAX

¿Necesito controlar desde mi código el flujo de lectura?
→ StAX
```

---

# 🏁 45. CONCLUSIÓN

La misión pretendía convertir XML en un flujo de trabajo:

```text
DOCUMENTO
    ↓
¿bien formado?
    ↓
¿válido?
    ↓
¿qué namespace utiliza?
    ↓
¿cómo localizo los datos?
    ↓
XPath
    ↓
¿cómo los transformo?
    ↓
XSLT
    ↓
¿cómo proceso documentos enormes?
    ↓
DOM / SAX / StAX
```

Si entiendes esta secuencia, has cubierto la parte esencial del capítulo.

---

# 🏁 FIN DE LA CORRECCIÓN · MISIÓN 9
