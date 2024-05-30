# Introducción a GitHub Actions

- Conceptos Básicos
  - ¿Qué es GitHub Actions?
 
GitHub Actions es una plataforma de automatización de CI/CD (Integración Continua y Entrega Continua) que permite definir y ejecutar flujos de trabajo automatizados directamente desde un repositorio de GitHub. 

  - Ventajas de usar GitHub Actions.

    1. Integración Nativa con GitHub
    
    2. Flexibilidad y Personalización
    
    3. Marketplace de Actions
    
    4. Automatización Completa
    
    5. Escalabilidad y Paralelismo
    
    6. Uso de Runners Propios y Alojados
    
    7. Gestión de Secretos y Variables de Entorno
    
    8. Monitoreo y Reportes
      
  - Casos de uso.

    1. Integración Continua (CI)
    
    2. Entrega Continua (CD)
    
    3. Publicación de Paquetes
    
    4. Automatización de Tareas de Mantenimiento
    
    5. Notificaciones y Alertas
  
    6. Integración con Herramientas de Terceros
       
    7. Deployments Multi-Cloud
    
    8. Pruebas de Seguridad y Análisis de Vulnerabilidades
    
    9. Automatización de Infraestructura como Código (IaC)

- Componentes de GitHub Actions
  - Workflows en GitHub Actions son definiciones de procesos automatizados que se ejecutan en respuesta a eventos específicos en un repositorio de GitHub. Cada workflow se define en un archivo YAML dentro del directorio .github/workflows/ de tu repositorio.

  - Jobs: Un workflow puede contener uno o más jobs que se ejecutan en paralelo o en secuencia.
  
  - Steps son las unidades más pequeñas de un job y representan tareas individuales que se ejecutan secuencialmente dentro de un job. Los steps pueden ejecutar comandos de shell, utilizar acciones predefinidas o definir scripts personalizados.
    
  - Actions son unidades reutilizables de código que pueden realizar tareas específicas dentro de un workflow. Pueden ser desarrolladas por la comunidad o por los propios usuarios y se pueden encontrar en el GitHub Marketplace.
    
  - Runners son máquinas que ejecutan los jobs de los workflows. GitHub ofrece runners alojados en GitHub (GitHub-hosted runners) y la opción de configurar runners auto-hospedados (self-hosted runners).

    - GitHub-hosted Runners: Proporcionados y mantenidos por GitHub, disponibles en múltiples plataformas como ubuntu-latest, windows-latest, macos-latest.
      
    - Self-hosted Runners: Configurados y mantenidos por el usuario, permitiendo mayor control sobre el entorno de ejecución.

## Configuración de Workflows

- Estructura de un Workflow
  - Archivo de configuración (.github/workflows/<nombre>.yml).

```bash

  name: CI Workflow
  
  on: [push, pull_request]
  
  jobs:
    build:
      runs-on: ubuntu-latest
      steps:
        - name: Checkout code
          uses: actions/checkout@v2
  
        - name: Set up Node.js
          uses: actions/setup-node@v2
          with:
            node-version: '14'
  
        - name: Install dependencies
          run: npm install
  
        - name: Run tests
          run: npm test
```

  - Sintaxis YAML básica.
  - Eventos que desencadenan Workflows (on).

- Definición de Jobs
  - Nombre y configuración básica de un Job.
  - Dependencias entre Jobs (needs).
  - Estrategias de matriz (matrix).

- Definición de Steps
  - Uso de comandos run.
  - Uso de Actions predefinidas.
  - Uso de scripts inline y archivos de scripts.
  - Contextos y Expresiones

- Contextos (github, env, jobs, etc.).
  - Expresiones y sintaxis.
  - Variables de entorno y secretos.

 ## Creación y Uso de Actions

- Tipos de Actions
  - JavaScript Actions.
  - Docker Container Actions.
  - Composites Actions.
    
- Creación de una Action
  - Repositorio de Actions.
  - Archivos necesarios (action.yml, Dockerfile, etc.).
  - Publicación de una Action en GitHub Marketplace.

## Integración y Automatización

- Integración Continua (CI)
  - Configuración básica para pruebas automáticas.
  - Uso de servicios de terceros (SonarQube, Coveralls, etc.).

- Entrega Continua (CD)
  - Deployment a diferentes entornos (AWS, Azure, GCP, etc.).
  - Uso de herramientas como Terraform y Kubernetes.

- Notificaciones y Reportes
  - Envío de notificaciones (Slack, email, etc.).
  - Generación de reportes de builds y deployments.

## Buenas Prácticas y Seguridad

- Gestión de Secretos
  - Añadir y usar secretos en Workflows.
  - Rotación de secretos y mejores prácticas de seguridad.

- Optimización de Workflows
  - Reutilización de código.
  - Minimización de tiempos de ejecución.

- Monitoreo y Debugging
  - Visualización de logs.
  - Debugging de errores comunes.
  - Uso de herramientas de monitoreo.

## Ejemplos Prácticos

- Proyecto de Ejemplo 1: CI para un Proyecto de Node.js
  - Setup básico.
  - Ejecución de pruebas unitarias.
  - Generación de reportes de cobertura de código.
    
- Proyecto de Ejemplo 2: CD para una Aplicación Web
  - Build y despliegue a AWS S3.
  - Invalidación de caché de CloudFront.
  - Notificaciones post-despliegue.
    
- Proyecto de Ejemplo 3: Workflows Avanzados
  - Uso de matrices y estrategias de despliegue.
  - Integración con Terraform para infraestructura como código.
  - Deploy a un clúster de Kubernetes.
