# Instalación de Docker en Windows

Habilitar el servicio de WSL2 (Windows Subsystem Linux). Para ello, en una terminal de Powershell (como administrador, click derecho en el icono) corra la siguiente instrucción:

```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

Reinicie el equipo.

Una vez habilitado el servicio, instale WSL ejecutando en Poweshell la instrucción:

```
wsl --install
```

Actualice WSL a la versión WSL2:

```
wsl --set-default-version 2
```

Descarga el ejecutable de Docker Desktop en la siguiente [liga](https://docs.docker.com/desktop/install/windows-install/), y corre la siguiente instrucción en Powershell:

```
Start-Process 'Docker Desktop Installer.exe' -Wait install
```

Si no ha habido ningún problema, el siguiente paso es correr el contenedor de la aplicación.

## Correr el contenedor de la aplicación

El contenedor de la aplicación se encuentra en el siguiente [repositorio](https://github.com/milocortes/docker_compose_ellsberg_app).

Para descargar el repositorio, utilice git. Corra la siguiente instrucción en Powershell:

```
git clone https://github.com/milocortes/docker_compose_ellsberg_app.git
```

Para lanzar la aplicación del contenedor, primero debemos ejecutar el servicio local de base de datos de docker-compose con la siguiente instrucción (dentro del repositorio descargado):

```
docker compose up -d db
```

Una vez creada la base de datos, ya podemos correr la aplicación con la siguiente instrucción:

```
docker compose up --build ellsbergapp
```

