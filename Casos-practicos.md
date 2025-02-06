<h1 align="center"> Casos Prácticos </h1> 

*Acabamos de terminar el CFGS ASIR y encontramos trabajo en la empresa Servicios Web RC, SA en Huelva. Anteriormente utilizaban Apache como servidor web y quieren migrar a Nginx. Una vez instalado y configurado, procedemos a realizar todos los casos prácticos solicitados.*

## A) Versión de Nginx 
Para ver la versión de *Nginx*, ejecutaremos el comando `nginx -v`. 

![Comprobación de red](./Img/captura5.png)

## B) Servicio asociado 
Para comprobar que *Nginx* está instalado correctamente ejecutaremos `systemctl status nginx`. 

![Comprobación de red](./Img/captura6.png)

## C) Ficheros de configuración 
El fichero se encuentra en `/etc/nginx`. 

![Comprobación de red](./Img/captura7.png)

Y el archivo de configuración es `nginx.conf`. 

![Comprobación de red](./Img/captura8.png)

## D) Modificación de la página web 
Para modificar la página web predererminada de *Nginx* modificaremos el archivo `index.nginx-debian.html` que se encuentra en `/var/www/html/`. 

![Comprobación de red](./Img/captura9.png)

## E) Virtual hosting 
- El servidor tendrá dos sitios web, para ello crearemos dos directorios para los dos sitios web y le concederemos sus permisos correspondiente. 

![Comprobación de red](./Img/captura10.png) 
![Comprobación de red](./Img/captura11.png) 

- Crearemos el archivo `index.html` para los dos sitios web. 

![Comprobación de red](./Img/captura12.png) 
![Comprobación de red](./Img/captura13.png) 

- Crearemos los dos archivos en `sites-availables` para los dos sitios web. 

![Comprobación de red](./Img/captura14.png) 

- Configuraremos el archivo `hosts` para los dos sitios web. 

![Comprobación de red](./Img/captura15.png) 

- Reiniciamos el servidor y comprobaremos el resultado. 

![Comprobación de red](./Img/captura16.png) 

## F) Autenticación, autorización y control de acceso 
El sitio web1 puede acceder desde la red interna como desde la red externa, en cambio el sitio web2 solo puede acceder mediante red interna. Para conseguir esto deberemos realizar: 

- Modificaremos los archivos web1 y web2 en `sites-availables` de cada archivo. 

![Comprobación de red](./Img/captura17.png) 
![Comprobación de red](./Img/captura18.png) 

- Modificaremos el archivos `hosts` para agregar las ip´s permitidas tanto para red interna como para red externa. 

![Comprobación de red](./Img/captura19.png)

- Comprobaremos la red interna.

![Comprobación de red](./Img/captura20.png) 

- Comprobaremos la red externa.

![Comprobación de red](./Img/captura21.png) 

## G) Autenticación, autorización y control de acceso 
*Web1.org* contiene un directorio privado al que sólo pueden acceder usuarios válidos. 

- Crearemos el usuario con el comando `htpasswd`.

![Comprobación de red](./Img/captura22.png) 

- Modificaremos el archivo `sites-availables`. 

![Comprobación de red](./Img/captura23.png) 

- Comprobamos que *web1.org* requiere autenticación. 

![Comprobación de red](./Img/captura24.png) 

- Comprobamos que tenemos acceso. 
  
![Comprobación de red](./Img/captura25.png) 

## H) Autenticación, autorización y control de acceso 
*Web1.org* contiene un directorio llamado privado, desde la red externa pide autorización y desde la red interna NO. 

- Modificamos el archivo `sites-availables`. 

![Comprobación de red](./Img/captura26.png) 

## I) Seguridad 
Configura el sitio virtual *www.web1.org* para que el acceso sea seguro. 

- Crearemos un key privado. 

![Comprobación de red](./Img/captura27.png) 
  
- Modificaremos el archivo `sites-availables`. 

![Comprobación de red](./Img/captura28.png) 

## Selección de página 
[Volver](./Instalacion.md)  
[Ir a Referencias](./Referencias.md)  
