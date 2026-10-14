# Arquitectura de la información — stayHard

> Guía: [Arquitectura de la información](../evaluacion/guias/fase-1-requerimientos/05-arquitectura.md)

## Mapa de sitio

<!-- Incluye landing, blog, tienda y las páginas obligatorias:
contacto, preguntas frecuentes, términos, privacidad y 404. -->

```text
Inicio (landing)
├── Tienda
│   ├── Planes por disciplina
│   │   ├── Running
│   │   ├── Fútbol
│   │   ├── Ciclismo
│   │   ├── Fuerza y gimnasio
│   │   ├── Deportes de combate
│   │   └── Funcional y CrossFit
│   ├── Detalle del plan
│   ├── Carrito
│   └── Checkout (datos y formulario de diagnóstico)
├── Blog
│   ├── Categorías del blog
│   └── Artículo
├── Cómo funciona
├── Testimonios y resultados
├── Contacto
├── Preguntas frecuentes
├── Términos y condiciones
├── Política de privacidad
└── Página 404
```

## User flows

> Guía: [User flow](../evaluacion/guias/fase-1-requerimientos/06-user-flow.md)

### Flujo 1: compra

```text
Inicio (landing)
   ↓
Clic en "Ver planes" → Tienda
   ↓
Filtrar por disciplina, nivel y duración
   ↓
Seleccionar un plan → Detalle del plan
   ↓
Elegir nivel, duración y seguimiento → Agregar al carrito
   ↓
Carrito (revisar el plan y el total)
   ↓
Checkout: completar datos y formulario de diagnóstico
   ↓
Pago
   ↓
Confirmación de compra (resumen y próximos pasos)
   ↓
Recepción del plan personalizado por correo o WhatsApp
```

### Flujo 2: contenido

```text
Inicio (landing) o buscador
   ↓
Clic en "Blog"
   ↓
Elegir categoría (por ejemplo, Running)
   ↓
Leer un artículo
   ↓
Comentar o compartir en redes sociales
   ↓
Clic en el plan relacionado (llamado a la acción al final del artículo)
   ↓
Detalle del plan → inicia el Flujo 1 (compra)
```

## Categorías

> Guía: [Categorías de productos y temas del blog](../evaluacion/guias/fase-1-requerimientos/07-categorias.md)

### Categorías de productos

| Categoría | Productos |
|---|---|
| Running | Plan 5K y 10K, plan media maratón, plan maratón |
| Fútbol | Plan de preparación física para fútbol amateur, plan de pretemporada, plan de resistencia y velocidad |
| Ciclismo | Plan de ruta y resistencia, plan de ciclismo de montaña |
| Fuerza y gimnasio | Plan de hipertrofia, plan de fuerza, plan de rendimiento general |
| Deportes de combate | Plan de acondicionamiento para boxeo, MMA y artes marciales |
| Funcional y CrossFit | Plan de entrenamiento funcional, plan de preparación para competencias |

### Categorías del blog

| Categoría | Idea de artículo | Necesidad o motivación de la proto-persona | Producto relacionado |
|---|---|---|---|
| Running | Cómo preparar tu primera media maratón en 12 semanas | Camila quiere terminar su primera media maratón y bajar su marca. | Plan media maratón |
| Prevención de lesiones | 5 errores que te pueden lesionar al aumentar tu carga de entrenamiento | Camila teme lesionarse por no saber cómo progresar. | Plan media maratón |
| Fútbol | Cómo mejorar tu resistencia para rendir los 90 minutos | Diego quiere rendir más en los partidos. | Plan de preparación física para fútbol |
| Fuerza y gimnasio | Por qué copiar rutinas de redes sociales no siempre funciona | Diego entrena sin método y no sabe si le sirve. | Plan de rendimiento general |
| Planificación | Cómo organizar tu semana de entrenamiento si trabajas o estudias | Camila y Diego tienen poco tiempo disponible. | Todos los planes |
| Nutrición y recuperación | Qué comer y cómo descansar para rendir mejor | Camila y Diego quieren mejorar su rendimiento de forma segura. | Planes con seguimiento |
