<h1 align="center">Apuntes de Java</h1>

## Tabla de Contenido



# 1. ¿Qué es Java?

+ Orientado a Objetos.
+ Con características de lenguajes orientados a la programación funcional.
+ Multiplataforma.

## 1.1. Categorías de Java

+ **Java SE (Standard Edition)**
    + Base y sintaxis del lenguaje para desarrollar apps de escritorio y consola.
    + Filosofía WORA (Write once run anywhere). Lo que aprendas en Java SE puedes llevarlo a Java EE y puede correr en cualquier SO.

+ **Java EE (Enterprise Edition)**
    + Enfocado a apps web, en servidores y distribuidas.

# 2. Versiones de Java y JDK

## 2.1. JDK (Java Development Kit)

También nombrado como SDK de Java, se compone de 3 elementos:

+ **JRE (Java Runtime Environment):** VM de Java que permite interpretar el código en distintos SO (filosofía WORA).
+ **Compilador Java:** traduce Java a `Byte Code` que finalmente será interpretado por la `JVM`.
+ **API de Desarrollo:** base de elementos y clases listas para usar.

## 2.2. Versiones

+ Java SE 8 LTS (2014)
+ Java SE 11 LTS (2018)

LTS (Long Term Support / 3 years)


+ Java SE 11 (JDK 11) es la primera versión en la que se cobra licencia.
+ JDK de Oracle FREE solo en ambientes de desarrollo y testing.

+ **OpenJDK:** 
    + versión open-source de Java SE. 
    + disponible desde Java SE 6.
    + apoyada por Red Hat.

La versión 8 es la más utilizada y es la única versión LTS con licencia gratuita (soporte) por parte de Oracle. Y apartir de ahí el soporte se adquirirá con licencia como en la versión 11 LTS.

# 3. Herramientas 

## Herramientas para proyectos Web

Integración de dependencias:
+ Maven
+ Gradle

Frameworks Java EE:
+ Spring

ORMs:
+ Hibernate

## IDEs
+ Netbeans
+ Eclipse
+ IntelliJ IDEA (más usado)
+ Replit (online)

## Entorno de Desarrollo en Windows

1. Descargar e instalar [IntelliJ IDEA](https://www.jetbrains.com/es-es/idea/).

2. Descargar e instalar las versiones LTS 8 y 11 de [OpenJDK](https://adoptopenjdk.net).

3. Crear un nuevo proyecto y en `Project SDK` seleccionar la versión deseada (ubicada en el directorio `C:\Program Files\AdoptOpenJDK`).

# 4. Código

**main:** punto de entrada de nuestra app en Java. Lo primero que se ejecuta cuando nuestra app corre.

```java
public static void main (String[] args){
    // acciones
}
```

+ En external libraries podemos ver las librerías con las que estamos trabajando, incluyendo el JDK.
+ En el directorio `src` es donde creamos nuestros archivos.
Ejemplo: `New` > `Java Class`.

Si escribimos `main` el IDE sugiere toda la estructura del método main.

Atajos/hacks/accesos directos:
+ si escribimos `sout` y damos enter el IDE automáticamente pondrá el método de impresión ``System.out.println();`.
+ Para sugerencias se presiona `CTRL + SPACE` en WIndows.
+ más atajos: https://programatutos.com/tips/atajos-de-netbeans-para-java/

Para correr la app damos click derecho y seleccionamos la opción `Run HolaMundo.main()`.
+ El IDE construye todo el programa.

# Etapas de Programación en Java

+ Escribimos código `.java`.
+ Cuando ejecutamos `run` se activa el compilador de Java `javac` que traduce el código a `Byte Code`. Este `Byte Code` es almacenado en archivos `.class` en el directorio `out`.
+ La `JVM` interpreta el `Byte Code`.

> Java es compilado e interpretado.

# Variables en Java

```java
int salary;
String name, surname;
```
+ No se puede inicializar una variable con un número al principio y no pueden tener guión medio.
+ Constantes se escriben en mayúsculas y pueden contener `_`.

Ejemplo de declaración de constante:
```java
final double PI = 3.14;
```

Variables estáticas o de clase


Concatenar strings:
```java
String name = "Cristian";
name += " Flores";
```

# Nombramiento

+ **Upper Camel Case** en clases y estas deben tener el mismo nombre que los archivos.
+ **Lower Camel Case** en variables y métodos.

## Variables númericas

Las variables tienen limites.

byte -128 a 127 (1 bye)
short -32.768 a 32.767 (2 byte)
int -2.147.483.648 a 2.147.483.647 (4 bytes)
long -9.223.372.036.854.775.808 a -9.223.372.036.854.775.807 (8 bytes)

Decimales
float (4 bytes)
double (8 bytes)

+ Para especificar tipo de dato `long` se debe poner una `L` al final:
```java
long longNum = 12345678901L;
```
+ Para especificar tipo de dato `float` se debe poner una `F` al final:
```java
float doubleNum = 123.456;
float floatNum = 123.456F;
```

Declarar tipos de datos sin signo para expandir sus limites.
```java
int intNum = Integer.parseUnsignedInt("4294967295");
long longNum = Long.parseUnsignedLong("18446744073709551615");
```

Tipos de datos
char un carácter 2 bytes
+ se utiliza con comillas simples.

| boolean | true / false| 2 bytes |
Desde Java 10 no es necesario establecer el tipo de variable y se puede poner var
```java
var intNum = 23455;
```


## Cast vs Parse

**Cast:** en operaciones matemáticas para garantizar precisión de las mismas, o ahorrar memoria optimizando los tipos.
```java
// option 1
float num = 2.5f;
// option 2
float value = (float) 2.5;
```

**Parse:** para cambiar entre tipos. Su uso más común es dar formato a strings recibidos por inputs.
```java
// example 1
String value = "10";
int number = Integer.parseInt(value);
// example 2
String value = "10.23";
float number = Float.parseFloat(value);
```

# Operadores

## Operadores de Asignación

| Operador | Aplicación | Desglose  |
|----------|------------|-----------|
| +=       | a += b     | a = a + b |
| -=       | a -= b     | a = a - b |
| *=       | a *= b     | a = a * b |
| /=       | a /= b     | a = a / b |
| %=       | a %= b     | a = a % b | 

## Operadores de Incremento y Decremento

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