# Codificación Multimodal de Ítems y Usuarios para Tareas de Recomendación

Este repositorio contiene el trabajo realizado para mi Trabajo Fin de Grado (TFG) de Ciencia e Ingeniería de Datos por la Universidad de Oviedo, centrado en el desarrollo de un sistema de recomendación de restaurantes basado en codificación multimodal de ítems y usuarios. Se combinan técnicas tradicionales de recomendación con representaciones generadas mediante el modelo CLIP de OpenAI, integrando texto e imágenes de las reseñas.

## Contenido

- `1_generar_embeddings_CLIP.ipynb`  
  Generación de embeddings de texto e imagen a partir de las reseñas usando CLIP.

- `2_particionado_dataset.ipynb`  
  Particionado estratificado de los datos en conjuntos de entrenamiento, validación y test.

- `3_estadisticas_generales.ipynb`  
  Análisis exploratorio del dataset, con visualización de estadísticas clave.

- `4_arquitecturas_recomendar.ipynb`  
  Implementación y entrenamiento de siete arquitecturas de recomendación en PyTorch.

- `5_experimentos_auxiliares.ipynb`  
  Experimentos complementarios para evaluar robustez y sensibilidad del sistema.


## Datos utilizados

Las bases de datos utilizadas en este proyecto proceden del repositorio público [Zenodo – MultiModal Yelp](https://zenodo.org/records/5644892). Para cada ciudad incluida en el dataset (por ejemplo, Nueva York, Gijón, Bogotá o Ciudad de México), se proporcionan tres archivos `.pkl`:

- `restaurants.pkl` – Información de los restaurantes
- `users.pkl` – Información de los usuarios
- `reviews.pkl` – Reseñas con textos e imágenes

Este proyecto se centra únicamente en el archivo `reviews.pkl`, ya que contiene tanto el texto de las reseñas como imágenes asociadas (cuando existen), lo que permite aplicar codificación multimodal con CLIP.


Para este TFG se ha trabajado con los datos de Gijón, una ciudad pequeña cuyas reseñas están escritas en español, lo que facilita su análisis y procesamiento. Posteriormente se analizaron también los datos de Nueva York, que presentan un volumen mucho mayor de datos (con decenas de miles de reseñas), pero también implican mayores requerimientos computacionales. Además, al estar redactadas en inglés, las reseñas de Nueva York podrían aprovechar mejor el rendimiento del modelo CLIP, entrenado principalmente en ese idioma.


# Datasets Preprocesados

Los datasets necesarios para entrenar y evaluar el sistema de recomendación están disponibles públicamente en Kaggle:

- **gij8010**  
  [https://www.kaggle.com/datasets/lucapropaganda/gij8010](https://www.kaggle.com/datasets/lucapropaganda/gij8010)

- **ny8010**  
  [https://www.kaggle.com/datasets/lucapropaganda/ny8010](https://www.kaggle.com/datasets/lucapropaganda/ny8010)

Estos datasets contienen reseñas de restaurantes extraídas y preprocesadas a partir del conjunto original Multimodal Yelp Dataset Challenge (Zenodo), e incluye embeddings de texto e imagen generados con CLIP de OpenAI. Se proporciona una partición estratificada (80/10/10) en tres archivos .pkl, con información como texto, imágenes, puntuación, identificadores y representaciones vectoriales, lo que permite aplicar sistemas de recomendación multimodal de forma eficiente y reproducible.

## Tecnologías

- Python 3
- PyTorch
- CLIP (OpenAI)
- Pandas, NumPy, Matplotlib, Seaborn
- Scikit-learn

## Métricas de evaluación

Los modelos se evalúan utilizando RMSE (Root Mean Square Error) sobre los conjuntos de entrenamiento, validación y test.

## Autora

Lucía Fernández Rodríguez  
Universidad de Oviedo – Grado en Ciencia e Ingeniería de Datos

## Licencia

Este proyecto está bajo la Licencia MIT.
