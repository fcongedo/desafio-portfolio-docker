# Instalación de Herramientas e Imagen de Docker

Este README proporciona instrucciones básicas para la instalación de herramientas necesarias y la configuración de una máquina virtual con Vagrant para ejecutar contenedores Docker.

## Configuración de Vagrant

1. **Directorio Vagrant**: En el directorio de tu proyecto, encontrarás una carpeta llamada "Vagrant". Esta carpeta contiene la configuración necesaria para levantar una máquina virtual.

2. **Iniciar la Máquina Virtual**: Para iniciar la máquina virtual, ejecuta el siguiente comando dentro del directorio "Vagrant":
   ```bash
   vagrant up

1. **Conexión SSH**:  Para conectarte a la máquina virtual por SSH, utiliza el siguiente comando:
   ```bash
   vagrant ssh

2. **Túnel a la Máquina Host**: Puedes crear un túnel desde la máquina virtual a tu máquina host para acceder a servicios que se ejecuten en la VM desde el host. Utiliza el siguiente comando para configurar el túnel:
   ```bash
   vagrant ssh -- -L 8080:localhost:8080

## Uso de docker

1. **Crear la Imagen de Docker Manualmente**:Para crear una imagen de Docker de manera manual, ejecuta el siguiente comando, que mapea el puerto 8080 de la máquina virtual al puerto 80 del contenedor. Asegúrate de cambiar los nombres y versiones según tu configuración:
   ```bash
   docker run -d -p 8080:80 --name mi-contenedor-apache2 fcongedo/mi-portfolio-apache2:1.0


2. **Crear la Imagen de Docker con Docker Compose**: Dirígete al directorio /vagrant/Docker-compose en la máquina virtual y ejecuta el siguiente comando para crear la imagen utilizando Docker Compose
   ```bash
   docker-compose up -d