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

## Conclusiones y Recomendaciones
En esta sección se presentarán las conclusiones y recomendaciones a partir de los resultados obtenidos. Se deben incluir los puntos fuertes y débiles del modelo, las limitaciones y los posibles escenarios de aplicación.

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

