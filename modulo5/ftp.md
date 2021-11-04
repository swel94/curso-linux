### THE ULTIMATE GUIDE 😶‍🌫️

  ![FTP server](https://www.redeszone.net/app/uploads-redeszone.net/2019/10/protocolo-ftp.jpg)

* Indice:
1.  [Introdución a FTP](#introduccion)
2.  [Instalacion FTP](#instalacion)
3.  [Configuracion FTP](#configuracion)
4.  [Desinstalacion FTP](desinstalacion)

## Introduccion

### ¿Que es FTP Server?
Las siglas de FTP significan _File Transfer Protocol_, que se traduce como _Protocolo de Transferencia de Archivos_. Como su nombre indica, se trata de un protocolo que **permite transferir archivos directamente de un dispositivo a otro**. 

Actualmente, [es un protocolo que poco a poco va abandonándose](https://www.xataka.com/aplicaciones/ftp-nos-va-dejando-50-anos-despues-su-creacion-chrome-firefox-seran-sus-verdugos), pero ha estado vigente más de 50 años. El protocolo FTP se empezó a utilizar en abril de 1971, y terminó de definir su estructura en el 73, aunque durante las décadas de los 70 y los 80 del siglo pasado fue perfeccionándose. Para que te hagas una idea,  **este protocolo nació antes de que existieran Internet o el correo electrónico**, ya que fue uno de los componentes básicos de  [ARPANET](https://www.xataka.com/historia-tecnologica/todo-internet-cabia-en-un-papel-a4-hace-40-anos-la-historia-del-nacimiento-de-arpanet), que fue esa red primigenia que luego dio lugar a Internet.

Este protocolo funciona entre ordenadores que estén conectados a una red TCP, que significa  _Transmission Control Protocol_  o Protocolo de control de transmisión. Este protocolo TCP da soporte a muchas tecnologías, entre ellas a Internet. Para que te hagas a la idea, la familia de protocolos que forman Internet se llama TCP/IP.

Pero vamos, dejándonos de palabrerías y nombres extraños, simplemente decirte que el protocolo FTP funciona para **compartir archivos entre ordenadores que estén conectados a Internet**, y los archivos se comparten de forma directa y sin ningún intermediario.

## Instalacion FTP:

**-Actualizamos los paquetes intalados con el siguiente comando:**
```bash
$ sudo apt-get update
```
**-Ahora procedemos con la intalacion del paquete VSFTPD:**
```bash
$ sudo apt-get install vsftpd -y
```
## Configuaracion FTP:

**-Ahora procedemos a realizar una copia del archivo vsftpd.conf:**
```bash
$ cp /etc/vsftpd.conf /etc/vsftpd.conf.bakup
```
**-Una vez hayamos realizado nuestro backup, accedemos al archivo con el siguiente comando:**
```bash
$ sudo nano /etc/vsftpd.conf
```
**-Ahora dentro del archivo debemos modificar los siguientes cambios**
```bash
#Write_enable=YES
#Anonymus_enable=YES
```
*Procedemos a guardar los cambios realizados y reiniciamos el servicio FTP con el siguiente comando:*
```bash
$ sudo systemctl restart vsftpd
```
**-Ahora debemos habiliar la configuracion del firewall con los siguientes comandos:**
```bash
$ sudo ufw allow ftp
```
```bash
$ sudo ufw allow ftp-data
```
**-Por ultimo para poder conectarnos a otro equipo bajo el protocolo FTP debemos utilizar la siguiente sintaxis:**
```nano
$ ftp (direccion de IP la cual nos deseamos conectar)
```
## Desinstalacion FTP:

**-Para desinstalar FTP debemos seguir los siguientes pasos:**

*Detenemos a FTP:*
```bash
$ sudo systemctl stop vsftpd
```
*Por ultimo procedemos a eliminar FTP y sus respectivas depencias dentro de nuestro equipo con el siguiente comando:*
```bash
$ sudo apt-get remove --auto-remove vsftpd
```