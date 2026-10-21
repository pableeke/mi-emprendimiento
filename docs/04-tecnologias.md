# Tecnologías del proyecto — Keep-Strong

> Guía: [Tecnologías del proyecto](../evaluacion/guias/fase-1-requerimientos/04-tecnologias.md)

## Stack

| Área | Herramienta | Para qué la uso |
|---|---|---|
| Construcción | HTML + CSS | Construir las páginas de la landing, el blog y la tienda de Keep-Strong sin frameworks ni gestor de contenido, para entender y controlar cada parte del sitio. |
| Versionado | Git y GitHub | Guardar el historial de documentos y código del proyecto, y mostrar el avance con commits descriptivos. |
| Publicación | GitHub Pages | Publicar el sitio de forma gratuita para que Matías y cualquier deportista pueda visitarlo desde el celular. |
| Diseño | Whimsical | Armar el moodboard, calcar componentes de sitios de referencia y dibujar los wireframes de cada pantalla. |
| Diseño | Google Stitch | Generar el prototipo referencial de las 6 pantallas (landing, tienda, ficha de plan, carrito, blog y artículo) en desktop y mobile a partir del `DESIGN.md`. |
| IA | Claude | Redactar borradores de los documentos, revisar la coherencia entre ellos y ayudar a escribir las specs; las decisiones las tomo yo. |
| Editor | Por confirmar | Editar los archivos Markdown y, más adelante, el HTML y CSS del sitio. |

## Qué es funcional y qué es prototipo

| Funcionalidad | Estado en esta versión |
|---|---|
| Navegar entre landing, blog y tienda | Funcional |
| Navegar artículos por categoría | Funcional |
| Buscar y filtrar planes en la tienda | Prototipo visual |
| Ver detalle de un plan y agregarlo al carrito | Prototipo visual |
| Pagar el carrito | Prototipo visual |
| Dejar datos en la landing / suscribirse al newsletter | Prototipo visual |
| Comentar un artículo | Prototipo visual |
| Compartir un artículo en redes | Funcional (enlaces a redes) |
| Consultar por WhatsApp | Funcional (enlace directo) |
| Cuestionario de recomendación de plan | Prototipo visual |
| Reseñas y favoritos | Prototipo visual |

## Integraciones para una versión real

- **Pasarela de pago** (por ejemplo, Webpay o Mercado Pago) para cobrar los planes online.
- **Entrega digital automática:** envío del plan en PDF o acceso a una plataforma privada después del pago.
- **Servicio de correo / newsletter** (por ejemplo, Mailchimp) para captar leads y enviar contenido.
- **Base de datos o servicio de comentarios** para guardar los comentarios del blog y las reseñas.
- **WhatsApp Business** para atender consultas antes de comprar.
- **Buscador y filtros dinámicos** que necesitan JavaScript o un backend, fuera de lo que se construye solo con HTML + CSS.

## Restricciones

- **Plazo:** el prototipo referencial se entrega dentro de los plazos de la Evaluación Parcial 02; el paso a código viene en la siguiente etapa del curso.
- **Marca:** el sitio debe transmitir fortaleza, confianza y cercanía con el deportista, tanto amateur como de alto rendimiento.
- **Dispositivos:** diseño pensado primero para celular (donde compra Matías) y adaptado a tablet y desktop.
