# Optimización del sistema de bicicletas compartidas de Medellín (Encicla)

## Datos de los Estudiantes
- Felipe Miranda Arboleda
- Emilio Porras Mejía

## Introducción
Este proyecto aborda un problema de la vida real inspirado en el clásico problema de la bicicleta compartida, un interesante desafío de optimización.

### 🚲 Problema de la Bicicleta Compartida para Grupos
Un grupo de *n* personas necesita trasladarse desde un punto A hasta un punto B en una distancia *d*. Solo existe una bicicleta disponible, que solo puede ser usada por una persona a la vez. Cada persona camina a una velocidad *wᵢ* y pedalea a una velocidad *bᵢ*, donde *bᵢ* > *wᵢ*. El objetivo es minimizar el tiempo en que la última persona llegue a B.

Este problema fundamental encapsula la esencia de la asignación de recursos limitados para minimizar el tiempo total, un principio clave en la optimización de sistemas de transporte como Encicla.

*Fuente: [The unexpected power of linear programming: an updated collection of surprising applications](https://link.springer.com/article/10.1007/s10479-024-06245-5)*

## Objetivo del Proyecto
El objetivo de este proyecto es analizar y modelar el sistema de bicicletas públicas Encicla de Medellín para sentar las bases de un modelo de optimización. A través del análisis de datos de las estaciones, se busca generar insumos clave, como matrices de distancia y tiempo, que son fundamentales para futuras estrategias de optimización logística (rebalanceo de bicicletas, planificación de rutas, etc.).

## Metodología y Resultados
El análisis se llevó a cabo en el notebook `proyecto.ipynb` y consistió en los siguientes pasos:

1.  **Carga y Limpieza de Datos:** Se procesó el archivo `Estaciones_EnCicla_AMVA_20250713.csv` para extraer y limpiar los datos de las estaciones, incluyendo sus coordenadas geográficas.
2.  **Visualización Geográfica:** Se generó un mapa interactivo (`medellin_map.html`) utilizando Folium, que muestra la ubicación de todas las estaciones de Encicla en Medellín.
3.  **Cálculo de Matriz de Distancias:**
    *   Se calculó una matriz de distancias directas (Haversine) entre todas las estaciones.
    *   Se generó una matriz de distancias más precisa utilizando una API externa, cuyos resultados se guardaron en `distance_api_matrix.csv` para evitar consultas repetidas.
4.  **Cálculo de Matriz de Tiempos:** A partir de la matriz de distancias, se estimó una matriz de tiempos de viaje promedio en bicicleta, asumiendo una velocidad constante de 13.07 km/h.

Estos artefactos (mapa y matrices) son la base para aplicar modelos de optimización lineal que busquen mejorar la eficiencia del sistema.

## Referencia Principal
El enfoque teórico se inspira en el estudio de Possani, E., & Castillo, E. (2021), *"Optimizing the inventory and routing decisions in a bike-sharing system"*, adaptando sus ideas al contexto de Medellín.

## Link al Documento de Trabajo
[Documento de Google](https://docs.google.com/document/d/1OZ_rHbJ9ZskrOAjijtfTFhxGbvQtEEer5AwAqgZq7_c)