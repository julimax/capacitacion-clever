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

En Bash, puedes utilizar la estructura if, else y elif para realizar operaciones condicionales basadas en el valor de las variables u otras condiciones.

```bash
edad=18

if [ $edad -eq 18 ]; then
    echo "Eres mayor de edad"
elif [ $edad -lt 18 ]; then
    echo "Eres menor de edad"
else
    echo "Eres mayor de edad"
fi
```

- Bucles (for, while, until)

En Bash, puedes utilizar diferentes tipos de bucles para repetir acciones basadas en una condición.

Bucle for:

```bash
for i in {1..5}; do
    echo "Número: $i"
done
```

Bucle while:

```bash
contador=0

while [ $contador -lt 5 ]; do
    echo "Contador: $contador"
    ((contador++))
done
```

Bucle until:

```bash
contador=0

until [ $contador -eq 5 ]; do
    echo "Contador: $contador"
    ((contador++))
done
```

- Case statements

Los statements case en Bash permiten realizar múltiples comparaciones en una estructura más compacta que múltiples if-elif-else.

```bash
fruta="manzana"

case $fruta in
    manzana)
        echo "Es una manzana"
        ;;
    naranja)
        echo "Es una naranja"
        ;;
    *)
        echo "No reconocido"
        ;;
esac
```

- Uso de break y continue

break: Se utiliza para salir de un bucle.
continue: Se utiliza para saltar a la siguiente iteración de un bucle.

Ejemplo con break:

```bash
for i in {1..5}; do
    if [ $i -eq 3 ]; then
        break
    fi
    echo "Número: $i"
done
```

Ejemplo con continue:

```bash
for i in {1..5}; do
    if [ $i -eq 3 ]; then
        continue
    fi
    echo "Número: $i"
done
```

## 6. Funciones

- Definición y uso de funciones

En Bash, puedes definir funciones para encapsular y reutilizar bloques de código.
Puedes pasar parámetros a una función en Bash. Dentro de la función, puedes acceder a estos parámetros utilizando $1, $2, etc., para el primer, segundo, etc
La sintaxis para definir una función es la siguiente:

```bash
function saludar {
    echo "Hola, $1"
}

saludar "Juan"
```

- Funciones recursivas

Bash admite funciones recursivas, donde una función se llama a sí misma dentro de su propio cuerpo. Por ejemplo, aquí hay una función factorial recursiva:

```bash
function factorial {
    if [ $1 -eq 0 ]; then
        echo 1
    else
        echo $(( $1 * $(factorial $(( $1 - 1 ))) ))
    fi
}

resultado=$(factorial 5)
echo "El factorial de 5 es $resultado"
```


## 7. Entrada y Salida

- Redirección de entrada/salida

En Bash, puedes redirigir la entrada y salida estándar de los comandos utilizando los operadores <, >, >>, entre otros.

<: Redirige la entrada estándar desde un archivo hacia un comando.
>: Redirige la salida estándar de un comando hacia un archivo (crea o sobrescribe el archivo).
>>: Redirige la salida estándar de un comando hacia un archivo (agrega al final del archivo).

```bash
# Redirigir la salida del comando ls hacia un archivo llamado archivos.txt
ls > archivos.txt

# Redirigir la entrada del comando sort desde un archivo llamado input.txt
sort < input.txt

# Redirigir la salida del comando echo hacia un archivo existente (agregando al final)
echo "Hola" >> archivo.txt
```
  
- Pipes (|) y uso avanzado

Los pipes (|) permiten enviar la salida de un comando como entrada a otro comando, lo que permite combinar varios comandos para realizar tareas más complejas.

```bash
# Mostrar los procesos del sistema ordenados por uso de CPU
ps aux --sort=-%cpu | head
```

- Entrada y salida estándar

Entrada Estándar (stdin): Se refiere a la entrada de datos de un comando. Por defecto, la entrada estándar es el teclado, pero puede ser redirigida desde un archivo o desde la salida de otro comando.
Salida Estándar (stdout): Se refiere a la salida de datos de un comando. Por defecto, la salida estándar es la pantalla, pero puede ser redirigida hacia un archivo o hacia la entrada de otro comando.

- Uso de /dev/null

/dev/null es un dispositivo especial en sistemas Unix-like que se puede usar como un agujero negro para desechar datos. Puedes redirigir la salida a /dev/null para eliminarla.

```bash
# Ejecutar un comando y desechar la salida
comando > /dev/null
```

## 8. Manejo de Archivos y Directorios

- Permisos de archivos y directorios

En Bash, puedes cambiar los permisos de archivos y directorios utilizando el comando chmod. Por ejemplo, para dar permisos de lectura, escritura y ejecución a un archivo para el propietario, y solo permisos de lectura para los demás, puedes hacer:

```bash
chmod 744 archivo.txt
```

chmod es un comando en sistemas operativos Unix y Unix-like (como Linux) que se utiliza para cambiar los permisos de acceso a archivos y directorios. La palabra "chmod" significa "change mode" (cambiar modo).


- Compresión y descompresión de archivos

Para comprimir y descomprimir archivos en Bash, puedes utilizar herramientas como gzip, bzip2, zip, tar, entre otros.

Compresión con gzip:

```bash
gzip archivo.txt
```

Descompresión con gzip:

```bash
gzip -d archivo.txt.gz
```

Compresión con tar:

```bash
tar -czf archivo.tar.gz archivo1 archivo2
```
Descompresión con tar:

```bash
tar -xzf archivo.tar.gz
```
  
- Búsqueda de archivos (find, grep, locate)

find: Permite buscar archivos en función de diferentes criterios como nombre, tipo, tamaño, etc. Por ejemplo, para buscar archivos con extensión .txt en el directorio actual y sus subdirectorios:

```bash
find . -type f -name "*.txt"
```

## 9. Scripting Avanzado

- Creación y ejecución de scripts

Para crear un script en Bash, simplemente crea un archivo de texto con la extensión .sh y escribe tus comandos en él. Por ejemplo, crea un archivo llamado mi_script.sh con el siguiente contenido:

```bash
#!/bin/bash

echo "Hola, mundo!"
```
- Uso de shebang (#!)

El #!/bin/bash, también conocido como shebang o hashbang, se utiliza al principio de un script de shell (como Bash) para indicar al sistema operativo qué intérprete debe utilizar para ejecutar el script.

- Debugging de scripts (set -x, set -e)

set -x: Activa el modo verbose, mostrando cada comando antes de ejecutarlo. Útil para ver qué comandos se están ejecutando y en qué orden.

set -e: Hace que el script se detenga si un comando devuelve un código de error distinto de cero. Esto evita que el script continúe ejecutándose si un comando falla.

## 10. Manejo de Procesos

- Gestión de procesos (ps, top, kill)

ps: Muestra información sobre los procesos en ejecución. Puedes usar diferentes opciones para personalizar la salida, como ps aux para mostrar todos los procesos del sistema.

```bash
ps aux
```

top: Muestra una lista dinámica de los procesos en ejecución y su uso de recursos. Es útil para monitorear el rendimiento del sistema en tiempo real.

```bash
top
```

kill: Se utiliza para enviar señales a procesos. Por ejemplo, para detener un proceso, puedes usar kill -9 PID, donde PID es el identificador del proceso que deseas detener.

```bash
kill -9 12345
```

- Creación de procesos en background

Para ejecutar un proceso en segundo plano, puedes agregar un & al final del comando. Por ejemplo, para ejecutar un script en segundo plano:

```bash
./mi_script.sh &
```
