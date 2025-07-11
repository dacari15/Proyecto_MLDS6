# Definición de los datos

## Origen de los datos

- [ ] Especificar la fuente de los datos y la forma en que se obtuvieron.
      Los datos se obtendrán de las Bases de Datos de Whonet de una Institución de Salud de reporte obligatorio al ministerio de salud de forma mensual, del periodo comprendido entre 2019 a mayo de 2025 para un
      tamaño aproximado de 50.000 registros. Estos reportes provienen de sistemas automatizados para la indentificación microbiólogica del laboratorio bioMérieux, el cual genera datos sobre la identificación de
      bacterias y su sensibilidad a los antibióticos. Estos datos pueden ser exportados en diferentes formatos, como CSV o archivos de texto para su posterior análisis. Para posteriormente ser interpretados y
      transformados a formato .sir en el aplicativo BacLink el cual se encarga de hacer la traducción de la informacio a datos de pacientes y resultados de cultivos, ademas informacion de localizacion, servicio,
      tipo de muestra, etc.
      
## Especificación de los scripts para la carga de datos

- [ ] Especificar los scripts utilizados para la carga de los datos.
      
  **Script de carga Bases de datos**: [`scripts/eda/preprocesamiento_y_analisis_exploratorio.ipynd`](scripts//eda//preprocesamiento_y_analisis_exploratorio.ipynd)
  - Lee el archivo `Clinicas_2019_2025.xlsx`. la cual contiene la informacion de concentración inhibitoria minima de cada microorganismos  y antibiótico.
  - Convierte el archivo en formato pandas
  - Verifica  y explora columnas esperadas.
  - Elimina columnas que contienen informacion del pacientes, por proteccion y privacidad. Adicionalmente, no es importante para nuestro analisis.
  - Lee el archivo `SIR_2019_2025.xlsx`, la cual contiene las etiquetas de cada microorganismo en formato SIR (Sensible, intermedio y resistente) segun puntos de corte establecidos por el CLSI para cada antibiótico.
  - Convierte el archivo en formato pandas.
  - Verifica  y explora columnas esperadas.
  - Elimina columnas que contienen el nombre de la clinica.
  - Elimina columnas vacias.
  
## Referencias a rutas o bases de datos origen y destino

- [ ] Especificar las rutas o bases de datos de origen y destino para los datos.

### Rutas de origen de datos

- [ ] Especificar la ubicación de los archivos de origen de los datos.
- [ ] Especificar la estructura de los archivos de origen de los datos.
- [ ] Describir los procedimientos de transformación y limpieza de los datos.


### Base de datos de destino

- [ ] Especificar la base de datos de destino para los datos.
- [ ] Especificar la estructura de la base de datos de destino.
- [ ] Describir los procedimientos de carga y transformación de los datos en la base de datos de destino.
