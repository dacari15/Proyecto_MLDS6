# Informe de salida

## Resumen Ejecutivo

Este informe describe los resultados del proyecto de machine learning y presenta los principales logros y lecciones aprendidas durante el proceso.

## Resultados del proyecto

- Resumen de los entregables y logros alcanzados en cada etapa del proyecto:
  Dentro de los principales entregables encontramos:
  - Las diferentes fases de documentacion ( entendimiento del negocio, datos, desallorro, modelado, etc).
  - Scripts o codigo de cada una de las fases.
    
- Evaluación del modelo final y comparación con el modelo base.
  - En nuestro caso nuestro modelo base se contruyo por medio de busqueda de hiperparametros usando optuna, el cual nos permitio construir el mejor modelo final.
      
- Descripción de los resultados y su relevancia para el negocio.
  Nuestros resultados son muy buenos para la mayoria de modelos construidos para cada antiobiotico, los cuales permite caractetizar de forma adecuada el perfil de resistencia de la mayoria  de microorganismos en las categorias SIR (Sensible, intermedio y resistente).

## Lecciones aprendidas

- Identificación de los principales desafíos y obstáculos encontrados durante el proyecto.
  - Dentro de los principales desafios encontramos:
    La falta de informacion de calidad para poder entrenar nuestros modelos.
    La dificultad de no poder contar con un modelo unico que sea generalizables para cada antibiotico, por lo cual fue necesario construir un modelo por cada antibitoico.
    La necesidad de realizar un preprocesamiento completo para obtener una base de datos en condiciones, para poder entrenar los diferentes modelos.
  - Dentro de los principales obstaculos encontramos:
    Dificultad de contar con datos etiquetados, por lo cual fue necesario construir un algoritmo capaz de realizar la transformacion de CIM a SIR, para poder utilizar los datos en un modelo de deep learning.
    Los datos de whonet en algunas ocasiones no son de buena calidad.
    
- Lecciones aprendidas en relación al manejo de los datos, el modelamiento y la implementación del modelo.
  En nuestro caso, fue necesario realizar un entendimeinto del negocio de forma extensa para poder realizar una adecauda implementacion.
- Recomendaciones para futuros proyectos de machine learning.
  Es posible construir un mejor modelo que permite integrar los diferetnes modelos por antibiotico, el cual sea capaz de categorizar el microorganismos de forma mas sencilla.

## Impacto del proyecto

- Descripción del impacto del modelo en el negocio o en la industria.
  El principal impacto del proyecto es realizar transformacion de informacion de resistencia antimicrobiana  de concentracion inhibitoria minima CIM a SIR, de forma mas eficiente, sin usar el software de Whonet el cual no es amigable para los usuarios.
- Identificación de las áreas de mejora y oportunidades de desarrollo futuras.
  Es necesario contar con informacion mas robusta para algunos microorganimos y antibioticos  que cuentan con un bajo volumen de observaciones en alguna de sus categorias de SIR que afecta su prediccion por el desbalance de categorias, a pesar del uso de metodologias para corregir este aspecto.

## Conclusiones

- La construccion de los diferentes modelos permiten realizar una prediccion adecuada del perfil de resistencia de microorganismos en una institucion de forma mas simple.
- A pesar de contrar con metricas de rendmientos con porcentajes por encima del 90%, algunos antibioticos y categorias, no funcionan del todo bien por falta de numero de observaciones.
- Se recomienda contar con datos de diferentes instituciones o de periodos mas largo para lograr un mejor rendimiento del modelo.
- Es importante, evaluar la posibilidad de construir un modelo mas robusto que integre la informacion de los diferentes modelos construidos por antibiotico.
- 
## Agradecimientos

- Agradecimientos al equipo de trabajo y a los colaboradores que hicieron posible este proyecto.
