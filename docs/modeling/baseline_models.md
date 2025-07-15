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


Reporte para: whonet_AMK_NM
              precision    recall  f1-score   support

           I       1.00      0.89      0.94        81
           R       0.97      1.00      0.98       325
           S       1.00      1.00      1.00      6128

    accuracy                           1.00      6534
   macro avg       0.99      0.96      0.98      6534
weighted avg       1.00      1.00      1.00      6534

Reporte para: whonet_AMP_NM
              precision    recall  f1-score   support

           I       0.67      0.12      0.21        16
           R       0.98      1.00      0.99       584
           S       1.00      1.00      1.00       947

    accuracy                           0.99      1547
   macro avg       0.88      0.71      0.73      1547
weighted avg       0.99      0.99      0.99      1547

Reporte para: whonet_ATM_NM
              precision    recall  f1-score   support

           I       0.91      1.00      0.95        10
           R       1.00      1.00      1.00       329
           S       1.00      1.00      1.00      1547

    accuracy                           1.00      1886
   macro avg       0.97      1.00      0.98      1886
weighted avg       1.00      1.00      1.00      1886

Reporte para: whonet_CAS_NM
              precision    recall  f1-score   support

           I       0.80      1.00      0.89         4
           R       0.89      1.00      0.94         8
           S       1.00      1.00      1.00       826

    accuracy                           1.00       838
   macro avg       0.90      1.00      0.94       838
weighted avg       1.00      1.00      1.00       838

Reporte para: whonet_CAZ_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00       272
           R       1.00      1.00      1.00       810
           S       1.00      1.00      1.00      5448

    accuracy                           1.00      6530
   macro avg       1.00      1.00      1.00      6530
weighted avg       1.00      1.00      1.00      6530

Reporte para: whonet_CIP_NM
              precision    recall  f1-score   support

           I       0.99      1.00      1.00       604
           R       1.00      1.00      1.00      2090
           S       1.00      1.00      1.00      5923

    accuracy                           1.00      8617
   macro avg       1.00      1.00      1.00      8617
weighted avg       1.00      1.00      1.00      8617


Reporte para: whonet_CLI_NM
              precision    recall  f1-score   support

           I       0.80      0.67      0.73         6
           R       0.99      1.00      1.00       155
           S       1.00      1.00      1.00       927

    accuracy                           1.00      1088
   macro avg       0.93      0.89      0.91      1088
weighted avg       1.00      1.00      1.00      1088

Reporte para: whonet_CPT_NM
              precision    recall  f1-score   support

           I       0.00      0.00      0.00         0
           R       1.00      1.00      1.00       550

    accuracy                           1.00       550
   macro avg       0.50      0.50      0.50       550
weighted avg       1.00      1.00      1.00       550

Reporte para: whonet_CRO_NM
              precision    recall  f1-score   support

           I       0.56      0.94      0.70        33
           R       1.00      0.98      0.99       815
           S       1.00      1.00      1.00      3150

    accuracy                           0.99      3998
   macro avg       0.85      0.97      0.90      3998
weighted avg       1.00      0.99      0.99      3998

Reporte para: whonet_CTX_NM
              precision    recall  f1-score   support

           I       0.27      1.00      0.42         4
           R       1.00      0.97      0.98       168
           S       1.00      0.99      1.00       814

    accuracy                           0.99       986
   macro avg       0.76      0.99      0.80       986
weighted avg       1.00      0.99      0.99       986

Reporte para: whonet_CZA_NM
              precision    recall  f1-score   support

           I       0.81      0.99      0.89       117
           R       1.00      0.98      0.99      1818

    accuracy                           0.99      1935
   macro avg       0.90      0.99      0.94      1935
weighted avg       0.99      0.99      0.99      1935

Reporte para: whonet_CZO_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00      1380
           R       1.00      1.00      1.00       510

    accuracy                           1.00      1890
   macro avg       1.00      1.00      1.00      1890
weighted avg       1.00      1.00      1.00      1890

Reporte para: whonet_CZT_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00        11
           R       1.00      1.00      1.00       207
           S       1.00      1.00      1.00      1743

    accuracy                           1.00      1961
   macro avg       1.00      1.00      1.00      1961
weighted avg       1.00      1.00      1.00      1961

Reporte para: whonet_DAP_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00       105
           R       1.00      1.00      1.00       376

    accuracy                           1.00       481
   macro avg       1.00      1.00      1.00       481
weighted avg       1.00      1.00      1.00       481

Reporte para: whonet_ERY_NM
              precision    recall  f1-score   support

           I       0.99      0.69      0.82       301
           R       0.90      1.00      0.95       849
           S       1.00      1.00      1.00      1074

    accuracy                           0.96      2224
   macro avg       0.96      0.90      0.92      2224
weighted avg       0.96      0.96      0.96      2224

Reporte para: whonet_ETP_NM
              precision    recall  f1-score   support

           I       1.00      0.95      0.97        19
           R       1.00      1.00      1.00       244
           S       1.00      1.00      1.00      5276

    accuracy                           1.00      5539
   macro avg       1.00      0.98      0.99      5539
weighted avg       1.00      1.00      1.00      5539

Reporte para: whonet_FEP_NM
              precision    recall  f1-score   support

           I       0.73      1.00      0.84       247
           R       1.00      0.87      0.93       697
           S       1.00      1.00      1.00      5515

    accuracy                           0.99      6459
   macro avg       0.91      0.96      0.93      6459
weighted avg       0.99      0.99      0.99      6459

Reporte para: whonet_FLU_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00         5
           R       1.00      1.00      1.00       102
           S       1.00      1.00      1.00       688

    accuracy                           1.00       795
   macro avg       1.00      1.00      1.00       795
weighted avg       1.00      1.00      1.00       795

Reporte para: whonet_FOS_NM
              precision    recall  f1-score   support

           I       0.11      1.00      0.20         9
           R       0.00      0.00      0.00        68
           S       1.00      1.00      1.00      1800

    accuracy                           0.96      1877
   macro avg       0.37      0.67      0.40      1877
weighted avg       0.96      0.96      0.96      1877

Reporte para: whonet_FOX_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00        44
           R       1.00      1.00      1.00        66
           S       1.00      1.00      1.00       713

    accuracy                           1.00       823
   macro avg       1.00      1.00      1.00       823
weighted avg       1.00      1.00      1.00       823

Reporte para: whonet_GEN_NM
              precision    recall  f1-score   support

           I       0.25      1.00      0.40        52
           R       1.00      0.79      0.88       750
           S       1.00      1.00      1.00      4278

    accuracy                           0.97      5080
   macro avg       0.75      0.93      0.76      5080
weighted avg       0.99      0.97      0.98      5080

Reporte para: whonet_IPM_NM
              precision    recall  f1-score   support

           I       1.00      0.98      0.99       200
           R       0.99      1.00      1.00       577
           S       1.00      1.00      1.00      2631

    accuracy                           1.00      3408
   macro avg       1.00      0.99      1.00      3408
weighted avg       1.00      1.00      1.00      3408

Reporte para: whonet_LNZ_NM
              precision    recall  f1-score   support

           I       0.50      1.00      0.67         7
           R       0.20      0.36      0.26        11
           S       1.00      0.99      1.00      2060

    accuracy                           0.99      2078
   macro avg       0.57      0.79      0.64      2078
weighted avg       0.99      0.99      0.99      2078

Reporte para: whonet_LVX_NM
              precision    recall  f1-score   support

           I       0.27      1.00      0.42        18
           R       1.00      0.68      0.81       152
           S       1.00      1.00      1.00      1377

    accuracy                           0.97      1547
   macro avg       0.76      0.89      0.74      1547
weighted avg       0.99      0.97      0.97      1547

Reporte para: whonet_MEM_NM
              precision    recall  f1-score   support

           I       0.88      0.98      0.93        47
           R       1.00      0.99      0.99       483
           S       1.00      1.00      1.00      6084

    accuracy                           1.00      6614
   macro avg       0.96      0.99      0.97      6614
weighted avg       1.00      1.00      1.00      6614

Reporte para: whonet_MIF_NM
              precision    recall  f1-score   support

           I       0.50      1.00      0.67         3
           R       0.00      0.00      0.00         0
           S       1.00      0.99      1.00       898

    accuracy                           0.99       901
   macro avg       0.50      0.66      0.55       901
weighted avg       1.00      0.99      1.00       901

Reporte para: whonet_NIT_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00       313
           R       0.99      1.00      1.00       113
           S       1.00      1.00      1.00      4242

    accuracy                           1.00      4668
   macro avg       1.00      1.00      1.00      4668
weighted avg       1.00      1.00      1.00      4668

Reporte para: whonet_NOR_NM
              precision    recall  f1-score   support

           I       0.24      0.41      0.30        59
           R       0.94      0.88      0.91       645
           S       1.00      1.00      1.00      2098

    accuracy                           0.96      2802
   macro avg       0.73      0.76      0.74      2802
weighted avg       0.97      0.96      0.96      2802

Reporte para: whonet_OXA_NM
              precision    recall  f1-score   support

           I       0.99      1.00      0.99       756
           R       1.00      0.99      0.99       709

    accuracy                           0.99      1465
   macro avg       0.99      0.99      0.99      1465
weighted avg       0.99      0.99      0.99      1465

Reporte para: whonet_PEN_NM
              precision    recall  f1-score   support

           I       0.67      1.00      0.80         4
           R       1.00      1.00      1.00        99
           S       1.00      1.00      1.00       588

    accuracy                           1.00       691
   macro avg       0.89      1.00      0.93       691
weighted avg       1.00      1.00      1.00       691

Reporte para: whonet_RIF_NM
              precision    recall  f1-score   support

           I       0.36      1.00      0.53        10
           R       1.00      0.61      0.76        46
           S       1.00      1.00      1.00       639

    accuracy                           0.97       695
   macro avg       0.79      0.87      0.76       695
weighted avg       0.99      0.97      0.98       695

Reporte para: whonet_SAM_NM
              precision    recall  f1-score   support

           I       0.41      0.91      0.56       707
           R       0.86      0.30      0.45      1332
           S       1.00      1.00      1.00      2883

    accuracy                           0.80      4922
   macro avg       0.76      0.74      0.67      4922
weighted avg       0.88      0.80      0.79      4922

Reporte para: whonet_SXT_NM
              precision    recall  f1-score   support

           I       0.67      1.00      0.80         2
           R       1.00      1.00      1.00      1262
           S       1.00      1.00      1.00      3349

    accuracy                           1.00      4613
   macro avg       0.89      1.00      0.93      4613
weighted avg       1.00      1.00      1.00      4613

Reporte para: whonet_TCY_NM
              precision    recall  f1-score   support

           I       0.04      0.80      0.08         5
           R       1.00      0.91      0.95       929
           S       1.00      0.99      1.00      1367

    accuracy                           0.96      2301
   macro avg       0.68      0.90      0.67      2301
weighted avg       1.00      0.96      0.98      2301

Reporte para: whonet_TGC_NM
              precision    recall  f1-score   support

           I       0.92      0.21      0.34        53
           R       0.53      0.98      0.69        48
           S       1.00      1.00      1.00      2355

    accuracy                           0.98      2456
   macro avg       0.81      0.73      0.67      2456
weighted avg       0.99      0.98      0.98      2456

Reporte para: whonet_TZP_NM
              precision    recall  f1-score   support

           I       0.79      0.99      0.88       148
           R       1.00      0.94      0.97       698
           S       1.00      1.00      1.00      2808

    accuracy                           0.99      3654
   macro avg       0.93      0.98      0.95      3654
weighted avg       0.99      0.99      0.99      3654

Reporte para: whonet_VAN_NM
              precision    recall  f1-score   support

           I       0.33      1.00      0.50         1
           R       1.00      0.94      0.97        16
           S       1.00      1.00      1.00      2060

    accuracy                           1.00      2077
   macro avg       0.78      0.98      0.82      2077
weighted avg       1.00      1.00      1.00      2077

Reporte para: whonet_VOR_NM
              precision    recall  f1-score   support

           I       0.97      0.98      0.98        62
           R       1.00      0.67      0.80         6
           S       1.00      1.00      1.00       729

    accuracy                           1.00       797
   macro avg       0.99      0.88      0.93       797
weighted avg       1.00      1.00      1.00       797


## Análisis de los resultados
Descripción de los resultados del modelo baseline, incluyendo fortalezas y debilidades del modelo.

Al realizar el analisis de los resultados se encuentra muy buenos resultados en la prediccion de las diferentes modelos en las categorias de SIR (sensibilidad, intermedio y resistente) para los diferentes antibioticos, con porcentajes por encima del 90%. No obstante, y a pesar de equilibrar y balancear  las categorias a predecir por medio de tecnicas especificas como Class Weighting, cuando los datos existentes se encontraban por debajo de 20 registro, esta porcentaje bajaba por debajo del 90% en su capacidad de predecir.  

## Conclusiones

Conclusiones generales sobre el rendimiento del modelo baseline y posibles áreas de mejora.

## Referencias
Lista de referencias utilizadas para construir el modelo baseline y evaluar su rendimiento.
No se utilizaron referencias para construir los modelos.

