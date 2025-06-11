# HomeAssistant-Install-NUC
Instalar Home Assistant en minipc usando live base de Void Linux
## Arrancar desde live de Void Linux
+ login user/pass
```
root
voidlinux
```
+ shell y teclado
```
loadkeys es
bash
```
+ listado de discos
```
lsblk
```
+ suponemos /dev/sda para instalar home assistant

+ instalar herraminetas necesarias
```
xbps-install -S wget xz
```
+ obtener el enlace para la descarga de la imagen de home assistant
+ consultar en navegador web móvil u otro dispositivo ...
+ en este caso el enlace es
```
https://github.com/home-assistant/operating-system/releases/download/15.2/haos_generic-x86-64-15.2.img.xz
```
+ situarnos en /mnt
```
cd /mnt
```
+ descargar el archivo que contiene la imagen
```
wget https://github.com/home-assistant/operating-system/releases/download/15.2/haos_generic-x86-64-15.2.img.xz
```
+ descomprimir y copiar la imagen al disco sda
```
xzcat haos_generic-x86-64-15.2.img.xz | dd of=/dev/sda
```
+ esperar a que termine el proceso
+ apagar el mini pc
+ extraer el live de void linux
+ reiniciar
+ acceder desde otro dispositivo a través del navegador, con ip del mini pc y puerto 8123
```
192.168.ip.minipc:8123
```
+ también en el navegador con 
```
http://homeassistant.local:8123/
```
+ o también en el navegador con 
```
http://homeassistant:8123/
```
+ si necesitamos averiguar la ip del home assistant se puede utilizar nmap
+ desde otro dispositivo, en este caso usando void linux 
```
xbps-install nmap
```
+ ejecutar como sudo
```
nmap -sP direccion.de.red.0/24
```
+ debería dar una salida similar a
```
Nmap scan report for homeassistant... (ip del dispositivo que tiene homeassistant instalado)
```


