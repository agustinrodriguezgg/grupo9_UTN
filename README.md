# Nuova Vita — Interfaz Web (TP2)

Sistema de gestión para el hogar de adultos mayores **Nuova Vita**. Este TP toma
la maqueta HTML del trabajo anterior y la transforma en una interfaz web completa,
aplicando **Flexbox**, **CSS Grid**, **variables CSS** y **Responsive Design**.

## Integrantes

- Agustín Rodríguez
- Constanza Segura
- Marcos Núñez

## Descripción breve

Sitio de tres pantallas que representan la cara pública y el acceso interno del
sistema:

- `index.html` — landing institucional (presentación, funcionalidades, roles y contacto).
- `login.html` — pantalla de inicio de sesión.
- `dashboard.html` — panel interno con estadísticas y actividad reciente.

Todos los estilos están centralizados en un único archivo externo: **`style.css`**.

## Tecnologías utilizadas

- **HTML5 semántico** (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`).
- **CSS3**: variables (`:root` + `var()`), Flexbox, CSS Grid, Media Queries, transiciones.
- **Google Fonts**: Poppins (títulos) y Nunito Sans (texto).
- **Imágenes SVG** propias (logo, ilustración del hero, favicon) en la carpeta `img/`.
- **Git y GitHub** para el control de versiones y el trabajo en equipo.

## Estructura del proyecto

```
TP2/
├── img/
│   ├── logo.svg
│   ├── hero.svg
│   └── favicon.svg
├── style.css
├── index.html
├── login.html
├── dashboard.html
└── README.md
```

## ¿Dónde utilizamos Flexbox?

- **Barra de navegación** (`.header-inner` y `.main-nav ul` en `index.html`): distribuye
  logo, menú y botón en una fila.
- **Sección de Roles** (`.roles-list` en `index.html`): las tarjetas se acomodan con
  `display: flex` + `flex-wrap`.
- **Formularios** (`.form`): dispuestos en columna con `flex-direction: column`.
- **Footer** (`.footer-inner`) y la **barra lateral** del dashboard (`.sidebar`).

## ¿Dónde utilizamos Grid?

- **Hero** (`.hero-grid` en `index.html`): dos columnas (texto + imagen) con
  `grid-template-columns: 1.1fr 0.9fr`.
- **Sección de Servicios** (`.card-grid`): grilla de tarjetas con
  `repeat(auto-fit, minmax(15rem, 1fr))`.
- **Login** (`.auth-card`): dos paneles con `grid-template-columns: 1fr 1fr`.
- **Dashboard** (`.dashboard`): barra lateral + contenido con
  `grid-template-columns: 240px 1fr`, y las tarjetas de estadísticas (`.stats-grid`).

## ¿Qué variables CSS creamos?

Definidas en `:root` dentro de `style.css` y usadas con `var()` en todo el archivo:

- **Colores** (paleta terracota / salvia / crema): `--color-primary` (#C5714E),
  `--color-secondary` (#8A9A7B), `--color-bg` (#FAF6EF), `--color-bg-alt`,
  `--color-text`, `--color-text-light`, `--color-border`, entre otros.
- **Tipografías**: `--font-heading`, `--font-body`.
- **Escala de espaciados**: `--space-xs`, `--space-sm`, `--space-md`, `--space-lg`, `--space-xl`.
- **Bordes y sombras**: `--radius`, `--radius-sm`, `--border`, `--shadow`, `--shadow-lg`.
- **Layout**: `--max-width`.

Centralizar estos valores permite cambiar la identidad visual del sitio editando
un solo lugar.

## ¿Cómo implementamos el Responsive Design?

- **Enfoque adaptable**: layouts fluidos con grillas `auto-fit` + `minmax` y unidades
  relativas (`rem`, `%`, `vh`, `vw`, `fr`) en lugar de medidas fijas.
- **Meta viewport** en todas las páginas.
- **Media Queries** en `style.css` con tres cortes:
  - `max-width: 900px` — el login pasa de dos columnas a una.
  - `max-width: 768px` — el hero se apila (imagen arriba) y el dashboard pone la
    barra lateral arriba y en horizontal.
  - `max-width: 480px` — se oculta el menú horizontal del header y se compactan
    los espaciados.
- **Box Model** con `box-sizing: border-box` global, para que padding y border no
  rompan los anchos.

Resultado: el sitio se visualiza correctamente en **celular, tablet y computadora**.

## Gestión con Git y GitHub

- Ramas `main` (estable) y `dev` (desarrollo).
- El desarrollo se hace sobre `dev` y se integra a `main` al finalizar.
- Se generan Pull Requests asignando compañeros para revisión.
- Commits frecuentes con mensajes claros y descriptivos.

## Estrategias SEO (Search Engine Optimization)

Para mejorar el posicionamiento y la accesibilidad del sitio en los motores de búsqueda, se aplicaron las siguientes estrategias SEO:

- **Títulos descriptivos en cada página:** utilizamos la etiqueta `<title>` con textos relacionados al contenido de cada sección, facilitando que los buscadores identifiquen de qué trata cada página.

- **Meta descripción:** incorporamos `<meta name="description">` con una breve descripción del sitio Nuova Vita y de su propósito.

- **HTML semántico:** utilizamos etiquetas como `<header>`, `<nav>`, `<main>`, `<section>`, `<article>` y `<footer>`, permitiendo que los motores de búsqueda comprendan mejor la estructura del contenido.

- **Jerarquía correcta de encabezados:** organizamos los títulos utilizando `<h1>`, `<h2>` y `<h3>` de forma ordenada, evitando saltos innecesarios en la jerarquía.

- **Texto alternativo en imágenes:** las imágenes importantes incluyen el atributo `alt`, facilitando su interpretación por buscadores y mejorando la accesibilidad.

- **Diseño Responsive:** el sitio se adapta a celulares, tablets y computadoras mediante Media Queries, favoreciendo la experiencia de usuario y el posicionamiento en dispositivos móviles.

- **URLs y nombres de archivos claros:** utilizamos nombres simples y descriptivos como `index.html`, `login.html` y `dashboard.html`, manteniendo una estructura organizada del proyecto.
