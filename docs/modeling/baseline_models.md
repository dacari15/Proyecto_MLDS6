# Reporte del Modelo Baseline

Este documento contiene los resultados del modelo baseline.

## Descripción del modelo

El modelo baseline es el primer modelo construido y se utiliza para establecer una línea base para el rendimiento de los modelos posteriores.
En nuestro caso se construyo un codigo que permite entrenar diferentes modelos para cada uno de los antibioticos incluidos en nuestra base de datos. El entrenamiento se realiza para cada antibiotico teniendo encuenta la informacion de cada microorganismo debido a que cada microorganismos presenta un punto de corte de concentracion inhibitoria minima.


## Variables de entrada

Lista de las variables de entrada utilizadas en el modelo.

Dentro de las variables de entrada utilizadas en nuestro modelo se encuentran las siguientes variables: 
**LOCAL_ORG**: Esta variable contiene la información del microorganismos aislado en cultivos microbiologicos en cada uno de los pacientes incluido en nuestra base de datos.
**Nombre de Antibiotico**:  Esta variable incluye la informacion de cada uno de los antibioticos que se corre en el modelo correspondiente con la informacion de Concentracion Inhibitoria Minima que incluye el rango de sensibilidad, intermedio y resistencia en valores numericos.
  "AMK_NM", # Amikacina
  "AMP_NM", # Anfotericina B
  "ATM_NM", # Aztreonam
  "CAS_NM", # Caspofungina
  "CAZ_NM", # Ceftazidima
  "CIP_NM", # Ciprofloxacina
  "CLI_NM", # Clindamicina
  "CPT_NM", # Ceftarolina
  "CRO_NM", # Ceftriaxona
  "CTX_NM", # Cefotaxima
  "CZA_NM", # Ceftazidima/Avibactam
  "CZO_NM", # Cefazolina
  "CZT_NM", # Ceftolozane/Tazobactam
  "DAP_NM", # Daptomocina
  "ERY_NM", # Eritromicina
  "ETP_NM", # Ertapenem
  "FEP_NM", # Cefepime
  "FLU_NM", # Fluconazol
  "FOS_NM", # Fosfomicina
  "FOX_NM", # Cefoxitina
  "GEH_NM", # Gentamicina
  "GEN_NM", # Gentamicina
  "IPM_NM", # Imipenem
  "LNZ_NM", # Linezolid
  "LVX_NM", # Levofloxacina
  "MEM_NM", # Meropenem
  "MFX_NM", # Moxifloxacina
  "MIF_NM", # Micafungina
  "NIT_NM", # Nitrofurantoina
  "NOR_NM", # Norfloxacina
  "OXA_NM", # Oxacilina
  "PEN_NM", # Penicilina
  "RIF_NM", # Rifanpicina.
  "SAM_NM", # Ampicilina/Sulbactam
  "SXT_NM", # Trimetropina/Sulfametoxazol
  "TCY_NM", # Tetraciclina
  "TGC_NM", # Tigeciclina
  "TZP_NM", # Piperacilina/Tazobactam
  "VAN_NM", # Vancomicina
  "VOR_NM", # Voriconazol 

## Variable objetivo
Nombre de la variable objetivo utilizada en el modelo.

Eti_nombre_atb =  La varianle Etiqueta incluye la informacion de concentracion inhibitoria minima (CIM) convertida a valores categoricos S= Sensible, I= Intermedio y R = Resistente.
  "Eti_AMK_NM", # Amikacina
  "Eti_AMP_NM", # Anfotericina B
  "Eti_ATM_NM", # Aztreonam
  "Eti_CAS_NM", # Caspofungina
  "Eti_CAZ_NM", # Ceftazidima
  "Eti_CIP_NM", # Ciprofloxacina
  "Eti_CLI_NM", # Clindamicina
  "Eti_CPT_NM", # Ceftarolina
  "Eti_CRO_NM", # Ceftriaxona
  "Eti_CTX_NM", # Cefotaxima
  "Eti_CZA_NM", # Ceftazidima/Avibactam
  "Eti_CZO_NM", # Cefazolina
  "Eti_CZT_NM", # Ceftolozane/Tazobactam
  "Eti_DAP_NM", # Daptomocina
  "Eti_ERY_NM", # Eritromicina
  "Eti_ETP_NM", # Ertapenem
  "Eti_FEP_NM", # Cefepime
  "Eti_FLU_NM", # Fluconazol
  "Eti_FOS_NM", # Fosfomicina
  "Eti_FOX_NM", # Cefoxitina
  "Eti_GEH_NM", # Gentamicina
  "Eti_GEN_NM", # Gentamicina
  "Eti_IPM_NM", # Imipenem
  "Eti_LNZ_NM", # Linezolid
  "Eti_LVX_NM", # Levofloxacina
  "Eti_MEM_NM", # Meropenem
  "Eti_MFX_NM", # Moxifloxacina
  "Eti_MIF_NM", # Micafungina
  "Eti_NIT_NM", # Nitrofurantoina
  "Eti_NOR_NM", # Norfloxacina
  "Eti_OXA_NM", # Oxacilina
  "Eti_PEN_NM", # Penicilina
  "Eti_RIF_NM", # Rifanpicina.
  "Eti_SAM_NM", # Ampicilina/Sulbactam
  "Eti_SXT_NM", # Trimetropina/Sulfametoxazol
  "Eti_TCY_NM", # Tetraciclina
  "Eti_TGC_NM", # Tigeciclina
  "Eti_TZP_NM", # Piperacilina/Tazobactam
  "Eti_VAN_NM", # Vancomicina
  "Eti_VOR_NM", # Voriconazol

## Evaluación del modelo

### Métricas de evaluación

Descripción de las métricas utilizadas para evaluar el rendimiento del modelo.

Dentro de las metricas utilizadas para evaluar el rendimiento de los modelos  utilizamos: 

**Accuracy** : 
La proporción de predicciones correctas entre el total de predicciones realizadas.

Fórmula:
Accuracy= TP+TN  / TP+FP+TN+FN
TP: Verdaderos positivos
TN: Verdaderos negativos
FP: Falsos positivos
FN: Falsos negativos

**precision** :
De todas las predicciones positivas que hizo el modelo, ¿cuántas fueron realmente correctas?

Fórmula:
Precision = TP / TP+FP

**Recall** : 
De todos los casos que realmente eran positivos, ¿cuántos fue capaz de identificar el modelo?

Fórmula:
Recall= TP+FN / TP
​
*f1-score** : 
Es la media armónica entre precision y recall. Equilibra ambos en una sola métrica.

Fórmula:
F1=2×  (PrecisionxRecall) /(Precision+Recall) 


### Resultados de evaluación

Tabla que muestra los resultados de evaluación del modelo baseline, incluyendo las métricas de evaluación.

## Análisis de los resultados
Descripción de los resultados del modelo baseline, incluyendo fortalezas y debilidades del modelo.

## Conclusiones

Conclusiones generales sobre el rendimiento del modelo baseline y posibles áreas de mejora.

## Referencias
Lista de referencias utilizadas para construir el modelo baseline y evaluar su rendimiento.
No se utilizaron referencias para construir los modelos.

