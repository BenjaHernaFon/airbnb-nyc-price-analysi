Análisis Exploratorio y Diagnóstico Estadístico de Precios — Airbnb NYC
Este proyecto realiza una limpieza inicial, análisis exploratorio de datos (EDA), evaluación de normalidad y detección de outliers sobre los precios de alojamientos de Airbnb en la ciudad de Nueva York (AB_NYC_2019.csv), preparando el conjunto de datos y su diagnóstico estadístico para tareas de modelado predictivo.

Objetivo
Comprender la distribución de los precios por noche (price), identificar diferencias según el tipo de alojamiento (room_type) y verificar supuestos estadísticos (normalidad y presencia de valores atípicos) antes de aplicar modelos de regresión o reducción de dimensionalidad.

Dataset
Archivo: AB_NYC_2019.csv (New York City Airbnb Open Data).
Registros procesados: 48,884 alojamientos válidos (tras filtrar registros con price > 0) y 16 variables.
Variables principales: price, room_type, neighbourhood_group, neighbourhood, minimum_nights, number_of_reviews, reviews_per_month, calculated_host_listings_count, availability_365, latitude, longitude.
Principales Hallazgos
Fuerte asimetría en los precios: El precio promedio por noche es de $152.76 USD, mientras que la mediana es de $106.00 USD (con un máximo de $10,000 USD y una asimetría de 19.12), lo que evidencia una distribución fuertemente sesgada a la derecha.
Rechazo de normalidad: Tanto la prueba de Kolmogorov-Smirnov (
D
=
0.2834
,
p
<
0.001
) como Shapiro-Wilk (
W
=
0.3420
,
p
<
0.001
) rechazan la hipótesis de normalidad en price, lo cual se confirma visualmente mediante el histograma con KDE y el gráfico Q-Q.
Detección de outliers: Mediante el criterio del rango intercuartílico (IQR), se identificaron 2,972 valores atípicos superiores (6.08% del total) y 0 inferiores.
Segmentación por tipo de alojamiento: Se analizaron las frecuencias y el precio promedio por categoría (Entire home/apt, Private room, Shared room).
Visualizaciones Destacadas
(Si subes las imágenes de outputs_airbnb/ al repositorio, puedes mostrarlas así)

Distribución de precios Precio promedio por tipo de alojamiento

Tecnologías y Librerías
Lenguaje: Python 3
Manipulación y análisis: pandas, numpy
Estadística y modelado: scipy, statsmodels, scikit-learn
Visualización: matplotlib, seaborn
Estructura del Proyecto
├── data/                   # Carpeta para el dataset AB_NYC_2019.csv (o enlace de descarga)
├── outputs_airbnb/         # Tablas resumen (.csv) y gráficos (.png) generados automáticamente
├── analisis_airbnb.ipynb   # Notebook principal con el código, análisis y resultados
├── requirements.txt        # Dependencias del proyecto
└── README.md               # Documentación del proyecto