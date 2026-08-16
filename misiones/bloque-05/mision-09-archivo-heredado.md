# 🧩 MISIÓN 9 · EL ARCHIVO HEREDADO

> **Bloque:** 5 - Programación  
> **Capítulo:** 5.8 XML  
> **Tipo:** Misión práctica  
> **Dificultad:** 🟠  
> **Continuidad:** Misión 7 + Misión 8 · GESTIONA

---

# 🎯 1. OBJETIVO

GESTIONA ya tiene:

```text
✓ modelo orientado a objetos
✓ diagramas UML
✓ interfaz HTML
✓ estilos CSS
```

Pero aparece un problema.

La organización lleva años utilizando un sistema antiguo que almacena información en **XML**.

El nuevo sistema necesita importar esos datos.

Tu trabajo será:

```text
XML
 ↓
comprobar
 ↓
validar
 ↓
consultar
 ↓
transformar
 ↓
preparar migración
```

Durante la misión trabajarás:

```text
XML
DTD
XSD
Namespaces
XPath
XSLT
DOM
SAX
StAX
```

---

# 📖 2. EL SISTEMA ANTIGUO

El sistema heredado proporciona un fichero:

```text
inventario.xml
```

con información sobre departamentos, empleados, equipos e incidencias.

Utiliza este documento como punto de partida:

```xml
<?xml version="1.0" encoding="UTF-8"?>

<gestiona
    xmlns="https://example.com/gestiona"
    xmlns:t="https://example.com/gestiona/equipos">

    <departamentos>

        <departamento id="D01">

            <nombre>Desarrollo</nombre>

            <empleados>

                <empleado id="E01">
                    <nombre>Pedro</nombre>
                    <apellidos>Luque</apellidos>
                    <email>pedro@example.com</email>
                </empleado>

                <empleado id="E02">
                    <nombre>Ana</nombre>
                    <apellidos>García</apellidos>
                    <email>ana@example.com</email>
                </empleado>

            </empleados>

        </departamento>

        <departamento id="D02">

            <nombre>Administración</nombre>

            <empleados>

                <empleado id="E03">
                    <nombre>Luis</nombre>
                    <apellidos>Martínez</apellidos>
                    <email>luis@example.com</email>
                </empleado>

            </empleados>

        </departamento>

    </departamentos>

    <t:equipos>

        <t:equipo id="EQ01" tipo="ordenador">

            <t:marca>Dell</t:marca>
            <t:modelo>OptiPlex 7090</t:modelo>
            <t:estado>activo</t:estado>
            <t:usuario>E01</t:usuario>

        </t:equipo>

        <t:equipo id="EQ02" tipo="monitor">

            <t:marca>LG</t:marca>
            <t:modelo>UltraFine</t:modelo>
            <t:estado>activo</t:estado>
            <t:usuario>E02</t:usuario>

        </t:equipo>

        <t:equipo id="EQ03" tipo="impresora">

            <t:marca>HP</t:marca>
            <t:modelo>LaserJet</t:modelo>
            <t:estado>averiado</t:estado>

        </t:equipo>

    </t:equipos>

    <incidencias>

        <incidencia id="I01" equipo="EQ03">

            <titulo>Impresora no responde</titulo>

            <descripcion>
                La impresora no responde a las solicitudes.
            </descripcion>

            <prioridad>alta</prioridad>
            <estado>abierta</estado>

        </incidencia>

        <incidencia id="I02" equipo="EQ01">

            <titulo>Error de arranque</titulo>

            <descripcion>
                El ordenador muestra un error durante el arranque.
            </descripcion>

            <prioridad>media</prioridad>
            <estado>resuelta</estado>

        </incidencia>

    </incidencias>

</gestiona>
```

---

# 🧩 3. PARTE I · XML BIEN FORMADO

Antes de validar nada debes determinar si el documento es:

```text
bien formado
```

### Comprueba:

```text
□ Existe un único elemento raíz.

□ Todos los elementos tienen cierre.

□ Las etiquetas están correctamente anidadas.

□ Los atributos están entre comillas.

□ No existen dos atributos iguales en un mismo elemento.

□ El documento respeta las reglas básicas de XML.
```

---

# 🧠 4. PREGUNTA

Explica con tus palabras la diferencia entre:

```text
XML bien formado
```

y:

```text
XML válido
```

No continúes hasta tener clara esta diferencia.

---

# 📐 5. PARTE II · NAMESPACES

Observa:

```xml
<gestiona
    xmlns="https://example.com/gestiona"
    xmlns:t="https://example.com/gestiona/equipos">
```

Aquí existen dos namespaces:

```text
namespace por defecto
→ https://example.com/gestiona

prefijo t
→ https://example.com/gestiona/equipos
```

### Tu misión

Explica qué problema solucionan los namespaces.

---

# 🔎 6. IDENTIFICAR NAMESPACES

Determina a qué namespace pertenece:

```text
gestiona
departamento
empleado
incidencias
t:equipos
t:equipo
t:marca
```

Recuerda que el prefijo:

```text
t:
```

es solamente un alias.

El namespace real es:

```text
https://example.com/gestiona/equipos
```

---

# 📄 7. PARTE III · DTD

Ahora debes crear una DTD que describa una versión simplificada del documento.

No es necesario describir absolutamente todos los datos del XML original.

Crea una DTD para esta estructura:

```text
gestiona
 ├── departamentos
 │    └── departamento*
 │         ├── nombre
 │         └── empleados
 │              └── empleado*
 │                   ├── nombre
 │                   ├── apellidos
 │                   └── email
 │
 └── incidencias
      └── incidencia*
           ├── titulo
           ├── descripcion
           ├── prioridad
           └── estado
```

---

# 🧪 8. DTD · REQUISITOS

Tu DTD debe expresar:

```text
gestiona
→ contiene departamentos e incidencias

departamentos
→ puede contener 0..* departamentos

departamento
→ contiene nombre y empleados

empleados
→ puede contener 0..* empleados

empleado
→ contiene nombre, apellidos y email

incidencias
→ puede contener 0..* incidencias

incidencia
→ contiene titulo, descripcion, prioridad y estado
```

Además:

```text
departamento
→ atributo id obligatorio

empleado
→ atributo id obligatorio

incidencia
→ atributo id obligatorio

incidencia
→ atributo equipo obligatorio
```

---

# 🔢 9. DTD · OCURRENCIAS

Utiliza correctamente:

```text
?
*
+
```

Recuerda:

```text
?
→ 0 o 1

*
→ 0 o más

+
→ 1 o más
```

### Tu misión

Explica por qué utilizarías cada símbolo en tu DTD.

---

# 📐 10. PARTE IV · XSD

Ahora vamos a sustituir la DTD por un:

```text
XML Schema Definition
```

Crea:

```text
gestiona.xsd
```

Debe validar como mínimo:

```text
departamento
empleado
incidencia
```

---

# 🧪 11. TIPOS DE DATOS XSD

Utiliza tipos adecuados.

Por ejemplo:

```text
id
→ xs:string

email
→ xs:string

fecha
→ xs:date

prioridad
→ xs:string
```

Para los estados, intenta crear una restricción mediante:

```text
xs:restriction
```

con valores permitidos:

```text
abierta
en_progreso
resuelta
cerrada
```

---

# 🔒 12. ENUMERACIONES

Crea restricciones para:

```text
prioridad
```

permitiendo:

```text
baja
media
alta
critica
```

y para:

```text
estado
```

permitiendo:

```text
abierta
en_progreso
resuelta
cerrada
```

---

# 🔢 13. OCURRENCIAS EN XSD

Utiliza:

```text
minOccurs
maxOccurs
```

Por ejemplo:

```xml
<xs:element
    name="empleado"
    minOccurs="0"
    maxOccurs="unbounded">
```

### Tu misión

Determina las ocurrencias correctas para:

```text
departamento
empleado
incidencia
```

---

# 🧠 14. DTD VS XSD

Explica al menos cinco diferencias entre:

```text
DTD
```

y:

```text
XSD
```

Puedes considerar:

```text
sintaxis
tipos de datos
namespaces
restricciones
extensibilidad
```

---

# 🔎 15. PARTE V · XPATH

Ahora debes consultar el documento mediante XPath.

Escribe una expresión XPath para obtener:

### 1.

Todos los departamentos.

### 2.

Todos los empleados.

### 3.

El empleado cuyo `id` sea:

```text
E01
```

### 4.

Todos los equipos.

### 5.

Todos los equipos cuyo estado sea:

```text
averiado
```

### 6.

Todas las incidencias abiertas.

### 7.

Todas las incidencias de prioridad alta.

### 8.

El atributo `id` de todas las incidencias.

---

# ⚠️ 16. NAMESPACES Y XPATH

Aquí llega la trampa.

Los equipos están dentro de:

```text
https://example.com/gestiona/equipos
```

Por tanto, una expresión como:

```xpath
//t:equipo
```

solo funcionará si el prefijo `t` está correctamente asociado al namespace correspondiente en el contexto de XPath.

### Explica por qué los namespaces importan en XPath.

---

# 🧪 17. PREDICADOS

Escribe XPath utilizando predicados para obtener:

```text
empleados cuyo nombre sea Pedro

equipos cuyo tipo sea ordenador

equipos cuyo estado sea activo

incidencias cuyo estado sea abierta

incidencias cuya prioridad sea alta
```

Utiliza:

```text
[...]
```

---

# 🧭 18. EJES BÁSICOS

Explica qué representan:

```text
.
..
/
//
@
```

y proporciona un ejemplo de cada uno.

---

# 🔍 19. PARTE VI · CONSULTAS COMBINADAS

Ahora aumenta la dificultad.

Escribe una expresión que permita localizar:

```text
la incidencia cuyo equipo sea EQ03
```

y otra que permita localizar:

```text
el equipo asignado al empleado E01
```

---

# 🧠 20. PARTE VII · XSLT

Ahora necesitamos transformar el XML heredado.

Crea:

```text
inventario.xsl
```

que genere HTML.

El resultado debería representar:

```text
GESTIONA
Inventario de equipos
```

y mostrar una tabla:

```text
ID | Tipo | Marca | Modelo | Estado
```

---

# 📄 21. XSLT · ESTRUCTURA

Tu transformación debe utilizar:

```text
xsl:stylesheet
xsl:template
xsl:for-each
xsl:value-of
```

como mínimo.

---

# 🔄 22. ITERACIÓN

Utiliza:

```xml
<xsl:for-each>
```

para recorrer los equipos.

Debes comprender qué nodo estás recorriendo.

---

# 🎯 23. SELECCIÓN

Utiliza:

```xml
<xsl:value-of>
```

para obtener:

```text
id
tipo
marca
modelo
estado
```

Recuerda que los equipos utilizan namespace.

Debes resolver correctamente esta cuestión.

---

# 🔀 24. CONDICIONALES XSLT

Haz que los equipos:

```text
activos
```

aparezcan de una forma y los:

```text
averiados
```

de otra.

Puedes utilizar:

```xml
<xsl:if>
```

o:

```xml
<xsl:choose>
```

---

# 🧪 25. XSLT · ORDENACIÓN

Ordena los equipos por:

```text
marca
```

utilizando:

```xml
<xsl:sort>
```

---

# 📊 26. XSLT · FILTRADO

Genera una segunda tabla que muestre únicamente:

```text
incidencias abiertas
```

Utiliza una selección XPath adecuada dentro de XSLT.

---

# 🧠 27. PARTE VIII · DOM

Explica qué ocurre conceptualmente cuando utilizamos DOM para procesar:

```text
inventario.xml
```

Piensa en:

```text
documento
↓
árbol
↓
memoria
↓
nodos
```

---

# 🌳 28. ÁRBOL DOM

Dibuja una representación simplificada:

```text
gestiona
├── departamentos
│   ├── departamento
│   └── departamento
├── equipos
│   └── equipo
└── incidencias
    └── incidencia
```

No necesitas representar todos los nodos.

---

# 🧠 29. VENTAJAS Y DESVENTAJAS DOM

Indica:

```text
3 ventajas
3 inconvenientes
```

de DOM.

---

# ⚡ 30. PARTE IX · SAX

Ahora imagina que:

```text
inventario.xml
```

tiene:

```text
5 GB
```

de tamaño.

Explica por qué DOM podría ser problemático.

Después explica por qué SAX puede ser adecuado.

---

# 🔔 31. MODELO DE EVENTOS SAX

Explica qué significa que SAX utilice un modelo:

```text
push
```

y qué eventos conceptuales podría recibir el procesador:

```text
inicio documento
inicio elemento
texto
fin elemento
fin documento
```

---

# 🔄 32. DOM VS SAX

Completa:

```text
DOM
→ ______________________
→ ______________________

SAX
→ ______________________
→ ______________________
```

Compara:

```text
memoria
acceso
velocidad
complejidad
```

---

# 🎛️ 33. PARTE X · StAX

Ahora aparece:

```text
StAX
```

Explica qué diferencia conceptual existe entre:

```text
SAX
```

y:

```text
StAX
```

Recuerda:

```text
SAX
→ push

StAX
→ pull
```

---

# 🧠 34. ¿CUÁNDO USAR CADA UNO?

Asocia:

```text
DOM
SAX
StAX
```

con escenarios apropiados.

Por ejemplo:

### Escenario A

Necesitas modificar y navegar repetidamente por un XML relativamente pequeño.

### Escenario B

Necesitas procesar un XML enorme y reaccionar a eventos secuencialmente.

### Escenario C

Quieres procesar XML grande pero controlar desde el código cuándo obtener el siguiente evento.

---

# 🧪 35. PARTE XI · DETECTAR ERRORES

Corrige estos fragmentos.

### Fragmento A

```xml
<empleado>
    <nombre>Pedro</apellidos>
</empleado>
```

### Fragmento B

```xml
<empleado id=E01>
```

### Fragmento C

```xml
<empleado>
    <nombre>Pedro</nombre>
    <nombre>Ana</nombre>
</empleado>
```

Suponiendo que la estructura esperada es:

```text
empleado
→ exactamente un nombre
```

### Fragmento D

```xml
<empleado>
    <nombre>Pedro</nombre>
</empleado>
<empleado>
    <nombre>Ana</nombre>
</empleado>
```

---

# 🧠 36. PARTE XII · DIAGNÓSTICO

Para cada error indica si es:

```text
error de XML bien formado
```

o:

```text
error de validación
```

o:

```text
ambos
```

Justifica.

---

# 🏆 37. DESAFÍO FINAL · MIGRACIÓN

La dirección de GESTIONA quiere abandonar el sistema XML.

Tu misión final:

Diseña un pequeño proceso conceptual:

```text
inventario.xml
       ↓
validación XSD
       ↓
XPath
       ↓
transformación XSLT
       ↓
HTML
```

Explica qué tecnología utilizarías en cada paso y por qué.

---

# ⭐ 38. DESAFÍO EXTRA

Supón ahora que el XML tiene:

```text
20 GB
```

y solo necesitas localizar:

```text
incidencias críticas
```

sin cargar todo el documento en memoria.

Compara:

```text
DOM
SAX
StAX
```

y elige una solución.

Justifica tu elección.

---

# 🧠 39. PREGUNTAS DE REFLEXIÓN

Responde sin consultar el temario:

### 1.

¿Qué diferencia hay entre XML bien formado y XML válido?

### 2.

¿Qué problema solucionan los namespaces?

### 3.

¿Qué diferencia fundamental hay entre DTD y XSD?

### 4.

¿Qué significa `*` en DTD?

### 5.

¿Qué significa `maxOccurs="unbounded"`?

### 6.

¿Qué representa `@id` en XPath?

### 7.

¿Qué representa `..`?

### 8.

¿Qué diferencia existe entre `/` y `//`?

### 9.

¿Para qué sirve XSLT?

### 10.

¿Qué diferencia existe entre DOM y SAX?

### 11.

¿Por qué DOM puede consumir mucha memoria?

### 12.

¿Qué significa que SAX sea push?

### 13.

¿Qué significa que StAX sea pull?

---

# 🧠 40. CHECKLIST

Antes de terminar:

```text
□ XML bien formado
□ XML válido
□ Namespaces
□ DTD
□ ? * +
□ XSD
□ tipos de datos
□ restricciones
□ enumeraciones
□ minOccurs
□ maxOccurs
□ XPath
□ predicados
□ atributos
□ ejes básicos
□ XSLT
□ xsl:template
□ xsl:for-each
□ xsl:value-of
□ xsl:if / xsl:choose
□ xsl:sort
□ DOM
□ SAX
□ StAX
□ push / pull
□ validación
□ transformación
□ migración
```

---

# 📊 41. CRITERIOS DE EVALUACIÓN

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

# 🏁 42. OBJETIVO FINAL

Al completar esta misión deberías poder mirar un XML y no pensar:

> «¿Qué demonios es este bosque de etiquetas?»

Sino:

```text
¿Está bien formado?
        ↓
¿Es válido?
        ↓
¿Tiene namespaces?
        ↓
¿Cómo lo consulto?
        ↓
¿Cómo lo transformo?
        ↓
¿Cómo lo proceso eficientemente?
```

Ese es exactamente el cambio de mentalidad que buscamos.

---

# 🔮 PRÓXIMA MISIÓN

## Misión 10 · «La API»

El sistema nuevo de GESTIONA abandonará finalmente XML y comenzará a comunicarse mediante:

```text
JSON
+
HTTP
+
API REST
+
JSON Schema
```

Y ahí aprovecharemos tus conocimientos de Laravel para convertir el último capítulo en algo muy práctico.

---

# 🏁 FIN DE MISIÓN 9
