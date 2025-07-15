# Reporte del Modelo Final

## Resumen Ejecutivo
En esta sección se presentará un resumen de los resultados obtenidos del modelo final. Es importante incluir los resultados de las métricas de evaluación y la interpretación de los mismos.



## Descripción del Problema
En esta sección se describirá el problema que se buscó resolver con el modelo final. Se debe incluir una descripción detallada del problema, el contexto en el que se desarrolla, los objetivos que se persiguen y la justificación del modelo.

El problema que se queria resolver con la construccion de este modelo era lograr convertir de forma automatica los valores de Concentracion Inhibitoria Minima (CIM) con la cual se reporta la accion de un antibiotico en diferentes microorganismos que normalmente se reporta en valores <0.001 a valores por encima de 256. En este sentido cada microorganimos presenta un rango de accion para cada antibiotico en donde se define si el microorganismo aislado por tecnicas de laboratorio presenta un perfil SIR,  Sensibilidad (el antibiotico es efectivo contra el microorganismo), Intermedio ( el antibiotico es efectivo parcialmente contra el microorganismo) y Resistente ( el antibiotico no es efectivo contra el microorganismos). Este modelo se desea construir debido  a que actualmente solo existe un software de la OMS que permite realizar analisis de perfiles de resistencia para instituciones de salud, el cual aunque realizar algunas analisis de forma automatic, no es totalmente personalizable los resultados, para ajustarlos a las necesidas de cada clinica u hospital.

## Descripción del Modelo
En esta sección se describirá el modelo final que se desarrolló para resolver el problema planteado. Se debe incluir una descripción detallada del modelo, la metodología utilizada y las técnicas empleadas.

La busqueda del modelo final para resolver el problema se realizo por medio de la libreria Optuna (busqueda bayesina) en donde se exploraron los siguientes hiperparametros: 

* n_layers = trial.suggest_int("n_layers", 1, 10)
* n_neurons = trial.suggest_categorical("n_neurons", [32, 64, 128, 256, 512])
* dropout_rate = trial.suggest_float("dropout_rate", 0.1 ,0.5)
* learning_rate = trial.suggest_loguniform("learning_rate", 1e-4, 1e-1)
* optimizer_name = trial.suggest_categorical("optimizer", ["adam", "rmsprop", "nadam"])
* batch_size = trial.suggest_categorical("batch_size", [16, 32, 64])

El modelo final definido es:  
Es una red neuronal profunda con las siguientes caracteristicas: 

*  Numero de capas: 2.
*  Numero de neuronas: 32
*  Tasa de Dropout :  0.181659756855986.
*  Tasa de aprendizaje: 0.0005788366781029293.
*  Optimizador : Adam.
*  Batch size: 64

## Evaluación del Modelo
En esta sección se presentará una evaluación detallada del modelo final. Se deben incluir las métricas de evaluación que se utilizaron y una interpretación detallada de los resultados.

LOCAL_ORG  AMK_NM pred_labels  pred_ids etiquetas etiquetas_predichas
28723         31    16.0           R         1         R                   R
16154         47     2.0           S         2         S                   S
42942         25     8.0           I         0         I                   I
15768         24     1.0           S         2         S                   S
6213          25     2.0           S         2         S                   S
✅ Accuracy: 0.9985

📊 Matriz de Confusión:
[[  72    9    0]
 [   0  325    0]
 [   0    1 6127]]


Reporte para: whonet_AMK_NM
              precision    recall  f1-score   support

           I       1.00      0.89      0.94        81
           R       0.97      1.00      0.98       325
           S       1.00      1.00      1.00      6128

    accuracy                           1.00      6534
   macro avg       0.99      0.96      0.98      6534
weighted avg       1.00      1.00      1.00      6534

       LOCAL_ORG  AMP_NM pred_labels  pred_ids etiquetas etiquetas_predichas
7568           3    2.00           S         2         S                   S
19013          8    2.00           S         2         S                   S
14836         20    0.25           I         0         S                   S
4185           3    2.00           S         2         S                   S
30387          0    2.00           S         2         S                   S
✅ Accuracy: 0.9903

📊 Matriz de Confusión:
[[  2  14   0]
 [  0 584   0]
 [  1   0 946]]

Reporte para: whonet_AMP_NM
              precision    recall  f1-score   support

           I       0.67      0.12      0.21        16
           R       0.98      1.00      0.99       584
           S       1.00      1.00      1.00       947

    accuracy                           0.99      1547
   macro avg       0.88      0.71      0.73      1547
weighted avg       0.99      0.99      0.99      1547

       LOCAL_ORG  ATM_NM pred_labels  pred_ids etiquetas etiquetas_predichas
13721         20     1.0           S         2         S                   S
14688         16     1.0           S         2         S                   S
37018         21    32.0           R         1         R                   R
16901         26     1.0           S         2         S                   S
20012          8     1.0           S         2         S                   S
✅ Accuracy: 0.9995

📊 Matriz de Confusión:
[[  10    0    0]
 [   0  329    0]
 [   1    0 1546]]

Reporte para: whonet_ATM_NM
              precision    recall  f1-score   support

           I       0.91      1.00      0.95        10
           R       1.00      1.00      1.00       329
           S       1.00      1.00      1.00      1547

    accuracy                           1.00      1886
   macro avg       0.97      1.00      0.98      1886
weighted avg       1.00      1.00      1.00      1886

       LOCAL_ORG  CAS_NM pred_labels  pred_ids etiquetas etiquetas_predichas
23101          0    0.12           S         2         S                   S
45133          0    0.12           S         2         S                   S
21200          2    2.00           S         2         S                   S
4418           0    0.12           S         2         S                   S
20875          0    0.12           S         2         S                   S
✅ Accuracy: 0.9976

📊 Matriz de Confusión:
[[  4   0   0]
 [  0   8   0]
 [  1   1 824]]

Reporte para: whonet_CAS_NM
              precision    recall  f1-score   support

           I       0.80      1.00      0.89         4
           R       0.89      1.00      0.94         8
           S       1.00      1.00      1.00       826

    accuracy                           1.00       838
   macro avg       0.90      1.00      0.94       838
weighted avg       1.00      1.00      1.00       838

       LOCAL_ORG  CAZ_NM pred_labels  pred_ids etiquetas etiquetas_predichas
48316         29    1.00           S         2         S                   S
4290          23    1.00           S         2         S                   S
43213         22    0.25           S         2         S                   S
47441         23    0.12           S         2         S                   S
27790         45    2.00           S         2         S                   S
✅ Accuracy: 0.9998

📊 Matriz de Confusión:
[[ 272    0    0]
 [   0  810    0]
 [   1    0 5447]]

Reporte para: whonet_CAZ_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00       272
           R       1.00      1.00      1.00       810
           S       1.00      1.00      1.00      5448

    accuracy                           1.00      6530
   macro avg       1.00      1.00      1.00      6530
weighted avg       1.00      1.00      1.00      6530

       LOCAL_ORG  CIP_NM pred_labels  pred_ids etiquetas etiquetas_predichas
44571         44    0.25           S         2         S                   S
14220         39    0.06           S         2         S                   S
34337         29    0.50           I         0         I                   I
20299          3    0.25           S         2         S                   S
43333         72    4.00           R         1         R                   R
✅ Accuracy: 0.9991

📊 Matriz de Confusión:
[[ 603    0    1]
 [   4 2084    2]
 [   1    0 5922]]

Reporte para: whonet_CIP_NM
              precision    recall  f1-score   support

           I       0.99      1.00      1.00       604
           R       1.00      1.00      1.00      2090
           S       1.00      1.00      1.00      5923

    accuracy                           1.00      8617
   macro avg       1.00      1.00      1.00      8617
weighted avg       1.00      1.00      1.00      8617

       LOCAL_ORG  CLI_NM pred_labels  pred_ids etiquetas etiquetas_predichas
30195          0    0.25           S         2         S                   S
44092          0    0.25           S         2         S                   S
20312          5    0.12           S         2         S                   S
29475          0    0.25           S         2         S                   S
7119           0    0.25           S         2         S                   S
✅ Accuracy: 0.9972

📊 Matriz de Confusión:
[[  4   1   1]
 [  0 155   0]
 [  1   0 926]]

Reporte para: whonet_CLI_NM
              precision    recall  f1-score   support

           I       0.80      0.67      0.73         6
           R       0.99      1.00      1.00       155
           S       1.00      1.00      1.00       927

    accuracy                           1.00      1088
   macro avg       0.93      0.89      0.91      1088
weighted avg       1.00      1.00      1.00      1088

       LOCAL_ORG  CPT_NM pred_labels  pred_ids etiquetas etiquetas_predichas
24728          0    0.50           R         1         R                   R
18707          0    0.25           R         1         R                   R
37495          0    0.50           R         1         R                   R
38520          0    0.25           R         1         R                   R
8033           0    0.25           R         1         R                   R
✅ Accuracy: 0.9964

📊 Matriz de Confusión:
[[  0   0   0]
 [  2 548   0]
 [  0   0   0]]

Reporte para: whonet_CPT_NM
              precision    recall  f1-score   support

           I       0.00      0.00      0.00         0
           R       1.00      1.00      1.00       550

    accuracy                           1.00       550
   macro avg       0.50      0.50      0.50       550
weighted avg       1.00      1.00      1.00       550

       LOCAL_ORG  CRO_NM pred_labels  pred_ids etiquetas etiquetas_predichas
10828         19    0.25           S         2         S                   S
25262         19    0.25           S         2         S                   S
4449          50    0.25           S         2         S                   S
22662         19    0.25           S         2         S                   S
29959         25    1.00           S         2         S                   S
✅ Accuracy: 0.9932

📊 Matriz de Confusión:
[[  31    2    0]
 [  16  799    0]
 [   8    1 3141]]

Reporte para: whonet_CRO_NM
              precision    recall  f1-score   support

           I       0.56      0.94      0.70        33
           R       1.00      0.98      0.99       815
           S       1.00      1.00      1.00      3150

    accuracy                           0.99      3998
   macro avg       0.85      0.97      0.90      3998
weighted avg       1.00      0.99      0.99      3998

       LOCAL_ORG  CTX_NM pred_labels  pred_ids etiquetas etiquetas_predichas
16735         10     1.0           S         2         S                   S
37022         10     1.0           S         2         S                   S
24933         10     1.0           S         2         S                   S
21981         10     1.0           S         2         S                   S
7531          10    32.0           R         1         R                   R
✅ Accuracy: 0.9888

📊 Matriz de Confusión:
[[  4   0   0]
 [  5 163   0]
 [  6   0 808]]

Reporte para: whonet_CTX_NM
              precision    recall  f1-score   support

           I       0.27      1.00      0.42         4
           R       1.00      0.97      0.98       168
           S       1.00      0.99      1.00       814

    accuracy                           0.99       986
   macro avg       0.76      0.99      0.80       986
weighted avg       1.00      0.99      0.99       986

       LOCAL_ORG  CZA_NM pred_labels  pred_ids etiquetas etiquetas_predichas
45891         11    0.12           R         1         R                   R
3039          15    0.12           R         1         R                   R
5854          10    0.25           R         1         R                   R
40532         29    2.00           R         1         R                   R
24839         29    2.00           R         1         R                   R
✅ Accuracy: 0.9850

📊 Matriz de Confusión:
[[ 116    1    0]
 [  28 1790    0]
 [   0    0    0]]

Reporte para: whonet_CZA_NM
              precision    recall  f1-score   support

           I       0.81      0.99      0.89       117
           R       1.00      0.98      0.99      1818

    accuracy                           0.99      1935
   macro avg       0.90      0.99      0.94      1935
weighted avg       0.99      0.99      0.99      1935

       LOCAL_ORG  CZO_NM pred_labels  pred_ids etiquetas etiquetas_predichas
14851          6    32.0           R         1         R                   R
42903          6     4.0           I         0         I                   I
3790          14     4.0           I         0         I                   I
8571           6     8.0           R         1         R                   R
6031           9     4.0           I         0         I                   I
✅ Accuracy: 1.0000

📊 Matriz de Confusión:
[[1380    0    0]
 [   0  510    0]
 [   0    0    0]]

Reporte para: whonet_CZO_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00      1380
           R       1.00      1.00      1.00       510

    accuracy                           1.00      1890
   macro avg       1.00      1.00      1.00      1890
weighted avg       1.00      1.00      1.00      1890

       LOCAL_ORG  CZT_NM pred_labels  pred_ids etiquetas etiquetas_predichas
31814         11    0.25           S         2         S                   S
38643         13    0.25           S         2         S                   S
19899          4   16.00           R         1         R                   R
14133         10    0.25           S         2         S                   S
14368         14    0.25           S         2         S                   S
✅ Accuracy: 1.0000

📊 Matriz de Confusión:
[[  11    0    0]
 [   0  207    0]
 [   0    0 1743]]

Reporte para: whonet_CZT_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00        11
           R       1.00      1.00      1.00       207
           S       1.00      1.00      1.00      1743

    accuracy                           1.00      1961
   macro avg       1.00      1.00      1.00      1961
weighted avg       1.00      1.00      1.00      1961

       LOCAL_ORG  DAP_NM pred_labels  pred_ids etiquetas etiquetas_predichas
12967          0     2.0           R         1         R                   R
2232           0     4.0           I         0         I                   I
30316          0     2.0           R         1         R                   R
33579          0     2.0           R         1         R                   R
13891          0     2.0           R         1         R                   R
✅ Accuracy: 1.0000

📊 Matriz de Confusión:
[[105   0   0]
 [  0 376   0]
 [  0   0   0]]

Reporte para: whonet_DAP_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00       105
           R       1.00      1.00      1.00       376

    accuracy                           1.00       481
   macro avg       1.00      1.00      1.00       481
weighted avg       1.00      1.00      1.00       481

       LOCAL_ORG  ERY_NM pred_labels  pred_ids etiquetas etiquetas_predichas
7018           3    4.00           R         1         I                   I
14722          4    4.00           R         1         R                   R
21728          3    0.50           S         2         S                   S
39495          6    0.25           S         2         S                   S
32723          6    4.00           R         1         R                   R
✅ Accuracy: 0.9577

📊 Matriz de Confusión:
[[ 209   92    0]
 [   2  847    0]
 [   0    0 1074]]

Reporte para: whonet_ERY_NM
              precision    recall  f1-score   support

           I       0.99      0.69      0.82       301
           R       0.90      1.00      0.95       849
           S       1.00      1.00      1.00      1074

    accuracy                           0.96      2224
   macro avg       0.96      0.90      0.92      2224
weighted avg       0.96      0.96      0.96      2224

       LOCAL_ORG  ETP_NM pred_labels  pred_ids etiquetas etiquetas_predichas
46159         11    0.50           S         2         S                   S
18054         16    0.12           S         2         S                   S
22652         17    0.12           S         2         S                   S
38766         17    0.50           S         2         S                   S
20240         11    0.12           S         2         S                   S
✅ Accuracy: 0.9998

📊 Matriz de Confusión:
[[  18    1    0]
 [   0  244    0]
 [   0    0 5276]]

Reporte para: whonet_ETP_NM
              precision    recall  f1-score   support

           I       1.00      0.95      0.97        19
           R       1.00      1.00      1.00       244
           S       1.00      1.00      1.00      5276

    accuracy                           1.00      5539
   macro avg       1.00      0.98      0.99      5539
weighted avg       1.00      1.00      1.00      5539

       LOCAL_ORG  FEP_NM pred_labels  pred_ids etiquetas etiquetas_predichas
2540          24     1.0           S         2         S                   S
44796         46     2.0           S         2         S                   S
19957         46    16.0           I         0         R                   R
42260         30    32.0           R         1         R                   R
37548         46     1.0           S         2         S                   S
✅ Accuracy: 0.9859

📊 Matriz de Confusión:
[[ 247    0    0]
 [  90  607    0]
 [   1    0 5514]]

Reporte para: whonet_FEP_NM
              precision    recall  f1-score   support

           I       0.73      1.00      0.84       247
           R       1.00      0.87      0.93       697
           S       1.00      1.00      1.00      5515

    accuracy                           0.99      6459
   macro avg       0.91      0.96      0.93      6459
weighted avg       0.99      0.99      0.99      6459

       LOCAL_ORG  FLU_NM pred_labels  pred_ids etiquetas etiquetas_predichas
37150          0     0.5           S         2         S                   S
24636          0     0.5           S         2         S                   S
33589          0     0.5           S         2         S                   S
24452          1    32.0           R         1         R                   R
37752          1     0.5           S         2         S                   S
✅ Accuracy: 1.0000

📊 Matriz de Confusión:
[[  5   0   0]
 [  0 102   0]
 [  0   0 688]]

Reporte para: whonet_FLU_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00         5
           R       1.00      1.00      1.00       102
           S       1.00      1.00      1.00       688

    accuracy                           1.00       795
   macro avg       1.00      1.00      1.00       795
weighted avg       1.00      1.00      1.00       795

       LOCAL_ORG  FOS_NM pred_labels  pred_ids etiquetas etiquetas_predichas
12736          0    16.0           S         2         S                   S
24924          0    32.0           S         2         S                   S
7320           0    16.0           S         2         S                   S
9827           0    16.0           S         2         S                   S
31588          0    16.0           S         2         S                   S
✅ Accuracy: 0.9606

📊 Matriz de Confusión:
[[   9    0    0]
 [  68    0    0]
 [   6    0 1794]]

Reporte para: whonet_FOS_NM
              precision    recall  f1-score   support

           I       0.11      1.00      0.20         9
           R       0.00      0.00      0.00        68
           S       1.00      1.00      1.00      1800

    accuracy                           0.96      1877
   macro avg       0.37      0.67      0.40      1877
weighted avg       0.96      0.96      0.96      1877

       LOCAL_ORG  FOX_NM pred_labels  pred_ids etiquetas etiquetas_predichas
1166           8    16.0           I         0         I                   I
1598           6     4.0           S         2         S                   S
36026          6     4.0           S         2         S                   S
8776          13     4.0           S         2         S                   S
40943          9     4.0           S         2         S                   S
✅ Accuracy: 1.0000

📊 Matriz de Confusión:
[[ 44   0   0]
 [  0  66   0]
 [  0   0 713]]

Reporte para: whonet_FOX_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00        44
           R       1.00      1.00      1.00        66
           S       1.00      1.00      1.00       713

    accuracy                           1.00       823
   macro avg       1.00      1.00      1.00       823
weighted avg       1.00      1.00      1.00       823

       LOCAL_ORG  GEN_NM pred_labels  pred_ids etiquetas etiquetas_predichas
32884         22     1.0           S         2         S                   S
25227         22     1.0           S         2         S                   S
3932          43     1.0           S         2         S                   S
10750         22     1.0           S         2         S                   S
42873         54     0.5           S         2         S                   S
✅ Accuracy: 0.9691

📊 Matriz de Confusión:
[[  52    0    0]
 [ 156  594    0]
 [   1    0 4277]]

Reporte para: whonet_GEN_NM
              precision    recall  f1-score   support

           I       0.25      1.00      0.40        52
           R       1.00      0.79      0.88       750
           S       1.00      1.00      1.00      4278

    accuracy                           0.97      5080
   macro avg       0.75      0.93      0.76      5080
weighted avg       0.99      0.97      0.98      5080

       LOCAL_ORG  IPM_NM pred_labels  pred_ids etiquetas etiquetas_predichas
22499         30    0.25           S         2         S                   S
11378         44    8.00           R         1         R                   R
45340          8    1.00           S         2         S                   S
9298          44    1.00           S         2         S                   S
20805         44    8.00           R         1         R                   R
✅ Accuracy: 0.9988

📊 Matriz de Confusión:
[[ 197    3    0]
 [   0  577    0]
 [   0    1 2630]]

Reporte para: whonet_IPM_NM
              precision    recall  f1-score   support

           I       1.00      0.98      0.99       200
           R       0.99      1.00      1.00       577
           S       1.00      1.00      1.00      2631

    accuracy                           1.00      3408
   macro avg       1.00      0.99      1.00      3408
weighted avg       1.00      1.00      1.00      3408

       LOCAL_ORG  LNZ_NM pred_labels  pred_ids etiquetas etiquetas_predichas
44118          6     2.0           S         2         S                   S
30280          4     2.0           S         2         S                   S
19407          6     2.0           S         2         S                   S
33027         12     1.0           S         2         S                   S
27345          6     2.0           S         2         S                   S
✅ Accuracy: 0.9889

📊 Matriz de Confusión:
[[   7    0    0]
 [   7    4    0]
 [   0   16 2044]]

Reporte para: whonet_LNZ_NM
              precision    recall  f1-score   support

           I       0.50      1.00      0.67         7
           R       0.20      0.36      0.26        11
           S       1.00      0.99      1.00      2060

    accuracy                           0.99      2078
   macro avg       0.57      0.79      0.64      2078
weighted avg       0.99      0.99      0.99      2078

       LOCAL_ORG  LVX_NM pred_labels  pred_ids etiquetas etiquetas_predichas
11406         19    0.50           S         2         S                   S
4241           3    0.25           S         2         S                   S
25064          3    0.25           S         2         S                   S
23559          3    1.00           S         2         S                   S
41240          3    1.00           S         2         S                   S
✅ Accuracy: 0.9683

📊 Matriz de Confusión:
[[  18    0    0]
 [  49  103    0]
 [   0    0 1377]]

Reporte para: whonet_LVX_NM
              precision    recall  f1-score   support

           I       0.27      1.00      0.42        18
           R       1.00      0.68      0.81       152
           S       1.00      1.00      1.00      1377

    accuracy                           0.97      1547
   macro avg       0.76      0.89      0.74      1547
weighted avg       0.99      0.97      0.97      1547

       LOCAL_ORG  MEM_NM pred_labels  pred_ids etiquetas etiquetas_predichas
48987         24    0.25           S         2         S                   S
21212          9    2.00           S         2         S                   S
39618         39    0.25           S         2         S                   S
33903         39    0.25           S         2         S                   S
8718          39    0.25           S         2         S                   S
✅ Accuracy: 0.9988

📊 Matriz de Confusión:
[[  46    0    1]
 [   6  476    1]
 [   0    0 6084]]

Reporte para: whonet_MEM_NM
              precision    recall  f1-score   support

           I       0.88      0.98      0.93        47
           R       1.00      0.99      0.99       483
           S       1.00      1.00      1.00      6084

    accuracy                           1.00      6614
   macro avg       0.96      0.99      0.97      6614
weighted avg       1.00      1.00      1.00      6614

       LOCAL_ORG  MIF_NM pred_labels  pred_ids etiquetas etiquetas_predichas
27520          0    0.06           S         2         S                   S
40480          0    0.06           S         2         S                   S
44068          0    0.06           S         2         S                   S
42314          3    0.06           S         2         S                   S
12106          0    0.06           S         2         S                   S
✅ Accuracy: 0.9945

📊 Matriz de Confusión:
[[  3   0   0]
 [  0   0   0]
 [  3   2 893]]

Reporte para: whonet_MIF_NM
              precision    recall  f1-score   support

           I       0.50      1.00      0.67         3
           R       0.00      0.00      0.00         0
           S       1.00      0.99      1.00       898

    accuracy                           0.99       901
   macro avg       0.50      0.66      0.55       901
weighted avg       1.00      0.99      1.00       901

       LOCAL_ORG  NIT_NM pred_labels  pred_ids etiquetas etiquetas_predichas
5727          15    16.0           S         2         S                   S
16182         40    16.0           S         2         S                   S
48790         30    16.0           S         2         S                   S
25113         15    16.0           S         2         S                   S
49203         15    16.0           S         2         S                   S
✅ Accuracy: 0.9996

📊 Matriz de Confusión:
[[ 312    1    0]
 [   0  113    0]
 [   1    0 4241]]

Reporte para: whonet_NIT_NM
              precision    recall  f1-score   support

           I       1.00      1.00      1.00       313
           R       0.99      1.00      1.00       113
           S       1.00      1.00      1.00      4242

    accuracy                           1.00      4668
   macro avg       1.00      1.00      1.00      4668
weighted avg       1.00      1.00      1.00      4668

       LOCAL_ORG  NOR_NM pred_labels  pred_ids etiquetas etiquetas_predichas
21808         29     0.5           S         2         S                   S
36966         17     8.0           R         1         R                   R
12898         17     2.0           S         2         S                   S
2915          20     2.0           S         2         S                   S
3439          17     2.0           S         2         S                   S
✅ Accuracy: 0.9597

📊 Matriz de Confusión:
[[  24   35    0]
 [  78  567    0]
 [   0    0 2098]]

Reporte para: whonet_NOR_NM
              precision    recall  f1-score   support

           I       0.24      0.41      0.30        59
           R       0.94      0.88      0.91       645
           S       1.00      1.00      1.00      2098

    accuracy                           0.96      2802
   macro avg       0.73      0.76      0.74      2802
weighted avg       0.97      0.96      0.96      2802

       LOCAL_ORG  OXA_NM pred_labels  pred_ids etiquetas etiquetas_predichas
25006          4    2.00           I         0         I                   I
9367           4    0.25           R         1         R                   R
29724          0    2.00           I         0         I                   I
24422          0    2.00           I         0         I                   I
41628          0    2.00           I         0         I                   I
✅ Accuracy: 0.9945

📊 Matriz de Confusión:
[[755   1   0]
 [  7 702   0]
 [  0   0   0]]

Reporte para: whonet_OXA_NM
              precision    recall  f1-score   support

           I       0.99      1.00      0.99       756
           R       1.00      0.99      0.99       709

    accuracy                           0.99      1465
   macro avg       0.99      0.99      0.99      1465
weighted avg       0.99      0.99      0.99      1465

       LOCAL_ORG  PEN_NM pred_labels  pred_ids etiquetas etiquetas_predichas
6511           3     4.0           S         2         S                   S
788            3     1.0           S         2         S                   S
16871          3     8.0           S         2         S                   S
30821          3     4.0           S         2         S                   S
7028           3     2.0           S         2         S                   S
✅ Accuracy: 0.9971

📊 Matriz de Confusión:
[[  4   0   0]
 [  0  99   0]
 [  2   0 586]]

Reporte para: whonet_PEN_NM
              precision    recall  f1-score   support

           I       0.67      1.00      0.80         4
           R       1.00      1.00      1.00        99
           S       1.00      1.00      1.00       588

    accuracy                           1.00       691
   macro avg       0.89      1.00      0.93       691
weighted avg       1.00      1.00      1.00       691

       LOCAL_ORG  RIF_NM pred_labels  pred_ids etiquetas etiquetas_predichas
47055          0     0.5           S         2         S                   S
22839          0     0.5           S         2         S                   S
10754          5     0.5           S         2         S                   S
48405          3     0.5           S         2         S                   S
2467           4     2.0           R         1         R                   R
✅ Accuracy: 0.9741

📊 Matriz de Confusión:
[[ 10   0   0]
 [ 18  28   0]
 [  0   0 639]]

Reporte para: whonet_RIF_NM
              precision    recall  f1-score   support

           I       0.36      1.00      0.53        10
           R       1.00      0.61      0.76        46
           S       1.00      1.00      1.00       639

    accuracy                           0.97       695
   macro avg       0.79      0.87      0.76       695
weighted avg       0.99      0.97      0.98       695

       LOCAL_ORG  SAM_NM pred_labels  pred_ids etiquetas etiquetas_predichas
9501          11     4.0           S         2         S                   S
23475          7     2.0           S         2         S                   S
49358          7    16.0           I         0         R                   R
36317         18     2.0           S         2         S                   S
18571          7    16.0           I         0         I                   I
✅ Accuracy: 0.7978

📊 Matriz de Confusión:
[[ 642   65    0]
 [ 930  402    0]
 [   0    0 2883]]

Reporte para: whonet_SAM_NM
              precision    recall  f1-score   support

           I       0.41      0.91      0.56       707
           R       0.86      0.30      0.45      1332
           S       1.00      1.00      1.00      2883

    accuracy                           0.80      4922
   macro avg       0.76      0.74      0.67      4922
weighted avg       0.88      0.80      0.79      4922

       LOCAL_ORG  SXT_NM pred_labels  pred_ids etiquetas etiquetas_predichas
481           50     0.5           S         2         S                   S
24940         19     8.0           R         1         R                   R
2934          19     8.0           R         1         R                   R
6648          50     0.5           S         2         S                   S
45866         50     0.5           S         2         S                   S
✅ Accuracy: 0.9996

📊 Matriz de Confusión:
[[   2    0    0]
 [   0 1262    0]
 [   1    1 3347]]

Reporte para: whonet_SXT_NM
              precision    recall  f1-score   support

           I       0.67      1.00      0.80         2
           R       1.00      1.00      1.00      1262
           S       1.00      1.00      1.00      3349

    accuracy                           1.00      4613
   macro avg       0.89      1.00      0.93      4613
weighted avg       1.00      1.00      1.00      4613

       LOCAL_ORG  TCY_NM pred_labels  pred_ids etiquetas etiquetas_predichas
46048          6     1.0           S         2         S                   S
26288         10     2.0           S         2         S                   S
23830         16     1.0           S         2         S                   S
20540          3     8.0           R         1         R                   R
28084          6     1.0           S         2         S                   S
✅ Accuracy: 0.9578

📊 Matriz de Confusión:
[[   4    1    0]
 [  83  846    0]
 [  13    0 1354]]

Reporte para: whonet_TCY_NM
              precision    recall  f1-score   support

           I       0.04      0.80      0.08         5
           R       1.00      0.91      0.95       929
           S       1.00      0.99      1.00      1367

    accuracy                           0.96      2301
   macro avg       0.68      0.90      0.67      2301
weighted avg       1.00      0.96      0.98      2301

       LOCAL_ORG  TGC_NM pred_labels  pred_ids etiquetas etiquetas_predichas
5371          11     0.5           S         2         S                   S
40184         16     0.5           S         2         S                   S
3147          29     0.5           S         2         S                   S
7779          11     0.5           S         2         S                   S
33914          1     0.5           S         2         S                   S
✅ Accuracy: 0.9825

📊 Matriz de Confusión:
[[  11   42    0]
 [   1   47    0]
 [   0    0 2355]]

Reporte para: whonet_TGC_NM
              precision    recall  f1-score   support

           I       0.92      0.21      0.34        53
           R       0.53      0.98      0.69        48
           S       1.00      1.00      1.00      2355

    accuracy                           0.98      2456
   macro avg       0.81      0.73      0.67      2456
weighted avg       0.99      0.98      0.98      2456

       LOCAL_ORG  TZP_NM pred_labels  pred_ids etiquetas etiquetas_predichas
24810         24     4.0           S         2         S                   S
25170         24     4.0           S         2         S                   S
45141         24     4.0           S         2         S                   S
39748         43     8.0           S         2         S                   S
28219         43    64.0           R         1         R                   R
✅ Accuracy: 0.9888

📊 Matriz de Confusión:
[[ 147    0    1]
 [  40  658    0]
 [   0    0 2808]]

Reporte para: whonet_TZP_NM
              precision    recall  f1-score   support

           I       0.79      0.99      0.88       148
           R       1.00      0.94      0.97       698
           S       1.00      1.00      1.00      2808

    accuracy                           0.99      3654
   macro avg       0.93      0.98      0.95      3654
weighted avg       0.99      0.99      0.99      3654

       LOCAL_ORG  VAN_NM pred_labels  pred_ids etiquetas etiquetas_predichas
49925          4     1.0           S         2         S                   S
4438           8     2.0           S         2         S                   S
2193           4     0.5           S         2         S                   S
43616         14     0.5           S         2         S                   S
29547          2     2.0           S         2         S                   S
✅ Accuracy: 0.9990

📊 Matriz de Confusión:
[[   1    0    0]
 [   1   15    0]
 [   1    0 2059]]

Reporte para: whonet_VAN_NM
              precision    recall  f1-score   support

           I       0.33      1.00      0.50         1
           R       1.00      0.94      0.97        16
           S       1.00      1.00      1.00      2060

    accuracy                           1.00      2077
   macro avg       0.78      0.98      0.82      2077
weighted avg       1.00      1.00      1.00      2077

       LOCAL_ORG  VOR_NM pred_labels  pred_ids etiquetas etiquetas_predichas
12204          0    0.12           S         2         S                   S
41180          2    0.12           S         2         S                   S
20412          0    0.12           S         2         S                   S
40121          1    0.12           S         2         S                   S
33724          0    0.12           S         2         S                   S
✅ Accuracy: 0.9962

📊 Matriz de Confusión:
[[ 61   0   1]
 [  2   4   0]
 [  0   0 729]]

Reporte para: whonet_VOR_NM
              precision    recall  f1-score   support

           I       0.97      0.98      0.98        62
           R       1.00      0.67      0.80         6
           S       1.00      1.00      1.00       729

    accuracy                           1.00       797
   macro avg       0.99      0.88      0.93       797
weighted avg       1.00      1.00      1.00       797


El modelo tiene un rendimiento excelente en términos generales para la mayoria de antibioticos y modelos, impulsado por su desempeño casi perfecto en la clase mayoritaria (S) y muy bueno en la clase R.
Sin embargo, muestra una debilidad en la mayoria de modelos  en la clase minoritaria I, donde si bien no comete falsos positivos, deja de detectar una parte significativa de los casos reales. En algunos casos, la clase minoritaria es la clase R, y apesar de utilizar tecnicas para balancear las clases, el bajo numero afecta la prediccion.

## Conclusiones y Recomendaciones
En esta sección se presentarán las conclusiones y recomendaciones a partir de los resultados obtenidos. Se deben incluir los puntos fuertes y débiles del modelo, las limitaciones y los posibles escenarios de aplicación.

Conclusiones generales sobre el rendimiento del modelo final y posibles áreas de mejora.

Dentro de las principales conclusiones sobre el rendimiento del modelo encontramos : 
* Los modelos depende principalmente de la calidad de la variable objetivo y el volumen de los datos de entrenamiento para obtener excelentes resultados.
* Es necesario contar con datos balanceados para obtener excelentes resultados.
* Baja capacidad para predecir las categorias minoritarias R e I en algunos modelos.
* En general, nuestros modelos presentaron un muy buen rendimeinto para predecir categorias SIR para cada atb y microorganismo.
* La busqueda del mejor modelo se realizo por medio de la implemtacion de la libreria optuna directamente.
* Su uso principalmente seria en instituciones de salud publicas y privadas, entidades de salud gubernamentales a nivel local y nacional.

## Referencias
En esta sección se deben incluir las referencias bibliográficas y fuentes de información utilizadas en el desarrollo del modelo.

🔢 NumPy
Harris, C. R., Millman, K. J., van der Walt, S. J., Gommers, R., Virtanen, P., Cournapeau, D., ... & Oliphant, T. E. (2020). Array programming with NumPy. Nature, 585(7825), 357–362.
https://doi.org/10.1038/s41586-020-2649-2

📊 Pandas
McKinney, W. (2010). Data structures for statistical computing in Python. In Proceedings of the 9th Python in Science Conference (Vol. 445, pp. 51–56).
https://doi.org/10.25080/Majora-92bf1922-00a

🧠 Scikit-learn
Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., ... & Duchesnay, É. (2011). Scikit-learn: Machine learning in Python. Journal of Machine Learning Research, 12, 2825–2830.
http://www.jmlr.org/papers/v12/pedregosa11a.html

🔬 Matplotlib
Hunter, J. D. (2007). Matplotlib: A 2D graphics environment. Computing in Science & Engineering, 9(3), 90–95.
https://doi.org/10.1109/MCSE.2007.55

📈 Seaborn
Waskom, M. L. (2021). Seaborn: Statistical data visualization. Journal of Open Source Software, 6(60), 3021.
https://doi.org/10.21105/joss.03021

🧮 TensorFlow
Abadi, M., Agarwal, A., Barham, P., Brevdo, E., Chen, Z., Citro, C., ... & Zheng, X. (2016). TensorFlow: Large-scale machine learning on heterogeneous systems. https://www.tensorflow.org
[White paper: https://arxiv.org/abs/1603.04467]

