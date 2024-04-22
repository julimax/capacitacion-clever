# Temario de Fundamentos de GitHub

## Introducción a GitHub
- ¿Qué es GitHub?

GitHub es una plataforma basada en la nube que utiliza Git, un sistema de control de versiones distribuido, en su núcleo. La plataforma GitHub simplifica el proceso de colaboración en proyectos y proporciona un sitio web, herramientas de línea de comandos y un flujo general que permite a los desarrolladores y usuarios trabajar juntos.
  
- Principales características y funciones

  - AI
    
  La IA generativa está transformando drásticamente el desarrollo de software en estos momentos.
  La plataforma GitHub Enterprise está mejorando la colaboración a través de solicitudes de extracción y problemas impulsados por IA, la productividad a través de Copilot y la seguridad al automatizar los controles de seguridad más rápidamente.

  - Colaboración
    
  La colaboración es el núcleo de todo lo que hace GitHub. Sabemos que una colaboración ineficiente resulta en una pérdida de tiempo y dinero. Contrarrestamos esto con un conjunto de herramientas integradas que permiten que la colaboración se produzca sin esfuerzo.
  Los repositorios, los problemas, las solicitudes de extracción y otras herramientas ayudan a que los desarrolladores, gerentes de proyectos, líderes de operaciones y otras personas de la misma empresa trabajen juntos más rápido, reduzcan los tiempos de aprobación y realicen envíos más rápidamente.

  - Productividad
    
  La productividad se acelera con la automatización que proporciona GitHub Enterprise Platform. Con herramientas CI/CD integradas directamente en el flujo de trabajo, la plataforma brinda a los usuarios la capacidad de establecer tareas y olvidarlas, encargándose de la administración rutinaria y acelerando el trabajo diario. Esto les da a sus desarrolladores más tiempo para concentrarse en lo más importante: crear soluciones innovadoras.

  - Seguridad
    
  GitHub se centra en integrar la seguridad directamente en el proceso de desarrollo desde el principio. La plataforma GitHub Enterprise incluye características de seguridad nativas propias que minimizan el riesgo de seguridad con una solución de seguridad integrada. Además, su código permanece privado dentro de su organización y, al mismo tiempo, puede aprovechar la descripción general de seguridad y el Dependabot.
  GitHub ha seguido invirtiendo para garantizar que nuestras funciones estén preparadas para la empresa. Contamos con el respaldo de Microsoft, la confianza de industrias altamente reguladas y cumplimos con los requisitos de cumplimiento a nivel mundial.

  - Escala
    
  GitHub es la comunidad de desarrolladores más grande de su tipo. Con datos en tiempo real sobre más de 100 millones de desarrolladores, más de 330 millones de repositorios e innumerables implementaciones, hemos podido comprender las necesidades cambiantes de los desarrolladores y realizar cambios en nuestro producto para adaptarnos.
  Esto se ha traducido en una escala increíble que no tiene comparación ni comparación con ninguna otra empresa del planeta. Cada día obtenemos más y más conocimientos de esta impresionante comunidad y evolucionamos la plataforma para satisfacer sus necesidades.
En esencia, la plataforma GitHub Enterprise se centra en la experiencia del desarrollador: tiene la escala para proporcionar conocimientos que cambian la industria, capacidades de colaboración para una eficiencia transformadora, las herramientas para una mayor productividad, seguridad en cada paso e inteligencia artificial para impulsarlo todo a nuevas alturas. una plataforma única e integrada.

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
- Colaborar en un repositorio
- Realizar pull requests
- Revisar y aprobar pull requests
- Forks y contribuciones a proyectos de código abierto
- Markdown
- README.md
- Github flow
- Discussions
- GitHub Pages
- Gists
- Wikis
- Issues

## Cuentas, planes y permisos
- Tipo de cuentas
    - Personal
    - Organization
    - Enterprise
- Tipos de planes
    - GitHub Free for personal accounts and organizations
    - GitHub Pro for personal accounts
    - GitHub Team
    - GitHub Enterprise
- Permisos
    - Read
    - Triage
    - Write
    - Maintain
    - Admin
  
## Seguridad y control en github
- Codeowners
- Branch Protection
- Rulesets
- Codeql
- Dependabot

## Introducción a GitHub Copilot
- ¿Qué es GitHub Copilot?
- Funcionalidades principales
- Integración con editores de código

## Codespaces, GitHub Mobile y GitHub Desktop
- Codespaces: desarrollo en la nube con GitHub
- GitHub Mobile: acceso a GitHub desde dispositivos móviles
- GitHub Desktop: cliente de escritorio para GitHub
    
## Gestión de proyectos en GitHub
- Crear proyectos y tableros
- Asignar tareas y gestionar el flujo de trabajo
- Uso de issues y milestones en Github projects

## Buenas prácticas y recomendaciones
- Estructura de repositorios
- Mensajes de commit descriptivos
- Uso de ramas de forma adecuada
- Mantenimiento y limpieza de repositorios
