# Spec de desarrollo — stayHard

> Guía: [Spec de desarrollo](../evaluacion/guias/fase-2-specs/07-spec-de-desarrollo.md)

## Insumos y prompt para el asistente

```text
Lee DESIGN.md, docs/09-spec-diseno.md y docs/10-spec-desarrollo.md.
En la carpeta stitch/ está el código exportado de Stitch de cada pantalla.
Construye el sitio siguiendo exactamente docs/10-spec-desarrollo.md:
solo HTML y CSS, la estructura de archivos y la navegación definidas,
las variables de :root con los valores de DESIGN.md y la estructura
semántica de cada página. Usa el código de Stitch solo como referencia
visual. Al terminar, revisa cada criterio de aceptación y dime cuáles
se cumplen y cuáles no.
```

## 1. Estructura de archivos

```text
stayhard/
├── index.html                  Landing
├── tienda.html                 Catálogo de planes
├── producto.html               Ficha de producto (Plan Media Maratón)
├── carrito.html                Carrito y formulario de diagnóstico
├── blog.html                   Listado de artículos por categoría
├── articulo.html               Artículo de ejemplo
├── como-funciona.html          Proceso paso a paso
├── testimonios.html            Testimonios y resultados
├── contacto.html               Datos de contacto y formulario
├── preguntas-frecuentes.html   Preguntas frecuentes
├── terminos.html               Términos y condiciones
├── privacidad.html             Política de privacidad
├── 404.html                    Página de error
├── css/
│   └── styles.css              Única hoja de estilos
├── img/                        Imágenes del sitio (optimizadas)
├── stitch/                     Código exportado de Stitch (solo referencia)
├── docs/                       Documentos del proyecto (01 al 10)
├── DESIGN.md
└── README.md
```

## 2. Páginas y navegación

La navegación es solo con enlaces HTML. Todas las rutas son relativas para que funcionen en GitHub Pages.

| Desde | Elemento | Lleva a |
|---|---|---|
| Todas las páginas | Logo stayHard | `index.html` |
| Todas las páginas | Enlace "Tienda" del navbar | `tienda.html` |
| Todas las páginas | Enlace "Blog" del navbar | `blog.html` |
| Todas las páginas | Enlace "Cómo funciona" del navbar | `como-funciona.html` |
| Todas las páginas | Enlace "Contacto" del navbar | `contacto.html` |
| Todas las páginas | Botón "Pedir mi plan" del navbar | `tienda.html` |
| Todas las páginas | Ícono de carrito | `carrito.html` |
| Todas las páginas | Botón flotante de WhatsApp | `https://wa.me/56900000000?text=Hola%20stayHard` (se abre en una pestaña nueva) |
| Todas las páginas | Footer: Preguntas frecuentes, Términos, Privacidad y Contacto | `preguntas-frecuentes.html`, `terminos.html`, `privacidad.html` y `contacto.html` |
| `index.html` | Botón "Ver planes" del hero y "Ver todos los planes" | `tienda.html` |
| `index.html` | Botón "Cómo funciona" del hero | `como-funciona.html` |
| `index.html` | Tarjetas de disciplina | `tienda.html` |
| `index.html` | Botones "Ver plan" de los planes destacados | `producto.html` |
| `index.html` | Enlace "Ver más testimonios" | `testimonios.html` |
| `tienda.html` | Botón "Ver plan" de cada card-product | `producto.html` |
| `producto.html` | Botón "Agregar al carrito" | `carrito.html` |
| `producto.html` | Botón "Ver ejemplo de una semana" | `producto.html#ejemplo` (ancla en la misma página) |
| `producto.html` | Breadcrumb | `index.html` y `tienda.html` |
| `producto.html` | Cards de planes relacionados | `producto.html` |
| `carrito.html` | Botón "Seguir comprando" | `tienda.html` |
| `carrito.html` | Botón "Continuar al pago" | Se queda en `carrito.html` (prototipo, sin pago real) |
| `blog.html` | Chips de categoría | Anclas a las secciones de la misma página (`blog.html#running`, `#futbol`, `#fuerza`, `#lesiones`, `#planificacion` y `#nutricion`) |
| `blog.html` | Cada card-article y el artículo destacado | `articulo.html` |
| `articulo.html` | Botones de compartir (WhatsApp, Facebook y X) | URLs de compartir de cada red (se abren en una pestaña nueva) |
| `articulo.html` | Tarjeta del plan relacionado | `producto.html` |
| `articulo.html` | Breadcrumb "Blog" | `blog.html` |
| `como-funciona.html` | Botón "Ver planes" | `tienda.html` |
| `testimonios.html` | Botón "Ver planes" | `tienda.html` |
| `404.html` | Botón "Volver al inicio" | `index.html` |

## 3. Estructura semántica

**Estructura común a todas las páginas**

- `<html lang="es">` con `<meta charset>`, `<meta name="viewport">` y un `<title>` único por página.
- Un `<header>` con el `<nav aria-label="Principal">` y la lista de enlaces en `<ul>`.
- Un único `<main>` con una sección por bloque, cada una con su título.
- Un `<footer>` con el `<nav aria-label="Información legal">`.
- Un solo `<h1>` por página y títulos en orden (h1, h2, h3), sin saltarse niveles.
- Todas las imágenes con `alt` descriptivo (o `alt=""` si son decorativas) y `width` y `height`.
- Cada campo de formulario con un `<label>` asociado mediante `for` e `id`.
- El menú de mobile se construye sin JavaScript con `<details>` y `<summary>`, o con un checkbox oculto.

**Por página**

- **index.html:** `header` con navbar; `main` con `section` hero (h1), `section` de disciplinas (h2 y lista de tarjetas), `section` "Cómo funciona" (h2 y `<ol>` de 4 pasos), `section` de planes destacados (h2 y 3 `<article>`), `section` de testimonios (h2 y 3 `<figure>` con `<blockquote>`), `section` de suscripción (h2 y `<form>`); `footer`.
- **tienda.html:** `main` con `h1`, `<form role="search">` con el buscador, `<aside aria-label="Filtros">` con los grupos de filtros en `<fieldset>` y `<legend>`, y `<section>` con la lista de planes en `<ul>` y cada plan en un `<article>`.
- **producto.html:** `<nav aria-label="Breadcrumb">` con `<ol>`; `<article>` con `<img>`, h1, precio y `<form>` con `<fieldset>` y `<legend>` para nivel, duración y seguimiento (usa `<input type="radio">`); `<section id="incluye">` con lista; `<section id="ejemplo">` con `<table>` con `<caption>`, `<thead>` y `<th scope>`; `<section>` de preguntas con `<details>` y `<summary>`; `<section>` de planes relacionados.
- **carrito.html:** `main` con h1, `<ol>` de pasos, `<section>` con el producto, `<form>` de diagnóstico con `<fieldset>`, `<label>` y `<select>`, y `<aside>` con el resumen del pedido.
- **blog.html:** `main` con h1, `<nav aria-label="Categorías">`, una `<section>` por categoría con su id (`running`, `futbol`, `fuerza`, `lesiones`, `planificacion` y `nutricion`) y cada artículo en un `<article>`.
- **articulo.html:** `<article>` con `<header>` (h1, autor, `<time datetime>`), cuerpo con h2 y h3, `<footer>` con los botones de compartir; `<aside>` con el plan relacionado; `<section>` de comentarios con `<form>` y lista de comentarios; `<section>` de artículos relacionados.
- **como-funciona.html, testimonios.html, contacto.html, preguntas-frecuentes.html, terminos.html y privacidad.html:** misma estructura común, h1 y secciones con h2 que reutilizan los componentes (section-dark, card-testimonial, input-field y details).
- **404.html:** `main` con h1 "Esta página no existe", un párrafo y un botón "Volver al inicio".

## 4. Organización del CSS

Un único archivo `css/styles.css` ordenado en este orden: variables, reset, base (tipografía y enlaces), layout, componentes, páginas y responsive (con `min-width` y mobile-first).

```css
:root {
  /* Colores (de DESIGN.md) */
  --color-primary: #C2410C;
  --color-primary-hover: #9A3412;
  --color-on-primary: #FFFFFF;
  --color-secondary: #0F172A;
  --color-on-secondary: #FFFFFF;
  --color-on-secondary-variant: #CBD5E1;
  --color-tertiary: #C6F135;
  --color-on-tertiary: #0F172A;
  --color-neutral: #F8FAFC;
  --color-surface: #FFFFFF;
  --color-on-surface: #0F172A;
  --color-on-surface-variant: #475569;
  --color-outline: #64748B;
  --color-disabled: #CBD5E1;
  --color-on-disabled: #334155;
  --color-success: #15803D;
  --color-error: #B3261E;

  /* Tipografía */
  --font-title: "Barlow Condensed", "Arial Narrow", sans-serif;
  --font-body: "Inter", system-ui, sans-serif;
  --fs-h1: 40px;   /* 56px desde 1024px */
  --fs-h2: 30px;   /* 40px desde 1024px */
  --fs-h3: 22px;   /* 28px desde 1024px */
  --fs-body: 16px;
  --fs-small: 14px;

  /* Espaciado */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 32px;
  --space-2xl: 48px;
  --space-3xl: 64px;

  /* Formas, sombras y layout */
  --radius-md: 8px;
  --radius-full: 9999px;
  --shadow-hover: 0 4px 12px rgba(15, 23, 42, 0.12);
  --container-max: 1200px;
}
```

Reglas de organización:

- Los estilos usan solo las variables de `:root`, sin valores de color o tamaño repetidos en el código.
- Clases con nombres por componente en minúsculas con guiones (`.navbar`, `.btn-primary`, `.card-product`, `.tag-level`, `.chip-filter`, `.footer`).
- Breakpoints con `min-width`: `768px` (tablet) y `1024px` (desktop).
- Las fuentes se cargan con un `<link>` a Google Fonts en el `<head>` de cada página (Barlow Condensed 700 e Inter 400 y 600).
- Todos los elementos interactivos tienen un estilo `:focus-visible` con contorno lima de 3 px.

## 5. Criterios de aceptación

**Navegación**
- [ ] Existen las 13 páginas definidas en la sección 1 y todas cargan sin errores.
- [ ] Todos los enlaces de la tabla de navegación llevan al destino indicado, sin enlaces rotos.
- [ ] El navbar y el footer son idénticos en todas las páginas y el enlace de la página actual está marcado visualmente.
- [ ] El botón de WhatsApp aparece en todas las páginas y abre un chat con un mensaje prellenado.
- [ ] Una URL inexistente muestra `404.html` al publicar en GitHub Pages.

**Funcionalidades**
- [ ] La landing incluye un formulario para dejar el correo (prototipo visual).
- [ ] El blog muestra los artículos agrupados por categoría y los chips llevan a cada sección.
- [ ] El artículo incluye un formulario de comentarios (prototipo visual) y botones de compartir en WhatsApp, Facebook y X que funcionan.
- [ ] La tienda incluye un buscador y filtros por disciplina, nivel, duración y precio (prototipo visual).
- [ ] La ficha de producto muestra la selección de nivel, duración y seguimiento, el precio y el botón "Agregar al carrito", que lleva al carrito (prototipo visual).
- [ ] El carrito incluye el formulario de diagnóstico con todos los campos definidos (prototipo visual).
- [ ] La ficha de producto muestra el ejemplo de una semana, y la landing y `testimonios.html` muestran los testimonios.

**Diseño**
- [ ] Las variables de `:root` coinciden exactamente con los valores de `DESIGN.md`.
- [ ] Los colores se usan según los roles de `DESIGN.md`: naranja solo en acciones, lima solo en etiquetas o sobre fondo oscuro, y ningún texto naranja sobre azul noche.
- [ ] Los títulos usan Barlow Condensed, el resto Inter, y los tamaños y pesos siguen la escala definida.
- [ ] Los componentes (navbar, botones, card-product, card-article, tag-level, chip-filter, input-field y footer) tienen el mismo aspecto en todas las páginas.
- [ ] Las pantallas se ven fieles a los diseños de Stitch.

**Responsive**
- [ ] El sitio se ve correctamente en 375 px, 768 px y 1280 px de ancho, sin scroll horizontal.
- [ ] En mobile el navbar se colapsa en un menú hamburguesa que funciona sin JavaScript.
- [ ] Las grillas de tarjetas pasan de 3 o 4 columnas en desktop a 2 en tablet y 1 en mobile.
- [ ] Los filtros de la tienda pasan de barra lateral a panel desplegable en mobile.
- [ ] En mobile los botones ocupan todo el ancho y el botón de WhatsApp muestra solo el ícono.

**Accesibilidad y publicación**
- [ ] Cada página tiene `lang="es"`, un título único y un solo h1, con títulos en orden.
- [ ] Todas las imágenes informativas tienen texto alternativo y todos los campos de formulario tienen una etiqueta asociada.
- [ ] Todo el texto cumple un contraste mínimo de 4,5:1.
- [ ] Todos los elementos interactivos se pueden usar con teclado y tienen un foco visible.
- [ ] El sitio usa solo HTML y CSS, sin JavaScript ni frameworks.
- [ ] El sitio está publicado en GitHub Pages, con rutas relativas y todas las imágenes visibles.
