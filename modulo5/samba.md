# Manuel de Instalacion y Configuracion de Samba

### THE ULTIMATE GUIDE 😶‍🌫️

> Este manual esta dirigido a los vagos

***Creditos***

A mi esfuerzoo exhaustivo de busqueda de Internet
*Este manual es incomparable*

![Samba Server](https://logowiki.net/uploads/logo/s/samba-4.svg)

Indice:
1. [Introdución a Samba](#introduccion)

## Introduccion 

### ¿Que es SAMBA? 

Es un conjunto de aplicaciones Linux, basada en el protocolo SMB[^1], que permite compartir archivos en red. ### Orígenes Fue creado por [Andrew Tridgell]([https://es.wikipedia.org/wiki/Andrew_Tridgell](https://es.wikipedia.org/wiki/Andrew_Tridgell) "[https://es.wikipedia.org/wiki/Andrew_Tridgell](https://es.wikipedia.org/wiki/Andrew_Tridgell)"). 

El necesitaba montar un espacio en disco en su computadora para un servidor Unix. Esa computadora utilizaba el sistema de archivos **NFS** (**Network File System**). Sin embargo, una aplicación necesitaba soporte para el protocolo **NetBIOS[^2]** (no soportado por el NFS). Tridgell lo solucionó escribiendo un sniffer[^3] que permitía analizar el tráfico de datos generado por el protocolo NetBIOS. Hizo [ingeniería inversa]([https://es.wikipedia.org/wiki/Ingenier%C3%ADa_inversa](https://es.wikipedia.org/wiki/Ingenier%C3%ADa_inversa) "[https://es.wikipedia.org/wiki/Ingeniería_inversa](https://es.wikipedia.org/wiki/Ingenier%C3%ADa_inversa)") en el protocolo SMB y lo implementó en el Unix. 

Eso hizo que el servidor Unix apareciera como un servidor de archivos Windows en su PC con DOS. ## Instalacion ## Configuracion ## Desinstalacion [^1]: Server Message Block [^2]: Network Basic Input/Output System [^3]: Pequeño programa para captura de tráfico de datos en red. 

[^1]: Server Message Block 
[^2]: Network Basic Input/Output System 
[^3]: Pequeño programa para captura de tráfico de datos en red