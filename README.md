<h1 align="center">Apuntes de Java</h1>

## Tabla de Contenido

- [Introducción](#introduction)

# 1. ¿Qué es Java?

+ Orientado a Objetos.
+ Con características de lenguajes orientados a la programación funcional.
+ Multiplataforma.

## 1.1. Categorías de Java

+ **Java SE (Standard Edition)**
    + Base y sintaxis del lenguaje para desarrollar apps de escritorio y consola.
    + Filosofía WORA (Write once run anywhere). Lo que aprendas en Java SE puedes llevarlo a Java EE y puede correr en cualquier SO.

+ **Java EE (Enterprise Edition)**
    + Enfocado a apps web en servidores y distribuidas.

# 2. Versiones de Java y JDK

## 2.1. JDK (Java Development Kit)

También conocido como SDK de Java, se compone de 3 elementos:

+ **JRE (Java Runtime Environment):** VM de Java que permite interpretar el código en distintos SO (filosofía WORA).
+ **Compilador Java:** traduce `Java` a `Byte Code` que finalmente será interpretado por la `JVM`.
+ **API de Desarrollo:** base de elementos y clases listas para usar.

## 2.2. Versiones

+ Existen dos versiones LTS:
    + Java SE 8 LTS (2014).
    + Java SE 11 LTS (2018).
+ LTS (Long Term Support) en Java consiste en soporte de hasta 3 años aproximadamente.
+ Java SE 11 (JDK 11) es la primera versión en la que se cobra licencia. El JDK 11 de Oracle es gratuito solo en ambientes de desarrollo y testing.
+ Desde la versión 6 existe un JDK open-souce ([OpenJDK](#)) mantenido por la comunidad.
+ La versión 8 es la más utilizada y es la única versión LTS con licencia gratuita (soporte) por parte de Oracle. Este soporte gratuito es hasta fines de 2020 y a apartir de ahí el soporte se adquirirá con licencia pagada como en la versión 11 LTS.

# 3. Herramientas 

## 3.1. Herramientas para proyectos Web

Integración de dependencias:
+ Maven
+ Gradle

Frameworks Java EE:
+ Spring

ORMs:
+ Hibernate

## 3.2. IDEs

+ Netbeans
+ Eclipse
+ IntelliJ IDEA (más usado)
+ Replit (online)

## 3.3. Entorno de Desarrollo en Windows

1. Descargar e instalar [IntelliJ IDEA](https://www.jetbrains.com/es-es/idea/).
2. Descargar e instalar las versiones LTS 8 y 11 de [OpenJDK](https://adoptopenjdk.net).
3. Crear un nuevo proyecto y en la opción `Project SDK` seleccionar la versión deseada (ubicada en el directorio `C:\Program Files\AdoptOpenJDK`).


# 4. Programación

## 4.1. Iniciando con Java

+ El método `main` es el punto de entrada de nuestra app. Es lo primero que se ejecuta cuando nuestra app corre.

```java
public static void main (String[] args){
    // acciones
}
```
+ En `external libraries` podemos ver las librerías con las que estamos trabajando, incluyendo el JDK.
+ En el directorio `src` es donde creamos nuestros archivos.
    + Crear una clase: `New` > `Java Class`.
    + Ejecutar la app: dar click derecho y seleccionar la opción `Run MyClass.main()`.

## 4.3. Etapas de Programación en Java

+ Escribimos código `.java`.
+ Cuando ejecutamos `run` se activa el compilador de Java `javac` que traduce el código a `Byte Code`. Este `Byte Code` es almacenado en archivos `.class` en el directorio `out`.
+ Finalmente la `JVM` interpreta el `Byte Code`.

> Java es compilado e interpretado.

# 5. Variables en Java

+ Declaración de variables:
```java
int salary;
String name, surname = "Flores";
```
+ No se puede inicializar una variable con un número al comienzo y no pueden tener guión medio `-`.
+ Constantes se escriben en mayúsculas y pueden contener `_`.
+ Declaración de una constante:
```java
final double MAX_WIDTH = 45.15;
```
+ Concatenar strings:
```java
String name = "Cristian";
name += " Flores";
```

## 5.1. Nombramiento

+ **Upper Camel Case:** en clases y deben tener el mismo nombre que los archivos.
+ **Lower Camel Case:** en variables y métodos.


## 5.2. Variables númericas

| Tipo   |  Rango                                                  | Tamaño  | 
|--------|---------------------------------------------------------|---------|
| byte   | -128 a 127                                              | 1 byte  |
| short  | -32.768 a 32.767                                        | 2 byte  |
| int    | -2.147.483.648 a 2.147.483.647                          | 4 bytes |
| long   | -9.223.372.036.854.775.808 a -9.223.372.036.854.775.807 | 8 bytes |
| float  |  decimal                                                | 4 bytes |
| double |  decimal                                                | 8 bytes |

+ Para especificar tipo de dato `long` se debe poner una `L` al final:
```java
long longNum = 12345678901L;
```
+ Para especificar tipo de dato `float` se debe poner una `F` al final:
```java
double doubleNum = 123.456;
float floatNum = 123.456F;
```
## 5.3. Otros tipos de variables

| Tipo    | Uso          | Tamaño  |
|---------|--------------|---------|
| char    | 'a'          | 2 bytes |
| boolean | true / false | 2 bytes |

+ Desde Java 10 se puede usar `var` para que este infiera el tipo de variable sin ser especificada.
```java
var intNum = 23455;
```

## 5.4. Declarar tipos de datos sin signo

Esto permite expandir el rango de los valores positivos.
```java
int intNum = Integer.parseUnsignedInt("4294967295");
long longNum = Long.parseUnsignedLong("18446744073709551615");
```

## 5.5. Cast vs Parse

+ **Cast:** en operaciones matemáticas para garantizar precisión de las mismas, o ahorrar memoria optimizando los tipos.
```java
// option 1
float num = 2.5f;
// option 2
float value = (float) 2.5;
```

+ **Parse:** para cambiar entre tipos. Su uso más común es dar formato a strings recibidos por inputs.
```java
// example 1
String value = "10";
int number = Integer.parseInt(value);
// example 2
String value = "10.23";
float number = Float.parseFloat(value);
```

## 5.6. Operadores

+ Operadores de Asignación:

| Operador | Aplicación | Desglose  |
|----------|------------|-----------|
| +=       | a += b     | a = a + b |
| -=       | a -= b     | a = a - b |
| *=       | a *= b     | a = a * b |
| /=       | a /= b     | a = a / b |
| %=       | a %= b     | a = a % b | 

+ Operadores de Incremento y Decremento:

| Operador | Ejemplo | Desglose  |
|----------|---------|-----------|
| ++       | i++     | i = i + 1 |
| --       | i--     | i = i - 1 |

Prefijo: 
```java
++i
```
Postfijo: 
```java
i++
```