# Ellsberg-App Docker Compose

Para ejecutar el servicio local de base de datos de  ```docker-compose```
ejecutamos la siguiente instrucción:


```
docker compose up -d db
```

Para verificar el estatus del contenedor, ejecutamos 

```
docker ps -a
```

Check the database

```
sudo docker exec -it db psql -U ellsberg_user ellsberg_db
```

Run Python app

```
docker compose up --build ellsbergapp
```

Stop Python app

```
docker compose stop ellsbergapp
```

Re run Python app

```
sudo docker compose run  ellsbergapp
```

Remove volume 

```
docker compose down -v 
```
