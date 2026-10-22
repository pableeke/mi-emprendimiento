---
version: alpha
name: "Keep-Strong"
description: "Design system de Keep-Strong: planes de entrenamiento, descanso y alimentación para deportistas, en celeste y gris con tipografía Oswald."
colors:
  primary: "#0A6EA8"
  primary-hover: "#085886"
  on-primary: "#FFFFFF"
  secondary: "#DCEEF9"
  on-secondary: "#1F2933"
  tertiary: "#5BC0F0"
  on-tertiary: "#1F2933"
  neutral: "#F4F6F8"
  surface: "#FFFFFF"
  on-surface: "#1F2933"
  on-surface-variant: "#4B5863"
  outline: "#8A949C"
  inverse-surface: "#2F3B45"
  on-inverse-surface: "#FFFFFF"
  disabled: "#D5DBE0"
  on-disabled: "#4B5863"
  success: "#1B7444"
  on-success: "#FFFFFF"
  error: "#B3261E"
  on-error: "#FFFFFF"
typography:
  headline-display:
    fontFamily: "Oswald"
    fontSize: 48px
    fontWeight: 600
    lineHeight: 1.1
  headline-lg:
    fontFamily: "Oswald"
    fontSize: 32px
    fontWeight: 600
    lineHeight: 1.2
  headline-md:
    fontFamily: "Oswald"
    fontSize: 24px
    fontWeight: 500
    lineHeight: 1.25
  title-md:
    fontFamily: "Oswald"
    fontSize: 20px
    fontWeight: 500
    lineHeight: 1.25
  body-md:
    fontFamily: "Source Sans 3"
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.6
  body-sm:
    fontFamily: "Source Sans 3"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
  label-md:
    fontFamily: "Oswald"
    fontSize: 16px
    fontWeight: 500
    lineHeight: 1
rounded:
  sm: 4px
  md: 8px
  full: 9999px
spacing:
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 32px
  2xl: 48px
  3xl: 64px
components:
  page:
    backgroundColor: "{colors.neutral}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
  text-secondary:
    backgroundColor: "{colors.neutral}"
    textColor: "{colors.on-surface-variant}"
    typography: "{typography.body-sm}"
  navbar:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.label-md}"
    height: 72px
    padding: "{spacing.md}"
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: 14px 24px
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
    textColor: "{colors.on-primary}"
  button-primary-active:
    backgroundColor: "{colors.primary-hover}"
    textColor: "{colors.on-primary}"
  button-primary-disabled:
    backgroundColor: "{colors.disabled}"
    textColor: "{colors.on-disabled}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.primary}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: 14px 24px
  button-secondary-hover:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.primary-hover}"
  button-secondary-disabled:
    backgroundColor: "{colors.disabled}"
    textColor: "{colors.on-disabled}"
  chip-filter:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.full}"
    padding: 8px 16px
  chip-filter-hover:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.on-secondary}"
  chip-filter-active:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  tag-category:
    backgroundColor: "{colors.tertiary}"
    textColor: "{colors.on-tertiary}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.full}"
    padding: 4px 12px
  input-field:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.sm}"
    padding: 12px 14px
  input-field-disabled:
    backgroundColor: "{colors.disabled}"
    textColor: "{colors.on-disabled}"
  message-error:
    backgroundColor: "{colors.error}"
    textColor: "{colors.on-error}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.sm}"
    padding: 8px 12px
  message-success:
    backgroundColor: "{colors.success}"
    textColor: "{colors.on-success}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.sm}"
    padding: 8px 12px
  card-plan:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.title-md}"
    rounded: "{rounded.md}"
    padding: "{spacing.md}"
  card-article:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.title-md}"
    rounded: "{rounded.md}"
    padding: "{spacing.md}"
  card-testimonial:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.on-secondary}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: "{spacing.lg}"
  form-lead:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.on-secondary}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: "{spacing.xl}"
  cart-summary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: "{spacing.lg}"
  divider:
    backgroundColor: "{colors.outline}"
    height: 1px
  footer:
    backgroundColor: "{colors.inverse-surface}"
    textColor: "{colors.on-inverse-surface}"
    typography: "{typography.body-sm}"
    padding: "{spacing.2xl}"
---

# Keep-Strong — Design system

## Overview

Keep-Strong ayuda a deportistas de resistencia (running, ciclismo, triatlón y maratón), desde amateur hasta alto rendimiento, a llegar a su meta con un plan que integra **entrenamiento, descanso y alimentación**. La usuaria o usuario principal es Matías, 34 años, oficinista que prepara su primera maratón con poco tiempo, compara varias opciones desde el celular y desconfía de los consejos sueltos y contradictorios.

La interfaz debe sentirse **fuerte, directa, confiable y con aire**: cielo despejado (celeste) sobre concreto y asfalto (gris), fotografía deportiva real y titulares en Oswald, en mayúsculas solo en botones y etiquetas. Palabras clave del moodboard: fuerza, energía, confianza, equilibrio, superación. Cada pantalla debe dejar claro qué incluye un plan y cuánto cuesta, sin sorpresas.

## Colors

- **Primary (#0A6EA8, celeste profundo):** botones principales, enlaces, logo y chip de filtro activo. Hay un solo `button-primary` por sección, sin contar el de cada card de una grilla.
- **Primary hover (#085886):** estado hover y active de `button-primary`.
- **Secondary (#DCEEF9, celeste claro):** fondos de secciones destacadas, `form-lead`, `card-testimonial` y hover de chips y botones secundarios.
- **Tertiary (#5BC0F0, celeste vivo):** solo en `tag-category` y detalles como el contador del carrito. Siempre con texto `on-tertiary` (#1F2933). Nunca como color de texto ni de ícono sobre fondo claro: su contraste es 1.89:1.
- **Neutral (#F4F6F8):** fondo general de las páginas.
- **Surface (#FFFFFF):** tarjetas, campos de formulario y navbar.
- **On-surface (#1F2933):** títulos y textos. **On-surface-variant (#4B5863):** bajadas, tiempo de lectura y textos secundarios.
- **Outline (#8A949C):** bordes de campos y de `button-secondary` y líneas divisorias. Los campos de formulario van siempre sobre `surface` (contraste 3.09:1); sobre `neutral` el borde no alcanza 3:1.
- **Inverse-surface (#2F3B45, gris asfalto):** footer y bloques de contraste, con texto `on-inverse-surface` (#FFFFFF).
- **Disabled (#D5DBE0) / On-disabled (#4B5863):** elementos que no se pueden usar.
- **Success (#1B7444):** confirmaciones ("Plan agregado al carrito"). **Error (#B3261E):** errores de formulario.

Proporción aproximada: 60 % neutros, 30 % celeste claro y gris asfalto, 10 % celeste profundo y celeste vivo.

## Typography

- **Títulos, precios y botones:** Oswald (sans serif condensada).
- **Textos:** Source Sans 3. Nunca se usa Oswald en párrafos.

| Token | Uso | Desktop | Mobile | Peso |
|---|---|---|---|---|
| `headline-display` | h1 | 48px | 36px | 600 |
| `headline-lg` | h2 | 32px | 28px | 600 |
| `headline-md` | h3 | 24px | 20px | 500 |
| `title-md` | Nombre y precio en cards | 20px | 20px | 500 |
| `body-md` | Párrafos | 16px | 16px | 400 |
| `body-sm` | Textos secundarios, etiquetas y chips | 14px | 14px | 400 |
| `label-md` | Botones | 16px | 16px | 500 |

Cada página tiene un solo h1. Los párrafos no superan 75 caracteres por línea.

## Layout

- **Ancho máximo del contenido:** 1200px, centrado.
- **Márgenes laterales:** 24px en desktop y tablet, 16px en mobile.
- **Escala de espaciado:** 4, 8, 16, 24, 32, 48 y 64px (tokens `xs` a `3xl`). Separación entre secciones: 64px en desktop y 48px en mobile.
- **Breakpoints:** mobile hasta 767px, tablet de 768 a 1023px y desktop desde 1024px. Se diseña primero para mobile.

| Elemento | Mobile (hasta 767px) | Tablet (768–1023px) | Desktop (desde 1024px) |
|---|---|---|---|
| Columnas de la grilla | 4 | 8 | 12 |
| Menú | Hamburguesa, con buscador y carrito siempre visibles | Hamburguesa | Enlaces visibles: Planes, Blog, Preguntas, Contacto |
| Grilla de `card-plan` y `card-article` | 1 por fila | 2 por fila | 3 por fila |
| Filtros de la tienda | Botón "Filtros" que abre un panel a pantalla completa | Botón "Filtros" que abre un panel lateral | Columna fija de 240px a la izquierda |
| Hero | Una columna: imagen arriba, texto y botones abajo | Una columna | Dos columnas: texto a la izquierda, imagen a la derecha |
| Ficha de producto | Una columna: imagen, datos y botones | Dos columnas | Dos columnas: imagen a la izquierda, datos a la derecha |
| Carrito | Lista y luego `cart-summary` debajo | Lista y resumen apilados | Lista a la izquierda y `cart-summary` fijo a la derecha |
| `form-lead` | Campos apilados, botón de ancho completo | Campos apilados | Texto a la izquierda y campos a la derecha |
| Footer | Columnas apiladas | 2 columnas | 4 columnas |

En mobile no hay scroll horizontal (ancho mínimo soportado: 375px). Los botones y enlaces tienen un área táctil de al menos 44px de alto.

## Elevation & Depth

La jerarquía se marca con **capas de color y bordes**, no con sombras fuertes.

- Las tarjetas (`card-plan`, `card-article`, `cart-summary`) son `surface` blancas sobre el fondo `neutral`, con borde de 1px en `outline` y sin sombra.
- En hover, `card-plan` y `card-article` suben su sombra a `0 4px 12px` con 12 % de opacidad de `inverse-surface`.
- Las secciones destacadas usan fondo `secondary`; el footer usa `inverse-surface`.
- La navbar es `surface` con una línea inferior de 1px en `outline` y queda fija arriba al hacer scroll.

## Shapes

- **Botones:** radio `md` (8px). Dan una forma firme, acorde a la marca.
- **Cards, formularios y resumen del carrito:** radio `md` (8px).
- **Campos de formulario y mensajes:** radio `sm` (4px).
- **Chips y etiquetas:** radio `full` (forma de píldora).
- Las imágenes de las cards tienen las esquinas superiores con radio `md`.

## Components

### Navbar (`navbar`)

Logo "KEEP-STRONG" en Oswald a la izquierda, enlaces (Planes, Blog, Preguntas, Contacto), buscador, favoritos y carrito con contador en `tag-category`.

- Es idéntica en todas las páginas y queda fija arriba al hacer scroll.
- El carrito siempre muestra su contador cuando tiene productos.
- En mobile y tablet los enlaces pasan a un menú hamburguesa; el buscador y el carrito siguen visibles.

### Botón principal (`button-primary`)

Texto en `label-md`, fondo `primary`, texto blanco.

- Máximo un `button-primary` por sección, sin contar el botón de cada card dentro de una grilla.
- Estados: normal, hover y active (`primary-hover`) y disabled (`disabled`, con el texto "Agotado" o "No disponible").
- El texto es una acción concreta: "Ver planes", "Agregar al carrito", "Ir a pagar", "Quiero mi guía".

### Botón secundario (`button-secondary`)

Fondo blanco, texto `primary` y borde de 1px en `outline`. Se usa para acciones alternativas, como "Consultar por WhatsApp" o "Seguir viendo planes".

- Estados: normal, hover (fondo `secondary`) y disabled.
- Nunca se pone un `button-secondary` solo en una sección sin un `button-primary`.

### Chip de filtro (`chip-filter`)

Píldora con el nombre de una categoría: Todos, Entrenamiento, Alimentación, Descanso.

- Estados: normal, hover (`secondary`) y active (`chip-filter-active`, fondo `primary`).
- Solo un chip activo a la vez; "Todos" está activo por defecto.

### Etiqueta de categoría (`tag-category`)

Píldora `tertiary` con texto oscuro que indica la disciplina o categoría (Running, Ciclismo, Triatlón, Alimentación, Descanso).

- Siempre texto `on-tertiary`; nunca texto blanco sobre `tertiary`.
- Máximo una etiqueta por card.

### Campo de formulario (`input-field`)

Fondo `surface`, borde de 1px en `outline`, etiqueta visible arriba del campo.

- Estados: normal, focus (borde de 2px en `primary`), error (borde `error` y `message-error` debajo con el motivo) y disabled.
- Nunca se usa el texto de ayuda dentro del campo (placeholder) como única etiqueta.

### Card de plan (`card-plan`)

Imagen en la parte superior, `tag-category`, nombre del plan en `title-md`, nivel, estrellas de reseñas, precio y `button-primary` "Ver plan".

- El precio siempre es visible.
- El nombre ocupa máximo 2 líneas; si es más largo, termina en "…".
- La imagen tiene proporción 4:3.
- Hover: sombra suave (ver Elevation & Depth).
- Agotado: imagen en escala de grises y botón deshabilitado con el texto "No disponible".

### Card de artículo (`card-article`)

Imagen, `tag-category` de la categoría del blog, título en `title-md`, tiempo de lectura en `text-secondary` y enlace "Leer artículo".

- El título ocupa máximo 3 líneas.
- Siempre muestra el tiempo de lectura.

### Testimonio (`card-testimonial`)

Fondo `secondary`, estrellas, frase entre comillas, nombre y disciplina de quien la dio.

- Siempre indica la disciplina (Maratonista, Ciclista, Triatleta).
- Máximo 3 testimonios visibles a la vez.

### Formulario de leads (`form-lead`)

Fondo `secondary`, título con la oferta, campos de nombre, correo y disciplina, casilla de aceptación de la política de privacidad y `button-primary`.

- El botón se mantiene deshabilitado hasta marcar la casilla de privacidad.
- Al enviar, se muestra `message-success`: "Listo, te enviamos la guía a tu correo".

### Resumen del carrito (`cart-summary`)

Productos con nombre, nivel y precio, subtotal, campo de cupón, total y `button-primary` "Ir a pagar".

- El total siempre es visible sin hacer scroll en desktop.
- Bajo el botón va el texto "Recibirás tu plan por correo" y el enlace de WhatsApp.

### Divisor (`divider`)

Línea de 1px en `outline` para separar productos del carrito y bloques de contenido.

### Footer (`footer`)

Fondo `inverse-surface`, logo, enlaces a Contacto, Preguntas frecuentes, Términos y condiciones y Política de privacidad, y redes sociales.

- Es idéntico en todas las páginas.
- Los enlaces son blancos y, en hover, `secondary`.

## Do's and Don'ts

**Do**

- Usa Oswald solo en títulos, precios y botones; Source Sans 3 en todos los textos.
- Muestra siempre el precio y el nivel del plan en las cards.
- Usa `tag-category` con texto oscuro y deja el celeste vivo para detalles.
- Pon los campos de formulario sobre fondo blanco.
- Usa fotografías reales de deportistas, con cielo y pavimento, y deja mucho espacio en blanco.
- Verifica un contraste mínimo AA (4.5:1) en todo texto.

**Don't**

- No uses el celeste vivo (`tertiary`) como color de texto ni con texto blanco encima.
- No pongas más de un `button-primary` por sección (los botones de las cards de una grilla son la excepción).
- No uses Oswald en párrafos.
- No agregues colores fuera de esta paleta (por ejemplo, naranja o verde como acento).
- No uses sombras fuertes ni degradados.
- No pongas campos de formulario sobre el fondo `neutral`: su borde no alcanza el contraste mínimo.
- No uses el placeholder como única etiqueta de un campo.
