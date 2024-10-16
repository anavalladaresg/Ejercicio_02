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

## 4. Obtener la IP del contenedor 'dam_alp1' y comprobar su conectividad a Internet
Inspeccionamos el contenedor para averiguar su dirección IP interna. Verificamos si el contenedor tiene acceso a Internet mediante un ping a Google.

**Comandos utilizados:**
```bash
sudo docker inspect dam_alp1 | grep IPAddress
```
```bash
sudo docker exec -it dam_alp1 ping www.google.com
```

## 5. Crear otro contenedor llamado 'dam_alp2' y verificar la comunicación entre ambos
Creamos un segundo contenedor denominado `dam_alp2`. Desde el terminal del primer contenedor `dam_alp1`, se intenta hacer ping al segundo contenedor utilizando su dirección IP interna, validando así la comunicación entre ellos.

**Comandos utilizados:**
```bash
sudo docker run -it -d --name dam_alp2 alpine
```
```bash
sudo docker exec -it dam_alp1 sh
```
```bash
ping <IP_dam_alp2> # En mi caso, la IP es 172.17.0.3
```

## 6. Salir del terminal del contenedor. ¿Qué sucede con los contenedores?
Al salir del terminal del contenedor, comprobamos si los contenedores siguen en ejecución mediante el comando `ps`. El resultado confirma que los contenedores permanecen activos.

**Comandos utilizados:**
```bash
exit
```
```bash
sudo docker ps -a
```

## 7. Verificar el espacio en disco ocupado por los contenedores
Verificamos cuánto espacio en disco han utilizado los contenedores tras haber sido ejecutados.

**Comando utilizado:**
```bash
sudo docker ps -ls
```
*Resultado obtenido:* `Size: 0B (Virtual 7.8MB)`

## 8. Consultar el uso de RAM por los contenedores y explorar un comando para monitorizar esto
Consultamos el uso de memoria RAM de los contenedores con el comando `docker stats`, el cual nos proporciona estadísticas en tiempo real sobre el rendimiento de los contenedores.

**Comando utilizado:**
```bash
sudo docker stats
```
*Resultado obtenido:* `dam_alp1: 516KiB / dam_alp2: 488KiB`
