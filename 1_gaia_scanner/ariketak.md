# 1. Gaia: Scanner - Ariketak

Ondorengo ariketetan Java-ko `Scanner` klasea erabiliz erabiltzailearen datuak kontsolatik irakurtzea praktikatuko dugu.

---

## 1. Ariketa: Agur pertsonalizatua (Oinarrizkoa)

**Ariketaren azalpena:**  
Eskatu erabiltzaileari bere izena eta adina kontsolatik. Ondoren, inprimatu mezu pertsonalizatua.

**Adibidea:**
```text
Sartu zure izena: Ane
Sartu zure adina: 20

Kaixo Ane, zure adina 20 urtekoa da.
```

??? tip "Laguntza eta egitura"
    Gogoratu `java.util.Scanner` inportatu behar duzula fitxategiaren hasieran:
    ```java
    import java.util.Scanner;

    public class Ariketa1 {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            
            // Zure kodea hemen
            
            scanner.close();
        }
    }
    ```

---

## 2. Ariketa: Eragiketa matematiko bakunak (Oinarrizkoa)

**Ariketaren azalpena:**  
Eskatu erabiltzaileari bi zenbaki oso (`int`) eta erakutsi haien arteko **batura**, **kenketa** eta **biderketa**.

**Adibidea:**
```text
Sartu lehenengo zenbakia: 10
Sartu bigarren zenbakia: 5

Batura: 15
Kenketa: 5
Biderketa: 50
```

---

## 3. Ariketa: Tenperatura bihurgailua (Tarteko maila)

**Ariketaren azalpena:**  
Eskatu erabiltzaileari tenperatura bat gradu Celsius-etan (`double` motakoa) eta bihur ezazu Fahrenheit gradutara formula hau erabiliz:

$$Fahrenheit = \left(Celsius \times \frac{9}{5}\right) + 32$$

**Adibidea:**
```text
Sartu tenperatura ºC-tan: 25.0
Fahrenheit-etan: 77.0 ºF
```

---

## 4. Ariketa: Buferraren garbiketa (Erronka)

**Ariketaren azalpena:**  
Eskatu erabiltzaileari lehenik bere **NAN zenbakia** (osokoa) `nextInt()` bidez, eta jarraian bere **izen-abizenak** `nextLine()` bidez.

> **Aholkua:** Gogoratu `nextInt()` erabili ondoren `\n` lerro-jauzia buferrean geratzen dela. `scanner.nextLine()` gehigarri bat erabili beharko duzu bufer hori garbitzeko izen-abizenak irakurri aurretik.

??? note "Ebazpena ikusi"
    ```java
    import java.util.Scanner;

    public class Ariketa4 {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);

            System.out.print("Sartu zure NAN zenbakia (letra gabe): ");
            int nan = scanner.nextInt();
            
            // Buferra garbitzeko lerro-jauzia irakurri
            scanner.nextLine();

            System.out.print("Sartu zure izen-abizenak: ");
            String izena = scanner.nextLine();

            System.out.println("NAN: " + nan + " | Izena: " + izena);
            
            scanner.close();
        }
    }
    ```