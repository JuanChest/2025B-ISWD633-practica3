## Esquema para el ejercicio
![Imagen](esquema-ejercicio3.PNG)

### Crear red net-wp

# Creación de la red
```
docker network create net-wp -d bridge
```
# COMPLETAR CON EL COMANDO COMANDO

### Para que persista la información es necesario conocer en dónde mysql almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio carpeta del contenedor (a) es ```/var/lib/mysql```

Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?

La carpeta despues de la creación del contenedor con mysql, contiene varios archivos, deduzco que son archivos de configuración, lo más interesante es la carpeta wordpress que también se encuentra en ese directorio.
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD

MySQL
```
docker run -d --name contenedormysql -v C:\Users\JuanChest\Documents\Contenedores\ejercicio3\db:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=wordpress -e MYSQL_USER=juanchest -e MYSQL_PASSWORD=wpass mysql:8
```
# COMPLETAR CON EL COMANDO

### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?

Pues como mencione, se encuentran nuevos archivos y carpetas.
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio la carpeta del contenedor (b) es ```/var/www/html/```

Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)

Wordpress
```
docker run -d --name contenedorwordpress --network net-wp -p 9500:80 -v C:\Users\JuanChest\Documents\Contenedores\ejercicio3\www:/var/www/html/ -e WORDPRESS_DB_HOST=contenedormysql -e WORDPRESS_DB_USER=juanchest -e WORDPRESS_DB_PASSWORD=wpass -e WORDPRESS_DB_NAME=wordpress wordpress
```
# COMPLETAR CON EL COMANDO

### Personalizar la apariencia de wordpress y agregar una entrada
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/3b732043-f0a3-4761-ad85-307706d239bc" />


### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?

Al eliminar el contenedor de WordPress y volverlo a crear, al acceder a su servicio, la personalización realizada se mantuvo.

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA 

