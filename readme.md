# Wordpress con MySQL y phpMyAdmin usando Docker

Este proyecto configura un entorno de desarrollo que incluye Wordpress, MySQL y phpMyAdmin utilizando Docker Compose. Es ideal para el desarrollo y pruebas locales de sitios Wordpress.

## Requisitos previos

Antes de comenzar, asegúrate de tener Docker y Docker Compose instalados en tu sistema. Si no los tienes instalados, puedes descargarlos desde [Docker official website](https://docs.docker.com/get-docker/).

## Estructura del Proyecto

El proyecto incluye los siguientes archivos y carpetas principales:
- `docker-compose.yml`: Define los servicios, redes y volúmenes que Docker Compose usa para desplegar los contenedores.
- `.env`: Un archivo de variables de entorno que almacena las configuraciones sensibles como usuarios y contraseñas.
- `wp-content`: Directorio donde se almacenarán los temas, plugins y uploads de tu sitio Wordpress.

## Configuración

1. **Archivo .env**: Antes de iniciar los servicios, debes crear un archivo `.env` en la raíz del proyecto con las siguientes variables:
    MYSQL_ROOT_PASSWORD=tu_password_root
    MYSQL_DATABASE=nombre_de_tu_base_de_datos
    MYSQL_USER=usuario_de_base_de_datos
    MYSQL_PASSWORD=password_de_usuario_de_base_de_datos

## Despliegue

Para levantar el entorno con Docker Compose, sigue estos pasos:
1. Abre una terminal.
2. Navega al directorio donde se encuentra el `docker-compose.yml`.
3. Ejecuta el siguiente comando para iniciar los contenedores en modo detached:
    docker-compose up -d --build

## Accesos

- **Wordpress**: Visita `http://localhost:8080` en tu navegador para acceder a Wordpress.
- **phpMyAdmin**: Accede a `http://localhost:8081` para gestionar la base de datos MySQL a través de phpMyAdmin.

## Gestión de Datos

- Los datos de MySQL se almacenan en un volumen Docker llamado `db-data`, lo cual preserva los datos incluso cuando los contenedores son detenidos o eliminados.
- Los archivos de Wordpress como temas, plugins y uploads se montan en `./wp-content` para facilitar su edición y persistencia.

## Comandos Útiles

- **Detener los contenedores**:
    docker-compose down
- **Ver logs de los contenedores**:
    docker-compose logs
- **Reiniciar los servicios**:
    docker-compose restart

## Soporte

Si tienes preguntas o encuentras algún problema al usar este proyecto, por favor abre un issue en el repositorio de GitHub del proyecto.
