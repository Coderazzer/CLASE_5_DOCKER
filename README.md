# CLASE_5_DOCKER

# Pasos para crear una imagen de Docker basada en Nginx con el nombre my_nginx_image

# 1. Crear un archivo llamado Dockerfile con el siguiente contenido:


FROM nginx
COPY index.html /usr/share/nginx/html/


# 2. Crear un archivo llamado index.html con el contenido deseado.


# 3. Ejecutar el siguiente comando en la terminal para construir la imagen:


docker build -t my_nginx_image .


# 4. Crear un archivo llamado docker-compose.yml con el siguiente contenido:


version: '3.9'
services:
  nginx:
    image: my_nginx_image
    ports:
      - "80:80"
    volumes:
      - nginx.config:/etc/nginx/nginx.conf
    restart: always
volumes:
  nginx.config


# 5. Ejecuta el siguiente comando en la terminal para levantar el contenedor utilizando Docker Compose:


docker-compose up -d
   

*El parametro -d levanta el contenedor en segundo plano.


# 6. Accede al servidor Nginx desde tu navegador:


http://localhost:8080
