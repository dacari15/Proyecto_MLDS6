# Despliegue de modelos

## Infraestructura

- **Nombre del modelo:** El nombre del modelo corresponde a cada modelo construido por cada antibiotico.
- modelo_AMK_NM
- modelo_AMP_NM
- modelo_ATM_NM
- modelo_CAS_NM
- modelo_CAZ_NM
- ...
- 
- 
- **Plataforma de despliegue:** El modelo se desplegara en la plataforma MlFlow
- **Requisitos técnicos:** (lista de requisitos técnicos necesarios para el despliegue, como versión de Python, bibliotecas de terceros, hardware, etc.)

### Requisitios técnicos 
|Recurso	            |Recomendación mínima|
| ------------------- | ------------------ |
|CPU / RAM	          |4 vCPU / 16 GB RAM|
|Disco	              |SSD, 50–100 GB mínimo|
|Sistema operativo	  |Linux Ubuntu 20.04+|
|Red	                |Puerto 5000 expuesto (o detrás de NGINX)|

### Software necesario
| Componente         | Versión recomendada           |
| ------------------ | ----------------------------- |
| Python             | 3.8 a 3.11                    |
| MLflow             | 2.17.1                        |
| PostgreSQL         | 12+ (para backend tracking)   |
| MinIO / S3         | Para artifact store           |
| Docker (opcional)  | Para contenerizar el servicio |
| TensorFlow / Keras | Compatibles con tus modelos   |

- **Requisitos de seguridad:** (lista de requisitos de seguridad necesarios para el despliegue, como autenticación, encriptación de datos, etc.)
  
| Aspecto               | Recomendación                                  |
| --------------------- | ---------------------------------------------- |
| Autenticación         | NGINX + basic auth, OAuth2 o tokens            |
| HTTPS                 | SSL vía NGINX / Let's Encrypt                  |
| Control de acceso     | IAM (si usas nube) o ACL por rol               |
| Versionado de modelos | MLflow lo gestiona con control de etapas       |
| Registro de auditoría | Logs + seguimiento de versiones de modelos     |
| Backup                | Base de datos y artefactos versionados diarios |

- **Diagrama de arquitectura:** (imagen que muestra la arquitectura del sistema que se utilizará para desplegar el modelo)
<img width="444" height="698" alt="image" src="https://github.com/user-attachments/assets/a5ccef11-6111-49be-baaa-04c5447a1b51" />


## Código de despliegue

- **Archivo principal:** (nombre del archivo principal que contiene el código de despliegue)
- **Rutas de acceso a los archivos:** (lista de rutas de acceso a los archivos necesarios para el despliegue)
- **Variables de entorno:** (lista de variables de entorno necesarias para el despliegue)

## Documentación del despliegue

- **Instrucciones de instalación:** (instrucciones detalladas para instalar el modelo en la plataforma de despliegue)
- **Instrucciones de configuración:** (instrucciones detalladas para configurar el modelo en la plataforma de despliegue)
- **Instrucciones de uso:** (instrucciones detalladas para utilizar el modelo en la plataforma de despliegue)
- **Instrucciones de mantenimiento:** (instrucciones detalladas para mantener el modelo en la plataforma de despliegue)
