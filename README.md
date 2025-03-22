# demo-docker
Demostración uso de Docker 2025

## Herramientas previas

Instalar telnet con:

```sh
apt update
apt install telnet
```

## Comandos básico

- `docker --version`: Ver la versión
- `docker ps`: Ver contenedores corriendo
- `docker ps -a`: Ver contenedores corriendo y parados
- `docker images`: Listar las imagenes base disponibles
- `docker pull nginx`: Descarga la imagen de NGinx
- `docker pull alpine`: Descarga la imagen de Alpine
- `docker run alpine`: Crea un contenedor Alpine pero se para inmediatamente verificar con `docker ps -a`
- `docker run nginx`: Crea un contenedor NGinx y queda ejecutandose verificar en otra ventana con `docker ps`
- `docker run -d nginx`: Crea un contenedor NGinx y queda ejecutandose EN SEGUNDO PLANO verificar con `docker ps`
- `docker run --name web-1 -d nginx`: Crea un contenedor NGinx y queda ejecutandose EN SEGUNDO PLANO verificar con `docker ps`
- `docker stop ID_CONTENEDOR`: Para el contenedor con el id ID_CONTENEDOR
- `docker run --name web-1 -d --rm nginx`: Crea un contenedor NGinx y queda ejecutandose EN SEGUNDO PLANO verificar con `docker ps`, Pero por el `--rm` cuando lo pare se va a eliminar automáticamente
- `docker run --rm -it alpine`: Ejecuto un alpine de forma INTERACTIVA compatiendo TERMINAL. Pero por el `--rm` cuando lo pare se va a eliminar automáticamente
- `docker run -d --name web-1 -p 7000:80 nginx`: Crea un contenedor NGINX en segundo plano enlazando el puerto 80 del NGINX dentro del contenedor al puerto 7000 en la maquina HOST.
- `docker run -d --name web-2 -p 8000:80 -v /workspaces/demo-docker:/usr/share/nginx/html:ro nginx`: Crear un contenedor, en segundo plano, con el nombre web-2. Además enlaza el puerto 8000 de la maquina HOST con el puerto 80 del contenedor (NGIX). Monta un volumen asociando la carpeta de la maquina local `/workspaces/demo-docker` en la carpeta dentro del contenedor `/usr/share/nginx/html` en modo sólo lectura `ro`

## Tarea: Explicar que hace este comando y por qué funciona.

En linux
- `docker run -d --name web-2 -p 8000:80 -v /workspaces/demo-docker:/usr/share/nginx/html:ro nginx`

En windows
- `docker run -d --name web-2 -p 8000:80 -v C:\Users\jperez\Mis\ documentos:/usr/share/nginx/html:ro nginx`