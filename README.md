# PHP 8.2 (cli) en Docker + usuario personalizado

## Antes de poder utilizarlo

1. Editar el archivo `php82-docker/docker/Dockerfile` y reemplazar "nombre-usuario" por el usuario real.

2. Sobre la carpeta `./docker` ejecutar el siguiente comando para crear la imagen:

```console
docker-compose build
```

3. El contenedor tiene configurada como carpeta de trabajo `src/`. Todos los comandos trabajarán sobre esta carpeta.

## Composer

Comandos para descargar e instalar:

```console
# Descargar
docker-compose run php82 php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

# Instalar
docker-compose run php82 php composer-setup.php

# Descartar instalador
docker-compose run php82 rm composer-setup.php
```

## Instalar paquetes

```console
docker-compose run php82 php composer.phar require phpmailer/phpmailer
```
