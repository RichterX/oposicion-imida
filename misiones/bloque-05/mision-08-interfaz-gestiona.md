# 🧩 MISIÓN 8 · LA INTERFAZ DE GESTIONA

> **Bloque:** 5 - Programación  
> **Capítulos:** 5.5 HTML + 5.6 CSS  
> **Tipo:** Misión práctica  
> **Dificultad:** 🟢 → 🟠  
> **Continuidad:** Misión 7 · El plano de la máquina

---

# 🎯 1. OBJETIVO

En la Misión 7 diseñaste:

```text
GESTIONA
│
├── usuarios
├── departamentos
├── equipos
└── incidencias
```

Ahora toca construir su **interfaz web**.

No vamos a programar todavía JavaScript ni conectar una API.

El objetivo es demostrar que sabes utilizar:

```text
HTML
+
CSS
```

para transformar el modelo anterior en una interfaz:

```text
semántica
accesible
organizada
responsive
```

---

# 🏢 2. ESCENARIO

El equipo de desarrollo de GESTIONA ha aprobado tu diseño.

Ahora necesitan una primera versión de la interfaz web.

El administrador debe poder consultar:

```text
Equipos
Empleados
Departamentos
Incidencias
```

y acceder rápidamente a las operaciones principales.

La aplicación se visualizará principalmente en:

```text
ordenador
tablet
móvil
```

Por tanto, debe adaptarse a diferentes tamaños de pantalla.

---

# 📁 3. ESTRUCTURA DEL PROYECTO

Crea una estructura sencilla:

```text
mission-08/
│
├── index.html
│
├── equipos.html
├── incidencias.html
│
└── css/
    └── styles.css
```

No necesitas JavaScript.

---

# 🧱 4. PARTE I · ESTRUCTURA HTML

Crea una estructura semántica utilizando, como mínimo:

```html
<header>
<nav>
<main>
<section>
<article>
<footer>
```

No es necesario utilizar todas en todas las páginas.

La idea es que cada elemento tenga una función semántica razonable.

---

# 🧭 5. CABECERA Y NAVEGACIÓN

La aplicación debe tener una cabecera similar a:

```text
┌─────────────────────────────────────────────┐
│ GESTIONA       Inicio  Equipos  Incidencias │
└─────────────────────────────────────────────┘
```

Incluye:

```text
nombre/logo textual
enlace Inicio
enlace Equipos
enlace Incidencias
```

Los enlaces deben ser elementos `<a>` reales.

No utilices:

```text
<div onclick="...">
```

para simular enlaces.

---

# 🏠 6. PÁGINA PRINCIPAL

En `index.html` crea un panel resumen.

Debe mostrar al menos:

```text
┌──────────────┐ ┌──────────────┐
│ Equipos      │ │ Incidencias  │
│     128      │ │      17      │
└──────────────┘ └──────────────┘

┌──────────────┐ ┌──────────────┐
│ Empleados    │ │ Departamentos│
│      86      │ │       8      │
└──────────────┘ └──────────────┘
```

No importa que los números sean ficticios.

---

# 🧩 7. TARJETAS

Cada indicador debe estar dentro de una estructura apropiada.

Por ejemplo:

```html
<article>
    <h2>Equipos</h2>
    <p>128</p>
</article>
```

No es obligatorio utilizar exactamente esta estructura.

Lo importante es:

```text
contenido agrupado
semántica razonable
jerarquía de encabezados
```

---

# 📋 8. SECCIÓN DE ACTIVIDAD

Añade una sección:

```text
Actividad reciente
```

con al menos cinco elementos.

Ejemplo:

```text
Equipo EQ-102 asignado a Pedro Luque
Incidencia #184 creada
Impresora PR-021 dada de baja
Incidencia #180 cerrada
Nuevo empleado registrado
```

Puedes utilizar:

```html
<ul>
<li>
```

si conceptualmente se trata de una lista.

---

# 🖥️ 9. PÁGINA DE EQUIPOS

Crea:

```text
equipos.html
```

Debe mostrar una tabla.

Columnas mínimas:

```text
ID
Tipo
Marca
Modelo
Estado
Usuario
```

Ejemplo:

| ID | Tipo | Marca | Modelo | Estado | Usuario |
|---|---|---|---|---|---|
| EQ-001 | Ordenador | Dell | OptiPlex | Activo | Pedro |
| EQ-002 | Monitor | LG | UltraFine | Activo | Ana |
| EQ-003 | Impresora | HP | LaserJet | Averiado | — |

---

# 📊 10. TABLA HTML

Utiliza correctamente:

```html
<table>
<thead>
<tbody>
<tr>
<th>
<td>
```

Los encabezados deben utilizar:

```html
<th>
```

y no simplemente:

```html
<td>
```

---

# ♿ 11. ACCESIBILIDAD DE LA TABLA

Los encabezados deben estar correctamente asociados con las columnas.

Puedes utilizar:

```html
scope="col"
```

Ejemplo:

```html
<th scope="col">
    Tipo
</th>
```

---

# 🔎 12. FILTRO VISUAL

Encima de la tabla crea un formulario de búsqueda/filtro.

Debe incluir:

```text
Buscar
Tipo
Estado
```

Por ejemplo:

```text
┌─────────────────────┐
│ Buscar equipo       │
└─────────────────────┘

Tipo:
[ Todos ▼ ]

Estado:
[ Todos ▼ ]

[ Filtrar ]
```

---

# 🧾 13. FORMULARIO

Utiliza elementos semánticos:

```html
<form>
<label>
<input>
<select>
<option>
<button>
```

Cada control debe tener una etiqueta correctamente asociada.

Por ejemplo:

```html
<label for="search">
    Buscar equipo
</label>

<input
    id="search"
    name="search"
    type="search"
>
```

---

# 🧠 14. TIPOS DE INPUT

Utiliza tipos apropiados.

Por ejemplo:

```text
type="search"
type="email"
type="date"
type="number"
```

No utilices:

```text
type="text"
```

para absolutamente todo.

---

# 🚨 15. PÁGINA DE INCIDENCIAS

Crea:

```text
incidencias.html
```

Debe mostrar una lista o tabla de incidencias.

Como mínimo:

```text
ID
Título
Equipo
Prioridad
Estado
Técnico
Fecha
```

Ejemplo:

| ID | Título | Equipo | Prioridad | Estado | Técnico | Fecha |
|---|---|---|---|---|---|---|
| #184 | No arranca | EQ-001 | Alta | Abierta | — | 16/08 |
| #183 | Pantalla negra | EQ-020 | Media | En progreso | Ana | 15/08 |
| #182 | Sin conexión | EQ-033 | Crítica | Resuelta | Luis | 15/08 |

---

# 🏷️ 16. ESTADOS

Representa visualmente:

```text
ABIERTA
EN PROGRESO
RESUELTA
CERRADA
```

Puedes utilizar:

```html
<span>
```

para representar una etiqueta de estado.

Por ejemplo:

```html
<span class="status status-open">
    Abierta
</span>
```

---

# 🎨 17. PARTE II · CSS

Ahora empieza el verdadero trabajo de CSS.

Crea:

```text
css/styles.css
```

y enlázalo desde todas las páginas.

Utiliza:

```html
<link
    rel="stylesheet"
    href="css/styles.css"
>
```

---

# 📦 18. RESET BÁSICO

Realiza un pequeño reset.

Como mínimo controla:

```text
box-sizing
margin
padding
```

Una solución habitual:

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

---

# 🧱 19. VARIABLES CSS

Define algunas variables mediante:

```css
:root
```

Por ejemplo:

```css
:root {
    --color-primary: #1f4b99;
    --color-background: #f4f6f8;
    --color-text: #1f2937;
    --color-border: #d1d5db;
}
```

Puedes utilizar otros valores.

El objetivo es practicar:

```text
custom properties
```

---

# 🧭 20. LAYOUT PRINCIPAL

La aplicación debe tener:

```text
header
main
footer
```

y una navegación horizontal en escritorio.

Utiliza:

```text
Flexbox
```

para construir la navegación.

---

# 📐 21. DASHBOARD CON GRID

Las tarjetas del dashboard deben utilizar:

```text
CSS Grid
```

Por ejemplo:

```css
.dashboard {
    display: grid;
}
```

Debes conseguir:

```text
Escritorio:

┌───────┐ ┌───────┐
│       │ │       │
└───────┘ └───────┘

┌───────┐ ┌───────┐
│       │ │       │
└───────┘ └───────┘
```

---

# 📱 22. RESPONSIVE

En móvil:

```text
┌───────────────┐
│ Equipos       │
├───────────────┤
│ Incidencias   │
├───────────────┤
│ Empleados     │
├───────────────┤
│ Departamentos │
└───────────────┘
```

Las tarjetas deben pasar de:

```text
varias columnas
```

a:

```text
una columna
```

Utiliza una:

```text
Media Query
```

---

# 🧭 23. MEDIA QUERY

Como mínimo debes crear una regla equivalente a:

```css
@media (max-width: 700px) {

    .dashboard {
        grid-template-columns: 1fr;
    }

}
```

Puedes elegir otro breakpoint.

Lo importante es comprender qué estás haciendo.

---

# 🎛️ 24. FLEXBOX

La navegación debe utilizar Flexbox.

Por ejemplo:

```css
.nav-list {
    display: flex;
    gap: 1rem;
}
```

En móvil puedes cambiar su comportamiento.

---

# 📦 25. BOX MODEL

Asegúrate de utilizar correctamente:

```text
margin
border
padding
content
```

En alguna tarjeta debe ser evidente que entiendes la diferencia.

---

# 🎨 26. ESPECIFICIDAD

Crea estilos con una estructura razonable.

Evita llenar el documento de:

```css
!important
```

### Regla:

```text
0 usos de !important
```

salvo que puedas justificar una excepción.

---

# 🧩 27. SELECTORES

Utiliza diferentes tipos de selectores:

```text
elemento
.clase
#id
```

pero prioriza clases para los estilos reutilizables.

No necesitas utilizar un ID para cada elemento visual.

---

# 🖱️ 28. ESTADOS INTERACTIVOS

Aunque todavía no utilicemos JavaScript, añade estados CSS:

```css
a:hover
button:hover
input:focus
```

Y procura que el foco sea visible.

---

# ♿ 29. ACCESIBILIDAD

La interfaz debe cumplir como mínimo:

```text
✓ imágenes con alt si existen
✓ labels asociados
✓ botones reales
✓ enlaces reales
✓ foco visible
✓ jerarquía de encabezados
✓ contraste razonable
```

No escondas el foco con:

```css
outline: none;
```

sin proporcionar una alternativa accesible.

---

# 🖼️ 30. ICONOS E IMÁGENES

Puedes utilizar:

```text
SVG
```

o texto.

No es necesario instalar ninguna librería externa.

Si utilizas una imagen puramente decorativa:

```html
<img src="..." alt="">
```

Si transmite información:

```html
<img
    src="..."
    alt="Descripción de la imagen"
>
```

---

# 📱 31. MOBILE-FIRST · NIVEL EXTRA

Si quieres subir la dificultad:

Construye primero el diseño móvil:

```text
1 columna
```

y después utiliza Media Queries para ampliar:

```text
tablet
desktop
```

Esto es:

```text
mobile-first
```

---

# 📐 32. NIVEL EXTRA · GRID AVANZADO

Haz que las tarjetas se adapten automáticamente utilizando algo como:

```css
grid-template-columns:
    repeat(
        auto-fit,
        minmax(220px, 1fr)
    );
```

Explica con tus palabras qué hace:

```text
auto-fit
minmax()
1fr
```

---

# 🧪 33. NIVEL EXTRA · CONTAINER QUERIES

Si quieres un desafío adicional, convierte las tarjetas en componentes capaces de reaccionar al tamaño de su contenedor.

Investiga y utiliza:

```css
container-type
@container
```

No es obligatorio para completar la misión.

---

# 🔍 34. AUDITORÍA FINAL

Antes de terminar, revisa tu proyecto.

### HTML

```text
□ Documento HTML válido
□ DOCTYPE
□ lang
□ head
□ title
□ meta charset
□ viewport
□ HTML semántico
□ encabezados correctos
□ formularios correctamente etiquetados
□ tablas correctamente estructuradas
```

### CSS

```text
□ CSS externo
□ variables CSS
□ box-sizing
□ Flexbox
□ Grid
□ Media Queries
□ responsive
□ estados :hover
□ estado :focus
□ sin !important innecesario
□ clases reutilizables
```

### Accesibilidad

```text
□ alt
□ labels
□ foco visible
□ navegación mediante enlaces
□ botones reales
□ contraste razonable
```

---

# 🧠 35. PREGUNTAS DE REFLEXIÓN

Responde por escrito:

### 1.

¿Por qué has utilizado:

```text
Grid
```

para el dashboard?

### 2.

¿Por qué has utilizado:

```text
Flexbox
```

para la navegación?

### 3.

¿Qué diferencia hay entre:

```text
display: none;
```

y:

```text
visibility: hidden;
```

### 4.

¿Por qué es importante:

```css
box-sizing: border-box;
```

?

### 5.

¿Qué ocurre si dos selectores tienen distinta especificidad?

### 6.

¿Qué diferencia existe entre:

```text
margin
padding
```

?

### 7.

¿Por qué `required` pertenece a HTML y no a CSS?

### 8.

¿Qué ventaja tiene utilizar variables CSS?

### 9.

¿Qué diferencia existe entre una Media Query y una Container Query?

### 10.

¿Por qué no deberíamos eliminar el indicador de foco?

---

# 🏆 36. DESAFÍO FINAL

Añade una página:

```text
equipo.html
```

que represente el detalle de un equipo.

Debe mostrar:

```text
Ordenador
Dell OptiPlex 7090
```

y:

```text
Número de serie
Estado
Usuario
Departamento
Fecha de alta
```

Además:

```text
Historial de incidencias
```

con al menos tres incidencias.

La página debe poder alcanzarse desde:

```text
equipos.html
```

mediante un enlace real.

---

# ⭐ 37. DESAFÍO RESPONSIVE

Comprueba tu aplicación en tres tamaños aproximados:

```text
📱 375px
📱 768px
🖥️ 1440px
```

Comprueba:

```text
¿se rompe la navegación?

¿las tarjetas caben?

¿la tabla desborda?

¿los formularios siguen siendo utilizables?

¿los textos siguen siendo legibles?
```

Si la tabla es demasiado ancha, busca una solución apropiada.

No simplemente:

```css
font-size: 8px;
```

😈

---

# 🧠 38. ENTREGA

La estructura final podría quedar:

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

---

# 📊 39. CRITERIOS DE EVALUACIÓN

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

Los desafíos opcionales pueden servir para subir el nivel, pero no son necesarios para obtener el 100% de la puntuación base.

---

# 🏁 40. OBJETIVO FINAL

Cuando termines esta misión deberías poder pasar de:

```text
"Necesito una aplicación web para gestionar equipos"
```

a:

```text
HTML
→ estructura semántica

CSS
→ presentación

Flexbox
→ distribución

Grid
→ layout

Media Queries
→ responsive

Accesibilidad
→ interfaz utilizable
```

---

# 🔮 PRÓXIMA MISIÓN

## Misión 9 · «El archivo heredado»

Nos enfrentaremos al sistema antiguo de GESTIONA:

```text
XML
```

Trabajaremos:

```text
XML
DTD
XSD
XPath
XSLT
DOM
SAX
StAX
```

y tendremos que extraer información del sistema antiguo para preparar su migración.

---

# 🏁 FIN DE MISIÓN 8
