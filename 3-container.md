# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
# COMPLETAR /
```
docker create --name srv-web nginx:alpine
```

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
# COMPLETAR /
```
docker create --name hello-world nginx:alpine
```

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 
# COMPLETAR /
```
docker start srv-web
```

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](img/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
# COMPLETAR /
```
docker run --name srv-web2 nginx:alpine
```

**¿Qué sucede luego de la ejecución del comando?**
# COMPLETAR  /
1. Creación y Ejecución del Contenedor : Docker crea y ejecuta un nuevo contenedor basado en la imagen nginx:alpine, asignándole el nombre srv-web2.
2. Ejecución en Primer Plano : El contenedor se ejecuta en primer plano (primer plano), lo que significa que la terminal se bloqueará y mostrará la salida del contenedor. En este caso, verás los logs del proceso Nginx en tiempo real.
3. Interacción con el Contenedor : Debido a que el contenedor se está ejecutando en primer plano, puede ver la salida de los troncos directamente en la terminal. Para detenerlo, deberás usar Ctrl + C
4. ID del contenedor : Docker mostrará el ID del contenedor creado.
5. Acceso al Contenedor : Docker inicia el contenedor, ejecutando el proceso predeterminado definido en la imagen nginx:alpine. Para nginx, esto significativamente significa iniciar el servidor web Nginx.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
# COMPLETAR /
```
docker run -d --name srv-web3 nginx:alpine
```

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
# COMPLETAR /
```
docker rm hello_world
```

Verificar que el contenedor que se eliminó
# COMPLETAR /
```
docker ps -a
```

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
# COMPLETAR /
```
docker rm -f srv-web3
```

Verificar que el contenedor que se eliminó
# COMPLETAR /
```
docker ps -a
```
### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
# COMPLETAR /
```
docker inspect srv-web
```
