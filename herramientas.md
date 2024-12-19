# Procesos
## ps

```bash 
ps a
```
> Muestra todos los procesos asociados al terminal actual (incluidos los de otros usuarios).

![ps](img/1.png)
---
```bash 
ps au
```
> Lista los procesos con detalles adicionales, como el usuario propietario, el consumo de CPU y memoria, y el comando ejecutado.

![ps au](img/2.png)
---
```bash 
ps aux
```
> Similar a ps au, pero muestra procesos de todos los usuarios y no se limita al terminal actual.

![ps aux](img/3.png)
---
```bash 
ps -C nano
```
> Filtra y muestra información sobre los procesos cuyo comando es nano.

![ps nano](img/4.png)
---
```bash 
ps -eo user,pid,command,comm,%cpu,%mem --sort=-%cpu | head -n 6
```
>Lista procesos con columnas personalizadas ```(user, pid, command, comm, %cpu, %mem)``` ordenados por mayor uso de CPU ```(--sort=-%cpu)``` y muestra las primeras 6 líneas ```(head -n 6)```.

![ps eo](img/5.png)
---
## top
```bash 
top -b -n 1 > top.txt
cat top.txt
```
> Ejecuta top en modo batch ```(-b)``` una vez ```(-n 1)``` y guarda la salida en el archivo top.txt.

![top](img/6.png)
---
```bash 
top -b -n 3 -o +%CPU|head -n 17 > procesos.txt
cat procesos.txt
```
> Ejecuta top en modo batch ```(-b)``` tres veces ```(-n 3)```, ordena por uso de CPU ```(-o +%CPU)```, muestra las primeras 17 líneas ```(head -n 17)``` y guarda el resultado en procesos.txt.

![procesos](img/7.png)
---

```bash 
atop
```
>atop: Es una herramienta avanzada de monitorización de sistemas que muestra estadísticas detalladas sobre el uso de CPU, memoria, disco, red y procesos en tiempo real.

![atop](img/atop.png)
---

# Gestión de memoria y espacios
---
## free
```bash 
free
free -h
free -s 3
```
>free: Muestra un resumen de la memoria RAM y swap en el sistema, en kilobytes por defecto.

>free -h: Igual que free, pero los valores se presentan en formato "legible para humanos" (KB, MB, GB).

>free -s 3: Actualiza la información de memoria cada 3 segundos.

![8](img/8.png)
---
## df
```bash 
df -h
df -h /
```
>df -h: Muestra el uso del espacio en disco de todos los sistemas de archivos en formato legible para humanos.

>df -h /: Muestra el uso del espacio en disco únicamente para el sistema de archivos donde está montado / (la raíz).

![9](img/9.png)
---
## du
```bash 
sudo du -hs
sudo du -hs /home
```
>sudo du -hs: Calcula el tamaño total del directorio actual y lo muestra en formato legible para humanos ```(-h)```, resumiendo en una única línea ```(-s)```.

>sudo du -hs /home: Igual que el anterior, pero calcula el tamaño total del directorio /home.

![10](img/10.png)
---

```bash 
sudo du -hd 1 /home
```
>sudo du -hd 1 /home: Muestra el tamaño de /home y sus subdirectorios inmediatos (profundidad 1), en formato legible para humanos.

![11](img/11.png)
---

## iostat
```bash 
iostat -x nvme0n1
```
>iostat -x nvme0n1: Muestra estadísticas extendidas ```(-x)``` de uso del dispositivo de almacenamiento nvme0n1, como tiempo de espera, uso porcentual y tasas de lectura/escritura.

![12](img/12.png)
---

# Red
---
## tcpdump
```bash 
sudo tcpdump
```
>tcpdump: Captura y muestra paquetes de red en tiempo real en la interfaz predeterminada.

![13](img/13.png)
---

```bash 
tcpdump -i eno1
```
>tcpdump -i eno1: Captura paquetes en la interfaz específica eno1.

![14](img/14.png)
---

```bash 
tcpdump -i eno1 -w capturas
```
>tcpdump -i eno1 -w capturas: Captura paquetes en la interfaz eno1 y los guarda en un archivo llamado ```capturas``` para poder analizarlo.

![15](img/15.png)
---

## tcptrack
```bash 
tcptrack -i eno1
```
>tcptrack -i eno1: Monitorea conexiones TCP en tiempo real en la interfaz eno1, mostrando el estado de las conexiones y el tráfico.

![16](img/16.png)
![16.5](img/16.5.png)
---

## iptraf
```bash 
iptraf
```
>iptraf: Herramienta interactiva para analizar el tráfico de red en tiempo real, incluyendo estadísticas por protocolo, interfaces y direcciones IP.

![17](img/17.png)
![17.1](img/17.1.png)
![17.2](img/17.2.png)
![17.3](img/17.3.png)
---
## bmon
```bash 
bmon
```
>bmon: Similar a iptrad, monitoriza el ancho de banda en tiempo real, mostrando estadísticas gráficas y detalladas por interfaz de red.

![18](img/18.png)
