# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](img/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
# COMPLETAR /
Imagen : Es un archivo único que contiene todo lo necesario para ejecutar una aplicación o conjunto de aplicaciones.
Contenedor : Es una instancia en ejecución de una imagen.
La imagen es el plano (archivo estático) y el contenedor es la aplicación en ejecución basada en ese plano.

![Imagen y contenedores](img/imagenContenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
# COMPLETAR /
```
docker pull hello-world
```

**¿Qué es nginx**
# COMPLETAR 
Nginx es un servidor web y proxy inverso de alto rendimiento. Se utiliza para servir contenido estático, equilibrar carga entre varios servidores y como proxy inverso que dirige solicitudes a servidores backend. Es eficiente en el manejo de muchas conexiones con poco uso de recursos, lo que lo hace ideal para sitios web de alto tráfico.


Descargar la imagen  **nginx** en la versión **alpine**
# COMPLETAR /
```
docker pull nginx:alpine
```

### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
# COMPLETAR/
```
docker inspect hello-world
```

**¿Con qué algoritmo se está generando el ID de la imagen**
# COMPLETAR /
En Docker, los identificadores de las imágenes (Image IDs) se generan utilizando el algoritmo de hash SHA-256 . Este es un algoritmo criptográfico que toma el contenido de la imagen (o de las capas que la componen) y genera un hash único. El ID de la imagen es una versión truncada del hash completo, generalmente de 64 caracteres.

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
# COMPLETAR /
```
docker rmi hello-world
```

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

