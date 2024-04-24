# CL01 -

```sh
#Create a new bridge network
docker network create my-fancy-bridge-network

#Start ubuntu container
docker run --rm --name ubuntu -d -ti --network my-fancy-bridge-network ubuntu:latest

## Find IP address
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' ubuntu
```

# CL03 - Definer og brug et custom bridge netværk i Docker Compose

```sh
#Start services
docker compose -f docker-compose.03.yml up -d

#Verify network config
docker network inspect cl04_vandcykel
```

# CL04 - Find MAC adressen på en container

```sh
docker inspect -f '{{range .NetworkSettings.Networks}}{{.MacAddress}}{{end}}' cl04-nginx-1
```
