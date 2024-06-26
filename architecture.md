## Documentation of the architecture for the backend

Se optó por utilizar una arquitectura serverless basada en **AWS**, debido a que se busca alta escalabilidad y bajos costos, eligieron los servicios de AWS para aprovechar al máximo la capa gratuita que ofrece y reducir costes buscando el desacoplamiento entre servicios modularizando el codigo en microservicios y utilizando SNS y SQS como metodo de comunicacion entre ellos.

### Servicios AWS elegidos

#### IAM
Administración de usuarios

#### Api Gateway
Como pasarela al backend, con la función de gestionar las peticiones y reenviarlas a los servicios correspondientes.

#### Secret Manager
Para poder almacenar las variables de entorno de los servicios.

#### RDS (postgres)
Para simplificar las bases de datos, sólo se utilizará SQL. Optamos por utilizar RDS, para evitar el mantenimiento del servidor anfitrión y obtener logs integrados.

#### S3
Para almacenar las imágenes de los usuarios y/o productos.

#### CloudFront
Para acceder a las imágenes públicas de S3 de forma segura.

#### SNS
Para enviar mensajes a la cola SQS.

#### SQS
Para desacoplar microservicios y utilizar colas SQS para enviar mensajes a otros servicios.

#### CloudFormation
Para implementar plantillas de IaC desarrolladas con el CDK de AWS.

#### CloudWatch
Monitorización de logs y aplicaciones.

#### VPC
Para evitar que las lambdas y los servicios de base de datos se consuman fuera de la red de AWS.
