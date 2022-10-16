# apache

Reemplace `$ALUMNO` por el nombre de su nombre de usuario en www.tecnologoinformatico.com

EJ: `dmascheroni`

1. Cree el directorio ~/repositorios y dentro clone el
repositorio: `https://github.com/TecnologoInformatico/AdmInf-web.git`
2. Actualice el repositorio de la lista de paquetes.
    `apt update`
3. Instalar el servidor Apache mediante apt.
4. Cree el directorio /var/www/$ALUMNO
5. Asigne como propietario del directorio su usuario.
6. Configure un nuevo Virtual host. (copiando el archivo de configuración por defecto)
  6.1. ServerName $ALUMNO.tecnologoinformatico.com
  6.2. Correo de contacto con el administrador.
  6.3. El root de la aplicación. (/var/www/$ALUMNO)
7. Modifique el archivo /etc/hosts de modo que el ServerName coincida con este equipo `127.0.0.1`.
8. Reinicie el servidor apache para que los cambios tengan efecto.
9. Copie el contenido del directorio ~/repositorios/AdmInf-web a /var/www/$ALUMNO, de tal modo que el contenido del repositorio antes clonado se encuentre en el root de la aplicación.
10. Verifique que el servidor funcione correctamente.
11. Ingrese la IP del servidor y el servername a continuación:

```json
{
    "serverName": "",
    "ip": ""
}
```
===========TAREA=========
sudo apt update
sudo apt install apache2
systemctl status apache2(chequea estado)
cd /etc/apache2/
ls
cd sites-available/
cd -(vuelve al directorio anterior)
ls sites-enables/
cd -
sudo cp 000-default.conf ./amartinez.conf
sudo nano amartinez.conf

borramos el comentario de ServerName y ponemos ServerName www.test.com
DocumentRoot /var/www/teast(guardar)
sudo mkdir /var/www/test
cd /var/www/test/
sudo nano index.html

poner cualquier texto
guardo
sudo a2ensite amartinez.conf
sudo systemctl relaod apache2
sudo nano /etc/hosts
copiamos primer linea 127.0.0.1 
y la ponemos abajo de todo el archivo
127.0.0.1	www.test.com
guardamos
curl http://www.test.com

---------------------------------------------------------------------------------------------
en la seccion de c, system32 en hosts pones la ip del servidor que quieras conectarse

