# Reporte de Datos

Este documento contiene los resultados del análisis exploratorio de datos.

## Resumen general de los datos

En esta sección se presenta un resumen general de los datos. Se describe el número total de observaciones, variables, el tipo de variables, la presencia de valores faltantes y la distribución de las variables.

* El numero total de observaciones es de `50843`.
* Se encuentran variables de tipo :
- `Numericas`.
- `String o cadenas de caracteres`.
- `Categoricas`.
* Se identifican varias variabes con valores faltantes o totalmente vacias.
* Al ser la mayoria de variables de tipo string, no es posible realizar un analisis de su distribucion adicinal al de frecuencias.
    
## Resumen de calidad de los datos

En esta sección se presenta un resumen de la calidad de los datos. Se describe la cantidad y porcentaje de valores faltantes, valores extremos, errores y duplicados. También se muestran las acciones tomadas para abordar estos problemas.

<img width="2273" height="3828" alt="image" src="https://github.com/user-attachments/assets/bf95fc97-f864-45e8-847f-10f6fea1dd9c" />

En la grafica se puese observa el numero total de valores faltantes  para cada varible en color gris oscuro. En este caso no se identifican valores extremos, valores con errores o duplicados. 
En nuestro caso dado que vamos a predecir la categoria SIR  de cada microorganismos por cada antibiotico no se tomo ninguna accion para eliminar o dar manejo a los valores perdidos de estas variables.

## Variable objetivo

En esta sección se describe la variable objetivo. Se muestra la distribución de la variable y se presentan gráficos que permiten entender mejor su comportamiento.

Para nuestro proyecto se intentara predecir las categoria SIR para las siguientes variables objetivo: 

|'Eti_AMK_NM'|'Eti_AMP_NM'|'Eti_ATM_NM'|'Eti_CAS_NM'|'Eti_CAZ_NM'|'Eti_CIP_NM'|'Eti_CLI_NM'|'Eti_CPT_NM'|
|'Eti_CRO_NM'|'Eti_CTX_NM'|'Eti_CZA_NM'|'Eti_CZO_NM'|'Eti_CZT_NM'|'Eti_DAP_NM'|'Eti_ERY_NM'|'Eti_ETP_NM'|'Eti_FEP_NM'|
|'Eti_FLU_NM'|'Eti_FOS_NM'|'Eti_FOX_NM'|'Eti_GEH_NM'|'Eti_GEN_NM'|'Eti_IPM_NM'|'Eti_LNZ_NM'|'Eti_LVX_NM'|'Eti_MEM_NM'|
|'Eti_MFX_NM'|'Eti_MIF_NM'|'Eti_NIT_NM'|'Eti_NOR_NM'|'Eti_OXA_NM'|'Eti_PEN_NM'|'Eti_RIF_NM'|'Eti_SAM_NM'|'Eti_STH_NM'| 
|'Eti_SXT_NM'|'Eti_TCY_NM'|'Eti_TGC_NM'|'Eti_TZP_NM'|'Eti_VAN_NM'|'Eti_VOR_NM'|

Todas las variables presentan una distribución similar mas no igual a la que se presenta en la siguiente imagen. En donde aparecen valores de S = Sensibles, I = Intermedio y R= Resistentes. En algunos casos aparecen valores numericos los cuales no se tendran en cuenta para la prediccion, dado que corresponden a microorganismos sin puntos de corte para los atb.

<img width="584" height="384" alt="image" src="https://github.com/user-attachments/assets/51cfaa56-d887-419b-8ed4-bc61e37dfbea" />

## Variables individuales

En esta sección se presenta un análisis detallado de cada variable individual. Se muestran estadísticas descriptivas, gráficos de distribución y de relación con la variable objetivo (si aplica). Además, se describen posibles transformaciones que se pueden aplicar a la variable.

En nuestro caso se usara la informacion de CIM minima de cada antibiotico para predecir su valor tomando como referencia la informacion del mismo atb transformada a valores categoricos.
Como ejemplo se presenta la distriucion del antibiotico Meropenem. El comportamiento de los demas antibioticos es similar al que se observa en la imagen adjunta.

<img width="584" height="384" alt="image" src="https://github.com/user-attachments/assets/d1904935-9d60-44e2-951e-be211bbec888" />


## Ranking de variables

En esta sección se presenta un ranking de las variables más importantes para predecir la variable objetivo. Se utilizan técnicas como la correlación, el análisis de componentes principales (PCA) o la importancia de las variables en un modelo de aprendizaje automático.

Como se menciono en el punto anterior solo se usara una unica variable por antibiotico, por lo cual se establecio un ranking de variables mas importantes por tecnicas como correlacion, PCA, etc.

## Relación entre variables explicativas y variable objetivo

No aplica esta seccion en nuestro proyecto
