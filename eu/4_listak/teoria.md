Dokumentu honen helburua Java programazio-lengoaian array dimentsiobakarrak, matrizeak eta testu-kateak (String eta StringBuffer) erabiltzeko kontzeptu teorigarriak eta adibide praktikoak azaltzea da, elementuen kudeaketa aurreratua (ezabatzea eta desplazatzea) eta ordenazio-algoritmoak barne.

## 1. Array-en kontzeptua eta deklarazioa

* **Array-aren definizioa / Definición de Array:** Mota bereko balio-zerrenda bat gordetzen duen tamaina finkoko datu-egitura lineala da. Elementu guztiak jarraian gordetzen dira memorian. / Es una estructura de datos lineal de tamaño fijo que almacena elementos del mismo tipo en posiciones continuas de memoria.

* **Deklarazioa / Declaración:** Array baten datu-mota eta izena definitzeko prozesua. / Proceso de definir el tipo de dato y el nombre del array.

* **Instantziazioa (new) / Instanciación:** Memorian elementu guztientzako espazioa erreserbatzea `new` eragilearen bidez. / Reserva de memoria para todos los elementos usando el operador `new`.

* **Hasieratzea / Inicialización:** Array-ari hasierako balioak esleitzea deklarazioan bertan `{}` erabiliz. / Asignación de valores iniciales en la propia declaración usando `{}`.

```java
// Deklarazioa eta sortzea lerro berean (Gomendatutako modua)
int[] tenperaturak = new int[12];

// Tamaina konstante baten bidez definitzea
final int NHILABETE = 12;
int[] tenperaturak2 = new int[NHILABETE];

// Hasieratze zuzena balioekin
int[] zenbakiak = {-2, 2, 3, 5, 6, 12, 14};
```

Hasierako baliorik zehazten ez bada, Javak balio lehenetsiak esleitzen dizkie elementuei:

| Datu-mota / Tipo de dato | Balio lehenetsia / Valor por defecto | 
| ----- | ----- | 
| `byte`, `short`, `int`, `long` | `0` | 
| `float`, `double` | `0.0` | 
| `boolean` | `false` | 
| `char` | `'\u0000'` (karaktere hutsa) | 
| Objektuak (`String`, etab.) | `null` | 

> **Oharra:** Behin array bat sortuta, bere tamaina ezin da aldatu exekuzioan zehar. / Una vez creado un array, su tamaño no se puede modificar durante la ejecución.

## 2. Elementuetara sarbidea eta zeharkatzea

* **Indizeak / Índices:** Array baten elementu bakoitza `0` posiziotik hasten den indize oso baten bidez identifikatzen da, `length - 1` posiziora arte. / Cada elemento se identifica con un índice entero desde `0` hasta `length - 1`.

* **Sarbidea / Acceso:** Indizea kortxeteen artean adierazten da: `arrayIzena[indizea]`. / El índice se indica entre corchetes.

* **length ezaugarria / Propiedad length:** Array baten tamaina edo elementu kopurua itzultzen duen propietatea. / Propiedad que devuelve la cantidad de elementos del array.

* **For sekuentziala / For secuencial:** Array osoa indize bidez zeharkatzeko begizta tradizionala. / Bucle tradicional para recorrer el array mediante índices.

* **For-each begizta / Bucle For-each:** Array-ko elementu bakoitza modu errazagoan irakurtzeko egitura. / Estructura simplificada para leer cada elemento del array.

```java
int[] adinak = {18, 20, 25, 30};

// Elementu bati balioa aldatzea
adinak[0] = 19;

// Zeharkatzea for begizta tradizionalarekin
for (int i = 0; i < adinak.length; i++) {
    System.out.println("Indizea " + i + ": " + adinak[i]);
}

// Zeharkatzea for-each egiturarekin (irakurketarako soilik)
for (int adina : adinak) {
    System.out.println("Adina: " + adina);
}
```

> **Oharra:** `for-each` begizta irakurtzeko oso erabilgarria da, baina ezin da erabili array-aren balioak aldatzeko edo posizio zehatzekin lan egiteko.

## 3. Elementuak ezabatzea eta desplazatzea (Shift Left)

Javan array-ek tamaina finkoa dutenez, ezin da benetan elementu bat ezabatu eta array-aren tamaina txikitu. Elementu bat ezabatzeko, **ezabatu nahi den posiziotik aurrera dauden elementu guztiak ezkerreko posiziora mugitu (desplazatu)** behar dira hula estaltzeko, eta azken posizioari balio lehenetsi bat (`0`, `null`, etab.) eman.

En Java, los arrays tienen un tamaño fijo, por lo que no es posible "eliminar" físicamente una casilla y encoger el array. Para eliminar un elemento, se deben **desplazar hacia la izquierda todos los elementos posteriores** para cubrir el hueco generado, asignando un valor por defecto (`0`, `null`, etc.) a la última posición libre.

* **Prozesuaren urratsak / Pasos del proceso:**
  1. Ezabatu nahi den posizioa (`posizioa`) identifikatu. / Identificar el índice a eliminar.
  2. Begizta baten bidez, `i = posizioa` denean hasi eta `i < tamaina - 1` denera arte, `array[i] = array[i + 1]` eginez elementuak ezkerreara mugitu. / Recorrer desde la posición eliminada copiando el elemento siguiente en la posición actual.
  3. Azken elementuari balio lehenetsia esleitu (adibidez, `0` edo `null`). / Asignar un valor por defecto a la última casilla.
  4. Erabili daitezkeen elementu erabilgarrien kopurua kontabilizatzen bada, kopuru hori unitate batean gutxitu. / Si se controla el número de elementos útiles, decrementar dicho contador.

```java
public class ElementuaEzabatu {

    public static void main(String[] args) {
        // Tamaina 6 duen array-a, baina 5 elementu erabilgarrirekin
        int[] zenbakiak = {10, 20, 30, 40, 50, 0};
        int elementuKopurua = 5; // Unean dauden elementu erabilgarriak
        int ezabatuIndizea = 2;   // 30 balioa duen indizea (posizioa 2) ezabatuko dugu

        System.out.println("Hasierako array-a:");
        inprimatuArraya(zenbakiak, elementuKopurua);

        // Desplazamendua (Shift Left)
        for (int i = ezabatuIndizea; i < elementuKopurua - 1; i++) {
            zenbakiak[i] = zenbakiak[i + 1]; // Eskuineko elementua ezkerrera mugitu
        }

        // Azken posizioa garbitu (balio lehenetsia jarri)
        zenbakiak[elementuKopurua - 1] = 0;
        
        // Elementu erabilgarrien kopurua gutxitu
        elementuKopurua--;

        System.out.println("\n30 ezabatu ondorengo array-a (desplazatuta):");
        inprimatuArraya(zenbakiak, elementuKopurua);
    }

    public static void inprimatuArraya(int[] arr, int tamaina) {
        for (int i = 0; i < tamaina; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }
}
```

> **Oharra:** Begiztan muga egokia erabiltzea ezinbestekoa da; `i < elementuKopurua - 1` erabili behar da, `arr[i + 1]` egitean `ArrayIndexOutOfBoundsException` errorea ez gertatzeko.

## 4. Array-ak ordenatzea (Sorting)

Datuak ordenatzea programazioaren oinarrizko zeregin bat da. Javan bi bide nagusi daude: algoritmo propioak inplementatzea (pedagogikoki garrantzitsua) edo Java libreria estandarra erabiltzea (eraginkorragoa).

Ordenar datos es fundamental en programación. En Java existen dos formas principales: implementar algoritmos manuales (importante a nivel conceptual) o usar la librería estándar (más eficiente para producción).

### 4.1 Burbuila Algoritmoa (Bubble Sort)
Burbuila algoritmoa konparazioetan oinarritutako algoritmo bakuna da. Viakorretan alboko bi elementu konparatzen dira eta ordenez kanpo badaude (adibidez, lehenengoa bigarrena baino handiagoa bada), beraien arteko posizioa trukatu egiten da. Prozesu hau behin eta berriz errepikatzen da array osoa ordenatuta egon arte.

El algoritmo de la burbuja compara elementos adyacentes y los intercambia si están en el orden incorrecto. Este proceso se repite hasta que no se necesiten más intercambios, desplazando los valores más grandes hacia el final en cada pasada (como una burbuja que asciende).

* **Funtzionamendua / Funcionamiento:**
  * **Kanpoko begizta:** Pasada kopurua kontrolatzen du. / Controla el número de pasadas.
  * **Barneko begizta:** Alboko bikoteak konparatzen ditu (`arr[j]` eta `arr[j+1]`). / Compara parejas adyacentes.
  * **Trukaketa (Swap):** Tarteko aldagai laguntzaile bat (`aux`) behar da balio bat ez galtzeko. / Se utiliza una variable auxiliar para intercambiar los valores.

```java
public class BubbleSortAdibidea {

    public static void bubbleSort(int[] arraya) {
        int n = arraya.length;
        boolean trukatua;

        for (int i = 0; i < n - 1; i++) {
            trukatua = false;
            // Azken i elementuak dagoeneko ordenatuta daude
            for (int j = 0; j < n - 1 - i; j++) {
                // Handiagora ordenatzeko (Goranzkoa / Ascendente): '>'
                if (arraya[j] > arraya[j + 1]) {
                    // Trukaketa (Swap)
                    int aux = arraya[j];
                    arraya[j] = arraya[j + 1];
                    arraya[j + 1] = aux;
                    
                    trukatua = true; // Aldaketa bat gertatu dela markatu
                }
            }
            // Pasada batean trukaketarik gertatu ez bada, array-a ordenatuta dago
            if (!trukatua) break;
        }
    }

    public static void main(String[] args) {
        int[] datuak = {64, 34, 25, 12, 22, 11, 90};
        
        System.out.println("Hasierako array-a:");
        for (int v : datuak) System.out.print(v + " ");

        bubbleSort(datuak);

        System.out.println("\n\nBurbuila algoritmo bidez ordenatutako array-a:");
        for (int v : datuak) System.out.print(v + " ");
    }
}
```

### 4.2 Java Estandarraren bidezko Ordenazioa (`Arrays.sort()`)
Ekoizpen-inguruneetan (producción) ez da algoritmo eskuzkoak inplementatzen; horren ordez, `java.util.Arrays` klaseko `Arrays.sort()` metodo estatikoa erabiltzen da. Metodo honek Dual-Pivot Quicksort edo Timsort bezalako algoritmo oso azkarrak eta optimizatuak erabiltzen ditu ($O(n \log n)$ konplexutasuna).

En entornos de desarrollo reales se utiliza `Arrays.sort()` de la librería estándar `java.util.Arrays`, la cual implementa algoritmos altamente optimizados.

```java
import java.util.Arrays;

public class ArraysSortAdibidea {

    public static void main(String[] args) {
        int[] zenbakiak = {50, 10, 80, 20, 40, 30};

        // 1. Array osoa ordenatu goranzko ordenean (Ascendente)
        Arrays.sort(zenbakiak);
        System.out.println("Arrays.sort() bidez ordenatua: " + Arrays.toString(zenbakiak));

        // 2. Array baten zati bat bakarrik ordenatu (indizea 1etik 4ra, 4 barne hartu gabe)
        int[] zatika = {9, 3, 7, 1, 5, 2};
        Arrays.sort(zatika, 1, 4); // 3, 7, 1 soilik ordenatuko ditu
        System.out.println("Zatika ordenatua (1etik 4ra): " + Arrays.toString(zatika));
    }
}
```

### 4.3 Ordenazio Metodoen Konparaketa / Comparativa de Métodos de Ordenación

| Ezaugarria / Característica | Bubble Sort (Burbuila) | `Arrays.sort()` |
| ----- | ----- | ----- |
| **Zailtasuna / Dificultad** | Erraza inplementatzen / Fácil de implementar | Berehalako erabilera / Uso inmediato |
| **Eraginkortasuna / Eficiencia** | Baxua ($O(n^2)$) | Oso altua ($O(n \log n)$) |
| **Uso gomendatua / Uso recomendado** | Ikasketa teorikoa / Aprendizaje académico | Proiektu errealak / Proyectos reales |

> **Oharra:** Datu-mota objektuekin (adibidez `Integer[]` edo `String[]`) beheranzko ordenean ordenatu nahi bada, `Arrays.sort(arraya, Collections.reverseOrder())` erabil daiteke.

## 5. Array-ak metodoetan

* **Balio bidezko igorpena / Paso por valor:** Datu-mota primitiboak (`int`, `double`, etab.) metodo bati pasatzean, kopiak igortzen dira. / Al pasar tipos primitivos, se envían copias de los datos.

* **Erreferentzia bidezko igorpena / Paso por referencia:** Array-ak objektuak dira. Metodo bati parametro gisa igortzean, memorian daukan erreferentzia (helbidea) pasatzen da. Beraz, metodo barruan egindako aldaketek **jatorrizko array-a aldatzen dute**. / Los arrays se pasan por referencia; las modificaciones dentro del método afectan al array original.

* **Array bat itzultzea / Retornar un array:** Metodo batek sortutako edo eraldatutako array bat itzul dezake `return` bidez. / Un método puede retornar un array creado o modificado.

```java
public class MetodoakArrayak {

    public static void main(String[] args) {
        int[] zenbakiak = arrayaSortu(5);
        arrayaInprimatu(zenbakiak);
    }

    public static int[] arrayaSortu(int tamaina) {
        int[] berria = new int[tamaina];
        for (int i = 0; i < berria.length; i++) {
            berria[i] = (int) (Math.random() * 10 + 1);
        }
        return berria;
    }

    public static void arrayaInprimatu(int[] arrayOsoa) {
        for (int balioa : arrayOsoa) {
            System.out.print(balioa + " ");
        }
        System.out.println();
    }
}
```

## 6. Ohiko akatsak eta egoera bereziak

* **ArrayIndexOutOfBoundsException:** Existitzen ez den indize batera sartzen saiatzean gertatzen den exekuzio-denborako errorea. / Error en tiempo de ejecución al acceder a un índice inexistente.

* **Inizializatu gabeko array-ak / Arrays no inicializados:** Array-aren erreferentzia deklaratu bai baina `new` bidez sortu ez denean gertatzen den konpilazio-errorea (`variable might not have been initialized`). / Error de compilación al usar un array no creado con `new`.

* **NullPointerException:** `null` balioa duen array baten atributu edo metodo batera sartzen saiatzean. / Error al intentar acceder a un array con valor `null`.

```java
int[] tenperaturak = new int[5]; // Indize erabilgarriak: 0, 1, 2, 3, 4

// ERROREA Exekuzioan: java.lang.ArrayIndexOutOfBoundsException: 5
// tenperaturak[5] = 22; 

int[] zenbakiak;
// ERROREA Konpilazioan: variable zenbakiak might not have been initialized
// System.out.println(zenbakiak[0]);
```

> **Oharra:** Begiztetan mugak egiaztatzea funtsezkoa da; `i <= array.length` idatzi ordez, beti `i < array.length` erabili behar da.

## 7. Array bidimentsionalak (Matrizeak)

* **Matrizearen kontzeptua / Concepto de Matriz:** Errenkada eta zutabez osatutako taula egitura (array-en array bat). / Estructura en forma de tabla con filas y columnas.

* **Deklarazioa eta sortzea / Declaración y creación:** Bi indize bikote erabiltzen dira: `datuMota[][] aldagaiIzena = new datuMota[errenkadak][zutabeak];`. / Se emplean dos pares de corchetes.

* **Hasieratzea / Inicialización:** Errenkada bakoitzeko balioak giltza artean biltzen dira. / Los valores de cada fila se agrupan entre llaves.

* **Zeharkatzea / Recorrido:** Peskatutako bi begizta anitz erabili behar dira. / Requiere bucles anidados.

```java
double[][] notak = {
    {5.2, 3.2, 6.7},
    {5.3, 6.5, 3.4},
    {2.3, 5.8, 9.7},
    {2.4, 5.5, 7.4}
};

int errenkadak = notak.length; // 4
int zutabeak = notak[0].length; // 3

for (int i = 0; i < notak.length; i++) {
    for (int j = 0; j < notak[i].length; j++) {
        System.out.print(notak[i][j] + "\t");
    }
    System.out.println();
}
```

## 8. String eta StringBuffer

* **String klasea / Clase String:** Karaktere-kateak kudeatzeko klasea. String objektuak **aldaezinak (immutables)** dira. / Los objetos String son inmutables.

* **StringBuffer klasea / Clase StringBuffer:** Karaktere-kate aldagarriak kudeatzeko egitura. / Cadena de caracteres mutable, ideal para modificaciones frecuentes.

* **Ihes-sekuentziak / Secuencias de escape:** Karaktere bereziak testuaren barnean adierazteko erabiltzen dira (`\n`, `\t`, etab.).

| Sekuentzia / Secuencia | Deskribapena / Descripción | 
| ----- | ----- | 
| `\n` | Lerro-jauzia / Salto de línea | 
| `\t` | Tabuladorea / Tabulador | 
| `\"` | Komatxo bikoitzak / Comillas dobles | 
| `\\` | Alderantzizko barra / Barra invertida (`\`) | 

```java
// String adibidea
String testua = "Kaixo Mundua";
int luzeera = testua.length(); // 12
char lehenengoa = testua.charAt(0); // 'K'

// StringBuffer adibidea
StringBuffer sb = new StringBuffer("Hasiera");
sb.append(" eta Jarraipena");
System.out.println(sb.toString()); // "Hasiera eta Jarraipena"
```

> **Oharra:** Bi String-en edukia berdin-berdina den konparatzeko, ez erabili `==` eragilea; erabili `equals()` edo `equalsIgnoreCase()` metodoa.