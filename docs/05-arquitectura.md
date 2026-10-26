# Arquitectura de la información — Keep-Strong

> Guía: [Arquitectura de la información](../evaluacion/guias/fase-1-requerimientos/05-arquitectura.md)

## Mapa de sitio

```text
Inicio (landing)
├── Tienda
│   ├── Planes para correr
│   │   ├── Plan 10K
│   │   ├── Plan media maratón
│   │   └── Plan maratón
│   ├── Planes para ciclismo
│   ├── Planes para triatlón
│   ├── Alimentación para deportistas
│   ├── Descanso y recuperación
│   ├── Ficha de producto (plan)
│   └── Carrito
├── Blog
│   ├── Entrenamiento
│   ├── Alimentación
│   ├── Descanso y recuperación
│   ├── Competencias
│   └── Artículo
├── Contacto
├── Preguntas frecuentes
├── Términos y condiciones
├── Política de privacidad
└── Página 404
```

## User flows

> Guía: [User flow](../evaluacion/guias/fase-1-requerimientos/06-user-flow.md)

Los dos flujos son los de **Matías**, nuestro corredor amateur que prepara su primera maratón.

### Flujo 1: compra

```text
Instagram (cuenta de Keep-Strong)
→ Inicio (landing)
→ [Ver planes]
→ Tienda
→ Filtra por disciplina "Running" y nivel "Principiante", o busca "maratón"
→ Ficha de producto (Plan maratón)
→ Lee qué incluye y las reseñas de otros corredores
→ ¿Le quedan dudas?
     ├─ Sí → [Consultar por WhatsApp] → vuelve a la ficha de producto
     └─ No → Elige la variante (duración y nivel)
→ [Agregar al carrito]
→ Carrito
```

### Flujo 2: contenido

```text
Búsqueda en Google: "qué comer antes de una maratón"
→ Blog
→ Categoría "Alimentación"
→ Artículo "Qué comer la semana antes de tu primera maratón"
→ Lee el artículo y lo comparte o lo comenta
→ [Ver el plan de alimentación recomendado]
→ Ficha de producto (Plan de alimentación para maratón)
→ ¿Quiere más información antes de comprar?
     ├─ Sí → Contacto (formulario o WhatsApp)
     └─ No → [Agregar al carrito] → Carrito
```

## Categorías

> Guía: [Categorías de productos y temas del blog](../evaluacion/guias/fase-1-requerimientos/07-categorias.md)

### Categorías de productos

Nombradas como las buscaría Matías, no como se organizan internamente.

| Categoría | Productos |
|---|---|
| Planes para correr | Plan 10K, Plan media maratón, Plan maratón (para principiantes y para quienes quieren mejorar su marca) |
| Planes para ciclismo | Plan ciclismo de ruta para principiantes, Plan ciclismo de fondo, Plan para mejorar rendimiento en pendientes |
| Planes para triatlón | Plan triatlón sprint, Plan triatlón olímpico, Plan media distancia |
| Alimentación para deportistas | Plan de alimentación para entrenar, Plan de alimentación para el día de la carrera, Plan de alimentación para recuperarse |
| Descanso y recuperación | Pauta de sueño para deportistas, Plan de recuperación activa, Guía para semanas de descarga |

### Categorías del blog

| Categoría | Idea de artículo | Necesidad o motivación de la proto-persona | Producto relacionado |
|---|---|---|---|
| Entrenamiento | "Cómo organizar tus semanas para preparar tu primera maratón" | Necesita un plan claro que se adapte al poco tiempo que tiene para entrenar. | Plan maratón |
| Alimentación | "Qué comer la semana antes de tu primera maratón" | Está confundido por consejos contradictorios y quiere comer bien para rendir y no tener problemas el día de la carrera. | Plan de alimentación para el día de la carrera |
| Descanso y recuperación | "Cuántos días de descanso necesitas a la semana si entrenas para correr" | Quiere llegar a la meta sin lesionarse ni sobreentrenar. | Pauta de sueño para deportistas |
| Competencias | "Checklist para el día de tu primera carrera: qué llevar y qué evitar" | Busca llegar a su primera maratón con confianza y sin errores de principiante. | Plan maratón |
