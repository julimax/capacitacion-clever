# Temario de Estudio de Git

## Introducción a Git
- ¿Qué es Git?
Git es un sistema de control de versiones distribuido de código abierto diseñado para manejar todo, desde proyectos pequeños hasta muy grandes, con velocidad y eficiencia. Fue creado por Linus Torvalds en 2005 para el desarrollo del kernel de Linux, pero su uso se ha extendido a muchos otros proyectos.


- Historia de Git

Git fue creado por Linus Torvalds en 2005 para el desarrollo del kernel de Linux. Antes de Git, el proyecto del kernel de Linux utilizaba un sistema de control de versiones llamado BitKeeper. Sin embargo, en 2005, hubo un desacuerdo sobre el acceso gratuito a BitKeeper, lo que llevó a Torvalds a crear su propio sistema de control de versiones.
Torvalds diseñó Git con un enfoque en la velocidad, el diseño sencillo y la capacidad de gestionar proyectos grandes de forma eficiente. Git se basa en un modelo distribuido, lo que significa que cada usuario tiene una copia completa del repositorio, lo que facilita el trabajo colaborativo y la gestión de ramas.
Desde su creación, Git ha ganado una gran popularidad y se ha convertido en uno de los sistemas de control de versiones más utilizados en la industria del desarrollo de software. Es ampliamente utilizado en proyectos de código abierto y en empresas de todo el mundo.

- Ventajas de usar Git

**Distribuido**: Git es un sistema de control de versiones distribuido, lo que significa que cada desarrollador tiene una copia completa del repositorio. Esto facilita el trabajo offline y la colaboración entre equipos distribuidos.
**Rápido y eficiente**: Git está diseñado para ser rápido y eficiente, incluso en proyectos muy grandes. Las operaciones como hacer commit, fusionar ramas y revisar el historial son rápidas y suelen realizarse localmente.
**Gestión de ramas**: Git facilita la creación y gestión de ramas, lo que permite a los equipos trabajar en paralelo en diferentes características o correcciones de errores sin interferir entre sí. Esto también facilita la integración continua y la entrega continua.
**Seguimiento de cambios**: Git realiza un seguimiento completo de los cambios realizados en el código, lo que permite a los desarrolladores revisar el historial, revertir cambios y realizar un seguimiento de quién hizo qué y cuándo.
**Compatibilidad**: Git es compatible con una amplia gama de sistemas operativos y servicios de alojamiento de repositorios, lo que facilita su integración en entornos de desarrollo existentes.
**Comunidad y soporte**: Git cuenta con una gran comunidad de usuarios y desarrolladores que ofrecen soporte y recursos, lo que facilita su aprendizaje y resolución de problemas.


## Configuración
- Configuración inicial de Git

Después de instalar Git, es importante configurarlo correctamente antes de empezar a usarlo. A continuación, se detallan los pasos para la configuración inicial:

### Configurar el nombre de usuario
Establece tu nombre de usuario que se utilizará para identificar tus commits:
```sh
git config --global user.name "Tu Nombre"
git config --global user.email "tu_correo@ejemplo.com"
git config --list
```

- Configuración de SSH en Git

Si deseas utilizar SSH para autenticarte con Git en lugar de HTTPS, sigue estos pasos:

### 1. Generar una nueva clave SSH
Si aún no tienes una clave SSH, genera una nueva usando el siguiente comando en tu terminal:
```sh
ssh-keygen -t rsa -b 4096 -C "tu_correo@ejemplo.com"
```

## Conceptos básicos de Git

- Repositorio

Un repositorio en Git es donde se almacena todo el historial de cambios de un proyecto, así como las diferentes versiones de los archivos.

- Commit

Un commit en Git representa un cambio específico en el repositorio. Cada commit tiene un mensaje que describe el cambio realizado.

- Branch

Una rama en Git es una línea de desarrollo independiente que permite trabajar en diferentes características o correcciones de errores sin afectar la rama principal.

- Merge

El merge en Git es el proceso de combinar los cambios de una rama en otra. Se utiliza para integrar los cambios de una rama de desarrollo en la rama principal.

- Remote

Un remote en Git es una referencia a un repositorio remoto, que puede estar alojado en un servidor en línea como GitHub, GitLab o Bitbucket.

- Pull y Push

Pull y Push son dos operaciones fundamentales en Git para sincronizar los cambios entre un repositorio local y un repositorio remoto. Pull se utiliza para obtener los cambios del repositorio remoto y actualizar el repositorio local, mientras que Push se utiliza para enviar los cambios locales al repositorio remoto.

- Conflictos

Los conflictos en Git ocurren cuando dos ramas tienen cambios diferentes en la misma parte de un archivo. Git no puede determinar automáticamente qué cambio debe prevalecer, por lo que es necesario resolver los conflictos manualmente.


## Uso básico de Git

- Clonar un repositorio remoto

Para clonar un repositorio remoto en Git y obtener una copia local en tu máquina, puedes utilizar el siguiente comando:

```sh
git clone <url_repositorio>
```

- Creación de un repositorio

Para crear un nuevo repositorio en Git, puedes utilizar el siguiente comando en la terminal en el directorio de tu proyecto:

```sh
git init
```

- Agregar y eliminar archivos

```sh
git add <nombre_archivo>
```

```sh
git rm <nombre_archivo>
```

- Realizar commits

```sh
git commit -m "Mensaje del commit"
```

- Ver historial de commits

```sh
git log
```

- Crear y gestionar ramas

Para crear una nueva rama en Git, puedes utilizar el siguiente comando:
```sh
git branch <nombre_rama>
```

Para cambiar a una rama existente, puedes utilizar el siguiente comando:
```sh
git checkout <nombre_rama>
```

Para fusionar una rama con la rama actual, puedes utilizar el siguiente comando:
```sh
git merge <nombre_rama>
```

## Uso avanzado de Git

- Revertir cambios

Para revertir cambios en Git y deshacer un commit, puedes utilizar el siguiente comando:

```sh
git revert <hash_commit>
```

- Resolución de conflictos

Para resolver conflictos en Git, primero necesitas abrir los archivos con conflictos y editarlos manualmente para elegir qué cambios mantener. Una vez resueltos los conflictos, puedes agregar los archivos al área de preparación y hacer un commit para finalizar la fusión.

- Uso de tags

Los tags en Git se utilizan para marcar puntos específicos en la historia de un repositorio, como versiones de lanzamiento. Para crear un tag en Git, puedes utilizar el siguiente comando:

```sh
git tag <nombre_tag>
```

- Submódulos

Los submódulos en Git permiten incluir otros repositorios Git dentro de un repositorio principal. Esto es útil cuando quieres incluir dependencias externas en tu proyecto. Para agregar un submódulo a tu repositorio, puedes utilizar el siguiente comando:

```sh
git submodule add <url_repositorio> <directorio_destino>
```

- Stashing

El stashing en Git te permite guardar temporalmente los cambios locales sin hacer un commit. Esto es útil cuando quieres cambiar de rama o aplicar otros cambios antes de comprometer los cambios guardados. Para hacer un stash en Git, puedes utilizar el siguiente comando:

```sh
git stash
```

Para aplicar los cambios guardados, puedes utilizar el siguiente comando:

```sh
git stash apply
```

## Buenas prácticas y recomendaciones

- Estructura de repositorios

Es importante mantener una estructura de repositorios organizada y coherente para facilitar la navegación y el mantenimiento del código. Algunas recomendaciones incluyen:

1- Utilizar directorios para organizar diferentes tipos de archivos (por ejemplo, `src` para el código fuente, `docs` para la documentación, `tests` para las pruebas, etc.).
2- Utilizar nombres descriptivos para los archivos y directorios.
3- Evitar tener demasiados archivos en un solo directorio para evitar la congestión.
4- Mensajes de commit descriptivos
5- Uso de ramas de forma adecuada
6- Mantenimiento y limpieza de repositorio26
