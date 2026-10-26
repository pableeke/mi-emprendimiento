# Spec de desarrollo — Keep-Strong

> Guía: [Spec de desarrollo](../evaluacion/guias/fase-2-specs/07-spec-de-desarrollo.md)

Esta spec describe **cómo se construye** el sitio de Keep-Strong. No se implementa en esta evaluación: queda lista para la etapa de código. Se apoya en cuatro documentos y no los contradice:

- [`DESIGN.md`](../DESIGN.md): valores de color, tipografía, espaciados, formas y reglas de cada componente.
- [`05-arquitectura.md`](05-arquitectura.md): mapa de sitio y user flows de Matías.
- [`03-funcionalidades.md`](03-funcionalidades.md) y [`04-tecnologias.md`](04-tecnologias.md): qué debe poder hacer el sitio y qué es funcional o prototipo visual.
- [`09-spec-diseno.md`](09-spec-diseno.md): las 6 pantallas de referencia.

## Insumos y prompt para el asistente

```text
Lee DESIGN.md, docs/09-spec-diseno.md y docs/10-spec-desarrollo.md.
En la carpeta stitch/ está el código exportado de Stitch de cada pantalla.
Construye el sitio siguiendo exactamente docs/10-spec-desarrollo.md:
solo HTML y CSS (sin JavaScript, sin frameworks), la estructura de archivos
y la navegación definidas, las variables de :root con los valores de
DESIGN.md y la estructura semántica de cada página. Usa los nombres de
componentes de DESIGN.md como nombres de clase (card-plan, button-primary,
chip-filter...). Usa el código de Stitch solo como referencia visual: no
copies su CSS ni sus clases. Donde la spec marque "prototipo visual",
construye el elemento con su aspecto final pero sin lógica. Al terminar,
revisa cada criterio de aceptación de la sección 5 y dime cuáles se
cumplen y cuáles no.
```

## Alcance de esta versión

Coincide con la tabla "Qué es funcional y qué es prototipo" de `04-tecnologias.md`:

| Funcionalidad | Cómo se construye con solo HTML + CSS |
|---|---|
| Navegar entre landing, tienda, blog y páginas legales | **Funcional:** enlaces entre archivos HTML |
| Navegar artículos por categoría | **Funcional sin JavaScript:** chips con botones de opción (`input type="radio"`) y el selector CSS `:has()` que muestra solo los artículos de la categoría elegida |
| Compartir un artículo en redes | **Funcional:** enlaces a WhatsApp y X; Instagram enlaza al perfil de Keep-Strong porque no ofrece un enlace para compartir desde sitios web |
| Consultar por WhatsApp | **Funcional:** enlace `https://wa.me/56975504598` (número real de Keep-Strong) |
| Buscar y filtrar planes | **Prototipo visual:** los campos y filtros se ven y tienen estados, pero no filtran. El buscador de la navbar envía a `tienda.html` |
| Ficha de producto y agregar al carrito | **Prototipo visual:** hay una sola ficha (`producto.html`, Plan maratón 16 semanas) a la que llevan todas las `card-plan`; "Agregar al carrito" lleva a `carrito.html`, que es estático |
| Pestañas "Qué incluye / Semana 1 / Reseñas" | **Funcional sin JavaScript:** botones de opción y `:has()` |
| Pagar | **Prototipo visual:** "Ir a pagar" muestra un aviso de prototipo |
| Dejar datos (landing), suscribirse (blog), comentar y contactar | **Prototipo visual:** no envían datos; muestran el `message-success` al enviar |
| Reseñas y favoritos | **Prototipo visual:** se ven, no guardan nada |

Fuera de esta versión (están en `03-funcionalidades.md`, pero no tienen pantalla en los wireframes): cuestionario de recomendación de plan, página de favoritos y pago real.

## 1. Estructura de archivos

Nombres en minúsculas, sin espacios ni tildes.

```text
keep-strong/
├── index.html                  ← landing
├── tienda.html
├── producto.html               ← ficha de producto (Plan maratón 16 semanas)
├── carrito.html
├── blog.html
├── articulo.html               ← artículo (Qué comer la semana antes de tu primera maratón)
├── contacto.html
├── preguntas-frecuentes.html
├── terminos.html
├── privacidad.html
├── 404.html
├── DESIGN.md
├── README.md
├── css/
│   └── styles.css
├── img/
│   ├── hero/                   ← fotos de la landing
│   ├── planes/                 ← imágenes de cada plan (4:3)
│   ├── blog/                   ← portadas de artículos
│   └── iconos/                 ← logo y íconos en SVG
├── stitch/                     ← código exportado de Stitch (solo referencia)
└── docs/                       ← documentación del proyecto
```

El mapa de sitio de `05-arquitectura.md` tiene las categorías de la tienda y del blog como ramas, pero **no son páginas aparte**: son chips, filtros y etiquetas dentro de `tienda.html` y `blog.html`.

## 2. Páginas y navegación

**Navbar** (igual en las 11 páginas, ver `navbar` en `DESIGN.md`):

| Elemento | Lleva a |
|---|---|
| Logo "KEEP-STRONG" | `index.html` |
| Planes | `tienda.html` |
| Blog | `blog.html` |
| Preguntas | `preguntas-frecuentes.html` |
| Contacto | `contacto.html` |
| Buscador (`form` con `action="tienda.html"`) | `tienda.html` |
| Ícono de carrito con contador | `carrito.html` |
| Ícono de favoritos | Sin destino (prototipo visual) |

**Footer** (igual en las 11 páginas): enlaces a `contacto.html`, `preguntas-frecuentes.html`, `terminos.html` y `privacidad.html`, y los enlaces a WhatsApp e Instagram. Así "Consultar por WhatsApp" está disponible desde cualquier página.

**Enlaces de cada página**, según los user flows de `05-arquitectura.md`:

| Desde | Elemento | Lleva a |
|---|---|---|
| `index.html` | Botón "Ver planes" del hero | `tienda.html` |
| `index.html` | Botón "Consultar por WhatsApp" del hero | `https://wa.me/56975504598` |
| `index.html` | Botón "Ver plan" de cada `card-plan` | `producto.html` |
| `index.html` | `form-lead` "Quiero mi guía" | `index.html#enviado` (muestra `message-success`) |
| `tienda.html` | Botón "Ver plan" de cada `card-plan` | `producto.html` |
| `producto.html` | Botón "Agregar al carrito" | `carrito.html` |
| `producto.html` | Botón "Consultar por WhatsApp" | `https://wa.me/56975504598` |
| `producto.html` | Enlace de ruta "Tienda" | `tienda.html` |
| `producto.html` | `card-plan` de "Planes relacionados" | `producto.html` |
| `carrito.html` | Enlace "Seguir viendo planes" | `tienda.html` |
| `carrito.html` | Botón "Ir a pagar" | `carrito.html#pago` (aviso de prototipo) |
| `carrito.html` | Enlace "¿Dudas? Escríbenos por WhatsApp" | `https://wa.me/56975504598` |
| `blog.html` | Artículo destacado y enlace "Leer artículo" de cada `card-article` | `articulo.html` |
| `articulo.html` | Botón "Ver plan de alimentación" | `producto.html` |
| `articulo.html` | Botones "Compartir" WhatsApp, X e Instagram | `https://wa.me/?text=…`, `https://twitter.com/intent/tweet?url=…` y el perfil de Instagram de Keep-Strong |
| `articulo.html` | Ruta de navegación "Blog" | `blog.html` |
| `404.html` | Enlaces "Volver al inicio" y "Ver planes" | `index.html` y `tienda.html` |

**Recorridos que deben poder completarse:**

- **Flujo de compra:** `index.html` → `tienda.html` → `producto.html` → `carrito.html`.
- **Flujo de contenido:** `blog.html` → `articulo.html` → `producto.html` → `carrito.html`.
- **Rama de dudas:** desde `producto.html` el botón de WhatsApp lleva a la conversación; desde `articulo.html` se llega a `contacto.html` por la navbar.

## 3. Estructura semántica

Todas las páginas comparten el esqueleto: `<header>` con la `navbar`, `<main>` con el contenido y `<footer>`. Cada página tiene un solo `<h1>`.

### index.html

```html
<header> → navbar
<main>
  <section> hero: h1, bajada, button-primary, button-secondary, imagen
  <section> h2 "Un plan, tres pilares" + 3 bloques (cada uno es un <article>)
  <section> h2 "Planes más elegidos" + 3 <article class="card-plan">
  <section> h2 "Lo que dicen…" + 3 <blockquote class="card-testimonial">
  <section> form-lead (<form>)
</main>
<footer>
```

### tienda.html

```html
<header> → navbar
<main>
  <section> h1, buscador, chips de categoría (chip-filter)
  <aside>   filtros (Disciplina, Nivel, Precio, "Limpiar filtros")
  <section> grilla de 6 <article class="card-plan">
</main>
<footer>
```

### producto.html

```html
<header> → navbar
<main>
  <nav aria-label="Ruta de navegación"> Tienda > Planes para correr > Plan maratón 16 semanas
  <section> imagen + datos: tag-category, h1, estrellas, precio, selects Nivel y Duración,
            button-primary, button-secondary, enlace "Guardar en favoritos"
  <section> pestañas (Qué incluye, Semana 1, Reseñas)
  <section> h2 "Planes relacionados" + 2 <article class="card-plan">
</main>
<footer>
```

### carrito.html

```html
<header> → navbar
<main>
  <h1> "Tu carrito (2)"
  <section> lista de productos (<ul>, un <li> por producto, separados por divider)
  <aside>   <section class="cart-summary"> resumen del pedido
  <p id="pago" class="message-success"> aviso de prototipo (visible con :target)
</main>
<footer>
```

### blog.html

```html
<header> → navbar
<main>
  <section> h1, bajada, chips de categoría (radios + labels con clase chip-filter)
  <section> artículo destacado (<article>)
  <section> grilla de 3 <article class="card-article"> con data-category
  <section> suscripción (<form>)
</main>
<footer>
```

### articulo.html

```html
<header> → navbar
<main>
  <nav aria-label="Ruta de navegación"> Blog > Alimentación > …
  <article>
    <header> tag-category, h1, autor y tiempo de lectura
    imagen de portada (<figure>)
    cuerpo con h2 y párrafos
  </article>
  <aside> bloque de recomendación (plan de alimentación + button-primary)
  <section> "Compartir" (3 enlaces)
  <section> h2 "Comentarios (3)" + formulario + lista de comentarios
</main>
<footer>
```

### contacto.html, preguntas-frecuentes.html, terminos.html, privacidad.html y 404.html

```html
<header> → navbar
<main>
  contacto: h1 + <form> (nombre, correo, mensaje) + enlace a WhatsApp
  preguntas-frecuentes: h1 + una <details><summary> por pregunta
  terminos / privacidad: h1 + <section> con h2 por apartado
  404: h1 "No encontramos esa página" + enlaces a index.html y tienda.html
</main>
<footer>
```

**Reglas de accesibilidad comunes:** cada `<input>` tiene su `<label>` visible; las imágenes llevan `alt` descriptivo (vacío solo si son decorativas); los íconos que son botones llevan `aria-label`; los enlaces de las `card-plan` y `card-article` tienen texto que los distingue ("Ver plan maratón 16 semanas") para lectores de pantalla.

## 4. Organización del CSS

Un solo archivo, `css/styles.css`, con las secciones en este orden y comentadas: variables, base, layout, componentes, páginas y media queries. Las tipografías se cargan desde Google Fonts en el `<head>` de cada página: Oswald (pesos 500 y 600) y Source Sans 3 (pesos 400 y 600).

```css
:root {
  /* Colores — valores de DESIGN.md */
  --color-primary: #0A6EA8;
  --color-primary-hover: #085886;
  --color-on-primary: #FFFFFF;
  --color-secondary: #DCEEF9;
  --color-on-secondary: #1F2933;
  --color-tertiary: #5BC0F0;
  --color-on-tertiary: #1F2933;
  --color-neutral: #F4F6F8;
  --color-surface: #FFFFFF;
  --color-on-surface: #1F2933;
  --color-on-surface-variant: #4B5863;
  --color-outline: #8A949C;
  --color-inverse-surface: #2F3B45;
  --color-on-inverse-surface: #FFFFFF;
  --color-disabled: #D5DBE0;
  --color-on-disabled: #4B5863;
  --color-success: #1B7444;
  --color-on-success: #FFFFFF;
  --color-error: #B3261E;
  --color-on-error: #FFFFFF;

  /* Tipografía */
  --font-title: 'Oswald', sans-serif;
  --font-body: 'Source Sans 3', sans-serif;

  /* Escala tipográfica (mobile; desde 768px se usan los valores de escritorio) */
  --text-display: 36px;   /* h1 · escritorio 48px · peso 600 · interlineado 1.1 */
  --text-headline-lg: 28px; /* h2 · escritorio 32px · peso 600 · interlineado 1.2 */
  --text-headline-md: 20px; /* h3 · escritorio 24px · peso 500 · interlineado 1.25 */
  --text-title-md: 20px;  /* nombre y precio en cards · peso 500 · interlineado 1.25 */
  --text-body-md: 16px;   /* párrafos · peso 400 · interlineado 1.6 */
  --text-body-sm: 14px;   /* textos secundarios, etiquetas y chips · peso 400 · interlineado 1.5 */
  --text-label-md: 16px;  /* botones · peso 500 · interlineado 1 */

  /* Espaciados */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 32px;
  --space-2xl: 48px;
  --space-3xl: 64px;

  /* Radios */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-full: 9999px;

  /* Layout */
  --container-max: 1200px;
  --gutter: 16px;          /* 24px desde 768px */
  --section-gap: 48px;     /* 64px desde 1024px */
  --navbar-height: 72px;
  --filters-width: 240px;
}
```

**Convenciones**

- **Clases en inglés, con guiones, con el nombre exacto del token de `DESIGN.md`:** `.navbar`, `.button-primary`, `.button-secondary`, `.chip-filter`, `.tag-category`, `.input-field`, `.card-plan`, `.card-article`, `.card-testimonial`, `.form-lead`, `.cart-summary`, `.divider`, `.footer`, `.message-error`, `.message-success`. Así cada clase se puede rastrear hasta su token.
- **Partes de un componente** con doble guion bajo (`.card-plan__title`, `.card-plan__price`); **variantes y estados** con una clase (`.is-active`, `.is-disabled`) o con pseudoclases (`:hover`, `:focus-visible`, `:disabled`, `:checked`).
- **Ningún color, tamaño de letra, espaciado ni radio escrito a mano:** todos salen de las variables de `:root`. Si un valor cambia, se cambia primero en `DESIGN.md` y luego en `:root`.
- **Mobile first:** los estilos base son los de mobile y se amplía con `@media (min-width: …)`.
- **Breakpoints** (los de `## Layout` de `DESIGN.md`): mobile hasta 767px, tablet desde `768px` y desktop desde `1024px`.

| Elemento | Mobile (base) | Desde 768px | Desde 1024px |
|---|---|---|---|
| Márgenes laterales (`--gutter`) | 16px | 24px | 24px |
| Separación entre secciones | 48px | 48px | 64px |
| Grilla de `.card-plan` y `.card-article` | 1 columna | 2 columnas | 3 columnas |
| Menú | Hamburguesa | Hamburguesa | Enlaces visibles |
| Filtros de la tienda | Botón "Filtros" que abre un panel a pantalla completa | Botón "Filtros" que abre un panel lateral | Columna fija de 240px a la izquierda |
| Hero | Una columna, imagen arriba | Una columna | Dos columnas |
| Ficha de producto | Una columna; "Agregar al carrito" fijo abajo | Dos columnas | Dos columnas |
| Carrito | Lista y `cart-summary` debajo | Apilados | Lista a la izquierda y `cart-summary` fijo a la derecha |
| `form-lead` | Campos apilados, botón de ancho completo | Campos apilados | Texto a la izquierda y campos a la derecha |
| Footer | Columnas apiladas | 2 columnas | 4 columnas |

**Técnicas CSS sin JavaScript**

- **Menú hamburguesa y panel de filtros:** `input type="checkbox"` oculto + `label` como botón; el panel se muestra con `:checked ~ …`.
- **Chips del blog y pestañas de la ficha:** `input type="radio"` + `label`; el contenido se filtra con `:has()`, por ejemplo `.blog:has(#cat-alimentacion:checked) .card-article:not([data-category="alimentacion"]) { display: none; }`.
- **Mensajes de éxito** (`message-success`): ocultos por defecto y visibles con `:target` cuando el formulario envía a `#enviado` o `#pago`.
- **Botón del formulario de leads:** se ve deshabilitado (`button-primary-disabled`) mientras la casilla de privacidad no esté marcada, con `:has(input[type="checkbox"]:not(:checked))`; los campos usan `required`.

## 5. Criterios de aceptación

Cada criterio se responde con sí o no.

**Navegación**
- [ ] La navbar y el footer son idénticos en las 11 páginas.
- [ ] Se puede completar el flujo de compra: landing → tienda → ficha de producto → carrito.
- [ ] Se puede completar el flujo de contenido: blog → artículo → ficha de producto → carrito.
- [ ] Existen los 11 archivos del mapa de sitio y no hay enlaces rotos (el número de WhatsApp y el perfil de Instagram son los reales, no `569XXXXXXXX`).
- [ ] Los enlaces de la tabla de la sección 2 llevan a la página indicada.
- [ ] Una dirección que no existe muestra `404.html`.

**Funcionalidades**
- [ ] La landing tiene un `form-lead` con nombre, correo, disciplina y casilla de privacidad; el botón se ve deshabilitado hasta marcar la casilla y, al enviar, aparece "Listo, te enviamos la guía a tu correo".
- [ ] Los chips del blog muestran solo los artículos de la categoría elegida, y "Todos" los muestra todos.
- [ ] El artículo tiene botones para compartir en WhatsApp, Instagram y X, y una sección de comentarios con campo de texto y botón.
- [ ] La tienda tiene buscador, chips de categoría y filtros por disciplina, nivel y precio.
- [ ] La ficha de producto muestra qué incluye el plan, una muestra de la semana 1, reseñas, selectores de nivel y duración y el botón "Agregar al carrito".
- [ ] La landing y la ficha muestran testimonios o reseñas con la disciplina de quien los escribió.
- [ ] Hay un enlace a WhatsApp en el footer de todas las páginas y en la ficha de producto.
- [ ] "Ir a pagar" muestra un aviso que dice que el pago es un prototipo.

**Diseño**
- [ ] Todos los colores, tamaños de letra, espaciados y radios del CSS salen de las variables de `:root`, y estas tienen los mismos valores que `DESIGN.md`.
- [ ] Los títulos, precios y botones usan Oswald y los párrafos usan Source Sans 3; Oswald no aparece en ningún párrafo.
- [ ] El sitio usa solo HTML y CSS propios: sin JavaScript, sin Tailwind y sin copiar el CSS exportado de Stitch.
- [ ] El precio es visible en todas las `card-plan`.
- [ ] El nombre de una `card-plan` ocupa máximo 2 líneas y el título de una `card-article`, máximo 3, y terminan en "…" si son más largos.
- [ ] Las imágenes de las `card-plan` tienen proporción 4:3.
- [ ] El `tag-category` siempre tiene texto oscuro (`--color-on-tertiary`), nunca blanco.
- [ ] Hay un solo `button-primary` por sección, sin contar el de cada card de una grilla.
- [ ] Los campos de formulario están sobre fondo blanco (`--color-surface`), tienen etiqueta visible y borde de 2px en `--color-primary` al recibir foco.
- [ ] Los botones, chips y cards tienen estado hover, y los enlaces y campos tienen un foco visible con el teclado.
- [ ] La navbar queda fija arriba al hacer scroll.
- [ ] Todo texto cumple un contraste mínimo de 4.5:1.

**Responsive**
- [ ] En mobile la tienda y el blog muestran 1 tarjeta por fila; en tablet, 2; en desktop, 3.
- [ ] En mobile y tablet los filtros de la tienda están en un panel que se abre con el botón "Filtros"; en desktop son una columna fija de 240px.
- [ ] En mobile y tablet el menú es una hamburguesa y el buscador y el carrito siguen visibles.
- [ ] En 375px de ancho no hay scroll horizontal en ninguna página.
- [ ] Los botones y enlaces tienen un área táctil de al menos 44px de alto.
- [ ] En mobile, "Agregar al carrito" queda fijo en la parte inferior de la ficha de producto.
- [ ] El footer se muestra en 1 columna en mobile, 2 en tablet y 4 en desktop.

**Accesibilidad y publicación**
- [ ] Todas las imágenes tienen `alt` descriptivo.
- [ ] Cada página tiene un solo `<h1>` y los títulos no saltan de nivel.
- [ ] Todas las páginas usan `<header>`, `<main>` y `<footer>`, y `lang="es"` en `<html>`.
- [ ] Cada campo de formulario tiene un `<label>` asociado.
- [ ] El sitio completo se puede recorrer con el teclado.
- [ ] El HTML de cada página pasa el validador de W3C sin errores.
- [ ] El sitio está publicado en GitHub Pages y su enlace figura en el `README.md`.
