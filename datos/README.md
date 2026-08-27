# Datos del proyecto

## Dataset utilizado

El presente proyecto utiliza el dataset público **Peruvian Food Reviews**, que contiene información sobre establecimientos gastronómicos peruanos y reseñas publicadas por usuarios en plataformas digitales.

Los archivos originales no se almacenan directamente en este repositorio debido a su tamaño.

## Fuente de los datos

**Dataset:** Peruvian Food Reviews  
**Plataforma:** Kaggle
**URL:** [Peruvian Food Reviews - Kaggle](https://www.kaggle.com/datasets/lazaro97/peruvian-food-reviews)

## Datos utilizados

El proyecto trabaja principalmente con información correspondiente a:

- Restaurantes y sus características.
- Reseñas realizadas por los usuarios.
- Puntuaciones asociadas a las reseñas.
- Información de ubicación y categoría de los establecimientos.
- Variables complementarias disponibles en la fuente original.

Después de los procesos de preparación y control de calidad se obtuvieron:

- **569.877 reseñas con texto válido.**
- **569.102 reseñas utilizadas para el modelado.**
- **9.871 restaurantes en el conjunto original de establecimientos.**
- **8.913 restaurantes disponibles para el sistema de recomendación.**

## Reproducción del proyecto

Para reproducir el análisis, los archivos correspondientes al dataset deben obtenerse desde la fuente original y cargarse en el entorno de ejecución siguiendo las rutas definidas en el notebook principal.

El código completo del procesamiento puede consultarse en la carpeta `cuadernos/` del repositorio.

## Nota

Los datos originales no han sido modificados ni redistribuidos mediante este repositorio. Las transformaciones, variables derivadas, análisis y resultados presentados corresponden al desarrollo realizado durante el Trabajo Fin de Máster.
