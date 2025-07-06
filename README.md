# FDS-2025-1-256
![image](https://github.com/user-attachments/assets/b47b251e-e65c-46c3-a1a4-f0c28ab554dc)

- [Universidad Peruana de Ciencias Aplicadas]

- [Curso : Fundamentos de Data Science]

- [Tema : Análisis exploratorio de un conjuntos de datos en R/RStudio]

- [Docente : Nérida Isabel Manrique Tunque]
## INTEGRANTES

- [Humberto Aesio Chumbiauca Camac]

- [Sofia Gabriel Miranda Cardenas]

- [Juan José Rodríguez Velásquez]


## OBJETIVO DEL TRABAJO

Objetivos del proyecto:
El principal objetivo del proyecto es responder a una serie de preguntas clave planteadas por el cliente, que busca identificar patrones de consumo, preferencias de los usuarios y posibles predicciones sobre el rendimiento de los videos.

Objetivos de Data Science:

Explorar y analizar la información para comprender cómo se estructura el dataset de los vídeos de contenido en tendencia en Youtube (Francia).

Encontrar patrones en la actitud de los usuarios más o menos fuertes ante variables como vistas, likes, dislikes, comentarios, fechas y la región.

Valorar la comunidad de los vídeos de forma general y, por categorías, por canales y por estados, a través de métricas como la comunidad, la proporción de likes/dislikes y la frecuencia de aparición.

Identificar relaciones significativas entre variables como vistas y comentarios y likes y dislikes, a través de análisis de correlación.
Construir variables adjuntas que permitan representar de forma mejor el rendimiento y la comunidad de los usuarios respecto a los vídeos (por ejemplo, engagement_rate, like_ratio).

Desarrollar técnicas de agrupamiento (clustering) para agrupar vídeos con características similares que permitan hacer análisis comparativos.

Diseñar un modelo predictivo para estimar el número de vistas y/o la cantidad de me gusta de un vídeo a partir de sus características observadas, valorando la capacidad del modelo para ajustarse a la realidad.

Proyectar recomendaciones a partir de los hallazgos obtenidos para tomar decisiones de marketing, de contenidos y de planificación estratégica del cliente.

## DATASET
El dataset principal (FRvideos_cc50_202101.csv) contiene 21 columnas y más de 40,000 registros. 
El archivo JSON contiene pares id - title para mapear correctamente las categorías de los videos.

Columna	Tipo de dato	Descripción
video_id	object	ID único del video
trending_date	datetime	Fecha en que el video fue tendencia
title	object	Título del video
channel_title	object	Canal que publicó el video
category_id	int64	ID de la categoría del video
publish_time	datetime	Fecha y hora de publicación
tags	object	Etiquetas asociadas al video
views	int64	Número de visualizaciones
likes	int64	Número de me gusta
dislikes	int64	Número de no me gusta
comment_count	int64	Número de comentarios
comments_disabled	bool	Si los comentarios están deshabilitados
ratings_disabled	bool	Si los ratings (likes/dislikes) están deshabilitados
video_error_or_removed	bool	Si el video tiene errores o fue eliminado
description	object	Descripción del video
state	object	Región geográfica
lat / lon	float64	Coordenadas geográficas
geometry	object	Geometría asociada a coordenadas

## CONCLUSIONES 


1. Las categorías determinan las tendencias de los videos.
 Se evidenció que la categoría "Entertainment" concentra la mayor cantidad de videos en tendencia, lo que refleja una fuerte preferencia del público por contenidos de ocio. En contraste, categorías como "Trailers / Promos" tienen muy baja representación, mostrando menor interés o actividad en esos temas por parte de los usuarios.


2. Las interacciones (likes, dislikes, comentarios) están altamente correlacionadas con las vistas.
 Se identificó una fuerte relación entre la cantidad de “me gusta”, “no me gusta” y comentarios con la cantidad de vistas de los videos. Esto fue confirmado mediante análisis de correlación y la construcción de un modelo predictivo con una precisión (R²) de 0.8487, lo que respalda que estas métricas son buenos predictores del alcance de un video.


3. El análisis mediante K-means permitió segmentar los videos en grupos con comportamientos distintos.
 A través del modelo de clustering se identificaron cuatro clústeres de videos con patrones diferenciados en términos de visualizaciones, interacciones y engagement. Esta segmentación es útil para comprender distintos tipos de contenido y su impacto, ayudando a orientar decisiones estratégicas en marketing digital o posicionamiento de contenidos.

4. Los valores atípicos y la transformación logarítmica fueron claves para mejorar el análisis.
 La presencia de valores extremadamente altos en variables como vistas, likes y comentarios podría haber distorsionado los resultados. Aplicar la transformación logarítmica permitió normalizar las distribuciones y mejorar tanto la visualización como el desempeño de los modelos analíticos.


5. La estandarización de variables fue esencial para una correcta agrupación.
 Dado que las métricas del dataset original estaban en escalas muy diferentes, fue necesario aplicar técnicas de escalado como MinMaxScaler para permitir que algoritmos como K-Means pudieran funcionar correctamente y evitar que las variables de mayor magnitud dominaran el análisis.

