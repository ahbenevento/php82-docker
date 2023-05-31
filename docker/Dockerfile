FROM php:8.2-cli

RUN apt-get update \
    && apt-get install -y sudo \
    && apt-get install -y libzip-dev

RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini" \
    && docker-php-ext-install zip

ARG USERNAME=nombre-usuario
ARG UID=1000
ARG GID=$UID

# Crear usuario y grupo
RUN groupadd --gid $GID $USERNAME \
    && useradd --uid $UID --gid $GID -m $USERNAME
# Establecer los permisos al usuario
RUN echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

USER $USERNAME
