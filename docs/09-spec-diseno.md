# Spec de diseño — stayHard

> Guía: [Spec de diseño](../evaluacion/guias/fase-2-specs/06-spec-de-diseno.md)

La spec de diseño tiene dos partes:

1. **[`DESIGN.md`](../DESIGN.md)** (en la raíz): tu design system, en el formato que Stitch importa.
2. **Este documento:** tus pantallas, escritas como prompts listos para pegar en Stitch.

**Wireframes en Whimsical:** [pega aquí el link]

> Guía de wireframes: [Wireframes](../evaluacion/guias/fase-2-specs/04-wireframes.md)

<!-- Captura de los wireframes: ![Wireframes](img/wireframes.png) -->

<!-- Los precios, nombres de planes, testimonios y el número de WhatsApp son de ejemplo:
reemplázalos por los tuyos antes de pegar los prompts en Stitch. -->

## Pantallas

<!-- Un prompt por pantalla. Cada uno con: pantalla y dispositivo, objetivo
de tu proto-persona, componentes de arriba hacia abajo (con los nombres de
tu DESIGN.md) y textos y datos reales. -->

### 1. Landing

```text
Pantalla: Landing de stayHard, versión desktop. Usa el design system del proyecto.
Objetivo: que Camila (28 años, corredora amateur) y Diego (22 años, futbolista universitario) entiendan en segundos que stayHard crea planes de entrenamiento 100% personalizados para su deporte, y que den el primer paso: ver los planes o dejar su correo.
Componentes, de arriba hacia abajo:
1. Navbar: logo "stayHard", enlaces "Tienda", "Blog", "Cómo funciona", "Contacto", ícono de carrito y button-primary "Pedir mi plan".
2. Hero (section-dark): h1 "ENTRENA PARA TU DEPORTE, NO PARA EL PROMEDIO". Subtítulo: "Planes de entrenamiento 100% personalizados según tu nivel, tu meta y el tiempo que tienes." button-primary "Ver planes" y button-secondary "Cómo funciona". A la derecha, foto de un corredor amateur al amanecer.
3. Sección "Elige tu disciplina": h2 "TU DISCIPLINA, TU PLAN" y 6 tarjetas con ícono y nombre: Running, Fútbol, Ciclismo, Fuerza y gimnasio, Deportes de combate, Funcional y CrossFit.
4. Sección "Cómo funciona" (section-dark): h2 "CÓMO FUNCIONA" y 4 pasos numerados con números en lima: 1. Cuéntanos tu meta (completas un diagnóstico de 3 minutos), 2. Diseñamos tu plan (a medida de tu nivel y tu agenda), 3. Recibes tu plan (por correo o WhatsApp en 48 horas), 4. Ajustamos contigo (el plan evoluciona a medida que avanzas).
5. Sección "Planes destacados": h2 "PLANES MÁS ELEGIDOS" y 3 card-product: "Plan 10K Running" (tag-level Principiante, 8 semanas, $29.990), "Plan Media Maratón" (tag-level Intermedio, 12 semanas, $39.990) y "Plan Fútbol Amateur" (tag-level Intermedio, 8 semanas, $34.990), cada una con button-primary "Ver plan". Debajo, button-secondary "Ver todos los planes".
6. Sección de testimonios: h2 "LO QUE LOGRARON" y 3 card-testimonial: Valentina, corredora, "Bajé 8 minutos mi marca en 10K en 8 semanas"; Matías, futbolista amateur, "Aguanto los 90 minutos sin quedarme sin aire"; Javiera, ciclista, "Por fin entreno con un plan que cabe en mi semana".
7. Sección de suscripción: h2 "RECIBE CONSEJOS DE ENTRENAMIENTO", input-field de correo con etiqueta visible y button-primary "Suscribirme".
8. Footer con enlaces a Contacto, Preguntas frecuentes, Términos y Privacidad, y redes sociales.
9. button-whatsapp flotante "Escríbenos" en la esquina inferior derecha.
```

### 2. Tienda

```text
Pantalla: Tienda de stayHard, versión desktop. Usa el design system del proyecto.
Objetivo: que Camila y Diego encuentren rápido el plan correcto para su disciplina, su nivel y su presupuesto, y puedan compararlos de un vistazo.
Componentes, de arriba hacia abajo:
1. Navbar.
2. Encabezado de página: h1 "PLANES DE ENTRENAMIENTO" y texto "Elige tu disciplina y tu nivel. Cada plan se personaliza según tus datos."
3. Barra de búsqueda: input-field con etiqueta "Buscar plan" y placeholder "Ej: media maratón".
4. Barra lateral de filtros a la izquierda, con chip-filter para: Disciplina (Running, Fútbol, Ciclismo, Fuerza y gimnasio, Deportes de combate, Funcional y CrossFit), Nivel (Principiante, Intermedio, Avanzado), Duración (4, 8 y 12 semanas) y Precio (hasta $30.000, $30.000 a $40.000, más de $40.000). Un chip-filter-active de ejemplo en "Running" y un enlace "Limpiar filtros".
5. Grilla de 8 card-product en 3 columnas, con imagen, tag-level, nombre, duración, precio y button-primary "Ver plan": "Plan 10K Running" ($29.990), "Plan Media Maratón" ($39.990), "Plan Maratón" ($49.990), "Plan Fútbol Amateur" ($34.990), "Plan Pretemporada Fútbol" ($29.990), "Plan Ciclismo de Ruta" ($39.990), "Plan Hipertrofia" ($34.990) y "Plan Funcional" ($29.990).
6. Texto de resultados "Mostrando 8 planes".
7. Footer.
8. button-whatsapp flotante.
```

### 3. Ficha de producto

```text
Pantalla: Ficha de producto de stayHard (Plan Media Maratón), versión desktop. Usa el design system del proyecto.
Objetivo: que Camila entienda qué incluye el plan, elija nivel, duración y seguimiento, vea cuánto cuesta y lo agregue al carrito con confianza.
Componentes, de arriba hacia abajo:
1. Navbar.
2. Breadcrumb: Inicio > Tienda > Running > Plan Media Maratón.
3. Dos columnas. Izquierda: imagen grande de una corredora entrenando. Derecha: tag-level "Intermedio", h1 "PLAN MEDIA MARATÓN", descripción corta "Prepara tus 21K con un plan hecho a la medida de tu nivel actual, tu fecha de carrera y los días que puedes entrenar", y precio "$39.990".
4. Selector del plan con tres grupos de chip-filter: Nivel (Principiante, Intermedio, Avanzado), Duración (8, 10 y 12 semanas) y Seguimiento ("Solo el plan" o "Plan + seguimiento semanal por WhatsApp"). Un precio total visible debajo.
5. button-primary "Agregar al carrito" y button-secondary "Ver ejemplo de una semana".
6. Sección "Qué incluye": lista con íconos: plan semanal con sesiones día por día, ritmos y zonas de esfuerzo, calentamiento y fuerza complementaria, ajustes según tu progreso, y entrega en PDF.
7. Sección "Ejemplo de una semana": tabla de 7 días con la sesión de cada uno (por ejemplo, Lunes: descanso, Martes: 6 x 400 m, Miércoles: fuerza, Jueves: rodaje suave 8 km, Viernes: descanso, Sábado: tempo 10 km, Domingo: fondo 14 km).
8. Sección "Preguntas frecuentes" con 3 acordeones: "¿Cuándo recibo mi plan?", "¿Puedo cambiarlo si me lesiono o cambia mi agenda?" y "¿Necesito reloj deportivo?".
9. Sección "Planes relacionados": 3 card-product.
10. Footer.
11. button-whatsapp flotante.
```

### 4. Carrito

```text
Pantalla: Carrito de stayHard, versión desktop. Usa el design system del proyecto.
Objetivo: que Camila revise su plan, complete el formulario de diagnóstico para personalizarlo y continúe al pago sin dudas.
Componentes, de arriba hacia abajo:
1. Navbar.
2. h1 "TU CARRITO" y un indicador de pasos: 1. Carrito, 2. Tus datos, 3. Pago.
3. Dos columnas. Izquierda: lista del producto (imagen pequeña, "Plan Media Maratón", Nivel Intermedio, 12 semanas, Plan + seguimiento semanal por WhatsApp, precio "$59.990") con enlace "Quitar". Debajo, h2 "CUÉNTANOS SOBRE TI" con un formulario de diagnóstico con input-field y etiqueta visible en cada campo: nombre, correo, WhatsApp, deporte (selector), nivel actual (selector), meta (texto, por ejemplo "Terminar mi primera media maratón"), fecha de la meta (opcional), días disponibles por semana (selector de 2 a 7) y equipamiento disponible. Un ejemplo de message-error bajo el campo de correo: "Ingresa un correo válido".
4. Derecha: tarjeta "Resumen del pedido" con subtotal, total "$59.990", button-primary "Continuar al pago" y button-secondary "Seguir comprando". Debajo, nota "Recibirás tu plan personalizado en máximo 48 horas".
5. Footer.
6. button-whatsapp flotante.
```

### 5. Blog

```text
Pantalla: Blog de stayHard, versión desktop. Usa el design system del proyecto.
Objetivo: que Camila y Diego encuentren consejos de entrenamiento por tema y lleguen al plan relacionado.
Componentes, de arriba hacia abajo:
1. Navbar.
2. Encabezado: h1 "BLOG DE ENTRENAMIENTO" y texto "Consejos para entrenar mejor, evitar lesiones y rendir más."
3. Fila de chip-filter por categoría: Todos, Running, Fútbol, Fuerza y gimnasio, Prevención de lesiones, Planificación, Nutrición y recuperación. "Todos" como chip-filter-active.
4. Artículo destacado grande en dos columnas: imagen a la izquierda y a la derecha etiqueta, título "Cómo preparar tu primera media maratón en 12 semanas", extracto y button-primary "Leer artículo".
5. Grilla de 6 card-article en 3 columnas: "5 errores que te pueden lesionar al aumentar tu carga de entrenamiento" (Prevención de lesiones), "Cómo mejorar tu resistencia para rendir los 90 minutos" (Fútbol), "Por qué copiar rutinas de redes sociales no siempre funciona" (Fuerza y gimnasio), "Cómo organizar tu semana de entrenamiento si trabajas o estudias" (Planificación), "Qué comer y cómo descansar para rendir mejor" (Nutrición y recuperación) y "Cómo elegir tu ritmo en tu primer 10K" (Running).
6. Sección de suscripción: input-field de correo y button-primary "Suscribirme".
7. Footer.
8. button-whatsapp flotante.
```

### 6. Artículo

```text
Pantalla: Artículo del blog de stayHard, versión desktop. Usa el design system del proyecto.
Objetivo: que Camila lea un artículo útil, lo comparta o comente, y llegue al plan relacionado.
Componentes, de arriba hacia abajo:
1. Navbar.
2. Breadcrumb: Inicio > Blog > Running.
3. Columna central de lectura (máximo 720 px): tag-level "Running", h1 "CÓMO PREPARAR TU PRIMERA MEDIA MARATÓN EN 12 SEMANAS", datos del autor y la fecha, tiempo de lectura "6 min" y una imagen principal.
4. Cuerpo del artículo con h2, h3, párrafos y una lista numerada con las fases del entrenamiento (base, desarrollo, afinación y carrera).
5. Fila "Compartir": button-secondary con WhatsApp, Facebook y X.
6. Tarjeta de llamado a la acción (card-product): "¿Quieres un plan a tu medida? Plan Media Maratón, desde $39.990" con button-primary "Ver plan".
7. Sección "Comentarios": formulario con input-field de nombre y comentario y button-primary "Publicar comentario", y 2 comentarios de ejemplo.
8. Sección "Artículos relacionados": 3 card-article.
9. Footer.
10. button-whatsapp flotante.
```

### Versión mobile (para cada pantalla)

```text
Genera la versión mobile (375px de ancho) de esta pantalla siguiendo la
sección Layout del design system: una sola columna con márgenes de 16 px, navbar colapsado en logo, ícono de carrito y menú hamburguesa, títulos en 40 px (h1), 30 px (h2) y 22 px (h3), botones a todo el ancho, imágenes en proporción 16:9, secciones separadas por 48 px y button-whatsapp fijo en la esquina inferior derecha mostrando solo el ícono.
Adaptaciones por pantalla:
- Landing: las 6 disciplinas en 2 columnas, los pasos de "Cómo funciona" apilados y los planes y testimonios en una columna.
- Tienda: los filtros pasan a un botón "Filtros" que abre un panel desplegable sobre el catálogo, y las card-product van en una columna.
- Ficha de producto: la imagen va arriba del título, los selectores se apilan y el botón "Agregar al carrito" queda fijo en la parte inferior de la pantalla.
- Carrito: el resumen del pedido va arriba del formulario y el botón "Continuar al pago" ocupa todo el ancho.
- Blog: los chips de categoría se desplazan en horizontal y las card-article van en una columna.
- Artículo: el texto ocupa todo el ancho útil y los botones de compartir van en una fila.
```
