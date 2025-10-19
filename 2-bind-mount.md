# BIND MOUNT
En un bind mount mapeamos (montar) un directorio o archivo específico del sistema de archivos del host con una parte del sistema de ficheros del contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```
ó
```
docker run -d --name <nombre contenedor> --mount type=bind,source=<ruta carpeta host>,target=<ruta carpeta contenedor> <imagen>
```
- destination, dst, target: La ruta donde se monta el archivo o directorio en el contenedor.
- source, src: El origen del montaje.
  
### En tu computador crear una carpeta llamada nginx y dentro de esta carpeta crea otra llamada html. Como se aprecia en la figura.
![Volúmenes](directorio.PNG)

### Crear un contenedor con la imagen nginx:alpine, mapear todos por puertos, para la ruta carpeta host colocar el directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html (esta ruta se obtiene al revisar la documentación de la imagen)
![Volúmenes](volumen-host.PNG)
# COMPLETAR CON EL COMANDO

```
Docker run -P -d --name nginxVolume -v C:\Users\JuanChest\Documents\Contenedores\nginx\html:/usr/share/nginx/html nginx:alpine
```

### ¿Qué sucede al ingresar al servidor de nginx?

Al ingresar al servidor de nginx no se muestra la página principal como normalmente suele hacer, en lugar de eso muestra el código de error 403.
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### ¿Qué pasa con el archivo index.html del contenedor?

Probablemente el archivo index como no se encuentra en el directorio creado, el servidor no puede mostrarlo.
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de tu computador en la carpeta html
### ¿Qué sucede al ingresar al servidor de nginx?

Esta vez si deja ingresar al servidor nginx y esta vez muestra la página web con la plantilla descargada.

<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/660c6371-de89-41db-8387-1622328475f2" />

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Eliminar el contenedor

```
Docker rm -f nginxVolume
```
# COMPLETAR CON EL COMANDO

### ¿Qué sucede al crear nuevamente un contenedor montado al directorio definidos anteriormente?

Pues esta vez al crear el contenedor en el mismo directorio, pero esta vez con la plantilla HTML cargada, al ingresar se muestra directamente esa plantilla.
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA



