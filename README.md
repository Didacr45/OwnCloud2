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


