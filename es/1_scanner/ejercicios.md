# Programación Básica — Tema 1: Ejercicios

---

## Bloque 1 — Salida por pantalla (`System.out`)

**Objetivo:** Dominar el uso de `System.out.println()` y `System.out.print()`, sin leer datos todavía.

1. Crea la clase `HolaMundo`. El programa mostrará en pantalla el mensaje `"¡Hola mundo!"`.
2. Crea la clase `PresentacionClase`. El programa mostrará en pantalla, línea por línea, tu nombre, tu centro educativo y el nombre de tu grupo (utilizando tres llamadas a `println` diferentes).
3. Crea la clase `PrintVsPrintln`. Utiliza `print()` cuatro veces y un `println()` al final para deducir cuál es la diferencia entre ambos (el salto de línea del cursor).

> ➔ **Nota:** En este bloque no se leen datos; el objetivo es tomar ritmo escribiendo, compilando y ejecutando código.

---

## Bloque 2 — Variables y tipos de datos

**Objetivo:** Declarar variables, asignarles un valor y mostrarlas por pantalla, sin leer todavía nada desde el teclado.

1. Modifica el siguiente programa para que compile y funcione correctamente:
   ```java
   public class batu {
       public static void main(String[] args) {
           int n1 = 50;
           int n2 = 30, batu = 0, n3;
           batu = n1 + n2;
           System.out.println("Hau da emaitza: " + batu);
           Batu = batu + n3;
           System.out.println(batu);
       }
   }
   ```

2. ¿Por qué no compila este programa? Corrígelo para que funcione:
   ```java
   public class batu {
       public static void main(String[] args) {
           int n1 = 50, n2 = 30,
           boolean batu = 0;
           batu = n1 + n2;
           System.out.println("Hau da emaitza: " + batu ");
       }
   }
   ```

3. El siguiente programa tiene errores; encuéntralos y corrígelos para que funcione:
   ```java
   public class karratua {
       public static void main(String[] args) {
           int zenbakia = 2,
           karratua = zenbakia zenbakia;
           System.out.println(ZENBAKIA + " ren karratua honako hau da: "
           + karratu);
       }
   }
   ```

4. ¿Qué mostrará en pantalla este código?
   ```java
   int zkia = 5;
   zkia += zkia - 1;
   System.out.println(zkia);
   zkia = 4;
   System.out.println(zkia);
   ```

5. Crea un programa llamado `Longitud` en Java que calcule la longitud de una circunferencia de radio $3\text{ m}$ y la muestre por pantalla. La fórmula es la siguiente:
   $$L = 2 \cdot \pi \cdot r$$

6. Crea un programa llamado `AreaCirculo` en Java que calcule el área de un círculo con un radio de $5.2\text{ cm}$ y la muestre por pantalla. Fórmula:
   $$A = \pi \cdot r^2$$

7. Crea un programa llamado `Intercambio` en Java que, dadas las variables $a$ y $b$, intercambie sus valores entre sí. En pantalla debe aparecer lo siguiente:
   ```text
   Al principio el valor de a es: 5
   Al principio el valor de b es: 3
   ************************************
   Después del intercambio los datos quedan así:
   a= 3
   b= 5
   ```

> ➔ **Nota:** En este ejercicio (`Intercambio`) aún no se leen datos; el objetivo es comprender que una variable almacena un único valor en cada momento.

---

## Bloque 3 — Entrada de datos (`Scanner`: `nextInt`, `nextDouble`, `next`)

**Objetivo:** Pedir datos al usuario. En este bloque no utilizaremos `nextLine()` ni parseos; bastará con `nextInt()`, `nextDouble()` y `next()` (para palabras únicas).

1. Crea la clase `MostrarEntero`; esta clase leerá un valor entero (`int`) desde el teclado y lo imprimirá en pantalla.
2. Crea la clase `MostrarDecimal`; esta clase leerá un valor decimal (`double`) desde el teclado y lo imprimirá en pantalla.
3. Crea la clase `MostrarCaracter`; esta clase leerá un carácter (`char`) desde el teclado y lo imprimirá en pantalla.
4. Crea la clase `MostrarCadena`; esta clase leerá una cadena de caracteres (`String`) desde el teclado y la imprimirá en pantalla.
5. Crea un programa que pida al usuario: su nombre, su primer apellido y su segundo apellido (los tres utilizando `next()`, uno a uno). Una vez recibidos los datos, saluda al usuario en pantalla, por ejemplo:
   ```text
   Introduce tu nombre: Maite
   Introduce tu primer apellido: Uriarte
   Introduce tu segundo apellido: Urrutia
   ¡¡¡¡Hola Maite Uriarte Urrutia!!!!
   ```

> ➔ **Nota:** En el ejercicio de Nombre + Apellidos no hace falta utilizar `nextLine()` en ningún momento: realizando tres llamadas a `next()` (una por cada palabra) es suficiente, siempre que no sean nombres o apellidos compuestos. Pero si tenemos un nombre/apellido compuesto y usamos `nextLine()` para leerlo… ¿qué ocurre?

---

## Bloque 4 — Operadores aritméticos y constantes

**Objetivo:** Realizar cálculos más reales, utilizando constantes y mostrando los resultados con un formato determinado (estilo `printf`, `%.2f`).

1. Crea la clase `DosNumeros`. Pide al usuario dos números enteros y muestra en pantalla la suma, resta, multiplicación y división de ambos.
2. Crea el programa `Ecuacion` que calcule el valor de $Z$ cuando le proporcionamos un valor $X$. La ecuación es:
   $$Z = 3X^2 + 7X - 15$$
   Pide al usuario el valor de $X$ (`double`) y muestra el valor de $Z$ por pantalla.
3. Crea el programa `Notas` para pedir al usuario 3 notas por teclado (pueden ser enteras o decimales) y muestra la nota media.
4. Crea un programa que pida el radio (número decimal). Una vez obtenido el radio, realiza los siguientes cálculos utilizando una constante con valor $\pi = 3.141592654$:
   - Perímetro de la circunferencia ($2 \cdot \pi \cdot R$)
   - Área del círculo ($\pi \cdot R^2$)
   - Área de una esfera ($4 \cdot \pi \cdot R^2$)
   - Volumen de la esfera ($\frac{4}{3} \cdot \pi \cdot R^3$)

   *Todos los resultados deben mostrarse con dos decimales.*
   *Las constantes se declaran con la palabra clave `final` en Java, por ejemplo:* `final double PI = 3.141592654;`

5. Crea el programa `Segundos` para calcular cuántas horas, minutos y segundos hay en una cantidad dada de segundos (número entero). Pide los segundos al usuario y el programa deberá indicar el desglose en horas, minutos y segundos.
   - Para obtener el cociente: `/`
   - Para obtener el resto: `%`
6. Crea el programa `Descuentos` para calcular el precio final en unos descuentos. Pide el precio original y el porcentaje de descuento ($\%$), y el programa deberá calcular cuánto se debe pagar.

---

## Bloque 5 — Ejercicios integrados (combinación de los anteriores)

**Objetivo:** En este bloque, cada ejercicio debe combinar la entrada de datos, variables, operadores y formato de salida para poner en práctica todo lo aprendido.

1. Crea el programa `CalculoSalario`. Pide al usuario el número de horas trabajadas y el precio por hora (ambos pueden ser decimales), y muestra cuánto cobrará en total, con dos decimales.
2. Crea el programa `ConIVA`. Pide el precio de un producto (sin IVA) y el porcentaje de IVA (por ejemplo $21$), y muestra en pantalla: el precio sin IVA, el importe del IVA y el precio final con IVA, todos con dos decimales.
3. Crea el programa `ConversionGrados`. Pide una temperatura en grados Celsius (`double`) y conviértela a Fahrenheit utilizando la siguiente fórmula:
   $$F = C \cdot \frac{9}{5} + 32$$
   Muestra el resultado con dos decimales.
4. Crea el programa `RectanguloYTriangulo`. Pide la base y la altura de un rectángulo, y muestra su área y perímetro. A continuación, utilizando la misma base y altura, calcula el área de un triángulo ($\text{base} \cdot \text{altura} / 2$).
5. Crea el programa `GastoGasolina`. Pide la distancia de un viaje ($\text{km}$), el consumo medio del vehículo ($\text{litros}/100\text{km}$) y el precio por litro (€), y calcula cuánto costará el viaje en gasolina, con dos decimales.