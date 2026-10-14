# Color y tipografía — stayHard

> Guía: [Color y tipografía](../evaluacion/guias/fase-2-specs/05-color-y-tipografia.md)

## Paleta

| Rol | Color | HEX | Uso |
|---|---|---|---|
| Principal | Naranja energía | `#C2410C` | Botones principales, enlaces y detalles de marca. Hover: `#9A3412`. |
| Secundario | Azul noche | `#0F172A` | Navbar, hero, secciones oscuras y footer. También es el color del texto principal. |
| Acento | Lima | `#C6F135` | Etiquetas de nivel y de categoría, y destacados sobre fondos oscuros. Nunca como color de texto sobre fondo claro. |
| Fondo | Gris azulado muy claro | `#F8FAFC` | Fondo de página. Las tarjetas y formularios usan blanco `#FFFFFF`. |
| Texto | Azul noche | `#0F172A` | Títulos y párrafos. El texto secundario usa `#475569`. |
| Éxito | Verde | `#15803D` | Confirmaciones y botón de WhatsApp. |
| Error | Rojo | `#B3261E` | Mensajes de error en formularios. |

## Contraste

Ratios calculados con la fórmula de luminancia relativa de WCAG 2.1. El mínimo exigido es 4,5:1 para texto normal y 3:1 para bordes de componentes.

| Combinación | Ratio | Resultado |
|---|---|---|
| Texto blanco sobre naranja `#C2410C` (botón principal) | 5,18:1 | Cumple AA |
| Texto blanco sobre naranja oscuro `#9A3412` (hover) | 7,31:1 | Cumple AAA |
| Texto blanco sobre azul noche `#0F172A` (navbar, hero, footer) | 17,85:1 | Cumple AAA |
| Texto azul noche `#0F172A` sobre lima `#C6F135` (etiquetas) | 13,63:1 | Cumple AAA |
| Texto azul noche `#0F172A` sobre fondo `#F8FAFC` | 17,06:1 | Cumple AAA |
| Texto secundario `#475569` sobre fondo `#F8FAFC` | 7,24:1 | Cumple AAA |
| Texto secundario `#475569` sobre blanco `#FFFFFF` | 7,58:1 | Cumple AAA |
| Enlaces naranja `#C2410C` sobre fondo `#F8FAFC` | 4,95:1 | Cumple AA |
| Texto gris claro `#CBD5E1` sobre azul noche `#0F172A` (texto secundario en secciones oscuras) | 12,02:1 | Cumple AAA |
| Texto `#334155` sobre botón deshabilitado `#CBD5E1` | 6,97:1 | Cumple AA |
| Error `#B3261E` sobre blanco `#FFFFFF` | 6,54:1 | Cumple AA |
| Texto blanco sobre verde `#15803D` (botón de WhatsApp) | 5,02:1 | Cumple AA |
| Borde de inputs `#64748B` sobre blanco `#FFFFFF` | 4,76:1 | Cumple (mínimo 3:1 para componentes) |
| Naranja `#C2410C` sobre azul noche `#0F172A` | 3,45:1 | No cumple para texto: no se usa texto naranja sobre fondo oscuro |

## Tipografía

- **Títulos:** Barlow Condensed (Google Fonts), peso 700, en mayúsculas para h1 y h2.
- **Textos:** Inter (Google Fonts), pesos 400 y 600.

| Elemento | Desktop | Mobile | Peso |
|---|---|---|---|
| h1 | 56 px | 40 px | 700 |
| h2 | 40 px | 30 px | 700 |
| h3 | 28 px | 22 px | 700 |
| Párrafo | 16 px | 16 px | 400 |
| Botón | 16 px | 16 px | 600 |

## Justificación

**Color:** el azul noche aporta seriedad y fuerza, y da un contraste muy alto para leer. El naranja se reserva para las acciones (botones y enlaces) porque transmite energía y llama la atención sin competir con el resto de la interfaz. El lima funciona como acento deportivo, pero solo sobre fondos oscuros o dentro de etiquetas con texto oscuro, donde se lee bien. Todas las combinaciones de texto cumplen el mínimo AA, y la única combinación que no cumple (naranja sobre azul noche) se documenta para evitarla.

**Tipografía:** Barlow Condensed es una fuente condensada de aire deportivo, con mucha presencia en títulos. Inter es muy legible en pantallas pequeñas, lo que importa porque Camila y Diego navegan sobre todo desde el celular. Ambas son gratuitas y se cargan desde Google Fonts, y la combinación de títulos fuertes con textos neutros mantiene el sitio ordenado.
