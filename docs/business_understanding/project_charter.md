# Project Charter - Entendimiento del Negocio

## **Presentado por**:  
# Daniel Cardozo

## Nombre del Proyecto

# **Aplicación de Deep Learning para la Interpretacion Clínica de Pruebas de Sensibilidad Antimicrobiana (SIR)**

## Objetivo del Proyecto
Construir  un modelo de Deep Learning capaz de convertir la concentracion inhibitoria minima CIM a pruebas de sensibilidad antimicrobiana (SIR) para su posterior interpretacion clinica.

## Alcance del Proyecto

### Incluye:

- [Descripción de los datos disponibles]
- [Descripción de los resultados esperados]
- [Criterios de éxito del proyecto]

## Dominio 
El proyecto se encuentra en el dominio de la salud y medicina, especificamente en el area de resistencia antimicrobiana (RAM), la cual surge cuando las bacterias, los virus, los hongos y los parásitos cambian a lo largo del tiempo y dejan de responder a los medicamentos (farmacorresistencia a antibioticos), lo que hace más dificil el tratamiento de las infecciones e incrementan el riesgo de propagacion de enfermedades, de aparacion de formas graves de estas y hasta el incremento de muertes. En este contexto surgen los Programas de Optimización de Antimicrobianos (PROA) como una respuesta para contener esta problematica, como principal objetivo el de reducir la resistencia a los antimicrobinos.

## Planteamiento del Problema
Los PROA buscan mejorar los resultados clínicos de los pacientes tratados con antimicrobianos de una manera costo-efectiva y segura, alargando su vida útil, por medio de la prescripción de antimicrobianos solo en casos necesarios y la elección del esquema terapéutico, la dosis, la vía de administración y la duración más conveniente de acuerdo con un buen diagnóstico.

En ese sentido, en la actualidad el análisis de resistencia a antimicrobianos se realiza con la información obtenida del laboratorio clínico de cultivos microbiológicos a bacterias y hongos en donde se informa el microorganismo aislado con las concentraciones inhibitorias mínimas (MIC o CIM) para cada antibiótico capaz de tratar la enfermedad infecciosa.

La información de CIM se reporta por los laboratorios clínicos por medio de una base de datos en formato .sir que es posible procesar en un aplicativo llamado WHONET el cual reconoce cuando un microrganismo presenta un perfil de susceptibilidad antimicrobiana categorizado en sensible, intermedio o resistente por medio de puntos de corte establecidas por el CLSI (Clinical and Laboratory Standards Institute) en EEUU y EUCAST (European Commitee on Antimicrobial Susceptibility Testing) las cuales son organizaciones globales que desarrollan y promueven estándares y directrices para la práctica Clinica y de laboratorio, en especial establecer p untos de cortes para la interpretación de pruebas de sensibilidad a los antimicrobianos. Este aplicativo no es un aplicativo de fácil manipulación y los análisis posibles son limitados y en algunos casos poco prácticos, para la construccion de perfiles y determinación de perfiles de resistencia.

## Alcance 
Se propone construir un modelo de Deep Learning el cual sera entrenado con datos etiquetados que permite reconocer las categorias de susceptibilidad sensible, intermedio o resistente para cada antibiotico o antifungico segun un microorganismos dado.

Inicialmente se construira un algoritmo que permite la transformacion de datos CIM a SIR, los cuales serviran como los datos etiquetados.
Se construira el modelo de red neuronal profunda capaz de aprender los puntos de corte y realizar la transformacion a SIR.
Exploracion de hiperparametros para obtener un modelo optimo.
El producto se utilizara directamente en pythom haciendo la transformacion de bases de datos de en formato .sir.

### Excluye:

- [Descripción de lo que no está incluido en el proyecto]

## Metodología

[Descripción breve de la metodología que se utilizará para llevar a cabo el proyecto]

## Cronograma

![image](https://github.com/user-attachments/assets/e21897ff-8b59-4d29-b90e-652434bc09b7)


## Equipo del Proyecto

- [Nombre y cargo del líder del proyecto]
- Daniel Cardozo
- [Nombre y cargo de los miembros del equipo]
- Daniel Cardozo 

## Presupuesto

[Descripción del presupuesto asignado al proyecto]
Para este proyecto no se tiene ningun presupuesto.

## Stakeholders

- [Nombre y cargo de los stakeholders del proyecto]
- [Descripción de la relación con los stakeholders]
- [Expectativas de los stakeholders]

- El Cliente o los beneficiarios del proyecto es el personal de salud perteneciente al Programa de Optimización de antimicrobianos PROA (infectologos, microbiologos, epidemiologos, medicos, quimicos farmaceuticos, enfermeros de infecciones, etc). de cualquier Instituciones Prestadoras de Salud, que buscan optimizar la interpretación de resultos de cultivos microbiologicos de pacientes con patologias infecciosas. Permitiendo asi, realizar la conversion de datos de concentracion inhibitoria minima (MIC) a una a su categoria SIR de susceptibilidad antimicrobiana (Sensible, Intermedio o Resistente) asi como definir mecanismos de resistencia para ciertos microorganismos.

## Aprobaciones

- [Nombre y cargo del aprobador del proyecto]
- Daniel Cardozo
- [Firma del aprobador]
- Daniel Cardozo
- [Fecha de aprobación]
- Mayo 2025
