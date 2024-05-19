# Temario para Estudiar Bash

## 1. Introducción a Bash
- ¿Qué es Bash?

Bash, acrónimo de "Bourne Again SHell", es un intérprete de comandos y un lenguaje de scripting diseñado para sistemas operativos Unix y similares, como Linux y macOS. Es el shell por defecto en muchas distribuciones de Linux y es conocido por su facilidad de uso y poderosas capacidades de scripting, lo que lo convierte en una herramienta esencial para la administración de sistemas y la automatización de tareas.
  
- Historia y evolución de Bash
  
Bash fue desarrollado por Brian Fox para el proyecto GNU y lanzado por primera vez en 1989. Su propósito era mejorar el shell Bourne (sh) existente con nuevas características y funcionalidades adicionales. 


## 2. Conceptos Básicos
- Sintaxis de Bash

La sintaxis de Bash se basa en líneas de comandos que el usuario ingresa en una terminal. Cada línea generalmente consiste en un comando seguido de opciones y argumentos. Aquí hay algunos elementos clave de la sintaxis de Bash:

Comandos: Son programas o scripts que se ejecutan en la terminal.
Opciones: Modifican el comportamiento de los comandos, usualmente precedidas por un guion (-).
Argumentos: Son datos adicionales que los comandos pueden necesitar.

- Comandos esenciales (ls, cd, pwd, cp, mv, rm, mkdir, rmdir)

Listar archivos en un directorio:

```bash
ls
ls -l
ls -a
```
cd: Cambia el directorio actual.

```bash
cd /ruta/del/directorio
cd ..
```

pwd: Muestra la ruta del directorio actual.

```bash
pwd
```
cp: Copia archivos o directorios.

```bash
cp archivo_origen archivo_destino
cp -r directorio_origen directorio_destino
```
mv: Mueve o renombra archivos o directorios.

```bash
mv archivo_origen archivo_destino
mv archivo_antiguo archivo_nuevo
```
rm: Borra archivos o directorios.

```bash
rm archivo
rm -r directorio
```
mkdir: Crea un nuevo directorio.

```bash
mkdir nuevo_directorio
```

rmdir: Borra un directorio vacío.

```bash
rmdir nombre_del_directorio
```

## 3. Variables y Tipos de Datos

- Declaración de variables

En Bash, declarar una variable es simple y no requiere el uso de palabras clave especiales como en otros lenguajes de programación. Simplemente se asigna un valor a un nombre de variable.

```bash
mi_variable="Hola, Mundo!"
numero=42
```
Para acceder al valor de una variable, se usa el signo $ seguido del nombre de la variable.

```bash
echo $mi_variable  # Imprime: Hola, Mundo!
echo $numero       # Imprime: 42
```

- Tipos de datos (números, cadenas, arrays)

Bash no tiene tipos de datos formales como otros lenguajes de programación. Sin embargo, se pueden manejar diferentes tipos de datos como números, cadenas y arrays.

Números:

```bash
# Variables numéricas
numero=10
otro_numero=20

# Operaciones aritméticas se realizan con `expr` o doble paréntesis
resultado=$(expr $numero + $otro_numero)
echo $resultado  # Imprime: 30

# Con doble paréntesis
resultado=$((numero + otro_numero))
echo $resultado  # Imprime: 30
```

Cadenas:

```bash
# Variables de cadena
saludo="Hola"
nombre="Mundo"

# Concatenación de cadenas
mensaje="$saludo, $nombre!"
echo $mensaje  # Imprime: Hola, Mundo!
```

Arrays:

```bash
# Declaración de un array
mi_array=("valor1" "valor2" "valor3")

# Acceder a elementos del array
echo ${mi_array[0]}  # Imprime: valor1

# Agregar un elemento al array
mi_array+=("valor4")

# Obtener todos los elementos del array
echo ${mi_array[@]}  # Imprime: valor1 valor2 valor3 valor4
```

- Variables predefinidas y especiales

Bash tiene varias variables predefinidas y especiales que son útiles en scripts:

```bash
$HOME # El directorio de inicio del usuario actual.
$PWD # El directorio de trabajo actual.
$PATH # Las rutas de búsqueda para comandos.
$USER # El nombre del usuario actual.
$? # El estado de salida del último comando ejecutado.
$# # El número de argumentos pasados al script.
$@ # Todos los argumentos pasados al script como una lista.
$0 # El nombre del script.
$1, $2, ... # Los argumentos posicionales pasados al script.
```

- Scope de las variables (local, global)
  
En Bash, las variables pueden tener un ámbito local o global. Por defecto, las variables son globales, pero se pueden declarar como locales dentro de funciones.

Variables Globales:

Las variables globales están disponibles en todo el script y en cualquier función dentro del script.

```bash
mi_variable_global="Soy global"

function mi_funcion {
    echo $mi_variable_global  # Imprime: Soy global
}

mi_funcion
```
Variables Locales:

Las variables locales solo están disponibles dentro de la función donde se declaran.

```bash
function mi_funcion {
    local mi_variable_local="Soy local"
    echo $mi_variable_local  # Imprime: Soy local
}

mi_funcion

# Intentar acceder a una variable local fuera de su función dará un error
echo $mi_variable_local  # No imprime nada
```

## 4. Operaciones y Expresiones

- Operadores aritméticos

En Bash, puedes utilizar varios operadores aritméticos para realizar operaciones matemáticas en variables numéricas. Algunos de los operadores más comunes son:

+: Suma
-: Resta
*: Multiplicación
/: División
%: Módulo (resto de la división)

```bash
a=10
b=3
suma=$((a + b))        # suma = 13
resta=$((a - b))       # resta = 7
multiplicacion=$((a * b))  # multiplicacion = 30
division=$((a / b))     # division = 3
modulo=$((a % b))       # modulo = 1
```
  
- Operadores de comparación

Los operadores de comparación en Bash se utilizan para comparar valores y devolver un resultado verdadero o falso. Algunos operadores comunes son:

-eq: Igual a
-ne: No igual a
-gt: Mayor que
-lt: Menor que
-ge: Mayor o igual que
-le: Menor o igual que

```bash
a=10
b=20

if [ $a -eq $b ]; then
    echo "a es igual a b"
fi

if [ $a -lt $b ]; then
    echo "a es menor que b"
fi
```

- Operadores lógicos

Los operadores lógicos en Bash se utilizan para combinar expresiones lógicas y devolver un resultado verdadero o falso. Algunos operadores comunes son:

&&: Y lógico (AND)
||: O lógico (OR)
!: Negación lógica (NOT)

```bash
a=10
b=20

if [ $a -lt 100 ] && [ $b -gt 10 ]; then
    echo "Ambas condiciones son verdaderas"
fi

if [ $a -lt 5 ] || [ $b -gt 100 ]; then
    echo "Al menos una de las condiciones es verdadera"
fi

if ! [ $a -eq 0 ]; then
    echo "a no es igual a 0"
fi
```

- Expresiones regulares

En Bash, puedes utilizar expresiones regulares en combinación con herramientas como grep o sed para buscar y manipular texto de forma avanzada. Por ejemplo, para buscar líneas que contengan la palabra "hello" en un archivo:

```bash
grep "hello" archivo.txt
```
O para sustituir todas las ocurrencias de "foo" por "bar" en un archivo:

```bash
sed -i 's/foo/bar/g' archivo.txt
```

## 5. Estructuras de Control
- Condicionales (if, else, elif)
- Bucles (for, while, until)
- Case statements
- Uso de break y continue

## 6. Funciones
- Definición y uso de funciones
- Parámetros y argumentos
- Funciones recursivas
- Scope de variables en funciones

## 7. Entrada y Salida
- Redirección de entrada/salida
- Pipes (|) y uso avanzado
- Entrada y salida estándar
- Uso de /dev/null

## 8. Manejo de Archivos y Directorios
- Manipulación de archivos (lectura, escritura, borrado)
- Permisos de archivos y directorios
- Compresión y descompresión de archivos
- Búsqueda de archivos (find, grep, locate)

## 9. Scripting Avanzado
- Creación y ejecución de scripts
- Parámetros y opciones de línea de comandos
- Uso de shebang (#!)
- Debugging de scripts (set -x, set -e)

## 10. Manejo de Procesos
- Gestión de procesos (ps, top, kill)
- Creación de procesos en background
- Jobs y control de trabajos
- Señales y manejo de señales

## 11. Trabajando con Texto
- Manipulación de texto (cut, sort, uniq, tr, sed, awk)
- Expresiones regulares avanzadas
- Procesamiento de archivos CSV y JSON
- Herramientas para procesamiento de texto (grep, sed, awk)

## 12. Programación de Bash Segura
- Manejo de errores y excepciones
- Validación de entrada de usuario
- Principios de scripting seguro
- Prácticas recomendadas

## 13. Automatización y Tareas Programadas
- Crontab y tareas programadas
- Scripts de inicio del sistema
- Automatización de tareas comunes
- Ejecución de scripts en intervalos regulares

## 14. Integración y Uso de Herramientas Externas
- Uso de herramientas como curl, wget
- Interacción con APIs
- Automatización de despliegues (Git, Docker, Terraform)
- Interacción con sistemas de control de versiones

## 15. Buenas Prácticas y Optimización
- Documentación de scripts
- Estructuración y modularidad del código
- Mejora del rendimiento de scripts
- Uso de herramientas de análisis y linting (shellcheck)

## 16. Ejemplos y Proyectos Prácticos
- Proyectos de ejemplo para practicar
- Scripts útiles para la administración del sistema
- Desafíos y ejercicios prácticos

## Recursos Adicionales
- Libros recomendados
- Cursos en línea y tutoriales
- Comunidades y foros de soporte
