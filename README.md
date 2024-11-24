#Sistema de Recomendación Inteligente para E-Commerce
Este repositorio presenta un sistema de recomendación de productos diseñado para plataformas de comercio electrónico, utilizando técnicas avanzadas de aprendizaje automático y Big Data. Basado en el análisis de calificaciones de estrellas proporcionadas por los usuarios, el sistema implementa dos modelos principales: Alternating Least Squares (ALS) para filtrado colaborativo y K-means para segmentación de usuarios y productos.
Algoritmos Utilizados
Alternating Least Squares (ALS)
Descripción: ALS es un algoritmo utilizado para el filtrado colaborativo que descompone la matriz de interacciones entre usuarios y productos, permitiendo predecir calificaciones no observadas.
Funcionamiento:
Se carga y preprocesa el dataset almacenado en Amazon S3 en formato Parquet.
Se seleccionan columnas clave como customer_id, product_id y star_rating.
Se configura el modelo ALS variando parámetros como el número de iteraciones, regularización y factores latentes.
El rendimiento se evalúa utilizando el error cuadrático medio (RMSE), con mejoras significativas al aumentar el tamaño del conjunto de datos.
K-means
Descripción: K-means es un algoritmo de agrupamiento que segmenta tanto a los usuarios como a los productos en clústeres homogéneos, mejorando la personalización de las recomendaciones.
Funcionamiento:
Se agrupan usuarios y productos en clústeres, evaluando la cohesión y separación mediante el índice de Silhouette.
Se realizan análisis con y sin reducción de dimensionalidad (PCA) para identificar patrones clave en las interacciones.
Metodología
Carga y Preprocesamiento de Datos: Los datos se almacenan en un bucket de Amazon S3 y se cargan en un DataFrame de Spark, eliminando valores nulos y transformando columnas relevantes.
Análisis Exploratorio de Datos (EDA): Se analiza la distribución de las variables y se normalizan los datos para preparar el modelado.
Modelado Predictivo: Se implementan los modelos ALS y K-means, evaluando su rendimiento y ajustando hiperparámetros para maximizar la precisión.
Resultados
El sistema ha demostrado ser efectivo en la predicción de calificaciones, con un RMSE que mejora al aumentar el tamaño del conjunto de datos. Además, la segmentación mediante K-means ha permitido identificar patrones diferenciados entre grupos de usuarios y productos, optimizando así las recomendaciones personalizadas.
Este enfoque no solo mejora la experiencia del usuario al ofrecer sugerencias más relevantes, sino que también contribuye a incrementar las tasas de conversión en plataformas de comercio electrónico.
