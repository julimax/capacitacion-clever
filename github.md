###### Temario de Fundamentos de GitHub

## Introducción a GitHub
- ¿Qué es GitHub?

GitHub es una plataforma basada en la nube que utiliza Git, un sistema de control de versiones distribuido, en su núcleo. La plataforma GitHub simplifica el proceso de colaboración en proyectos y proporciona un sitio web, herramientas de línea de comandos y un flujo general que permite a los desarrolladores y usuarios trabajar juntos.
  
- Principales características y funciones

  - AI
    
  La plataforma GitHub Enterprise está mejorando la colaboración a través de solicitudes de extracción y problemas impulsados por IA, la productividad a través de Copilot y la seguridad al automatizar los controles de seguridad más rápidamente.

  - Colaboración
    
  La colaboración es el núcleo de todo lo que hace GitHub. Sabemos que una colaboración ineficiente resulta en una pérdida de tiempo y dinero. Contrarrestamos esto con un conjunto de herramientas integradas que permiten que la colaboración se produzca sin esfuerzo.

  - Productividad
    
  La productividad se acelera con la automatización que proporciona GitHub Enterprise Platform. Con herramientas CI/CD integradas directamente en el flujo de trabajo, la plataforma brinda a los usuarios la capacidad de establecer tareas y olvidarlas, encargándose de la administración rutinaria y acelerando el trabajo diario. Esto les da a sus desarrolladores más tiempo para concentrarse en lo más importante: crear soluciones innovadoras.

  - Seguridad
    
  GitHub se centra en integrar la seguridad directamente en el proceso de desarrollo desde el principio. La plataforma GitHub Enterprise incluye características de seguridad nativas propias que minimizan el riesgo de seguridad con una solución de seguridad integrada. Además, su código permanece privado dentro de su organización y, al mismo tiempo, puede aprovechar la descripción general de seguridad y el Dependabot.
  GitHub ha seguido invirtiendo para garantizar que nuestras funciones estén preparadas para la empresa. Contamos con el respaldo de Microsoft, la confianza de industrias altamente reguladas y cumplimos con los requisitos de cumplimiento a nivel mundial.

  - Escala
    
  GitHub es la comunidad de desarrolladores más grande de su tipo. Con datos en tiempo real sobre más de 100 millones de desarrolladores, más de 330 millones de repositorios e innumerables implementaciones, hemos podido comprender las necesidades cambiantes de los desarrolladores y realizar cambios en nuestro producto para adaptarnos.

Ahora entremos en la columna vertebral de GitHub, los repositorios.

## Creación y configuración de una cuenta
- Crear una cuenta en GitHub

1. Ve a la página principal de GitHub en [github.com](https://github.com).
2. Haz clic en "Sign up" (Registrarse) en la esquina superior derecha.
3. Completa el formulario de registro con tu dirección de correo electrónico, nombre de usuario y contraseña.
4. Verifica tu dirección de correo electrónico haciendo clic en el enlace de confirmación que recibirás por correo electrónico.

- Configuración básica del perfil

1. Inicia sesión en tu cuenta de GitHub.
2. Haz clic en tu foto de perfil en la esquina superior derecha y selecciona "Your profile" (Tu perfil).
3. En la pestaña "Overview" (Resumen), puedes editar tu nombre, nombre de usuario, biografía, foto de perfil y más.
4. En la pestaña "Account settings" (Configuración de la cuenta), puedes actualizar tu dirección de correo electrónico, cambiar tu contraseña y gestionar otras configuraciones de la cuenta.

- Configuración de la autenticación de dos factores
  
1. En tu perfil de GitHub, ve a "Account settings" (Configuración de la cuenta) > "Security" (Seguridad).
2. Haz clic en "Set up two-factor authentication" (Configurar autenticación de dos factores).
3. Selecciona el método de autenticación que prefieras (por ejemplo, SMS, aplicación de autenticación).
4. Sigue las instrucciones para completar la configuración de la autenticación de dos factores.

## Uso básico de GitHub
- Crear un repositorio
  
Para crear un repositorio en GitHub, sigue estos pasos:
1. Inicia sesión en tu cuenta de GitHub.
2. En la esquina superior derecha, haz clic en el signo más (`+`) y selecciona "New repository" (Nuevo repositorio).
3. Ingresa un nombre para tu repositorio, una descripción opcional y selecciona si será público o privado.
4. Opcionalmente, puedes inicializar el repositorio con un archivo README, un archivo gitignore o una licencia.
5. Haz clic en "Create repository" (Crear repositorio) para finalizar la creación.

- Clonar un repositorio
  
Para clonar un repositorio existente en GitHub a tu computadora, sigue estos pasos:
1. Ve al repositorio en GitHub que deseas clonar.
2. Haz clic en el botón "Code" (Código) y copia la URL del repositorio.
3. Abre tu terminal y ejecuta el siguiente comando, reemplazando `<URL>` con la URL que copiaste:
   
   ```sh
   git clone <URL>
   ```
   
- Agregar y eliminar archivos
Para agregar y eliminar archivos en GitHub, sigue estos pasos:

1. Ve al repositorio en GitHub donde deseas realizar los cambios.
2. Haz clic en el botón "Add file" (Agregar archivo) y selecciona "Upload files" (Cargar archivos) para agregar archivos, o selecciona un archivo existente y luego haz clic en el botón de eliminar (icono de papelera) para eliminarlo.

- Realizar commits
Para realizar un commit en GitHub, sigue estos pasos:

1. Haz los cambios deseados en tus archivos.
2. En la página del repositorio, haz clic en el botón "Commit changes" (Confirmar cambios).
3. Proporciona un mensaje descriptivo para tu commit y haz clic en "Commit changes" nuevamente.

- Ver historial de commits
Para ver el historial de commits en GitHub, sigue estos pasos:

1. Ve al repositorio en GitHub.
2. Haz clic en la pestaña "Commits" para ver una lista de todos los commits realizados en el repositorio, junto con sus mensajes y quién los realizó.

- Crear y gestionar ramas
Para crear y gestionar ramas en GitHub, sigue estos pasos:

1. En la parte superior de la página del repositorio, haz clic en el menú desplegable que muestra la rama actual.
2. Escribe el nombre de la nueva rama en el campo de búsqueda y presiona Enter para crearla.
3. Para cambiar de una rama a otra, utiliza el mismo menú desplegable y selecciona la rama deseada.
4. Puedes fusionar ramas usando la interfaz web de GitHub, pero ten en cuenta que algunas fusiones pueden requerir un pull request y aprobación.

## Trabajo colaborativo en GitHub

- **Colaborar en un repositorio:** Trabajar en equipo en un repositorio compartido, permitiendo a múltiples personas contribuir al código, realizar cambios y mantener un historial de versiones.

- **Realizar pull requests:** Solicitar la incorporación de cambios realizados en una rama a otra rama, permitiendo revisar y discutir los cambios antes de fusionarlos.

- **Revisar y aprobar pull requests:** Analizar los cambios propuestos en un pull request, hacer comentarios, sugerir modificaciones y finalmente aprobar la fusión si los cambios son aceptables.

- **Forks y contribuciones a proyectos de código abierto:** Crear una copia personal de un repositorio ajeno para realizar cambios sin afectar el repositorio original, y contribuir con mejoras a proyectos de código abierto mediante pull requests desde el fork.

- **Markdown:** Lenguaje de marcado ligero para formatear texto de manera sencilla y legible en plataformas como GitHub, permitiendo agregar estilo al texto sin necesidad de utilizar HTML.

- **README.md:** Archivo de texto Markdown que se encuentra en la raíz de un repositorio y que suele contener información relevante sobre el proyecto, como su descripción, instrucciones de instalación, uso y contribución, entre otros.

- **GitHub flow:** Metodología de trabajo que utiliza ramas para cada nueva funcionalidad o corrección de errores, pull requests para solicitar la revisión de los cambios y la fusión de ramas una vez que los cambios han sido aprobados.

- **Discussions:** Espacio en GitHub para discutir temas relacionados con un repositorio, permitiendo a los colaboradores intercambiar ideas, hacer preguntas y proponer soluciones.

- **GitHub Pages:** Servicio de GitHub que permite publicar sitios web estáticos directamente desde un repositorio, facilitando la creación de páginas web para documentación, portafolios y proyectos personales.

- **Gists:** Pequeños fragmentos de código, textos o imágenes que se pueden compartir de forma pública o privada en GitHub, útiles para mostrar ejemplos de código, tomar notas o colaborar en pequeños proyectos.

- **Wikis:** Páginas web colaborativas asociadas a un repositorio en GitHub, que permiten documentar el proyecto, compartir información y colaborar en la creación de contenido.

- **Issues:** Registro de tareas, mejoras, errores o cualquier otro tema relacionado con un proyecto en GitHub, que permite realizar un seguimiento de las actividades y facilita la colaboración entre los miembros del equipo.


## Cuentas, planes y permisos

- **Tipo de cuentas**
    - Personal: Cuenta individual para uso personal.
    - Organization: Cuenta para organizaciones o equipos de trabajo, que permite gestionar varios repositorios y colaboradores.
    - Enterprise: Cuenta para empresas grandes que necesitan funciones avanzadas de seguridad y gestión.

- **Tipos de planes**
    - GitHub Free: Gratuito para cuentas personales y organizaciones, con funciones básicas como control de versiones, seguimiento de problemas y colaboración básica.
    - GitHub Pro: Para cuentas personales que requieren funciones avanzadas como repositorios privados y soporte prioritario.
    - GitHub Team: Para equipos que necesitan colaboración y administración de proyectos avanzada.
    - GitHub Enterprise: Para empresas que necesitan control total sobre su infraestructura de GitHub, con funciones de seguridad y gestión avanzadas.

- **Permisos**
    - Read: Permite ver y clonar repositorios.
    - Triage: Permite gestionar problemas y solicitudes de extracción.
    - Write: Permite realizar cambios en los repositorios, incluida la creación de ramas y la confirmación de cambios.
    - Maintain: Permite administrar el repositorio, incluida la administración de problemas, solicitudes de extracción y ramas.
    - Admin: Permite realizar cambios en la configuración del repositorio, incluidos los permisos de los colaboradores y la configuración de la seguridad.

  
## Seguridad y control en GitHub

- **Codeowners:** Archivo en un repositorio que especifica qué usuarios o equipos son responsables de revisar y aprobar cambios en ciertos archivos o directorios, ayudando a distribuir la responsabilidad de revisión del código.

- **Branch Protection:** Funcionalidad que permite proteger ramas específicas de un repositorio, configurando reglas que controlan quién puede hacer cambios directamente en la rama y quién debe hacer cambios a través de solicitudes de extracción (pull requests).

- **Rulesets:** Conjunto de reglas configurables que se pueden aplicar a un repositorio para controlar el comportamiento de los colaboradores y las acciones que pueden realizar, como requerir revisiones de código antes de fusionar cambios.

- **CodeQL:** Herramienta de análisis estático de código propiedad de GitHub que permite identificar vulnerabilidades de seguridad y errores en el código, ayudando a mejorar la calidad y seguridad del software.

- **Dependabot:** Bot de GitHub que escanea los archivos de dependencias de un repositorio en busca de actualizaciones de paquetes y crea solicitudes de extracción automáticas para mantener las dependencias actualizadas y seguras.

## Introducción a GitHub Copilot

- **¿Qué es GitHub Copilot?** GitHub Copilot es una extensión para varios editores de código que utiliza inteligencia artificial para ayudarte a escribir código, ofreciendo sugerencias de código en tiempo real basadas en el contexto de tu proyecto y tus patrones de escritura.

- **Funcionalidades principales** GitHub Copilot puede ayudarte a completar líneas de código, escribir funciones completas, ofrecer correcciones rápidas y sugerencias de refactorización, todo ello basado en el contexto de tu código y el lenguaje de programación que estés utilizando.

- **Integración con editores de código** GitHub Copilot está integrado con varios editores de código populares, como Visual Studio Code, JetBrains IntelliJ IDEA y PyCharm, Atom y Visual Studio, lo que te permite utilizar sus funciones directamente desde tu entorno de desarrollo favorito.

## Codespaces, GitHub Mobile y GitHub Desktop

- **Codespaces: desarrollo en la nube con GitHub** Codespaces es un entorno de desarrollo en la nube que te permite crear y gestionar entornos de desarrollo completos directamente desde GitHub, lo que facilita la colaboración y el desarrollo desde cualquier lugar.

- **GitHub Mobile: acceso a GitHub desde dispositivos móviles** GitHub Mobile es una aplicación móvil que te permite acceder a tus repositorios, problemas, solicitudes de extracción y otras funciones de GitHub desde tu dispositivo móvil, facilitando la colaboración y la gestión de tus proyectos en movimiento.

- **GitHub Desktop: cliente de escritorio para GitHub** GitHub Desktop es una aplicación de escritorio que te permite gestionar tus repositorios de GitHub de forma visual y sencilla, permitiéndote clonar repositorios, crear ramas, realizar confirmaciones y fusionar cambios de forma intuitiva.

    
## Gestión de proyectos en GitHub

- **Crear proyectos y tableros:** Utiliza la función de proyectos de GitHub para organizar y priorizar tareas, crear tableros personalizados y visualizar el progreso de tu proyecto.

- **Asignar tareas y gestionar el flujo de trabajo:** Asigna tareas a colaboradores, establece fechas límite y utiliza etiquetas para categorizar y seguir el progreso de las tareas.

- **Uso de issues y milestones en GitHub projects:** Utiliza issues para rastrear errores, solicitudes de funcionalidades y otras tareas, y agrupa issues relacionados en milestones para un mejor seguimiento del progreso del proyecto.

## Buenas prácticas y recomendaciones

- **Estructura de repositorios:** Mantén una estructura de repositorio clara y coherente, con carpetas bien organizadas y nombres de archivos descriptivos para facilitar la navegación y la colaboración.

- **Mensajes de commit descriptivos:** Escribe mensajes de commit claros y descriptivos que expliquen los cambios realizados y por qué se realizaron, para que otros colaboradores puedan entender fácilmente el historial de cambios.

- **Uso de ramas de forma adecuada:** Utiliza ramas para trabajar en nuevas funcionalidades o correcciones de errores, fusionando cambios a la rama principal (por ejemplo, `main` o `master`) mediante solicitudes de extracción una vez que estén listos y revisados.

- **Mantenimiento y limpieza de repositorios:** Elimina ramas y archivos obsoletos, revisa regularmente los issues y las tareas pendientes, y realiza una limpieza periódica del repositorio para mantenerlo organizado y eficiente.

