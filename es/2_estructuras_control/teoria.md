# Unidad 2: Estructuras Básicas de Control en Java
## (2. UD: Oinarrizko Kontrol Egiturak Javan)

Este documento contiene una guía completa con los conceptos, explicaciones y ejemplos sobre **operadores**, **estructuras condicionales** y **estructuras repetitivas (bucles)** contenidos en las presentaciones de la asignatura.

---

## 1. Operadores en Java (Eragileak)

Los operadores se utilizan en las expresiones booleanas para evaluar condiciones dentro de las estructuras de control.

### 1.1 Operadores Relacionales (Eragile Erlazionalak)
Sirven para comparar dos valores. El resultado de la evaluación siempre es un valor booleano (`true` o `false`).

| Operador | Descripción (Euskara) | Descripción (Español) | Orden de Precedencia |
| :---: | :--- | :--- | :---: |
| `<` | Txikiagoa | Menor que | 5 |
| `>` | Handiagoa | Mayor que | 5 |
| `<=` | Txikiagoa edo berdina | Menor o igual que | 5 |
| `>=` | Handiagoa edo berdina | Mayor o igual que | 5 |
| `==` | Berdina | Igual a | 6 |
| `!=` | Ezberdina | Diferente de | 6 |

---

### 1.2 Operadores Lógicos (Eragile Logikoak)
Permiten combinar múltiples expresiones booleanas.

| Operador | Nombre / Descripción | Significado | Orden de Precedencia |
| :---: | :--- | :--- | :---: |
| `!` | *Not* (ez) | Negación lógica | 1 |
| `&&` | *And* (eta) | Conjunción (ambas condiciones deben ser verdaderas) | 10 |
| `\|\|` | *Or* (edo) | Disyunción (al menos una condición debe ser verdadera) | 11 |

---

## 2. Estructuras Condicionales (Baldintzazko Egiturak)

Las estructuras condicionales permiten alterar el flujo de ejecución del programa evaluando si una condición es verdadera ($true$) o falsa ($false$).

---

### 2.1 La Sentencia `if`
Se utiliza cuando se requiere ejecutar un bloque de código **únicamente si** la condición se cumple.

> **Nota:** Si la instrucción a ejecutar dentro de un bloque ocupa una sola línea, las llaves `{}` son opcionales en Java.

#### Sintaxis general:
```java
if (baldinza) {
    // Código a ejecutar si la condición es TRUE
}
```

#### Ejemplo 1 (`if` simple):
```java
int matematikak = 4;

if (matematikak >= 5) {
    System.out.println("Matematika gainditu duzu.");
}
```

---

### 2.2 La Sentencia `if ... else`
Define una alternativa de ejecución cuando la condición dada resulta ser falsa ($false$).

#### Sintaxis general:
```java
if (baldintza) {
    // Código si la condición es TRUE
} else {
    // Código si la condición es FALSE
}
```

#### Ejemplo 2 (`if ... else`):
```java
int matematikak = 4;

if (matematikak >= 5) {
    System.out.println("Matematika gainditu duzu.");
} else {
    System.out.println("Ez duzu matematika gainditu.");
}
```

---

### 2.3 La Sentencia `if ... else if ... else`
Permite encadenar múltiples condiciones para evaluar varias alternativas de forma secuencial.

#### Sintaxis general:
```java
if (baldintza1) {
    // Código si baldintza1 es TRUE
} else if (baldintza2) {
    // Código si baldintza2 es TRUE
} else {
    // Código si ninguna de las condiciones anteriores se cumple
}
```

#### Ejemplo 3 (`if ... else if ... else`):
```java
int matematikak = 4;

if (matematikak == 5) {
    System.out.println("5 bat atera duzu Matematikan.");
} else if (matematikak > 5) {
    System.out.println("5 bat baino gehiago atera duzu Matematikan.");
} else {
    System.out.println("Ez duzu Matematika gainditu.");
}
```

---

### 2.4 La Sentencia `switch`
Es una alternativa más clara y ordenada frente a múltiples `if ... else if` cuando se necesita comparar una misma variable frente a varios valores posibles.

*   **Palabras clave**:
    *   `switch`: Inicia la evaluación de la variable.
    *   `case`: Define cada uno de los valores con los que se compara la variable.
    *   `break`: Finaliza el bloque de un `case`. Evita que el programa continúe ejecutando los siguientes casos (*fall-through*).
    *   `default`: Ejecuta el código asignado cuando ningún caso anterior coincide con el valor evaluado.

#### Sintaxis general:
```java
switch (aldagaia) {
    case balioa1:
    case balioa2:
        Aginduak;
        break;
    case balioaN:
        Aginduak;
        break;
    default:
        Aginduak;
}
```

#### Ejemplo 1 (`switch` con casos independientes):
```java
int posizioa = 1;

switch (posizioa) {
    case 1:
        System.out.println("Urrezko domina");
        break;
    case 2:
        System.out.println("Zilarrezko domina");
        break;
    case 3:
        System.out.println("Brontzeko domina");
        break;
    case 4:
        System.out.println("Diploma");
        break;
    case 5:
        System.out.println("Diploma");
        break;
    default:
        System.out.println("Saririk gabe");
        break;
}
```

#### Ejemplo 2 (`switch` agrupando casos):
Es posible agrupar múltiples `case` cuando comparten la misma lógica u orden de ejecución:
```java
int posizioa = 4;

switch (posizioa) {
    case 1:
        System.out.println("Urrezko domina");
        break;
    case 2:
        System.out.println("Zilarrezko domina");
        break;
    case 3:
        System.out.println("Brontzeko domina");
        break;
    case 4:
    case 5: // Tanto el caso 4 como el 5 ejecutan este bloque
        System.out.println("Diploma");
        break;
    default:
        System.out.println("Saririk gabe");
        break;
}
```

---

## 3. Estructuras Repetitivas o Bucles (Egitura Errepikakorrak / Bukleak)

Permiten ejecutar un conjunto de instrucciones de manera repetida ($0$, $1$ o varias veces) en función del valor de una expresión booleana.

> **¡Atención! Bucles infinitos (Bukle amaigabeak)**  
> Se producen cuando la expresión booleana permanece siempre en estado verdadero ($true$). Como consecuencia, las sentencias se ejecutan continuamente sin llegar al final y el programa se queda "colgado".

---

### 3.1 Bucle `while`
Se utiliza cuando se necesita ejecutar un bloque de código un número indeterminado de veces (**$0$ o más veces**).

*   La comprobación de la condición se hace **al inicio**.
*   Si la condición se evalúa como $false$ desde el principio, las sentencias dentro del bucle no se ejecutarán ninguna vez.

#### Sintaxis:
```java
while (boolexp) {
    sentencias;
}
```

---

### 3.2 Bucle `do ... while`
Estructura similar al bucle `while`, con la diferencia de que la condición se evalúa **al final**.

*   Garantiza que el bloque de código dentro del bucle se ejecutará **al menos una vez** ($\ge 1$).

#### Sintaxis:
```java
do {
    sentencias;
} while (expresion);
```

---

### 3.3 Bucle `for`
Se utiliza cuando se conoce de antemano el número exacto de veces que se debe ejecutar un conjunto de sentencias.

Su estructura consta de tres partes fundamentales:
1. **Inicialización**: Se asigna un valor inicial a la variable de control.
2. **Expresión booleana**: Es la condición que determina si el bucle continúa ejecutándose.
3. **Incremento / Decremento**: Actualiza la variable de control al final de cada iteración.

#### Sintaxis:
```java
for (inicializacion; boolexpresion; incremento) {
    sentencias;
}
```

---

## Resumen Comparativo de los Bucles

| Bucle | Momento de Evaluación | Mínimo de Iteraciones | Caso de Uso Principal |
| :--- | :---: | :---: | :--- |
| **`while`** | Al principio | $0$ | Cuando no sabemos si será necesario ejecutar el bucle al menos una vez. |
| **`do ... while`** | Al final | $1$ | Cuando se requiere obligatoriamente una primera ejecución (ej. menú de usuario, validación de entrada). |
| **`for`** | Al principio | $0$ | Cuando el número de iteraciones es fijo o prefijado. |