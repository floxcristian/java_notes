

<h1 align="center"> Cast vs Parse</h1>

# 1. Cast

+ En operaciones matemáticas para garantizar precisión de las mismas, o ahorrar memoria optimizando los tipos.
+ cuando tenemos un objeto de un tipo derivado pero almacenado en una variable base, y necesita utilizarlo como un tipo más específico.
+ Conversión de un objeto a un tipo similar.
+ No crea un nuevo objeto, modifica el original.

## Estimación:

```java
double monthlyDogs = dogsQuantity / 12.0; // 2.5 (pero no es posible, ¡no rescatamos medio perrito!)
int estimatedMonthlyDogs = (int) monthlyDogs; // 2 (trunca el valor)

// El casteo no redondea, solo quita los decimales (trunca):
Math.sqrt(3) // 1.7320508075688772
(int) Math.sqrt(3) // 1
```

## Exactitud:

Resultado exacto de una división:
```java
int a = 30;
int b = 12;

a / b // 2 (valor no exacto)
(double) a / b // 2.5 (casting)
```
Definir una variable flotante:
```java
// option 1
float num = 2.5f;
// option 2
float value = (float) 2.5;
```
# 2. Parse

+ Su uso más común es dar formato a strings.
+ Crea un nuevo objeto y no modifica el original

```java
// example 1
String value = "10";
int number = Integer.parseInt(value);
// example 2
String value = "10.23";
float number = Float.parseFloat(value);
```