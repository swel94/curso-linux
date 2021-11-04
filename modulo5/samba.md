# Manuel de Instalacion y Configuracion de Samba

  

### THE ULTIMATE GUIDE 😶‍🌫️

  > Este manual esta dirigido a los vagos

  ***Creditos***
A mi esfuerzoo exhaustivo de busqueda de Internet

*Este manual es incomparable*

  ![Samba Server](https://logowiki.net/uploads/logo/s/samba-4.svg)

Indice:

1. [Introdución a Samba](#introduccion)
2. [Instalacion Samba](#instalacion)
3. [Configuracion Samba](#configuracion)
4. [Desinstalacion Samba](desinstalacion)
 
## Introduccion

  ### ¿Que es SAMBA?

  Es un conjunto de aplicaciones Linux, basada en el protocolo SMB[^1], que permite compartir archivos en red. ### Orígenes Fue creado por [Andrew Tridgell]([https://es.wikipedia.org/wiki/Andrew_Tridgell](https://es.wikipedia.org/wiki/Andrew_Tridgell)  "[https://es.wikipedia.org/wiki/Andrew_Tridgell](https://es.wikipedia.org/wiki/Andrew_Tridgell)").

  El necesitaba montar un espacio en disco en su computadora para un servidor Unix. Esa computadora utilizaba el sistema de archivos **NFS** (**Network File System**). Sin embargo, una aplicación necesitaba soporte para el protocolo **NetBIOS[^2]** (no soportado por el NFS). Tridgell lo solucionó escribiendo un sniffer[^3] que permitía analizar el tráfico de datos generado por el protocolo NetBIOS. Hizo [ingeniería inversa]([https://es.wikipedia.org/wiki/Ingenier%C3%ADa_inversa](https://es.wikipedia.org/wiki/Ingenier%C3%ADa_inversa)  "[https://es.wikipedia.org/wiki/Ingeniería_inversa](https://es.wikipedia.org/wiki/Ingenier%C3%ADa_inversa)") en el protocolo SMB y lo implementó en el Unix.

  Eso hizo que el servidor Unix apareciera como un servidor de archivos Windows en su PC con DOS. ## Instalacion ## Configuracion ## Desinstalacion [^1]: Server Message Block [^2]: Network Basic Input/Output System [^3]: Pequeño programa para captura de tráfico de datos en red.

  ## Instalacion Samba:

  #### Cómo instalar Samba en Ubuntu 21.04:

 **-Comprobamos la version de ubunto utilizando el siguiente comando:**

```bash
$ lsb _releasae -a
```
**- Ahora actualizamos el sistema con el comando:**

```bash
$ sudo apt update
```

**- Después de esto instalaremos Samba con el siguiente comando:**

```bash
$ sudo apt install samba*
```
Ahora podemos verificar si se encuentra corriendo apropiadamente utilizando el siguiente comando:*

```bash
$ sudo systemctl status smbn
```
## Configuracion Samba:

**-Crearemos la carpeta que se compartirá:**

```bash
$ sudo  mkdir /home/sharedfolder
```
**- Copiamos los archivos de configuración de Samba para tener un respaldo de ellos:**
```bash
$ sudo cp /etc/samba/smb.conf /etc/samba/smb.conf.org
```
**- Ahora editaremos este archivo de configuración con el editor deseado:**
```bash
$ sudo nano /etc/samba/smb.conf
```
**- Vamos al final del archivo e ingresamos lo siguiente:**
 ```bash
[sharedfolder]
			comment = samba on Ubuntu
			path = /home/sharedfolder
			browseable = yes
			readonly = no
``` 

**-Reiniciamos el servicio de Samba con el siguiente comando:**
```bash
$ sudo service smbd restart
```
 **-Creamos el usuario root para Samba y otorgamos permisos:**
```bash
$ sudo smbpasswd -a root
``` 
*Ingresamos y confirmamos la contraseña de este usuario root:*
![Samba Server](https://www.solvetic.com/uploads/monthly_11_2020/tutorials-7463-0-78671000-1604999024_thumb.png)

 **-Es momento de conceder los permisos en el Firewall del sistema   con el comando:**
```bash
$ sudo ufw allow samba
``` 
 **-Ahora con  cualquiera de los siguientes comandos procedemos a verificar nuestra IP:**
```bash
$ ifconfig / hostname -I
```
 **-Teniendo en mente esta dirección IP, vamos a Windows 10 y abrimos Ejecutar, allí ingresamos la siguiente sintaxis:**
```bash
\\IP_Ubuntu_21.04
```
![Samba Server](https://www.solvetic.com/uploads/monthly_11_2020/tutorials-7463-0-70231400-1604999019.png)

 **-Damos clic en Aceptar y esto abrirá la carpeta que hemos creado para compartir en Ubuntu 21.04:**
 
![Samba Server](https://www.solvetic.com/uploads/monthly_11_2020/tutorials-7463-0-73916400-1604999018.png)

**-  
Al acceder a ella debemos ingresar el usuario root con la contraseña que hemos definido:**

![Samba Server](https://www.solvetic.com/uploads/monthly_11_2020/tutorials-7463-0-23042000-1604999018.png)

**-Damos clic en Aceptar y podemos crear algún archivo en la carpeta:**

![Samba Server](https://www.solvetic.com/uploads/monthly_11_2020/tutorials-7463-0-17988600-1604999017.png)

*Confirmamos el funcionamiento de Samba en Ubuntu 21.04, en la terminal ingresamos lo siguiente:*
```bash
$ cd /home/sharedfolder
ls
```
 **-Al listar el contenido podemos ver el archivo creado en Windows 10:**
 
![Samba Server](https://www.solvetic.com/uploads/monthly_11_2020/tutorials-7463-0-70387600-1604999015_thumb.png)

## Desinstalacion de Samba:
 
 **-Para desinstalar samba completamente de nuestro equipo debemos seguir los siguientes pasos:**

```bash
$ sudo apt-get autoremove --purge samba
```

```bash
$ sudo apt-get remove samba
```
```bash
$ sudo apt-get autoremove samba
```

[^1]: Server Message Block

[^2]: Network Basic Input/Output System

[^3]: Pequeño programa para captura de tráfico de datos en red