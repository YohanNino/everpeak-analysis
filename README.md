# everpeak-analysis
# Análisis de Movilidad Urbana e Indicadores Económicos (2024)

## ¿De qué trata este proyecto?

Este proyecto evalúa cómo se relaciona la **movilidad urbana (congestión vehicular)** con la **productividad económica** en las principales ciudades latinoamericanas y globales durante el año **2024**. 

A través del procesamiento y combinación de datasets reales provenientes de **TomTom Traffic Index** y **OECD Cities**, el análisis busca identificar patrones de tráfico, niveles de demora (*jams_delay*) e impacto socioeconómico (PIB per cápita, desempleo, población) para respaldar la toma de decisiones e inversiones en infraestructura de transporte.

---

## ¿Qué contiene este repositorio?

- **notebook.ipynb**: Cuaderno principal con todo el flujo de trabajo: carga de datos, limpieza, estandarización de columnas (*snake_case*), conversión de tipos numéricos y de fechas, agrupación de promedios anuales, unión de tablas (*merge*) y visualizaciones gráficas.
- **Gráficos e Insights**:
  - **Boxplot de jams_delay**: Visualización de demoras medias y detección de valores atípicos (ciudades con congestión extrema como Ciudad de México).
  - **Histograma de PIB per Cápita**: Distribución y promedios de productividad económica entre las ciudades analizadas.
- **README.md**: Documentación general del proyecto.

---

## ¿Cómo abrir el notebook en Colab?

Puedes ejecutar este análisis directamente en la nube sin necesidad de instalar entornos locales:

1. Abre el cuaderno directamente en Google Colab a través del siguiente enlace: [Abrir en Google Colab](https://colab.research.google.com/)
2. Si ejecutas en Google Colab, asegúrate de subir o verificar la ruta de los datasets requeridos (`/datasets/tomtom_traffic.csv` y `/datasets/oecd_city_economy.csv`) o adaptar las rutas según tu estructura en Google Drive.

---

## ¿Cómo reproducir tu análisis?

Para replicar el análisis paso a paso en tu entorno local o en Colab:

## Requisitos previos

Asegúrate de contar con Python 3 e instalar las siguientes librerías:

```bash
pip install pandas numpy matplotlib seaborn

Archivos requeridos
El flujo utiliza dos archivos CSV principales:

tomtom_traffic.csv: Registros de tiempos de viaje, demoras y longitud de embotellamientos.

oecd_city_economy.csv: Indicadores económicos por ciudad y año (PIB per cápita, desempleo, población, PM2.5).

Orden de ejecución del Notebook
Abre el notebook notebook.ipynb y ejecuta las celdas en orden secuencial:

Paso 1: Carga y Exploración: Importación de librerías (pandas, numpy, matplotlib, seaborn) y revisión preliminar con .head() e .info().

Paso 2: Limpieza y Preparación:

Conversión a formato snake_case en los nombres de variables.

Corrección de formatos de texto a numéricos (float) y fechas (datetime).

Cálculo de población absoluta multiplicando population_m por 1,000,000.

Paso 3: Filtrado: Extracción del año mediante .dt.year y filtrado para trabajar exclusivamente con el año 2024.

Paso 4: Consolidación de Movilidad: Agrupación por city, country y year para obtener los promedios anuales de tráfico.

Paso 5: Unión (Merge): Combinación de las métricas de tráfico y variables económicas clave bajo un inner join por ciudad y año.

Paso 6: Visualización: Generación de diagramas de caja (boxplots) e histogramas para explorar el comportamiento del PIB per cápita y las demoras por tráfico.

Autor
Yohan Nino

Estudiante de  Análisis de Datos
