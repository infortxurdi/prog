# Programación — Tema 4 — Arrays y Matrices: Ejercicios

## Bloque 1 — Arrays Unidimensionales Básicos (Java SE)

**Objetivo:** Comprender la estructura interna de un array unidimensional, trabajar con índices desde 0, aplicar iteraciones con bucles `for` y realizar cálculos estadísticos elementales.

1. Crear un array de 5 números enteros inicializados directamente en el código. Mostrar sus elementos por pantalla, cada uno en una línea diferente. A continuación, modificar el programa para mostrar junto a cada valor el índice numérico que ocupa en el array.

2. Diseñar un programa que declare un array de 7 números enteros. Pedir al usuario que introduzca los valores uno a uno por consola, almacenarlos en el array y, posteriormente, imprimirlos por pantalla en el mismo orden de entrada.

3. Almacenar los nombres de 5 alumnos en un array de tipo `String`. Recorrer el array para mostrar los nombres junto a la posición o índice asociado a cada uno.

4. Solicitar al usuario la introducción de 6 números enteros y almacenarlos en un array. A continuación, recorrer el array en sentido inverso para imprimir los elementos desde la última posición hasta la primera.

5. Pedir al usuario 5 números enteros, guardarlos en un array y calcular tanto la suma total de sus elementos como su media aritmética:

$$
\text{Media} = \frac{1}{N} \sum_{i=0}^{N-1} \text{array}[i]
$$

6. Generar aleatoriamente 10 números enteros comprendidos en el intervalo $[1, 10]$ y guardarlos en un array. Contar e imprimir cuántos de esos números son pares y cuántos son impares.

7. Cargar un array con 8 números enteros aleatorios entre 1 y 10. Recorrer la estructura para determinar y mostrar el valor máximo y el valor mínimo almacenados.

8. Generar un array de 10 enteros aleatorios entre 1 y 10. A continuación, pedir al usuario un número a buscar e indicar si dicho número existe dentro del array y, en caso afirmativo, cuántas veces se repite.

9. Crear dos arrays de 10 posiciones: uno para almacenar nombres de alumnos (`String[]`) y otro para sus respectivas notas (`double[]`). Validar que las notas introducidas se encuentren dentro del rango $[0, 10]$ e imprimir la relación completa de alumno y calificación.

> ➔ **Nota:** Recuerda que los índices en Java son base 0, por lo que un array de tamaño $N$ tiene posiciones válidas desde $0$ hasta $N-1$. Acceder a la posición $N$ lanzará la excepción `ArrayIndexOutOfBoundsException`.

---

## Bloque 2 — Modularidad y Operaciones con Arrays (Java Methods & Modularity)

**Objetivo:** Desarrollar programas modularizados divididos en métodos específicos para la lectura, procesamiento, manipulación avanzada y visualización de arrays.

1. **Gestión de edades de estudiantes:**

   * Crear un programa que lea la edad de 20 estudiantes (valores válidos entre 18 y 35 años) y calcule su media.

   * Refactorizar el código en los siguientes métodos:

     * `int adinaIrakurri()`: Pide una edad válida entre 18 y 35 por teclado y la devuelve.

     * `double mediaKalkulatu(int[] adinak)`: Recibe el array y devuelve la media aritmética de las edades.

     * `void adinaInprimatu(int[] adinak)`: Recibe el array, muestra las edades registradas y, al final, imprime la media calculada.

2. **Operaciones por posiciones pares e impares:**

   * Cargar un array de 20 enteros aleatorios entre 1 y 100.

   * Diseñar una versión modularizada con los siguientes métodos:

     * `int sortuZenbakia()`: Genera y devuelve un número aleatorio en el rango $[1, 100]$.

     * `void taulaKargatu(int[] taula)`: Rellena el array llamando repetidamente a `sortuZenbakia()`.

     * `int bikoitiakBatu(int[] taula)`: Calcula y devuelve la suma de los elementos situados en **posiciones/índices pares**.

     * `long bakoitiakBiderkatu(int[] taula)`: Calcula y devuelve el producto acumulado de los elementos situados en **posiciones/índices impares**.

     * `void datuakInprimatu(int[] taula, int batura, long produktua)`: Muestra el contenido del array y los resultados obtenidos.

3. **Análisis de frecuencia de dígitos:**

   * Generar un array de 20 elementos con valores aleatorios entre 1 y 9.

   * Modularizar con las siguientes funciones:

     * `int[] arrayaKargatu(int tamaina, int min, int max)`: Crea y retorna un array poblado con valores aleatorios entre `min` y `max`.

     * `void maiztasunaErakutsi(int[] arraya)`: Cuenta y muestra por pantalla el número total de apariciones de cada dígito (cuántos 1, cuántos 2, ..., cuántos 9).

     * `void arrayInprimatu(int[] arraya)`: Imprime el contenido completo del array.

4. **Registro de notas e informes estadísticos:**

   * Diseñar un sistema de calificaciones para 10 estudiantes con los siguientes métodos:

     * `String[] arrayIzenakKargatu()`: Devuelve un array con los nombres de 10 alumnos.

     * `double[] arrayNotakKargatu()`: Devuelve un array con 10 notas validadas en el rango $[0.0, 10.0]$.

     * `void datuGuztiakAurkeztu(String[] izenak, double[] notak)`: Muestra en formato lista cada alumno junto a su nota:

       ```text
       Nombre1 Apellido11 Apellido12 - Nota
       Nombre2 Apellido21 Apellido22 - Nota
       ```

     * `double[] datuakKalkulatu(double[] notak)`: Procesa las notas y devuelve un array de 4 posiciones con:

       1. Media de la clase ($\bar{x}$)

       2. Nota máxima

       3. Nota mínima

       4. Cantidad de aprobados

     * `void estatistikakAurkeztu(String[] izenak, double[] notak, double[] kalkuluak)`: Muestra en pantalla el informe completo con la media, el alumno con la máxima nota y el alumno con la mínima nota.

5. **Simulación estadística de sorteo de caracteres:**

   * Realizar una simulación de 100 tiradas de letras entre la `'a'` y la `'z'`.

   * Implementar los métodos:

     * `char[] sortuZozketa(int jaurtiketaKop, char valMin, char valMax)`: Retorna un array con caracteres aleatorios entre `valMin` y `valMax`.

     * `void zozketaErakutsi(char[] zozketaArray)`: Muestra el contenido del array organizado en exactamente 15 columnas.

     * `int[] zenbatuMaiztasuna(char[] zozketaArray)`: Devuelve un array con la frecuencia absoluta de aparición de cada letra del abecedario.

     * `void maiztasunaErakutsi(int[] maiztasunArray)`: Muestra en consola la frecuencia acumulada de cada carácter.

6. **Inversión de arrays *in-place*:**

   * Cargar un array de 20 enteros aleatorios e invertir el orden de sus elementos sobre el mismo array, **sin utilizar arrays auxiliares**.

   * Métodos a implementar:

     * `int[] taulaKargatu(int n, int min, int max)`

     * `void alderantzikatuArray(int[] arraya)`: Invierte la estructura intercambiando los extremos:

$$
\text{array}[i] \longleftrightarrow \text{array}[N - 1 - i] \quad \forall i \in \left[0, \frac{N}{2}\right)
$$

   * `void arrayInprimatu(int[] arraya)`

7. **Empaquetado de arrays (desplazamiento de ceros al final):**

   * Dado un array de 20 enteros aleatorios con presencia de ceros, reordenar el array desplazando todos los valores nulos hacia el extremo derecho, conservando el orden relativo de los demás números.

   * *Ejemplo de transformación:*

     ```text
     Estado inicial:  [20, 0, 0, 31, 12, 0, 15, 18, 0, 3]
     Estado final:    [20, 31, 12, 15, 18, 3, 0, 0, 0, 0]
     ```

   * Métodos:

     * `int[] taulaKargatu(int n, int min, int max)`

     * `void zeroakMugitu(int[] arraya)`

     * `void arrayInprimatu(int[] arraya)`

> ➔ **Nota:** Al trabajar con métodos que modifican un array pasado como argumento, recuerda que Java pasa las referencias a los objetos por valor. Las modificaciones realizadas en los elementos del array dentro del método afectarán directamente al array original.

---

## Bloque 3 — Algoritmos de Ordenación de Arrays (Sorting Algorithms)

**Objetivo:** Comprender e implementar los algoritmos clásicos de ordenación de arrays sobre números y cadenas de texto, comparando su lógica e intercambios.

1. **Ordenación por Método de la Burbuja (Bubble Sort):**

   * Dado un array de 10 enteros desordenados generados aleatoriamente entre 1 y 50, implementar el algoritmo de la burbuja para ordenarlos de menor a mayor.

   * Implementar un método `void burbuja(int[] array)` que realice comparaciones entre elementos adyacentes e intercambie sus posiciones si están fuera de orden.

   * Añadir un contador que muestre por consola cuántos intercambios (*swaps*) se han realizado en total al finalizar el proceso.

2. **Ordenación por Selección Directa (Selection Sort):**

   * Cargar un array con 8 números enteros introducidos por el usuario.

   * Crear un método `void seleccion(int[] array)` que busque recursivamente el elemento mínimo del subvector no ordenado y lo coloque en la posición correspondiente.

3. **Ordenación por Inserción Directa (Insertion Sort):**

   * Generar un array de 10 enteros aleatorios entre 1 y 100.

   * Crear un método `void insercion(int[] array)` que ordene el array construyendo la lista ordenada elemento a elemento (similar a como se ordenan las cartas en la mano).

4. **Ordenación Paralela de Arrays (Nombres y Notas):**

   * Dado un array de nombres `String[] alumnos = {"Miren", "Aitor", "Jon", "Ane"}` y sus correspondientes notas `double[] notas = {4.5, 9.0, 6.2, 8.5}`, implementar un programa que ordene las notas de mayor a menor.

   * **Requisito clave:** Cada vez que se realice un intercambio en el array de notas, se debe realizar el mismo intercambio en el array de nombres para mantener la correspondencia entre alumno y calificación.

> ➔ **Nota:** Para comparar cadenas de texto (`String`) al ordenar alfabéticamente en Java, no se deben usar los operadores `<` o `>`, sino el método `cadena1.compareTo(cadena2)`.

---

## Bloque 4 — Arrays Bidimensionales / Matrices (Java 2D Arrays)

**Objetivo:** Dominar el uso de tablas bidimensionales (matrices), el acceso mediante doble índice `[fila][columna]`, el recorrido por filas/columnas y el formateo tabular de datos.

1. **Gestión académica multidimensional:**

   * Dado el siguiente escenario con 4 alumnos y 3 módulos formativos:

     ```java
     final int IKASLEAK = 4;
     final int MODULUAK = 3;
     double[][] notak = {
         {5.2, 3.2, 6.7},
         {5.3, 6.5, 3.4},
         {2.3, 5.8, 9.7},
         {2.4, 5.5, 7.4}
     };
     String[] ikasleak = {"Ana", "Kepa", "Miren", "Jon"};
     String[] moduluak = {"PROG", "LM", "BD"};
     ```

   * Desarrollar los algoritmos necesarios para:

     1. Imprimir la matriz de notas simple.

     2. Mostrar la información formateada en forma de tabla con encabezados de filas y columnas:

        ```text
               PROG   LM     BD
        Ana    5.2    3.2    6.7
        Kepa   5.3    6.5    3.4
        Miren  2.3    5.8    9.7
        Jon    2.4    5.5    7.4
        ```

     3. Calcular e imprimir la nota media por cada estudiante.

     4. Calcular e imprimir la nota media por cada módulo/asignatura.

     5. Presentar una tabla consolidada completa que incluya la columna de promedio por alumno y la fila de promedio por módulo:

        ```text
        ----------------------------------
        |        | PROG | LM   | BD   | Media |
        ----------------------------------
        | Ana    | 5.2  | 3.2  | 6.7  | 5.03  |
        | Kepa   | 5.3  | 6.5  | 3.4  | 5.07  |
        | Miren  | 2.3  | 5.8  | 9.7  | 5.93  |
        | Jon    | 2.4  | 5.5  | 7.4  | 5.10  |
        ----------------------------------
        | Media  | 3.80 | 5.25 | 6.80 |       |
        ----------------------------------
        ```

2. **Control de plantilla por departamentos y categorías:**

   * Una empresa cuenta con 10 departamentos y 5 categorías laborales en cada uno.

   * Diseñar una matriz $10 \times 5$ donde cada celda $[i][j]$ represente el número de empleados del Departamento $i$ con Categoría $j$.

   * Calcular:

     * Total de empleados por cada departamento (suma por filas).

     * Total de empleados por cada categoría profesional (suma por columnas).

     * Total general de trabajadores de la empresa.

   * Imprimir la tabla completa de distribución formateada en columnas:

     ```text
     CATEGORÍAS
     | Dep  |  1 |  2 |  3 |  4 |  5 | Total |
     |------|----|----|----|----|----|-------|
     | 1    |  2 |  2 |  1 |  3 |  1 |   9   |
     | 2    |  0 |  1 |  4 |  1 |  2 |   8   |
     | ...  | .. | .. | .. | .. | .. |  ..   |
     | 10   |  0 |  0 |  0 |  1 |  2 |   3   |
     | Tot: | 11 | 10 | 12 | 15 | 14 |  62   |
     ```

3. **Estudio bancario por distritos de Bilbao:**

   * Se analiza el número de clientes distribuidos en 6 bancos (BBVA, BBK, LA CAIXA, EUSKADIKO KUTXA, SANTANDER, KUTXA) y 7 distritos de Bilbao (Deustu, Uribarri, Otxarkoaga, Begoña, Abando, Errekalde, Basurtu).

   * Implementar las siguientes funciones:

     * `int[] bezeroKopBankuko(int[][] matriz)`: Retorna un array con la suma total de clientes por banco.

     * `int[] bezeroKopAuzoko(int[][] matriz)`: Retorna un array con la suma total de clientes por distrito.

     * `void datuakAurkeztu(...)`: Muestra en formato gráfico/tabular el desglose completo.

     * `void bezeroakBankukoOrdenatutaAurkeztu(String[] bancos, int[] totales)`: Ordena de mayor a menor la lista de bancos según su número total de clientes (usando un algoritmo de ordenación como Burbuja o Selección) e imprime el resultado final:

       ```text
       Lista de bancos ordenada por clientes
       -------------------------------------
           Banco           Clientes
         LA CAIXA            1878
         C.LABORAL           1747
         BBK                 1737
         BBVA                1334
         KUTXA               1280
         SANTANDER            756
       ```

> ➔ **Nota:** Al recorrer matrices mediante bucles anidados, el bucle externo suele controlar las filas (`matriz.length`) y el bucle interno las columnas (`matriz[i].length`).

---

## Bloque 5 — Búsquedas, Desplazamientos y Gestión CRUD (Array Operations)

**Objetivo:** Dominar el algoritmo de **desplazamiento a la izquierda para el borrado de elementos** en un array estático y construir una aplicación de consola interactiva.

1. **Algoritmo explícito de borrado con desplazamiento:**

   * Escribir un método `boolean eliminarElemento(int[] array, int numElementos, int valorAEliminar)` que realice lo siguiente:

     1. Buscar la primera posición $pos$ donde se encuentre `valorAEliminar`.

     2. Si no existe, devolver `false`.

     3. Si existe, **desplazar todos los elementos posteriores una posición hacia la izquierda** desde $pos$ hasta $numElementos - 2$ para cubrir el hueco dejado:

$$
\text{array}[i] = \text{array}[i + 1] \quad \forall i \in [pos, \text{numElementos} - 2]
$$

     4. Asignar el valor `0` a la última posición que quedó duplicada y devolver `true`.

   * *Ejemplo visual del borrado del valor 15 en la posición 2:*

     ```text
     Antes del borrado (numElementos = 5):   [10, 20, 15, 30, 40, 0, 0]
     Tras desplazar a la izquierda:          [10, 20, 30, 40, 40, 0, 0]
     Tras limpiar última posición ocupada:  [10, 20, 30, 40,  0, 0, 0] (numElementos = 4)
     ```

2. **Gestor interactivo de un array dinámico (Consola CRUD):**

   * Diseñar un programa controlado por un menú de opciones para gestionar un array con capacidad para 10 números enteros y una variable `int numElementos = 0` para controlar la ocupación real.

   * El menú debe mantenerse en ejecución continua hasta que el usuario elija la opción de salir:

   ```text
   =================================
          MENÚ DE GESTIÓN
   =================================
   1. Insertar valor
   2. Buscar valor
   3. Eliminar valor (con desplazamiento)
   4. Mostrar array
   5. Salir
   Seleccione una opción: _
   ```

   * **Especificación de las funcionalidades:**

     * **1. Insertar valor:** Solicita un número. Si ya existe o el array está lleno (`numElementos == 10`), muestra un mensaje de advertencia. En caso contrario, lo inserta en `array[numElementos]` e incrementa `numElementos++`.

     * **2. Buscar valor:** Pide un número y realiza una búsqueda lineal indicando su posición o si no existe.

     * **3. Eliminar valor:** Pide un número y llama al método de eliminación con desplazamiento explicado en el ejercicio anterior, decrementando `numElementos--`.

     * **4. Mostrar array:** Imprime únicamente las posiciones válidas desde `0` hasta `numElementos - 1`.

     * **5. Salir:** Finaliza la ejecución de la aplicación.

> ➔ **Nota:** El desplazamiento hacia la izquierda es imprescindible en arrays de tamaño fijo cuando se desea mantener la continuidad de los datos sin dejar "huecos" vacíos o valores nulos intermedios.