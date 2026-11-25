# hola-mundo-seo

Página web del **Proyecto SEO (1º DAM): Lanzamiento y Posicionamiento Orgánico**. Es una sola página estática que presenta el proyecto, sus objetivos, las fases y entregables, la rúbrica de evaluación, los modelos de monetización de webs de nicho y una checklist para el alumno.

## Requisitos

- [Node.js](https://nodejs.org/) 20 o superior (con npm)

## Puesta en marcha

```bash
npm install      # instala Vite
npm run dev      # servidor de desarrollo con recarga en caliente (http://localhost:5173)
npm run build    # genera la versión de producción en dist/
npm run preview  # sirve dist/ en local para comprobar el build
```

## Estructura

```
.
├── index.html      # La página completa: HTML, estilos y scripts
├── public/         # Ficheros que se copian tal cual a dist/ (favicon.svg, icons.svg)
├── src/            # Restos de la plantilla de Vite (ver nota abajo)
├── package.json
└── dist/           # Salida de `npm run build` (no se sube a git)
```

### Secciones de la página

| Ancla           | Contenido                                   |
| --------------- | ------------------------------------------- |
| `#contexto`     | Introducción y contexto académico           |
| `#objetivos`    | Objetivos y stack tecnológico               |
| `#fases`        | Las 5 fases del proyecto y sus entregables  |
| `#rubrica`      | Rúbrica de evaluación                       |
| `#monetizacion` | Modelos de monetización de webs de nicho    |
| `#checklist`    | Checklist interactiva del alumno            |

## Tecnologías

Todo se carga desde CDN, sin paso de compilación de CSS:

- **Tailwind CSS** (Play CDN), con la configuración de colores `brand` / `accent` y fuentes dentro de `index.html`
- **Google Fonts**: Inter (texto) y Outfit (títulos)
- **Font Awesome 6.4** para los iconos
- **Vite** solo como servidor de desarrollo y empaquetador

## Funcionalidades

- **Modo claro/oscuro**: sigue la preferencia del sistema y guarda la elección del usuario en `localStorage` (clave `theme`).
- **Checklist interactiva**: el progreso de cada alumno se guarda en `localStorage` de su navegador y se puede reiniciar desde la propia página.

## Cómo editar el contenido

Todo el contenido está en [index.html](index.html). Cada sección es un `<section id="...">` dentro de `<main>`; edita el texto directamente ahí. Los colores del tema se cambian en el bloque `tailwind.config` del `<head>`.

## Notas

- `index.html` **no carga** `src/main.js`, así que `src/` (contador, logos e imagen de la plantilla de Vite) no forma parte de la página. Se puede borrar sin afectar al resultado.
- Al tratarse de un proyecto SEO, conviene añadir en el `<head>` una `<meta name="description">`, etiquetas Open Graph y un enlace al favicon, que ahora mismo no están.
- Para producción, Tailwind recomienda sustituir el Play CDN por la instalación con Vite, que genera un CSS más ligero.

## Despliegue

`npm run build` deja la web lista en `dist/`. Esa carpeta se puede publicar en cualquier hosting estático (GitHub Pages, Netlify, Vercel…).
