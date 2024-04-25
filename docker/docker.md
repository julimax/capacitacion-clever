
## Introducción a Docker
- ¿Qué es Docker?

Docker es una plataforma de código abierto que permite automatizar el despliegue de aplicaciones dentro de contenedores de software. Los contenedores son una forma de empaquetar una aplicación con todas sus dependencias y ejecutarla de forma aislada en cualquier entorno.

- Historia y contexto

Docker fue lanzado por primera vez en 2013 y se basa en tecnologías de contenedores Linux existentes, como cgroups y namespaces, para crear un entorno ligero y portátil para aplicaciones. Docker se ha convertido en una herramienta popular en el desarrollo de software moderno debido a su capacidad para simplificar el proceso de desarrollo, pruebas y despliegue de aplicaciones.

- Ventajas y casos de uso

  - Aislamiento de aplicaciones: Los contenedores proporcionan un entorno aislado para ejecutar aplicaciones, lo que ayuda a prevenir conflictos entre ellas.
  - Portabilidad: Los contenedores Docker pueden ejecutarse en cualquier entorno que admita Docker, lo que facilita el despliegue de aplicaciones en diferentes plataformas.
  - Escalabilidad: Docker permite escalar aplicaciones de forma rápida y sencilla mediante la creación de múltiples instancias de contenedores.
  - Eficiencia: Los contenedores Docker son ligeros y comparten el kernel del sistema operativo, lo que los hace más eficientes en recursos que las máquinas virtuales.

- Algunos casos de uso comunes de Docker incluyen:
  - Despliegue de aplicaciones: Docker facilita el despliegue de aplicaciones al proporcionar un entorno consistente y predecible para su ejecución.
  - Desarrollo de software: Los contenedores Docker permiten a los desarrolladores trabajar en entornos aislados que reproducen fielmente el entorno de producción.
  - Microservicios: Docker es una herramienta popular para implementar arquitecturas de microservicios, ya que permite a las aplicaciones estar encapsuladas en contenedores independientes y escalables.

## Conceptos fundamentales
- Contenedores vs. máquinas virtuales
  
    - **Máquinas virtuales (VMs):**
    - Las VMs emulan un hardware físico para ejecutar sistemas operativos y aplicaciones.
    - Cada VM incluye un sistema operativo completo, lo que puede llevar a un uso intensivo de recursos.
    - El tiempo de inicio de una VM puede ser relativamente largo.

    - **Contenedores:**
    - Los contenedores comparten el mismo sistema operativo y kernel del host, lo que los hace más ligeros.
    - Cada contenedor ejecuta una aplicación o proceso específico, con sus propias bibliotecas y dependencias, pero comparte el kernel con otros contenedores.
    - Los contenedores son más rápidos de iniciar que las VMs y utilizan menos recursos.
      
  ![Docker Image](../imagenes/docker-vs-virtual-machine.png)
      
- Imágenes Docker

  - Las imágenes Docker son plantillas de solo lectura que contienen el sistema operativo, las bibliotecas y las dependencias necesarias para ejecutar una aplicación.
  - Las imágenes se utilizan para crear contenedores Docker, que son instancias en ejecución de una imagen.
  - Las imágenes se definen mediante un archivo Dockerfile, que especifica los pasos necesarios para construir la imagen.
    
- Contenedores Docker

  - Un contenedor Docker es una instancia en ejecución de una imagen Docker.
  - Los contenedores proporcionan un entorno aislado para ejecutar aplicaciones, con sus propios procesos, redes y sistemas de archivos.
  - Los contenedores son portátiles y pueden ejecutarse en cualquier entorno que admita Docker.
    
- Docker Engine

  - Docker Engine es el componente de Docker que ejecuta y gestiona los contenedores Docker.
  - Docker Engine incluye el daemon de Docker, que es un servicio que se ejecuta en segundo plano para gestionar la creación, ejecución y destrucción de contenedores.
  - Docker Engine también incluye la CLI de Docker, que se utiliza para interactuar con el daemon y gestionar los contenedores y las imágenes.


## Instalación y configuración
- Descarga e instalación en diferentes sistemas operativos
- Configuración básica

## Crear imagen docker

###Una vez construida la imagen, se puede utilizar para crear y ejecutar contenedores Docker
  
  docker build -t mydjangoapp .

Esto construiría una imagen con nombre "mi_imagen" a partir del Dockerfile en el directorio actual

## Creación y gestión de contenedores

- Ejecución de contenedores
  - Para ejecutar un contenedor Docker, se utiliza el comando `docker run`.

  docker run -p 5000:443 mydjangoapp

- Interacción con contenedores
  
  - Para interactuar con un contenedor en ejecución, se pueden utilizar varios comandos de Docker, como `docker exec`, `docker attach`, y `docker logs`.
  - Ejemplo: `docker exec -it mydjangoapp /bin/bash` (esto abriría una sesión bash interactiva en el contenedor llamado "mi_contenedor").

- Ciclo de vida de un contenedor
  
  1. **Creación:** Un contenedor se crea a partir de una imagen Docker utilizando el comando `docker run`.
  2. **Ejecución:** El contenedor está en ejecución mientras su proceso principal (PID 1) está en ejecución.
  3. **Pausa:** Se puede pausar un contenedor en ejecución utilizando el comando `docker pause`.
  4. **Reanudación:** Un contenedor pausado se puede reanudar utilizando el comando `docker unpause`.
  5. **Detención:** Un contenedor en ejecución se puede detener utilizando el comando `docker stop`.
  6. **Inicio:** Un contenedor detenido se puede reiniciar utilizando el comando `docker start`.
  7. **Eliminación:** Un contenedor detenido se puede eliminar utilizando el comando `docker rm`.


## Dockerfile
- Estructura y sintaxis
  
  - Un Dockerfile es un archivo de texto plano que contiene una serie de instrucciones que Docker utiliza para construir una imagen Docker.
  - Cada instrucción en un Dockerfile se ejecuta secuencialmente y se utiliza para definir diferentes aspectos de la imagen, como el sistema operativo base, las dependencias, los comandos a ejecutar, etc.
  - El Dockerfile debe comenzar con una instrucción `FROM` que especifique la imagen base a partir de la cual se construirá la nueva imagen.

- Instrucciones básica
  
  - **FROM:** Especifica la imagen base a partir de la cual se construirá la nueva imagen.
  - **RUN:** Ejecuta comandos en la nueva capa de la imagen y crea una nueva capa con los resultados. Se utiliza para instalar paquetes, configurar el entorno, etc.
  - **COPY:** Copia archivos y directorios desde el sistema de archivos del host al sistema de archivos de la imagen.
  - **ADD:** Similar a COPY, pero también puede aceptar URLs como fuente y descomprimir automáticamente archivos comprimidos.
  - **CMD:** Proporciona un comando predeterminado para ejecutar cuando se inicie un contenedor a partir de la imagen. Solo puede haber una instrucción CMD en un Dockerfile.
  - **ENTRYPOINT:** Define un comando que se ejecutará cada vez que se inicie un contenedor a partir de la imagen. Puede haber solo una instrucción ENTRYPOINT en un Dockerfile.
  - **ENV:** Establece variables de entorno dentro de la imagen.
  - **EXPOSE:** Expone puertos en los contenedores basados en la imagen.
  - **WORKDIR:** Establece el directorio de trabajo para cualquier instrucción RUN, CMD, ENTRYPOINT, COPY y ADD que se ejecute en la imagen.
  - **VOLUME:** Crea un punto de montaje para almacenar datos generados por el contenedor o para acceder a datos desde el host.


## Redes en Docker
- Tipos de redes en Docker
- Creación y gestión de redes
- Conexión de contenedores en redes

## Volúmenes en Docker
- Persistencia de datos en contenedores
- Tipos de volúmenes
- Gestión de volúmenes

## Docker Compose
- Definición y sintaxis de archivos YAML
- Uso de Docker Compose para la gestión de aplicaciones multi-contenedor
- Ejemplos de uso

## Orquestación de contenedores con Docker Swarm (opcional)
- Conceptos básicos de orquestación
- Configuración de un clúster Docker Swarm
- Despliegue y gestión de servicios

## Integración con otras herramientas
- Docker y CI/CD
- Docker y herramientas de monitorización
- Docker y Kubernetes
