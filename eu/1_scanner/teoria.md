# Teoria - 1. Gaia: Oinarrizko Programazioa Javan

Dokumentu honek Web Aplikazioen Garapena ziklorako **1. Gaia: Oinarrizko Programazioa**ren azalpen teoriko osoa biltzen du.

---

## 1. Programaziora eta Javara Sarrera

* **Programazio-lengoaia:** **Java** lengoaia erabiltzen da programak garatzeko.
* **Garapen-ingurunea (IDE):** **Eclipse** erabiltzen da kodea idatzi, konpilatu eta exekutatzeko.
* **`.java` fitxategiak:**
  * Javako iturburu-kodea duten fitxategiek beti `.java` luzapena izan behar dute.
  * Fitxategiaren izenak barruan definitutako **klase publikoaren** (`public class`) izenarekin guztiz bat etorri behar du.
* **Jardunbide egokiak:** Oso garrantzitsua da kodean iruzkinak sartzea, klaseen, metodoen eta kode-blokeen funtzionaltasuna dokumentatzeko.

---

## 2. Java Programa Baten Egitura Orokorra

Java programa guztiak klase eta paketeen barruan egituratzen dira. Oinarrizko egitura honako hau da:

```java
package paketea; // Paketearen deklarazioa

import libreriak; // Beharrezko liburutegien inportazioa

public class ProgramaAdibidea {
    
    // Klase/instantzia aldagaien deklarazioa
    int ald1;
    float ald2;
    String ald3;

    // Eraikitzailearen / metodoen deklarazioa
    public ProgramaAdibidea() {
        // ...
    }

    // main metodoa: programaren sarrera-puntua
    public static void main(String[] args) {
        // Exekutatu beharreko aginduak
    }
}
```

---

## 3. Kodeko Iruzkinak (`Iruzkinak`)

Iruzkinak konpiladoreak baztertzen dituen oharrak dira. Kodea dokumentatzeko soilik balio dute eta ez diote exekuzio-fluxuari eragiten.

Javan hiru iruzkin mota daude:

1. **Lerro bakarreko iruzkina (`//`):** `//` ikurrarekin hasten da eta lerroaren amaierara arte luzatzen da.
   ```java
   // Hau lerro bakarreko iruzkin bat da
   ```
2. **Lerro anitzeko iruzkina / paragrafoa (`/* ... */`):** `/*` eta `*/` arteko testu guztia iruzkintzat hartzen da.
   ```java
   /*
    * Lerro bat baino gehiago
    * hartzen dituen iruzkina.
    */
   ```
3. **Javadoc dokumentazio-iruzkina (`/** ... */`):** Oracle estiloko HTML dokumentazio automatikoa sortzeko erabiltzen da.
   ```java
   /**
    * @param args Komando-lerroko argumentuak
    */
   ```

---

## 4. Lehenengo Programa: `KaixoMundua`

Javako programa baten adibide klasikoa:

```java
package adibideak;

/*
 * KaixoMundua adibidea
 * "Kaixo, Mundua!" mezua inprimatzen du lerro-jauziarekin
 */
public class KaixoMundua {
    public static void main(String[] args) {
        // "Kaixo, Mundua!" mezua inprimatzen du
        System.out.println("Kaixo, Mundua!");
    }
}
```

### `main` metodoaren gako-osagaiak:
* `public`: Klasetik kanpoko edozein lekutatik atzigarria.
* `static`: Klasearen instantzia bat sortu beharrik gabe deitu daiteke.
* `void`: Metodoak baliorik itzultzen ez duela adierazten du.
* `String[] args`: Kontsolatik pasatako argumentuen kate-matrize (array) bat jasotzen duen parametroa.
* `System.out.println(...)`: Zehaztutako mezua kontsolatik inprimatzen du eta lerro-jauzi bat gehitzen du amaieran.

---

## 5. Aldagaiak eta Deklarazioa (`Aldagaiak`)

**Aldagai** bat balio bat gordetzeko erreserbatutako memoria-posizio bat da. Ezaugarri hauek ditu:
* **Identifikatzaile** bat (izena) bertara sartzeko.
* Zein balio gorde ditzakeen eta zenbat leku hartzen duen zehazten duen **datu mota** bat.

### Deklaratzeko eta hasieratzeko sintaxia:
```java
<mota> <izena> [= hasierako_balioa];
```

### Estilo-jardunbide egokiak:
* Izen deskribatzaileak erabiltzea.
* Letra minuskulaz hastea (`camelCase` hitzarmena).

### Balio lehenetsiak (esplizituki hasieratzen ez badira):
| Mota | Hasierako Balio Lehenetsia |
| :--- | :--- |
| Osoak (`Integer`) | `0` |
| Koma mugikorra (`Floating-point`) | `0.0` |
| Karakterea (`Char`) | `\u0000` |
| Boolearra (`Boolean`) | `false` |
| Erreferentzia (`Reference`) | `null` |

---

## 6. Oinarrizko Datu Motak (`Datu Motak`)

Javak **oinarrizko 8 datu mota** (primitiboak) onartzen ditu:

1. **`boolean`**: Egoera logikoak gordetzen ditu (`true` edo `false`).
2. **`char`**: Komatxo bakun artean mugatutako Unicode karaktere bakarra gordetzen du (adib. `'a'`).
3. **Mota Osoak (hamartarrik gabeak):**
   * `byte`: 8 bit
   * `short`: 16 bit
   * `int`: 32 bit (mota osorik ohikoena)
   * `long`: 64 bit
4. **Koma Mugikorreko Motak (hamartarrekin):**
   * `float`: 32 bit (zehaztasun bakuna)
   * `double`: 64 bit (zehaztasun bikoitza, hamartarretarako erabiliena)

> **Oharra:** `String` klaseak testu-kateak adierazten ditu (adib. `"Kaixo"`) eta **erreferentziazko** mota bat da, ez oinarrizkoa (primitiboa).

---

## 7. Pantailaratzea (`System.out`)

Informazioa kontsolan erakusteko nagusiki bi metodo erabiltzen dira:
* `System.out.print(...)`: Edukia inprimatzen du amaierako lerro-jauzirik gabe.
* `System.out.println(...)`: Edukia inprimatzen du eta amaieran lerro-jauzi bat gehitzen du.

### Kateatzea / Biltzea (Concatenación):
`+` eragilea erabiltzen da aldagaiak eta testu-kateak lotzeko:
```java
int balioa = 10;
char x = 'A';
System.out.println(balioa); // Erakusten du: 10
System.out.println("x-ren balioa = " + x); // Erakusten du: x-ren balioa = A
```

---

## 8. Datuak Teklatutik Irakurtzea (`Scanner`)

Erabiltzaileari kontsolatik datuak eskatzeko, `java.util` paketekoa den `Scanner` klasea erabiltzen da.

### `Scanner` erabiltzeko urratsak:
1. **Klasea inportatzea:**
   ```java
   import java.util.Scanner;
   ```
2. **`Scanner` objektua sortzea:**
   ```java
   Scanner teklatua = new Scanner(System.in);
   ```
3. **Datu motaren arabera irakurtzea:**
   * **Osoak (`int`):** `int n = teklatua.nextInt();`
   * **Hamartarrak (`double`):** `double r = teklatua.nextDouble();`
   * **Karakterea (`char`):** `char k = teklatua.next().charAt(0);`
   * **Testu-katea / Hitz bakarra (`String`):** `String s = teklatua.next();`
   * **Lerro osoa (`String`):** `String linea = teklatua.nextLine();`
4. **Baliabidea ixtea:**
   ```java
   teklatua.close();
   ```

---

## 9. Konstanteak (`Konstanteak`)

Konstanteak behin balioa esleituta **aldatu ezin diren** aldagaiak dira.
* `final` gako-hitza aurretik jarriz definitzen dira.
* Haien izenak LETRA MAIUSKULEZ idatzi ohi dira, marra azpiaz bereizita.

```java
final int ASTEKO_EGUNAK = 7;
final int LAN_EGUNAK = 5;
final double PI = 3.141592654;
```

---

## 10. Eragileak (`Operadores`)

### Aritmetikoak
| Eragilea | Deskribapena | Lehentasuna |
| :---: | :--- | :---: |
| `++` / `--` | Inkrementua / Dekrementua | 1 |
| `-` (zeinua) | Negoaketa unitarioa | 2 |
| `*` | Biderketa | 2 |
| `/` | Zatiketa | 2 |
| `%` | Modulua (zatiketaren hondarra) | 2 |
| `+` | Batura | 3 |
| `-` | Kenketa | 3 |

### Erlazionalak
| Eragilea | Deskribapena | Lehentasuna |
| :---: | :--- | :---: |
| `<` | Txikiagoa | 5 |
| `>` | Handiagoa | 5 |
| `<=` | Txikiagoa edo berdina | 5 |
| `>=` | Handiagoa edo berdina | 5 |
| `==` | Berdina | 6 |
| `!=` | Desberdina | 6 |

### Logikoak
| Eragilea | Deskribapena | Lehentasuna |
| :---: | :--- | :---: |
| `!` | EZ (Ezeztapena / NOT) | 1 |
| `&&` | ETA (AND logikoa) | 10 |
| `||` | EDO (OR logikoa) | 11 |

---

## 11. Irteera-Formatua (`System.out.printf`)

Zenbakizko zein testuzko irteerari formatu zehatza emateko, `System.out.printf(...)` erabiltzen da.

### Formatu-zehaztatzaile ohikoenak:
* `%d`: Zenbaki osoak (`int`, `byte`, `short`, `long`)
* `%f`: Zenbaki hamartarrak (`float`, `double`)
* `%c`: Karaktereak (`char`)
* `%s`: Testu-kateak (`String`)
* `%.2f`: 2 zifra hamartarrekin formatuatutako zenbakiak
* `%n`: Lerro-jauzi unibertsala

### Adibidea:
```java
double r = 5.2;
final double PI = 3.141592654;
System.out.printf("Zirkunferentziaren perimetroa: %.2f%n", 2 * PI * r);
```