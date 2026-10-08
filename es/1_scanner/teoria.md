# Teoría - Tema 1: Programación Básica en Java

Este documento contiene la explicación teórica completa del **Tema 1: Oinarrizko Programazioa (Programación Básica)** para el ciclo de Desarrollo de Aplicaciones Web.

---

## 1. Introducción a la Programación y Java

* **Lenguaje de programación:** Se utiliza el lenguaje **Java** para el desarrollo de programas .
* **Entorno de Desarrollo (IDE):** Se utiliza **Eclipse** para escribir, compilar y ejecutar el código .
* **Archivos `.java`:**
  * Los archivos con código fuente de Java deben llevar siempre la extensión `.java` .
  * El nombre del archivo debe coincidir exactamente con el nombre de la **clase pública** definida en su interior .
* **Buenas prácticas:** Es fundamental incluir comentarios en el código para documentar la funcionalidad de las clases, métodos y bloques de código .

---

## 2. Estructura Genérica de un Programa en Java

Todo programa en Java se estructura dentro de clases y paquetes . La estructura básica es la siguiente:

```java
package paketea; // Declaración del paquete

import librerias; // Importación de librerías necesarias

public class ProgramaAdibidea {
    
    // Declaración de variables de clase/instancia
    int ald1;
    float ald2;
    String ald3;

    // Declaración de constructor / métodos
    public ProgramaAdibidea() {
        // ...
    }

    // Método main: punto de entrada al programa
    public static void main(String[] args) {
        // Sentencias a ejecutar
    }
}
``` 

---

## 3. Comentarios en el Código (`Iruzkinak`)

Los comentarios son anotaciones que el compilador ignora. Sirven exclusivamente para documentar el código y no afectan al flujo de ejecución .

Existen tres tipos de comentarios en Java:

1. **Comentario de una línea (`//`):** Comienza con `//` y se extiende hasta el final de la línea .
   ```java
   // Esto es un comentario de una sola línea
   ```
2. **Comentario multilínea / párrafo (`/* ... */`):** Todo el texto entre `/*` y `*/` es considerado un comentario .
   ```java
   /*
    * Comentario que abarca
    * varias líneas.
    */
   ```
3. **Comentario de documentación Javadoc (`/** ... */`):** Se utiliza para generar documentación HTML automática estilo API de Oracle .
   ```java
   /**
    * @param args Argumentos de la línea de comandos
    */
   ```

---

## 4. El Primer Programa: `HolaMundo`

Ejemplo clásico de programa en Java :

```java
package ejemplos;

/*
 * Ejemplo HolaMundo
 * Imprime el mensaje "Hola, Mundo!" con salto de línea
 */
public class HolaMundo {
    public static void main(String[] args) {
        // Imprime el mensaje "Hola, Mundo!"
        System.out.println("Hola, Mundo!");
      }
}
``` 

### Componentes clave del método `main`:
* `public`: Accesible desde cualquier lugar fuera de la clase .
* `static`: Se puede invocar sin necesidad de crear una instancia de la clase .
* `void`: Indica que el método no devuelve ningún valor .
* `String[] args`: Parámetro que recibe un array de cadenas con los argumentos pasados por consola .
* `System.out.println(...)`: Imprime el mensaje especificado por la consola y añade un salto de línea .

---

## 5. Variables y Declaración (`Aldagaiak`)

Una **variable** es una posición de memoria reservada para almacenar un valor . Posee:
* Un **identificador** (nombre) para acceder a ella .
* Un **tipo de dato** que determina qué valores puede almacenar y cuánto espacio ocupa .

### Sintaxis de declaración e inicialización:
```java
<tipo> <nombre> [= valor_inicial];
``` 

### Buenas prácticas de estilo:
* Usar nombres descriptivos .
* Empezar con minúscula (convención `camelCase`) .

### Valores por defecto (si no se inicializan explícitamente):
| Tipo | Valor Inicial por Defecto |
| :--- | :--- |
| Enteros (`Integer`) | `0` |
| Coma flotante (`Floating-point`) | `0.0` |
| Carácter (`Char`) | `\u0000` |
| Booleano (`Boolean`) | `false` |
| Referencia (`Reference`) | `null` |

---

## 6. Tipos de Datos Primitivos (`Datu Motak`)

Java soporta **8 tipos de datos primitivos** :

1. **`boolean`**: Almacena estados lógicos (`true` o `false`) .
2. **`char`**: Almacena un único carácter Unicode delimitado por comillas simples (ej. `'a'`) .
3. **Tipos Enteros (sin decimales):**
   * `byte`: 8 bits 
   * `short`: 16 bits 
   * `int`: 32 bits (tipo entero más común) 
   * `long`: 64 bits 
4. **Tipos en Coma Flotante (con decimales):**
   * `float`: 32 bits (precisión simple) 
   * `double`: 64 bits (precisión doble, el más usado para decimales) 

> **Nota:** La clase `String` representa cadenas de texto (ej. `"Hola"`) y es un tipo por **referencia**, no un primitivo .

---

## 7. Salida por Pantalla (`System.out`)

Para mostrar información en la consola se utilizan principalmente dos métodos :
* `System.out.print(...)`: Imprime el contenido sin añadir salto de línea final .
* `System.out.println(...)`: Imprime el contenido y añade un salto de línea al final .

### Concatenación:
Se utiliza el operador `+` para unir variables y cadenas :
```java
int valor = 10;
char x = 'A';
System.out.println(valor); // Muestra: 10
System.out.println("Valor de x = " + x); // Muestra: Valor de x = A
``` 

---

## 8. Lectura de Datos desde Teclado (`Scanner`)

Para solicitar datos al usuario desde la consola, se utiliza la clase `Scanner` del paquete `java.util` .

### Pasos para usar `Scanner`:
1. **Importar la clase:**
   ```java
   import java.util.Scanner;
   ``` 
2. **Crear el objeto `Scanner`:**
   ```java
   Scanner teklatua = new Scanner(System.in);
   ``` 
3. **Leer según el tipo de dato:**
   * **Enteros (`int`):** `int n = teklatua.nextInt();` 
   * **Decimales (`double`):** `double r = teklatua.nextDouble();` 
   * **Carácter (`char`):** `char k = teklatua.next().charAt(0);` 
   * **Cadena / Palabra (`String`):** `String s = teklatua.next();` 
   * **Línea completa (`String`):** `String linea = teklatua.nextLine();` 
4. **Cerrar el recurso:**
   ```java
   teklatua.close();
   ``` 

---

## 9. Constantes (`Konstanteak`)

Las constantes son variables cuyo valor **no puede modificarse** una vez asignado .
* Se definen antecediendo la palabra clave `final` .
* Se acostumbra escribir sus nombres en MAYÚSCULAS separadas por guion bajo .

```java
final int DIAS_SEMANA = 7;
final int DIAS_LABORABLES = 5;
final double PI = 3.141592654;
``` 

---

## 10. Operadores y Eragileak

### Aritméticos
| Operador | Descripción | Precedencia |
| :---: | :--- | :---: |
| `++` / `--` | Incremento / Decremento | 1 |
| `-` (signo) | Negación unitaria | 2 |
| `*` | Multiplicación | 2 |
| `/` | División | 2 |
| `%` | Módulo (resto de la división) | 2 |
| `+` | Suma | 3 |
| `-` | Resta | 3 |

### Relacionales
| Operador | Descripción | Precedencia |
| :---: | :--- | :---: |
| `<` | Menor que | 5 |
| `>` | Mayor que | 5 |
| `<=` | Menor o igual que | 5 |
| `>=` | Mayor o igual que | 5 |
| `==` | Igual a | 6 |
| `!=` | Distinto de | 6 |

### Lógicos
| Operador | Descripción | Precedencia |
| :---: | :--- | :---: |
| `!` | NOT (negación) | 1 |
| `&&` | AND (y lógico) | 10 |
| `||` | OR (o lógico) | 11 |

---

## 11. Formato de Salida (`System.out.printf`)

Para dar formato específico a la salida numérica o textual, se utiliza `System.out.printf(...)` .

### Especificadores de formato más comunes:
* `%d`: Números enteros (`int`, `byte`, `short`, `long`) 
* `%f`: Números decimales (`float`, `double`) 
* `%c`: Caracteres (`char`) 
* `%s`: Cadenas de texto (`String`) 
* `%.2f`: Decimales formateados a 2 cifras decimales 
* `%n`: Salto de línea universal 

### Ejemplo:
```java
double r = 5.2;
final double PI = 3.141592654;
System.out.printf("Zirkunferentziaren perimetroa: %.2f%n", 2 * PI * r);
``` 
