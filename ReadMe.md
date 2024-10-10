# Ejercicio 2  
**Ana Valladares González**

## 1. Descargar la imagen "Alpine" sin iniciarla y verificar su presencia en tu equipo  
Descargamos la imagen de Docker "Alpine" sin ejecutarla, utilizando el comando `docker pull`. Comprobamos que la imagen ha sido descargada correctamente al listar las imágenes disponibles.

**Comandos utilizados:**  
```bash
sudo docker pull alpine
```
```bash
sudo docker images
```

## 2. Crear un contenedor sin asignarle un nombre. Verificación de su estado
Creamos un contenedor a partir de la imagen `Alpine` sin asignarle un nombre. Para verificar si está en ejecución y obtener el nombre automáticamente asignado, usamos el comando `ps`.

**Comandos utilizados:**
```bash
sudo docker run -d alpine
```
```bash
sudo docker ps -a
```

## 3. Crear un contenedor con nombre 'dam_alp1' y acceder a su terminal
Creamos un nuevo contenedor, esta vez asignándole el nombre `dam_alp1`. Nos conectamos a su terminal utilizando el comando exec, que nos permite interactuar directamente con el contenedor.

**Comandos utilizados:**
```bash
sudo docker run -it -d --name dam_alp1 alpine
```
```bash
sudo docker exec -it dam_alp1 sh
```