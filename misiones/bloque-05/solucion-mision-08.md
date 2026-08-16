# 📝 MISIÓN 8 · CORRECCIÓN
## «La interfaz de GESTIONA»

> **Bloque:** 5 - Programación  
> **Capítulos:** 5.5 HTML + 5.6 CSS  
> **Misión:** 8  
> **Objetivo:** Construir una interfaz web semántica, accesible y responsive mediante HTML y CSS.

---

# 1. CORRECCIÓN GENERAL

Esta misión admite muchas soluciones visuales diferentes.

No buscamos que tu interfaz tenga exactamente el mismo aspecto que esta corrección.

La evaluación debe centrarse en:

```text
✓ estructura HTML
✓ semántica
✓ accesibilidad
✓ formularios
✓ tablas
✓ CSS
✓ Flexbox
✓ Grid
✓ responsive
✓ organización
✓ justificación técnica
```

Un diseño visualmente diferente puede ser perfectamente correcto.

---

# 🧱 2. ESTRUCTURA DEL PROYECTO

Una solución de referencia:

```text
mission-08/
│
├── index.html
├── equipos.html
├── equipo.html
├── incidencias.html
│
└── css/
    └── styles.css
```

También sería válido utilizar otra organización razonable, siempre que:

```text
✓ los recursos estén correctamente enlazados
✓ no existan rutas rotas
✓ el proyecto sea mantenible
```

---

# 🌐 3. ESTRUCTURA HTML BASE

Una estructura razonable:

```html
<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>GESTIONA</title>

    <link
        rel="stylesheet"
        href="css/styles.css"
    >
</head>

<body>

    <header>
        ...
    </header>

    <main>
        ...
    </main>

    <footer>
        ...
    </footer>

</body>

</html>
```

---

# 🧠 4. ¿POR QUÉ `<!DOCTYPE html>`?

Indica que el documento utiliza HTML moderno.

Debe aparecer al principio:

```html
<!DOCTYPE html>
```

---

# 🌍 5. `lang`

Una página en español debería utilizar:

```html
<html lang="es">
```

Esto ayuda a:

```text
lectores de pantalla
navegadores
herramientas de accesibilidad
procesamiento lingüístico
```

---

# 📱 6. VIEWPORT

Es recomendable incluir:

```html
<meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
>
```

Permite que la página se adapte correctamente a dispositivos móviles.

---

# 🧭 7. CABECERA

Una solución razonable:

```html
<header class="site-header">

    <a
        class="logo"
        href="index.html"
    >
        GESTIONA
    </a>

    <nav aria-label="Navegación principal">

        <ul class="nav-list">

            <li>
                <a href="index.html">
                    Inicio
                </a>
            </li>

            <li>
                <a href="equipos.html">
                    Equipos
                </a>
            </li>

            <li>
                <a href="incidencias.html">
                    Incidencias
                </a>
            </li>

        </ul>

    </nav>

</header>
```

---

# ♿ 8. ¿POR QUÉ `<nav>`?

Porque representa una sección cuyo propósito es proporcionar enlaces de navegación.

Es preferible:

```html
<nav>
```

a:

```html
<div class="navigation">
```

cuando realmente estamos representando navegación.

---

# 🔗 9. ENLACES

Los enlaces deben utilizar:

```html
<a href="...">
```

No:

```html
<div onclick="...">
```

ni:

```html
<button>
```

para navegar entre documentos.

Conceptualmente:

```text
<a>
→ navegación

<button>
→ acción
```

---

# 🏠 10. DASHBOARD

Una estructura posible:

```html
<main>

    <h1>Panel de control</h1>

    <section
        class="dashboard"
        aria-labelledby="dashboard-title"
    >

        <h2 id="dashboard-title">
            Resumen
        </h2>

        <article class="card">
            <h3>Equipos</h3>
            <p>128</p>
        </article>

        <article class="card">
            <h3>Incidencias</h3>
            <p>17</p>
        </article>

        <article class="card">
            <h3>Empleados</h3>
            <p>86</p>
        </article>

        <article class="card">
            <h3>Departamentos</h3>
            <p>8</p>
        </article>

    </section>

</main>
```

---

# 🧠 11. ¿POR QUÉ `article`?

Una tarjeta puede modelarse como:

```html
<article>
```

si representa una unidad de contenido relativamente independiente.

También puede utilizarse:

```html
<div>
```

si la tarjeta es simplemente un contenedor sin significado semántico propio.

Por tanto:

```text
article
→ buena solución si la tarjeta representa contenido independiente

div
→ también puede ser correcto si únicamente agrupa elementos
```

No hay que convertir cada `div` en un `article` por obligación.

---

# 📋 12. ACTIVIDAD RECIENTE

Una solución natural:

```html
<section aria-labelledby="activity-title">

    <h2 id="activity-title">
        Actividad reciente
    </h2>

    <ul>
        <li>
            Equipo EQ-102 asignado a Pedro Luque
        </li>

        <li>
            Incidencia #184 creada
        </li>

        <li>
            Impresora PR-021 dada de baja
        </li>

        <li>
            Incidencia #180 cerrada
        </li>

        <li>
            Nuevo empleado registrado
        </li>
    </ul>

</section>
```

Una lista es apropiada porque tenemos:

```text
colección de elementos
```

---

# 📊 13. TABLA DE EQUIPOS

Una estructura correcta:

```html
<table>

    <caption>
        Inventario de equipos
    </caption>

    <thead>

        <tr>
            <th scope="col">ID</th>
            <th scope="col">Tipo</th>
            <th scope="col">Marca</th>
            <th scope="col">Modelo</th>
            <th scope="col">Estado</th>
            <th scope="col">Usuario</th>
        </tr>

    </thead>

    <tbody>

        <tr>
            <td>EQ-001</td>
            <td>Ordenador</td>
            <td>Dell</td>
            <td>OptiPlex</td>
            <td>Activo</td>
            <td>Pedro</td>
        </tr>

    </tbody>

</table>
```

---

# ♿ 14. `th` VS `td`

```text
<th>
→ encabezado de celda

<td>
→ dato de celda
```

No debemos utilizar:

```html
<td>Tipo</td>
```

como encabezado cuando corresponde:

```html
<th scope="col">Tipo</th>
```

---

# 🔎 15. `scope`

Para encabezados de columnas:

```html
<th scope="col">
```

Para encabezados de filas, cuando corresponda:

```html
<th scope="row">
```

Esto ayuda a las tecnologías de asistencia a interpretar las relaciones de la tabla.

---

# 🧾 16. FORMULARIO

Ejemplo:

```html
<form>

    <div class="form-group">

        <label for="search">
            Buscar equipo
        </label>

        <input
            id="search"
            name="search"
            type="search"
        >

    </div>

    <div class="form-group">

        <label for="type">
            Tipo
        </label>

        <select
            id="type"
            name="type"
        >

            <option value="">
                Todos
            </option>

            <option value="computer">
                Ordenador
            </option>

            <option value="monitor">
                Monitor
            </option>

        </select>

    </div>

    <button type="submit">
        Filtrar
    </button>

</form>
```

---

# 🧠 17. `label`

La etiqueta debe estar relacionada con el control.

Una forma:

```html
<label for="email">
    Email
</label>

<input
    id="email"
    name="email"
    type="email"
>
```

La coincidencia es:

```text
label[for]
        ↓
input[id]
```

---

# 🧪 18. `name`

`name` identifica el campo cuando sus datos se envían mediante un formulario.

Por ejemplo:

```html
<input
    id="search"
    name="search"
>
```

No debemos confundir:

```text
id
→ identificación del elemento en el documento

name
→ nombre del campo del formulario
```

---

# 🔐 19. `required`

Ejemplo:

```html
<input
    id="email"
    name="email"
    type="email"
    required
>
```

Indica que el campo es obligatorio.

Es una característica de HTML.

No es CSS.

---

# 🧪 20. TIPOS DE INPUT

Ejemplos apropiados:

```text
search
email
date
number
```

Ventaja:

```text
mejor semántica
+
validación nativa
+
mejor experiencia de usuario
```

---

# 🏷️ 21. ESTADOS DE INCIDENCIA

Una solución:

```html
<span class="status status-open">
    Abierta
</span>
```

Y CSS:

```css
.status-open {
    ...
}
```

El nombre de clase puede ser diferente.

Lo importante es separar:

```text
estado semántico
+
presentación visual
```

---

# 🎨 22. RESET Y BOX-SIZING

Una solución:

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}

html,
body {
    margin: 0;
    padding: 0;
}
```

---

# 📦 23. ¿QUÉ HACE `border-box`?

Con:

```css
box-sizing: border-box;
```

el tamaño declarado:

```css
width
height
```

incluye:

```text
content
+
padding
+
border
```

---

# 📐 24. BOX MODEL

El modelo conceptual:

```text
┌─────────────────────────────┐
│           margin            │
│   ┌─────────────────────┐   │
│   │       border        │   │
│   │  ┌───────────────┐  │   │
│   │  │    padding    │  │   │
│   │  │ ┌───────────┐ │  │   │
│   │  │ │  content  │ │  │   │
│   │  │ └───────────┘ │  │   │
│   │  └───────────────┘  │   │
│   └─────────────────────┘   │
└─────────────────────────────┘
```

---

# 🎨 25. VARIABLES CSS

Una solución:

```css
:root {
    --color-primary: #1f4b99;
    --color-background: #f4f6f8;
    --color-text: #1f2937;
    --color-border: #d1d5db;
}
```

Uso:

```css
body {
    background-color: var(--color-background);
    color: var(--color-text);
}
```

---

# 🧠 26. VENTAJA DE CUSTOM PROPERTIES

Permiten centralizar valores reutilizables.

Por ejemplo:

```text
color principal
color de fondo
bordes
espaciado
```

Si cambiamos:

```css
--color-primary
```

podemos modificar múltiples reglas que utilizan esa variable.

---

# 🧭 27. FLEXBOX · NAVEGACIÓN

Una solución:

```css
.nav-list {
    display: flex;
    gap: 1rem;
    list-style: none;
    margin: 0;
    padding: 0;
}
```

Podemos controlar:

```text
dirección
alineación
distribución
espaciado
```

---

# 🧠 28. ¿POR QUÉ FLEXBOX?

La navegación es esencialmente una distribución:

```text
Inicio
Equipos
Incidencias
```

en un eje.

Por eso Flexbox es una herramienta apropiada para:

```text
layout unidimensional
```

---

# 📊 29. GRID · DASHBOARD

Una solución:

```css
.dashboard {
    display: grid;
    grid-template-columns:
        repeat(2, minmax(0, 1fr));
    gap: 1rem;
}
```

Esto crea:

```text
2 columnas
```

en escritorio.

---

# 🧠 30. ¿POR QUÉ GRID?

El dashboard tiene una distribución bidimensional:

```text
filas
+
columnas
```

Grid resulta especialmente apropiado para este tipo de layout.

---

# 📱 31. MEDIA QUERY

Para móvil:

```css
@media (max-width: 700px) {

    .dashboard {
        grid-template-columns: 1fr;
    }

    .nav-list {
        flex-direction: column;
    }

}
```

La idea:

```text
desktop
→ varias columnas

mobile
→ una columna
```

---

# 📐 32. `1fr`

En Grid:

```css
1fr
```

representa una fracción del espacio disponible.

Por ejemplo:

```css
grid-template-columns:
    1fr 1fr;
```

crea dos columnas que comparten el espacio disponible en partes iguales, considerando las demás restricciones del grid.

---

# 🧩 33. `minmax()`

Ejemplo:

```css
grid-template-columns:
    repeat(
        auto-fit,
        minmax(220px, 1fr)
    );
```

Conceptualmente:

```text
mínimo
→ 220px

máximo
→ 1fr
```

Esto permite que las columnas se adapten al espacio disponible.

---

# 🔍 34. `auto-fit`

En este contexto:

```text
auto-fit
```

permite que Grid ajuste el número de columnas que caben en el espacio disponible, colapsando pistas vacías cuando corresponde.

---

# 🖱️ 35. HOVER

Ejemplo:

```css
a:hover {
    text-decoration: underline;
}
```

Indica el estado cuando el puntero se encuentra sobre el elemento.

---

# ⌨️ 36. FOCUS

Una solución:

```css
a:focus-visible,
button:focus-visible,
input:focus-visible,
select:focus-visible {
    outline: 3px solid #1f4b99;
    outline-offset: 2px;
}
```

El objetivo es que el usuario que navega mediante teclado pueda identificar dónde está el foco.

---

# ♿ 37. POR QUÉ NO `outline: none`

Eliminar:

```css
outline: none;
```

sin proporcionar una alternativa puede hacer que el indicador de foco desaparezca.

Eso perjudica especialmente a usuarios que navegan mediante teclado.

---

# 🖼️ 38. IMÁGENES

Si una imagen aporta información:

```html
<img
    src="equipo.jpg"
    alt="Ordenador Dell OptiPlex"
>
```

Si es puramente decorativa:

```html
<img
    src="decoracion.svg"
    alt=""
>
```

---

# 📱 39. MOBILE-FIRST

Una solución avanzada sería comenzar por:

```text
móvil
```

y ampliar progresivamente:

```text
tablet
desktop
```

Por ejemplo:

```css
.dashboard {
    grid-template-columns: 1fr;
}

@media (min-width: 700px) {

    .dashboard {
        grid-template-columns:
            repeat(2, 1fr);
    }

}

@media (min-width: 1100px) {

    .dashboard {
        grid-template-columns:
            repeat(4, 1fr);
    }

}
```

---

# 📦 40. CONTAINER QUERIES

Nivel extra:

```css
.card-container {
    container-type: inline-size;
}
```

Y:

```css
@container (min-width: 400px) {
    ...
}
```

La diferencia conceptual:

```text
Media Query
→ características del viewport/entorno

Container Query
→ características del contenedor
```

---

# 🧠 41. RESPUESTAS A LAS PREGUNTAS DE REFLEXIÓN

## 1. ¿Por qué Grid para dashboard?

Porque el dashboard organiza tarjetas en:

```text
filas
+
columnas
```

Grid está diseñado especialmente para layouts bidimensionales.

---

## 2. ¿Por qué Flexbox para navegación?

Porque la navegación se distribuye principalmente en un eje.

Flexbox es especialmente adecuado para:

```text
layout unidimensional
```

---

## 3. `display: none` vs `visibility: hidden`

```text
display: none
→ el elemento no participa en el layout

visibility: hidden
→ el elemento permanece ocupando espacio,
  pero no es visible
```

---

## 4. ¿Por qué `box-sizing: border-box`?

Porque facilita controlar el tamaño total de los elementos:

```text
width/height
→ incluyen padding + border
```

Esto hace más predecible el layout.

---

## 5. Especificidad

Si varias reglas compiten, la especificidad participa en la determinación de qué declaración gana, junto con:

```text
origen
importancia
orden de aparición
```

De forma simplificada, un selector de ID tiene mayor especificidad que uno de clase y este mayor que uno de elemento.

---

## 6. Margin vs padding

```text
margin
→ espacio exterior

padding
→ espacio interior
```

---

## 7. ¿Por qué `required` pertenece a HTML?

Porque expresa una característica del control/formulario y forma parte de la semántica y validación nativa del formulario.

CSS controla principalmente:

```text
presentación
```

---

## 8. Ventaja de variables CSS

Permiten reutilizar valores y centralizar decisiones de diseño.

---

## 9. Media Query vs Container Query

```text
Media Query
→ responde a características del entorno/viewport

Container Query
→ responde al tamaño/condiciones del contenedor
```

---

## 10. ¿Por qué mantener el foco?

Porque usuarios que navegan mediante teclado necesitan saber qué elemento está activo.

---

# 🏆 42. DESAFÍO FINAL · EQUIPO

La página:

```text
equipo.html
```

debe poder mostrar algo como:

```text
┌─────────────────────────────────────┐
│ ORDENADOR                            │
│ Dell OptiPlex 7090                  │
├─────────────────────────────────────┤
│ Nº serie:     DL-829192             │
│ Estado:       Activo                │
│ Usuario:      Pedro Luque           │
│ Departamento: Desarrollo            │
│ Alta:         10/03/2026            │
└─────────────────────────────────────┘

Historial de incidencias

#184  No arranca          Resuelta
#162  Pantalla negra      Cerrada
#141  Actualización       Cerrada
```

Debe existir un enlace real desde:

```text
equipos.html
```

---

# 📊 43. CRITERIOS DE EVALUACIÓN

| Área | Peso |
|---|---:|
| HTML semántico | 15% |
| Formularios | 10% |
| Tablas | 10% |
| Accesibilidad | 10% |
| CSS / selectores | 10% |
| Box Model / especificidad | 10% |
| Flexbox | 10% |
| CSS Grid | 10% |
| Responsive / Media Queries | 10% |
| Calidad y organización | 5% |
| **TOTAL** | **100%** |

---

# 🔎 44. ERRORES TÍPICOS

## HTML

```text
✗ usar div para absolutamente todo
✗ utilizar <td> como encabezado
✗ formularios sin label
✗ enlaces simulados con div
✗ imágenes sin alt cuando lo necesitan
✗ jerarquía de headings incoherente
```

## CSS

```text
✗ utilizar !important constantemente
✗ usar IDs para todos los estilos
✗ confundir margin y padding
✗ olvidar box-sizing
✗ utilizar Flexbox para absolutamente todo
✗ utilizar Grid para absolutamente todo
✗ romper el layout móvil
✗ eliminar el foco
```

---

# 🧠 45. CONCEPTOS QUE DEBES PODER EXPLICAR

Al terminar deberías poder explicar:

```text
¿Qué diferencia hay entre HTML y CSS?

¿Qué es HTML semántico?

¿Qué diferencia hay entre div y span?

¿Qué hace alt?

¿Qué hace label?

¿Qué diferencia hay entre id y name?

¿Qué hace required?

¿Qué hace pattern?

¿Qué es el Box Model?

¿Qué hace box-sizing?

¿Qué es la especificidad?

¿Qué es Flexbox?

¿Qué es CSS Grid?

¿Qué es 1fr?

¿Qué hace minmax()?

¿Qué hace auto-fit?

¿Qué es una Media Query?

¿Qué es una Container Query?

¿Qué diferencia hay entre hover y focus?

¿Por qué es importante el foco?

¿Qué significa responsive?
```

---

# 🏁 46. CONCLUSIÓN

La misión buscaba pasar de:

```text
REQUISITOS
    ↓
HTML
    ↓
CSS
    ↓
LAYOUT
    ↓
RESPONSIVE
    ↓
ACCESIBILIDAD
```

El objetivo no era crear una interfaz espectacular.

El objetivo era demostrar que puedes construir una interfaz:

```text
correcta
semántica
mantenible
accesible
responsive
```

---

# 🏁 FIN DE LA CORRECCIÓN · MISIÓN 8
