# OwnCloud2

## Instalaremos la version 7.4 de PHP en Ubuntu

Instalaremos los requisitos del PPA con el comando:
```bash
sudo apt install software-properties-common -y
```

Instalaremos las herramientas necesarias para trabajar con los archivos de (PPA) con el comando:
```bash
LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y
```

Ahora actualizaremos los repositorios con el comando:
```bash
sudo apt update
```
Instalaremos las librerías de PHP de la versión 7.4 con esta serie de comandos:
```bash
sudo apt install php7.4 -y
```
```bash
sudo apt install -y php libapache2-mod-php7.4
```

```bash
sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl
```

Selecionamos la version de PHP que queremos instalar con el comando:
```bash
sudo update-alternatives --config php
```

Activaremos los modulos necesarios de apache2 con el comando:
```bash
sudo a2enmod proxy_fcgi setenvif
```
```bash
sudo a2enconf php7.4-fpm
```
Ahora reiniciaremos apache2 con el comando:
```bash
sudo service apache2 restart
```

## Instalacion de apache2, mysql y algunas librerias mas. 

1. Primero actualizaremos la maquina virtual con el comando
 ```bash
sudo apt update
```
```bash
sudo apt upgrade
```
2.  Instalacion del servidor apache2 con el comando:
   ```bash
sudo apt install -y apache2
```

3.  Instalacion del servidor base de mysql-server
   ```bash
sudo apt install -y mysql-server
```
4. Instalacion de algunas librerias PHP
```bash
sudo apt install -y php libapache2-mod-php
```
```bash
sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl
```
5. Reiniciamos el servidor apache2
```bash
sudo systemctl restart apache2
```

## Configuracion en el servidor MySQL

1. Accederemos a la consola MySQL con el comando
```bash
sudo mysql
```

2. Creacion de la base de datos de MySQL
```bash
CREATE DATABASE bbdd;
```
3. Creacion de usuarios en la base de datos MySQL
```bash
CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
4. Daremos privilegios al usuario creado anteriormente
```bash
GRANT ALL ON bbdd.* to 'usuario'@'localhost';
```
5. Saldremos de la base de datos
```bash
exit
```
6. Probaremos la conexsion con la base de datos
```bash
mysql -u usuario -p
```
7. Volveremos a salir de la base de datos MySQL
```bash
exit
```

## Descargaremos el archivo de OwnCloud

1. Primero descargaremos el archivo del OwnCloud
```bash
https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip
```

2. Iremos al directorio /var/www/html
```bash
cd /var/www/html
```

3. Descomprimiremos el archivo cambiando el appp-web por el nombre de nuestro archivo
```bash
sudo unzip app-web.zip
```

4. Moveremos la carpeta al directorio /var/www/html
```bash
sudo cp -R app-web/. /var/www/html
```

5. Eliminaremos el unzip del archivo de la carpeta de descargas
```bash
sudo rm -rf app-web/
```

6. Eliminaremos el archivo llamado index.html
```bash


