# 🎧 Music Festival
 
Página web responsiva para un festival de música electrónica (Techno & EDM), maquetada con **HTML5 + SCSS (arquitectura modular)** y con interactividad en **JavaScript**. El flujo de construcción está automatizado con **Gulp**, incluyendo compilación de Sass, minificación de JS y un pipeline de optimización/conversión de imágenes (JPG, WebP y AVIF) con **Sharp**.
 
## 🌐 Demo
 
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
 
🔗 [music-festival-delta.vercel.app](https://music-festival-delta.vercel.app/)
 
## 🛠️ Tecnologías Usadas
 
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![SCSS](https://img.shields.io/badge/SCSS-CC6699?style=for-the-badge&logo=sass&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Gulp](https://img.shields.io/badge/Gulp-CF4647?style=for-the-badge&logo=gulp&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
 
Además:

- **Sharp** — procesamiento y conversión de imágenes (JPG, WebP, AVIF)
- **Terser** — minificación de JavaScript
- **Google Fonts** — tipografía (Montserrat)

## ✨ Características
 
- 🎥 **Hero con video de fondo** (mp4 / ogv / webm) con overlay en gradiente.
- 🧭 **Navegación fija (sticky nav)** que aparece al hacer scroll pasada la sección "Sobre el festival".
- 🎯 **Scrollspy**: resalta el enlace del menú correspondiente a la sección visible.
- 🖱️ **Scroll suave** al hacer clic en los enlaces de navegación (`scrollIntoView`).
- 🗓️ **Lineup por días y escenarios** (Techno / EDM) con horarios de artistas.
- 🖼️ **Galería dinámica generada por JS**, con miniaturas (`thumb`) y modal de imagen completa (`full`) al hacer clic.
- 🎫 **Sección de boletos** con tarjetas de precios (pases de 1 y 2 días).
- 🖼️ **Optimización automática de imágenes**: cada imagen se procesa y exporta en `.jpg`, `.webp` y `.avif`, sirviendo el formato más eficiente que soporte el navegador mediante `<picture>`.
- 📱 **Diseño responsivo** con mixins de media queries (`telefono`, `tablet`, `desktop`, `desktopXL`).
 
## 📂 Estructura SCSS
 
Los estilos se organizan en dos carpetas principales usando `@use` y `@forward` para modularizar:

- **`base/`** → `_variables.scss` (colores, tipografía, breakpoints), `_mixins.scss` (media queries, grid, reset de listas), `_normalize.scss` y `_globales.scss`.
- **`layout/`** → un archivo por sección de la página (`_header.scss`, `_video.scss`, `_festival.scss`, `_lineup.scss`, `_galeria.scss`, `_boletos.scss`, `_footer.scss`).
- **`app.scss`** → reexporta `base` y `layout` como punto único de entrada para Gulp.

## ⚙️ Tareas de Gulp
 
| Tarea       | Descripción                                                                 |
|-------------|-------------------------------------------------------------------------------|
| `js`        | Minifica `src/js/app.js` con Terser y lo copia a `build/js`                  |
| `css`       | Compila `src/scss/app.scss` a CSS comprimido con sourcemaps                  |
| `crop`      | Recorta las imágenes de la galería a un tamaño uniforme para las miniaturas  |
| `imagenes`  | Convierte y optimiza las imágenes a `.jpg`, `.webp` y `.avif` con Sharp      |
| `dev`       | Observa cambios en SCSS, JS e imágenes y recompila automáticamente          |
| `default`   | Ejecuta `crop → js → css → imagenes → dev` en secuencia                     |
 
## 🧠 Conceptos practicados
 
- Manipulación del DOM y generación dinámica de elementos (galería y modal) con JavaScript.
- Detección de la sección activa durante el scroll (*scrollspy*) y navegación con `scrollIntoView`.
- Uso de `IntersectionObserver`/`getBoundingClientRect` para alternar clases según la posición del scroll.
- Arquitectura SCSS modular con `@use` y `@forward` (namespacing, evitar contaminación global).
- Creación de mixins reutilizables para media queries y layouts en grid.
- Optimización de imágenes para web: generación automática de formatos modernos (WebP, AVIF) junto a un fallback JPG.
- Automatización del flujo de trabajo frontend con Gulp (tareas, watchers y pipelines de imágenes).
- Diseño responsivo mobile-first con breakpoints definidos como variables.

## 🚀 Instalación y uso
 
1. Clonar el repositorio:
```bash
   git clone https://github.com/andresmdevco/music-festival.git
   cd music-festival
```
 
2. Instalar las dependencias:
```bash
   npm install
```
 
3. Ejecutar el proyecto en modo desarrollo (compila y observa cambios):
```bash
   npm run dev
```
 
4. Abrir `index.html` en el navegador.

