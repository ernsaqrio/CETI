
funcion.php (code)

EC2 (Iaas) €/h
lambda (serverless) €/petición
elastic beanstalk (Paas)
ECS (docker) / EKS (kubernetes) = docker  €/h/contenedor (Esta opción es mas rentable)

Almancenamiento:

.pdf
.bck
.png  
S3 (SSS): simple storage service (una opcion economica) : barato el €/GB y bajo  rendimento
EBS (volumenes): muy caro el €/GB y mejor rendimiento
EFS : Elastic file system (sistema compartido para servidores linux)
S3 Glacier: super barato el €/GB pero el rendimiento es muy bajo

Base de datos y sistemas gestores:

-Con tablas: RDS / Aurora: base relacional (mismo precio que EC2)
-Bases no relacionales: DynamoDB (precio serverless)
-Cache : ElasticCache €/GB muy alto y mayor rendimiento
-Redshift: Analísitcas

Redes:

-VPC (nube privada virtual): red privada para conexión entre equipos o una S3 con una lambda.
-Route 53: Servidor DNS de AWS
-CloudFront (CDN, Edge computing): La web se distribuye de forma global.

Al introducir url va Route53 y no se pone la ip de la EC2, se usa la del CDN y luego se conecta con tu servidor.

-