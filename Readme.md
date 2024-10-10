#####

# S3: First steps with docker

###

```shell
#docker build -t image_name [options y arguments] .
docker build -t billing-app --no-cache --build-arg JAR_FILE=billingApp/target/*.jar .
```

```shell
#docker run [options] container_name image_name
# 80 Frontend App
# 7080 Backend App
docker run -d -p 80:80 -p 7080:7080 --name local-container-billing billing-app
```

# S4: Docker compose

Go to folder 02_07.09.24_billingApp_v2

```shell
docker compose -f stack-billing.yml up -d
```

Ver logs

```shell
docker logs billingApp-back
```

Remove images

```shell
docker system prune --all
```

Remove volumes

```shell
docker volume prune
```

Connect SSH to docker

```shell
docker exec -it billingApp-back sh
```

# S5 Docker Swarm

go to billing AppV3

Hasta ahora hemos creado un contenedor por cada app. Ahora vamos crear el entorno de PRE y PRD.
Por lo tanto, vamos a tener que duplicar los entornos de cada app.Esto requiere algunos pasos:

- Cambiar nombres de contenedores
- puertos
- REvisar volumenes de base de datos
  -...

```shell
docker system prune --all
```
