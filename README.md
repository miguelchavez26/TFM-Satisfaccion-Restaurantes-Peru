# TFM-Satisfaccion-Restaurantes-Peru
Análisis de satisfacción de clientes de restaurantes peruanos mediante NLP, Machine Learning, análisis de aspectos y sistema de recomendación

---

## Acceso rápido al proyecto

Los principales componentes del Trabajo Fin de Máster pueden consultarse en los siguientes apartados:

- 📓 **[Notebook principal](cuadernos/)**  
  Contiene el código completo utilizado para el procesamiento de datos, análisis exploratorio, NLP, modelización, análisis de aspectos, recomendador y dashboard.

- 🌐 **[Versión HTML](html/)**  
  Contiene la versión ejecutada y estática del notebook, incluyendo resultados, gráficos, análisis y ejemplos de las aplicaciones desarrolladas.

- 📄 **[Informe final](documentación/)**  
  Contiene el documento final del Trabajo Fin de Máster con la metodología, resultados, interpretación de negocio y conclusiones.

- 📊 **[Datos](datos/)**  
  Contiene la descripción del dataset, su procedencia y la información necesaria para obtener los datos originales.

---

## Descripción del proyecto

El presente proyecto corresponde al Trabajo Fin de Máster y tiene como objetivo analizar la satisfacción y experiencia de los clientes de restaurantes peruanos a partir de reseñas publicadas en plataformas digitales.

Para ello, se aplican técnicas de **Procesamiento de Lenguaje Natural (NLP)** y **Machine Learning** que permiten analizar el contenido textual de las reseñas y clasificar la experiencia del cliente en tres categorías:

- Positiva (POS)
- Neutral (NEU)
- Negativa (NEG)

El proyecto complementa el análisis predictivo con un **análisis de sentimiento**, un **análisis de aspectos de la experiencia gastronómica**, un **sistema de recomendación de restaurantes** y un **dashboard interactivo orientado a negocio**.

---

## Problema de negocio

Los restaurantes reciben grandes cantidades de opiniones a través de plataformas digitales. El análisis manual de estas reseñas puede resultar complejo cuando aumenta el volumen de información.

El proyecto busca responder la siguiente pregunta:

> **¿Es posible utilizar técnicas de Inteligencia Artificial para estimar la satisfacción de clientes de restaurantes peruanos a partir de las reseñas publicadas en plataformas digitales?**

La solución desarrollada busca transformar las opiniones de los clientes en información que pueda facilitar la identificación de patrones de satisfacción, fortalezas y posibles oportunidades de mejora.

---

## Dataset

El proyecto utiliza el dataset público **Peruvian Food Reviews**, que contiene información sobre restaurantes peruanos y las reseñas realizadas por sus usuarios.

Después de los procesos de preparación y control de calidad se utilizaron:

- **569.877 reseñas** con texto válido.
- **569.102 reseñas** para el modelado.
- **9.871 restaurantes** en el dataset de establecimientos.
- **8.913 restaurantes** disponibles en la base utilizada por el recomendador.

Debido al tamaño de los archivos originales, los datasets no se almacenan directamente en este repositorio. En la carpeta `datos/` se documenta su procedencia.

---

## Metodología

El proyecto se desarrolló mediante las siguientes etapas:

1. Preparación y control de calidad de los datos.
2. Análisis exploratorio.
3. Procesamiento y normalización del texto.
4. Análisis de palabras, bigramas y trigramas.
5. Análisis de sentimiento mediante PySentimiento.
6. Representación del texto mediante TF-IDF.
7. Construcción de un modelo baseline.
8. Comparación de alternativas de modelización.
9. Incorporación de nuevas variables y probabilidades NLP.
10. Optimización del tratamiento de las clases.
11. Análisis de aspectos de la experiencia gastronómica.
12. Evaluación del modelo final.    
13. Desarrollo del sistema de recomendación.
14. Desarrollo del dashboard de satisfacción.
15. Preparación de los componentes para su consulta y revisión.
    
---

## Análisis de sentimiento

El análisis NLP permitió identificar la siguiente distribución general:

| Sentimiento | Porcentaje |
|---|---:|
| Positivo | 72.76 % |
| Neutral | 12.76 % |
| Negativo | 14.48 % |

Los resultados muestran una percepción predominantemente positiva de los establecimientos presentes en el conjunto analizado.

---

## Análisis de aspectos

Además de determinar el sentimiento general, el proyecto analiza nueve dimensiones de la experiencia gastronómica:

- Comida
- Atención
- Precio
- Ambiente
- Tiempo de espera
- Bebidas
- Calidad
- Ubicación
- Porciones

Este análisis permite pasar de una clasificación general de satisfacción a la identificación de los componentes específicos de la experiencia que generan opiniones positivas, neutrales o negativas.

Entre los resultados obtenidos, el **ambiente** presenta uno de los mayores niveles de percepción positiva, mientras que el **tiempo de espera** constituye uno de los principales puntos de fricción identificados.

---

## Modelo predictivo final

Después de evaluar diferentes alternativas, el modelo final seleccionado corresponde a una **Regresión Logística** que combina:

- Representación textual mediante **TF-IDF**.
- Probabilidades de sentimiento obtenidas mediante **PySentimiento**.
- Ponderación específica para mejorar el tratamiento de la clase neutral.

### Resultados sobre el conjunto de test

| Métrica | Resultado |
|---|---:|
| Accuracy | 0.8518 |
| Macro F1 | 0.6955 |
| Weighted F1 | 0.8473 |
| F1 - Positivo | 0.9308 |
| F1 - Neutral | 0.4481 |
| F1 - Negativo | 0.7076 |

Los resultados muestran un elevado desempeño en la identificación de experiencias positivas y un comportamiento adecuado en las experiencias negativas. La identificación de reseñas neutrales representa el principal reto del modelo.

---

## Sistema de recomendación de restaurantes

El proyecto incorpora un prototipo funcional de recomendación que permite buscar restaurantes según diferentes criterios, entre ellos:

- Distrito.
- Categoría gastronómica.
- Nivel de precio.
- Aspecto de interés.
- Número mínimo de reseñas.
- Número mínimo de menciones.
- Cantidad de recomendaciones.

Para reducir el efecto de restaurantes con puntuaciones elevadas pero pocas opiniones, el sistema incorpora una **valoración ajustada (Weighted Rating)**.

Cuando el usuario selecciona un aspecto específico, la puntuación de recomendación combina la valoración general del establecimiento con su desempeño en dicho aspecto.

---

## Dashboard de satisfacción gastronómica

Se desarrolló adicionalmente un dashboard interactivo para facilitar la interpretación de los resultados desde una perspectiva de negocio.

Entre sus principales funcionalidades se encuentran:

- Distribución general del sentimiento.
- Satisfacción por distrito.
- Satisfacción por categoría gastronómica.
- Distribución del sentimiento por aspecto.
- Ranking de restaurantes según valoración ajustada.

El dashboard permite transformar los resultados analíticos en indicadores de consulta más accesibles para usuarios sin conocimientos técnicos especializados.

---

## Estructura del repositorio

```text
TFM-Satisfaccion-Restaurantes-Perú/
│
├── datos/
│   └── Información sobre el dataset
│
├── documentación/
│   └── Informe final del TFM
│
├── html/
│   └── Versión HTML ejecutada del proyecto
│
├── cuadernos/
│   └── Notebook principal de Google Colab
│
└── README.md
```

### Archivos principales

- **`cuadernos/`**: contiene el notebook completo utilizado para desarrollar el proyecto.
- **`html/`**: contiene la versión ejecutada en HTML, incluyendo resultados, análisis y visualizaciones.
- **`documentación/`**: contiene el informe final del Trabajo Fin de Máster.
- **`datos/`**: contiene información sobre la procedencia de los datos utilizados.

---

## Tecnologías utilizadas

El proyecto fue desarrollado principalmente con:

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- SciPy
- TF-IDF
- PySentimiento
- Matplotlib
- ipywidgets

---

## Aplicabilidad empresarial

El proyecto busca aproximar los resultados del análisis a un escenario de utilización empresarial mediante dos componentes funcionales:

1. **Sistema de recomendación**, orientado al usuario que desea identificar restaurantes según determinados criterios.
2. **Dashboard de satisfacción**, orientado al análisis agregado de la experiencia de los clientes.

El entorno desarrollado constituye un **prototipo funcional** y podría evolucionar posteriormente hacia una aplicación independiente mediante el despliegue del procesamiento y del modelo como servicios accesibles desde una aplicación web o API.

---

## Autor

**Miguel Ángel Chávez Calle**

Trabajo Fin de Máster  
Data Science, Big Data & Business Analytics  
Universidad Complutense de Madrid
