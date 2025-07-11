# Definición de los datos

## Origen de los datos

- [ ] Especificar la fuente de los datos y la forma en que se obtuvieron.
      Los datos se obtendrán de las Bases de Datos de Whonet de una Institución de Salud de reporte obligatorio al ministerio de salud de forma mensual, del periodo comprendido entre 2019 a mayo de 2025 para un tamaño aproximado de 50.000 registros. Estos reportes provienen de sistemas automatizados para la indentificación microbiólogica del laboratorio bioMérieux, el cual genera datos sobre la identificación de bacterias y su sensibilidad a los antibióticos. Estos datos pueden ser exportados en diferentes formatos, como CSV o archivos de texto para su posterior análisis. Para posteriormente ser interpretados y transformados a formato .sir en el aplicativo BacLink el cual se encarga de hacer la traducción de la informacio a datos de pacientes y resultados de cultivos, ademas informacion de localizacion, servicio, tipo de muestra, etc. Este archivo .sir es transformado posteriormente a formato .xlsx.
      
## Especificación de los scripts para la carga de datos

- [ ] Especificar los scripts utilizados para la carga de los datos.
      
  **Script de carga Bases de datos**: [`scripts/data_acquisition/1_Carga_datos.ipynd`](scripts//data_acquisition//1_Carga_datos.ipynd)
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
      La ubicaciónde de los archivos de whonet se obtiene de un repositorio privado de una institución de salud de tercer nivel de complejidad. La información se obtiene directamente de las bases de datos reportadas las secretaria de salud, con una periodicidad mensual. Estas bases de datos mensuales son consolidadas en un solo archivo que contiene la informacion desde enero del 2019, hasta el mes de mayo del 2025 en un archivo xlsx para ser cargado de forma mas facil en el aplicativo colab. 
- [ ] Especificar la estructura de los archivos de origen de los datos.
      Estructura del archivo de origen: `Clinicas_2019_2025.xlsx`
      - **Ubicación**: `/content/Clinicas_2019_2025.xlsx`
      - **Formato**: Excel (.xlsx)
      - **Separador**: Na
      - **Codificación**: `utf-8`
      - **Hojas (sheets)** : `default_1`
      - **Columnas**: `ver data_dictionary`
      Estructura del archivo de origen: `SIR_2019_2025.xlsx`
      - **Ubicación**: `/content/SIR_2019_2025.xlsx`
      - **Formato**: Excel (.xlsx)
      - **Separador**: Na
      - **Codificación**: `utf-8`
      - **Hojas (sheets)** : `SIR`
      - **Columnas**: `ver data_dictionary` 
 
- [ ] Describir los procedimientos de transformación y limpieza de los datos.
  **Script de carga Bases de datos**: [`scripts/eda/preprocesamiento_y_analisis_exploratorio.ipynd`](scripts//eda//preprocesamiento_y_analisis_exploratorio.ipynd)
  - Se realiza explorar inicial de las bases de datos.
  - Se explora tamaño de la base de datos.
  - Se exploran valores faltantes o missing.
  - Se evalua la correlación entre variables.
  - Se borran columnas que no son necesarias.
  - Se ajustan y transforman informacion de servicios.
  - Se ajusta codificacion de tipos de muestras por medio de diccionarios.
  - Se ajustan nombres y codigos de microorganismos.
  - Se elimina filas vacias.
  - Se ordena columnas.
  - Se revisa CIM de cada microorganismos y antibiotico con el objetivo de corregir y estandarizar sus valores.
 

### Base de datos de destino

- [ ] Especificar la base de datos de destino para los datos.
        Estructura del archivo de origen: `whonet_etiquetas.xlsx`
      - **Ubicación**: `/content/whonet_etiquetas.xlsx.xlsx`
      - **Formato**: Excel (.xlsx)
      - **Separador**: Na
      - **Codificación**: `utf-8`
      - **Hojas (sheets)** : `default_1`
      - **Columnas**:

- [ ] Especificar la estructura de la base de datos de destino.
      |PATIENT_ID|AGE|PAT_TYPE|WARD|DATE_ADMIS|SPEC_NUM|SPEC_DATE|SPEC_TYPE|
      |SPEC_CODE|LOCAL_SPEC|LOCAL_SPEC2|ORGANISM|LOCAL_ORG|ORG_TYPE|SEROTYPE|MRSA|
      |VRE|BETA_LACT|ESBL|AMK_NM|Eti_AMK_NM|AMP_NM|Eti_AMP_NM|ATM_NM|
      |Eti_ATM_NM|CAS_NM|Eti_CAS_NM|CAZ_NM|Eti_CAZ_NM|CHL_NM|Eti_CHL_NM|CIP_NM|
      |Eti_CIP_NM|CLI_NM|Eti_CLI_NM|CPT_NM|Eti_CPT_NM|CRO_NM|Eti_CRO_NM|CTX_NM|
      |Eti_CTX_NM|CZA_NM|Eti_CZA_NM|CZO_NM|Eti_CZO_NM|CZT_NM|Eti_CZT_NM|DAP_NM|
      |Eti_DAP_NM|ERY_NM|Eti_ERY_NM|ETP_NM|Eti_ETP_NM|FEP_NM|Eti_FEP_NM|FLU_NM|
      |Eti_FLU_NM|FOS_NM|Eti_FOS_NM|FOX_NM|Eti_FOX_NM|GEH_NM|Eti_GEH_NM|GEN_NM|
      |Eti_GEN_NM|IPM_NM|Eti_IPM_NM|LNZ_NM|Eti_LNZ_NM|LVX_NM|Eti_LVX_NM|MCZ_NM|
      |Eti_MCZ_NM|MEM_NM|Eti_MEM_NM|MFX_NM|Eti_MFX_NM|MIF_NM|Eti_MIF_NM|NIT_NM|
      |Eti_NIT_NM|NOR_NM|Eti_NOR_NM|OXA_NM|Eti_OXA_NM|PEN_NM|Eti_PEN_NM|RIF_NM|
      |Eti_RIF_NM|SAM_NM|Eti_SAM_NM|STH_NM|Eti_STH_NM|SXT_NM|Eti_SXT_NM|TCY_NM|
      |Eti_TCY_NM|Eti_TGC_NM|TGC_NM|TZP_NM|Eti_TZP_NM|VAN_NM|Eti_VAN_NM|VOR_NM|
      |Eti_VOR_NM|MX_RX|General3|year|month|key|
      
- [ ] Describir los procedimientos de carga y transformación de los datos en la base de datos de destino.
       - Se combina la informacion de `Clinicas_2019_2025.xlsx` con las etiquetas para cada antibiotico `SIR_2019_2025.xlsx`.
        - Se guarda la  base de datos modificada.
