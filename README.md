
![Static Badge](https://img.shields.io/badge/PowerBI-gray?style=flat&logo=powerbi)
![Static Badge](https://img.shields.io/badge/Python-gray?style=flat&logo=python)
![Static Badge](https://img.shields.io/badge/-Pandas-gray?style=flat&logo=pandas)
![Static Badge](https://img.shields.io/badge/-Matplotlib-gray?style=flat&logo=matplotlib)
![Static Badge](https://img.shields.io/badge/-Seaborn-gray?style=flat&logo=seaborn)
![Static Badge](https://img.shields.io/badge/-Jupyter_Notebook-gray?style=flat&logo=jupyter)
![Static Badge](https://img.shields.io/badge/Visual_Studio_Code-gray?style=flat&logo=visual%20studio%20code&logoColor=white)

# Proyecto Individual 2 
## Siniestros Viales en CABA con víctimas fatales desde 2016 a 2021

## Contexto 
El `Observatorio de Movilidad y Seguridad Vial` (OMSV), centro de estudios que se encuentra bajo la órbita de la ***Secretaría de Transporte*** del Gobierno de la Ciudad Autónoma de Buenos Aires, nos solicita la elaboración de un proyecto de anális de datos, con el fin de generar información que le permita a las autoridades locales tomar medidas para disminuir la cantidad de víctimas fatales de los siniestros viales.
Para ello, nos disponibilizan un dataset sobre homicidios en siniestros viales acaecidos en la Ciudad de Buenos Aires durante el periodo 2016-2021. Este dataset se encuentra en formato *xlsx* y contiene dos hojas llamadas: **hechos** y **víctimas**. Asimismo, observarán que incluye otras dos hojas adicionales de diccionarios de datos, que les podrá servir de guía para un mayor entendimiento de la data compartida.

## Desarrollo

### Datos Originales

Para este trabajo se  uso como base los datos proporcionados de los siniestros viales desde el 2016 al 2021, los cuales se encuentran en formato Excel:

  [Buenos Aires Data](https://docs.google.com/spreadsheets/d/1nq00jGIZHQ1RLSET43zKnUsMsoFb-pBg/edit#gid=1625530738)
  [Diccionario de datos](https://docs.google.com/spreadsheets/d/1Op98U-Hh2a3Q7uuznAzdl4Bf8r8qPr4m/edit#gid=1771770012)

## ETL (Extracción, Limpieza y Carga de datos)
  Se realiza un proceso de [ETL](ETL.ipynb) sobre la tabla de 'Hechos' y 'Victima', eliminando nulos, duplicados, con transformaciones necesarias como cambio en los tipos de datos, eliminación de columnas y unión de las tablas y generamos un csv llamado [Casos](casos.csv)

## EDA (Análisis Exploratorio de los datos)
  Se realiza un proceso [EDA](EDA.ipnyb), para revisar las relaciones que existen entre las variables numéricas y categóricas de los datasets, encontrar si hay presencia de outliers o anomalías.

### Análisis de los datos

  Se analizan las variables numéricas del dataset su correlación por medio de una matriz y se puede ver una relación positiva entre las variables Edad y Hora.
  
  ![Mapa de Correlación](/Imágenes/MapadeCorrelación.png)

- Análisis Temporal
  El análisis temporal muestra para el período 2016-2018 una tendencia alta y estacionaria de homicidios , que luego baja (Pandemia por COVID19 durante 2020); puede verse un pico de siniestros durante Diciembre de 2021 y se retoma una tendencia baja.
  
  ![Victimas por año](/Imágenes/VictimasporAño.png)
  
  Los meses con más victimas fatales son Diciembre (86) y Agosto (71); mientras que los días de la semana Sábado (114) y Domingo (114) tienen la mayor cantidad de víctimas.
  
  ![Victimas por Mes](/Imágenes/VictimasporMes.png)

  El 20 de cada mes en promedio tiene mayor cantidad de victimas

  ![Victimas por Día](/Imágenes/VictimasporDía.png)

  Los Sabados y Domingos la mayor cantidad de accidentes se suelen dar entre las 3:00 hs y las 9:00 hs (probablemente tenga que ver con las salida del boliche). Tambien podemos ver un patron entre los dias martes y sabados entre las 10 y 12 am, entre los días Míercoles y Viernes desde las 17 a 20 pm (Probablemente salida laboral)

  ![Victimas por Hora](/Imágenes/HoraporDía.png)

- Análisis Demográfico

  Análizamos el patrón de Edad y Hora de las variables númericas se analiza agregando la variable Sexo de la víctima, y se llega a la conclusión que las edades de mayor ocurrencia es entre 20 y 40 años desde las 5 a las 9 hs para los masculinos mientras que las mujeres tienden a tener un rango mas dispersado.

  ![Victimas por Hora](/Imágenes/SexoporHora.png)

  La distribución del rango etario de víctimas, es para los Hombres entre 20 y 40 años; mientras que para las Mujeres entre 40, 60 y 80 años.

  ![Victimas por Sexo y Edad](/Imágenes/VictimasSexo.png)

  Tambien podemos ver que las victimas masculinas tienen a ser Conductores y Peatones y las victimas mujeres tienen a ser Peatones seguido por Pasajero-Acompañante

  ![RolySexo](/Imágenes/RolySexo.png)
  
- Análisis Geográfico

  Hay una clara tendencia a que los accidentes sean en avenidas (442) seguido por calles(136).

  ![Victimas por Calle](/Imágenes/VictimasporCalle.png)

- Análisis de los Participantes

  Para los Participantes de los sinietros se analiza a los Acusados, como el responsable del siniestro, los cuales Autos, Colectivos y Vehículos de Carga son los mayores participantes.

  ![Acusados](/Imágenes/Acusados.png)

  Y para Victimas el siniestro se produce en la mayoría de los casos en Motos y luego Peaton.

  ![Victima](/Imágenes/Victimas.png)

  Cuando el acusado es un auto, las victimas tienden a ser Motos, Peatones y otros Autos
  Cuando el acusado es cargas, las victimas en mayor medida son Motos y Peatones
  Cuando el acusado es un pasajero, las victimas son Peatones y Motos

  ![RelaciónVictimaAcusado](/Imágenes/RelacionVictimaAcusado.png)

### Indicadores de Rendimiento Clave KPI  
  Una vez finalizado el Análisis Exploratorio, se utiliza el dataset resultante [Casos](data/casos.csv) para trabajar en la herramienta PowerBi a fin de obtener los KPI (Indicadores de Rendimiento Clave) y un dashboard de presentación del informe y visualización de datos.


KPI Propuestos: 
Debes graficar y medir los 2 KPIs propuestos a continuación, representándolos adecuadamente en el dashboard. A su vez, tambíen tienes que proponer, medir y graficar un tercer KPI que consideres relevante para la temática. Los dos KPIs propuestos son:

- Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.

Definimos a la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000

- Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

Definimos a la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100

![KPI 1](/Imágenes/KPI1.PNG)
![KPI 2](/Imágenes/KPI2.PNG)
![KPI 3](/Imágenes/KPI3.PNG)
  
  
  

  


