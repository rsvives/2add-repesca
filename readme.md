# Acceso a datos: Recuperación 1ª Ev

## Contenidos
1. Ficheros
   1. De texto
   2. De acceso aleatorio
2. Bases de datos relacionales:
    1. Sentencias parametrizadas
    2. Transacciones


## Instrucciones

- Leer todo el contenido de este fichero detenidamente antes de empezar.
- Cada ejercicio puntúa diferente y está compuesto por una serie de apartados que van puntuando.
  Es altamente recomendable detectar qué ejercicios se pueden hacer de manera más sencilla y rápida para aprovechar el
  tiempo de la mejor manera posible.
- Todos los métodos tendrán que contemplar las excepciones necesarias.
- ⚠️ Se recuerda que, para los ejercicios de bases de datos, es necesario instalar el driver de MySQL.

## Enunciados

### Ejercicio 1: ficheros (4 puntos) 

El fichero `temperaturas.txt` en la carpeta "archivos" contiene un conjunto de temperaturas, cada una de ellas en una línea diferente.
Crear los siguientes métodos y llamarlos desde el main:

#### - leerTemperaturas(File) [2pts]:
Método que recibe el fichero `temperaturas.txt` y devuelve un ArrayList con las temperaturas que contiene en su interior. 

#### - aumentarTemperaturas(ArrayList<Integer>, numero) [2pts]:
Método que recibe un ArrayList y un número y crea un fichero llamado `nuevas_temperaturas.txt` con las temperaturas contenidas en el ArrayList, sumándoles el número recibido por parámetros.


### Ejercicio 2: bases de datos (6 puntos)
Se va a utilizar un servidor de bases de datos en local, por lo que habrá que arrancar servidor MySQL del XAMPP.
>⚠️ Es importante incluir el driver de MySQL en este proyecto para poder testear y ejecutar dicha conexión correctamente.

#### - crearConexión [1pts]
Crear un método que permita crear una conexión con una base de datos cuyos datos se facilitan a continuación.
El método ha de retornar un objeto de tipo Connection, con la conexión a la base de datos.
**No es necesario** que reciba los parámetros de la conexión como argumentos.

- Host: localhost
- Puerto: el que indica el XAMPP
- Nombre base de datos: add_repesca_1ev (crearla a mano con el Heidi / PHPMyAdmin)
- Usuario: root
- Contraseña: (vacío)

#### - crearTabla() [1,5pts]

Crear una tabla de películas con Java.
El nombre de los campos de la tabla, se obtiene leyendo el fichero de texto llamado `tabla_peliculas.txt`.

#### - insertarRegistros() [2pts]
Método que sirve para insertar 3 registros de películas.
Dichos registros, se encuentran leyendo el fichero `peliculas.txt`, en el que cada línea representa una película.
Por cada línea leida, se ha de crear un objeto de la clase Pelicula, y añadirse a un ArrayList de Peliculas.
Para insertar los registros, es necesario hacerlo iterando el ArrayList<Pelicula> creado al leer el archivo, y no leyendo directamente dicho fichero
La inserción se tiene que hacer de cada registro por separado, pero todos englobados en una transacción. 

#### - consultaPreparada() [1,5pt]
Método que muestra por pantalla aquellas películas que se hicieron a partir del año 2000. 
La consulta se tiene que realizar mediante una sentencia preparada