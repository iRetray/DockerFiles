[Volver al inicio](../README.md)

# Corriendo el proyecto con como un contenedor de Docker

<img src="images/docker.png" alt="drawing" width="350"/>

Las **pruebas unitarias** en este proyecto pueden correse dentro de un **contenedor de Docker**, evitando asi problemas con versiones de Node locales o algun otro inconveniente con el ambiente local.

## Creación del contenedor

1. Descargar la imagen oficial de docker para **Node v16.14.2**

   ```sh
   docker pull node:16.14.2
   ```

2. Construir el contenedor

   ```sh
   docker build ./ --file=dockerfile.testing --progress=tty --tag=unitary_testing
   ```

3. Iniciar el contenedor previamente construido

   ```sh
   docker run -it --rm unitary_testing
   ```

Esto iniciará una **consola de bash dentro del contenedor**, con todo el proyecto y sus dependencias, listo para correr comandos como:

```sh
nx test webadmin
nx test webadmin --watch
```

> Próximament se añadirán funcionalidades para **exponer el contenedor al entorno local** y **detectar cambios en el código** para procesarlos en el contenedor
