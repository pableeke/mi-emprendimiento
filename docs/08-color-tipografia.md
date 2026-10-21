# Color y tipografía — Keep-Strong

> Guía: [Color y tipografía](../evaluacion/guias/fase-2-specs/05-color-y-tipografia.md)

## Paleta

Celeste con gris, tal como se definió en el [moodboard](06-moodboard.md): el celeste del cielo despejado y el gris del concreto y el asfalto.

| Rol | Color | HEX | Uso |
|---|---|---|---|
| Principal | Celeste profundo | `#0A6EA8` | Botones principales, enlaces, logo y elementos destacados |
| Principal (hover) | Celeste más oscuro | `#085886` | Botones principales al pasar el cursor o presionar |
| Secundario | Celeste claro | `#DCEEF9` | Fondos de secciones, tarjetas de plan, chips seleccionados |
| Acento | Celeste vivo | `#5BC0F0` | Etiquetas, contador del carrito y detalles. Siempre con texto oscuro; no se usa como color de texto sobre claro |
| Fondo | Gris nube | `#F4F6F8` | Fondo general de las páginas |
| Superficie | Blanco | `#FFFFFF` | Campos de formulario y tarjetas |
| Texto | Gris carbón | `#1F2933` | Títulos y textos |
| Texto suave | Gris pizarra | `#4B5863` | Bajadas, tiempo de lectura y textos secundarios |
| Borde | Gris acero | `#8A949C` | Bordes de campos de formulario y de botones secundarios |
| Fondo oscuro | Gris asfalto | `#2F3B45` | Footer y bloques de contraste |
| Deshabilitado | Gris claro | `#D5DBE0` | Fondo de botones deshabilitados (texto `#4B5863`) |
| Éxito | Verde | `#1B7444` | Mensajes de confirmación (por ejemplo, "Plan agregado al carrito") |
| Error | Rojo ladrillo | `#B3261E` | Errores de formulario |

Regla 60-30-10: 60 % neutros (fondo, blanco y texto), 30 % celeste claro y gris asfalto, 10 % celeste profundo y celeste vivo.

## Contraste

Calculado con la fórmula de contraste de WCAG 2.1.

| Combinación | Ratio | Resultado |
|---|---|---|
| Texto `#1F2933` sobre fondo `#F4F6F8` | 13.62:1 | AA ✅ |
| Texto `#1F2933` sobre blanco `#FFFFFF` | 14.76:1 | AA ✅ |
| Texto `#1F2933` sobre secundario `#DCEEF9` | 12.39:1 | AA ✅ |
| Texto suave `#4B5863` sobre fondo `#F4F6F8` | 6.74:1 | AA ✅ |
| Texto suave `#4B5863` sobre blanco | 7.30:1 | AA ✅ |
| Texto suave `#4B5863` sobre secundario `#DCEEF9` | 6.14:1 | AA ✅ |
| Texto blanco sobre principal `#0A6EA8` (botón) | 5.51:1 | AA ✅ |
| Texto blanco sobre principal hover `#085886` | 7.64:1 | AA ✅ |
| Enlace principal `#0A6EA8` sobre fondo `#F4F6F8` | 5.09:1 | AA ✅ |
| Principal `#0A6EA8` sobre secundario `#DCEEF9` | 4.63:1 | AA ✅ |
| Texto `#1F2933` sobre acento `#5BC0F0` (etiquetas) | 7.20:1 | AA ✅ |
| Acento `#5BC0F0` como texto sobre fondo `#F4F6F8` | 1.89:1 | No alcanza AA ❌ (solo detalles, nunca texto) |
| Texto blanco sobre gris asfalto `#2F3B45` (footer) | 11.46:1 | AA ✅ |
| Celeste claro `#DCEEF9` sobre gris asfalto `#2F3B45` (enlaces del footer) | 9.63:1 | AA ✅ |
| Texto `#4B5863` sobre deshabilitado `#D5DBE0` | 5.23:1 | AA ✅ |
| Texto blanco sobre éxito `#1B7444` | 5.79:1 | AA ✅ |
| Texto blanco sobre error `#B3261E` | 6.54:1 | AA ✅ |
| Error `#B3261E` sobre blanco | 6.54:1 | AA ✅ |
| Borde `#8A949C` sobre blanco (campos de formulario) | 3.09:1 | Cumple 3:1 para componentes de interfaz ✅ |
| Borde `#8A949C` sobre fondo `#F4F6F8` | 2.85:1 | No alcanza 3:1 ⚠️ (por eso los campos van sobre blanco) |

El celeste vivo `#5BC0F0` no alcanza contraste como texto ni con texto blanco encima, así que se usa solo como fondo de etiquetas con texto oscuro y como detalle. Por la misma razón el color principal es un celeste profundo y no uno claro.

## Tipografía

- **Títulos y botones:** [Oswald](https://fonts.google.com/specimen/Oswald) (sans serif condensada, fuerte y deportiva).
- **Textos:** [Source Sans 3](https://fonts.google.com/specimen/Source+Sans+3) (sans serif muy legible en párrafos y en pantallas pequeñas).

| Elemento | Fuente | Desktop | Mobile | Peso |
|---|---|---|---|---|
| h1 | Oswald | 3rem | 2.25rem | 600 |
| h2 | Oswald | 2rem | 1.75rem | 600 |
| h3 | Oswald | 1.5rem | 1.25rem | 500 |
| Párrafo | Source Sans 3 | 1rem | 1rem | 400 |
| Botón | Oswald | 1rem | 1rem | 500 |

## Justificación

El celeste sale del cielo despejado de las fotos del moodboard y representa energía, frescura y descanso; el gris viene del concreto y el asfalto donde entrena Matías y aporta seriedad y confianza. Juntos transmiten las palabras clave de la marca: fuerza, energía, confianza, equilibrio y superación. Oswald, condensada y de trazo firme, da a los títulos y botones la fuerza de una marca deportiva y deja mucho espacio para el contenido. Como Oswald cansa en párrafos largos, los textos usan Source Sans 3, que Matías puede leer sin esfuerzo en su celular cuando compara planes o lee un artículo sobre alimentación.
