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

```yml

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
  - Eventos que desencadenan Workflows (on).
```yml

name: Event types
on:
  push:
    branches:
      - main
      - 'release/*'
  pull_request:
    branches:
      - main
  schedule:
    - cron: '0 0 * * 0'  # Cada domingo a medianoche
  workflow_dispatch:
  release:
    types: [published]
```

  - Schedule: La palabra clave schedule en GitHub Actions se utiliza para definir workflows que se ejecutan automáticamente en momentos específicos, utilizando una expresión cron para programar las ejecuciones. Esto es útil para tareas que necesitan ejecutarse periódicamente sin intervención manual, como mantenimiento, actualizaciones, análisis o pruebas regulares.

```plaintext
 ┌───────────── minuto (0 - 59)
 │ ┌───────────── hora (0 - 23)
 │ │ ┌───────────── día del mes (1 - 31)
 │ │ │ ┌───────────── mes (1 - 12)
 │ │ │ │ ┌───────────── día de la semana (0 - 7) (domingo=0 o 7)
 │ │ │ │ │
 │ │ │ │ │
 0 0 * * 0
```

- Definición de Jobs
  - Nombre y configuración básica de un Job.
    - Cada job tiene un nombre y una configuración básica que incluye el tipo de runner a utilizar ```runs-on:```, los pasos a seguir ```steps:```, y otras configuraciones opcionales.
  - Dependencias entre Jobs (needs).
    - Puedes definir dependencias entre jobs utilizando la palabra clave needs. Esto permite ejecutar jobs en secuencia, donde un job espera a que otro job termine antes de comenzar.
      
```yml
      name: CI Workflow

      on: [push]
      
      jobs:
        build:
          runs-on: ubuntu-latest
          steps:
            - name: Checkout code
              uses: actions/checkout@v2
      
            - name: Build project
              run: npm build
      
        test:
          runs-on: ubuntu-latest
          needs: build  # Depende del job "build"
          steps:
            - name: Checkout code
              uses: actions/checkout@v2
      
            - name: Run tests
              run: npm test
      
        deploy:
          runs-on: ubuntu-latest
          needs: test  # Depende del job "test"
          steps:
            - name: Checkout code
              uses: actions/checkout@v2
      
            - name: Deploy to production
              run: ./deploy.sh
```

  - Estrategias de matriz (matrix).
    - Las estrategias de matriz (matrix) permiten ejecutar múltiples variaciones de un job con diferentes configuraciones. Esto es útil para probar el código en diferentes entornos, versiones de lenguajes, sistemas operativos, etc.

```yml
name: CI Workflow

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [12, 14, 16]
        os: [ubuntu-latest, windows-latest, macos-latest]
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: ${{ matrix.node-version }}

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test
```

- Definición de Steps
  - Uso de comandos run: En GitHub Actions, el comando run se utiliza para ejecutar comandos de shell directamente en los pasos (steps) de un workflow. Puedes utilizar cualquier comando que normalmente ejecutarías en la línea de comandos del sistema operativo especificado por el runner.

```yml
      - name: Run a script
        run: |
          echo "Running a multi-line script"
          echo "Hello, world!"
```

  - Uso de Actions predefinidas: GitHub Actions proporciona muchas acciones predefinidas que puedes utilizar para realizar tareas comunes. Estas acciones están disponibles en el Marketplace de GitHub Actions.

```yml
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
```
    
  - Uso de scripts inline y archivos de scripts: Puedes incluir scripts directamente en el archivo YAML (scripts inline) o ejecutar scripts almacenados en archivos del repositorio.

```yml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Run build script
        run: ./scripts/build.sh
```
    
  - - Contextos (github, env, jobs, etc.): GitHub Actions proporciona contextos y expresiones para acceder a información y datos dentro de los workflows. Los contextos contienen datos sobre el workflow, los eventos que lo desencadenaron, los jobs, los pasos y más.

```yml
name: Context testing
on: workflow_dispatch

jobs:
  dump_contexts_to_log:
    runs-on: ubuntu-latest
    steps:
      - name: Dump GitHub context
        env:
          GITHUB_CONTEXT: ${{ toJson(github) }}
        run: echo "$GITHUB_CONTEXT"
      - name: Dump job context
        env:
          JOB_CONTEXT: ${{ toJson(jobs) }}
        run: echo "$JOB_CONTEXT"
      - name: Dump steps context
        env:
          STEPS_CONTEXT: ${{ toJson(steps) }}
        run: echo "$STEPS_CONTEXT"
      - name: Dump runner context
        env:
          RUNNER_CONTEXT: ${{ toJson(runner) }}
        run: echo "$RUNNER_CONTEXT"
      - name: Dump strategy context
        env:
          STRATEGY_CONTEXT: ${{ toJson(strategy) }}
        run: echo "$STRATEGY_CONTEXT"
      - name: Dump matrix context
        env:
          MATRIX_CONTEXT: ${{ toJson(matrix) }}
        run: echo "$MATRIX_CONTEXT"

      - name: mis agregados
        env:
          CONTEXT: ${{ toJson(toJson(github.sha)) }}
        run: echo "$CONTEXT"
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Print GitHub context
        run: echo "Repository: ${{ github.repository }}"

      - name: Print event name
        run: echo "Event: ${{ github.event_name }}"
```

  - Expresiones y sintaxis.
```plaintext
    Sintaxis de expresiones
    Las expresiones se utilizan para acceder a datos y realizar operaciones lógicas, aritméticas y de comparación. A continuación se presenta la sintaxis básica de las expresiones y algunos ejemplos de su uso.
    
    Operadores de expresiones
    Acceso a propiedades: context.property
    Operadores lógicos: && (AND), || (OR), ! (NOT)
    Operadores de comparación: ==, !=, <, >, <=, >=
    Operadores aritméticos: +, -, *, /, %
    Operadores de funciones: contains(), startsWith(), endsWith(), format()
```

    - Variables de entorno y secretos.
      - Variables de entorno: Se utilizan para almacenar y reutilizar valores configurables en varios niveles (workflow, job, step). Se definen usando la clave env.
```yml
name: Variable Example

on: [push]

env:
  WORKFLOW_VAR: "This is a workflow-level variable"

jobs:
  build:
    runs-on: ubuntu-latest
    env:
      JOB_VAR: "This is a job-level variable"
    steps:
      - name: Print workflow-level variable
        run: echo "Workflow variable: ${{ env.WORKFLOW_VAR }}"

      - name: Print job-level variable
        run: echo "Job variable: ${{ env.JOB_VAR }}"

      - name: Set step-level variable
        id: set_step_var
        run: echo "name=This is a step-level variable" >> GITHUB_ENV

      - name: Print step-level variable
        run: echo "Step variable: ${{ steps.set_step_var.outputs.STEP_VAR }}"
```
      
      - Secretos: Se utilizan para almacenar valores sensibles y se inyectan en los workflows de manera segura. Se definen en la configuración del repositorio y se accede a ellos usando secrets.SECRET_NAME.
```yml
name: Secret Example

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Use a secret
        env:
          STEP_SECRET: ${{ secrets.MY_SECRET }}
        run: echo "Secret: ${{ env.STEP_SECRET }}"
```

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
