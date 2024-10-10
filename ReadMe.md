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