# Teoria - 6. Gaia: Informazioa metatzea datu egituratan II

Irakasgai honen helburua Javako bildumak (Collections), egitura dinamikoak (List, ArrayList), lista ordenatuak eta egitura bereziak (Pilak eta Ilarak) sakonki ezagutzea eta erabiltzen ikastea da.

---

## 1. Objektuen bilduma

Javako bildumak (Collections) datu egitura dinamiko bat dira. Hauen ezaugarri nagusia metatzen diren datuak mota berdinekoak (edo mota bateragarrikoak) direla da.

- **Collection interfazea:** Javako `java.util` paketean lehenetsitako interfaze nagusia da, bilduma guztiak kudeatzeko oinarri gisa erabiltzen dena.
- **Framework-a:** Bildumak kudeatzeko Javak `Collections Framework` eskaintzen du (`java.util` eta `java.util.concurrent` paketeen bidez).

| Interfazea / Egitura | Deskribapena | Ezaugarri nagusiak |
| :--- | :--- | :--- |
| **List** | Datu egitura sekuentziala eta ordenatua. | Indize bidezko sarbidea, elementu bikoiztuak onartzen ditu. |
| **Set** | Elementu multzo ez-ordenatua. | Ezin dira elementu bikoiztuak sartu, ez dauka indize zuzenik. |
| **Queue** | Datuak sartzeko eta ateratzeko ilara egitura. | FIFO (First Input First Output) kudeaketa-eskema erabilgarria. |
| **Stack** | Lista mota berezia (pila). | LIFO (Last Input First Output) kudeaketa-eskema. |

> **Oharra:** Aurreko interfazeak `AbstractList`, `AbstractSet` eta `AbstractQueue` bezalako klase abstraktuen bidez ere egituratzen dira Javaren hierarkian.

---

## 2. Egitura dinamikoak. List, ArrayList

`ArrayList` klasea `List` interfazearen inplementaziorik erabilienetako bat da. Beharren arabera tamaina dinamikoki aldatzeko gaitasuna du.

- **Tamaina dinamikoa:** Array arruntetan ez bezala, `ArrayList` baten tamaina automatikoki hazten edo txikitzen da elementuak gehitu edo ezabatu ahala.
- **Klase Generikoak:** Generikoak (`<T>`) erabiltzen dira zerrendak edukiko duen datu mota zehazteko.
- **Inportazioa:** Klase hau erabiltzeko nezesarioa da `java.util.ArrayList` inportatzea.

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        // String motatako ArrayList bat sortzea
        ArrayList<String> arrayListString = new ArrayList<String>();

        // Mota bakunentzako Wrapper klaseak erabili behar dira (Integer, Double, Character, etab.)
        ArrayList<Integer> arrayListInteger = new ArrayList<Integer>();
    }
}
```

> **Oharra:** Ez badugu mota zehazten eremu generikoan (`ArrayList list = new ArrayList()`), `Object` motako elementuak gordeko dira. Kasu hau erabilgarria izan daiteke polimorfismoa aprobetxatu nahi denean.

---

## 3. Lista linealekin lanean. Sartu, bilatu eta ezabatu

Javak metodo multzo zabala eskaintzen du `ArrayList` objektuen edukia kudeatzeko eta eragiketak egiteko.

- **`add(elementu)`:** Elementu bat gehitzen du zerrendaren amaieran.
- **`add(index, elementu)`:** Elementu bat sartzen du zehaztutako posizioan.
- **`get(index)`:** Posizio jakin batean dagoen elementua bueltatzen du.
- **`set(index, elementu)`:** Posizio jakineko balioa ordezkatzen du berri bategatik.
- **`remove(index)` / `remove(object)`:** Elementua ezabatzen du indize bidez edo objektuaren erreferentzia bidez.
- **`contains(object)`:** Elementua zerrendan dagoen egiaztatzen du (`true`/`false`).
- **`indexOf(object)` / `lastIndexOf(object)`:** Elementuaren lehen edo azken agerpenaren indizea bueltatzen du.
- **`size()`:** Zerrendako elementu kopurua bueltatzen du.
- **`clear()`:** Zerrendako elementu guztiak ezabatzen ditu.
- **`isEmpty()`:** Zerrenda hutsik dagoen egiaztatzen du.

```java
ArrayList<String> zerrenda = new ArrayList<>();

// Elementuak gehitu
zerrenda.add("Java");
zerrenda.add("Python");
zerrenda.add(1, "C++"); // 1 posizioan sartu

// Elementuak irakurri eta aldatu
String lehenengoa = zerrenda.get(0);
zerrenda.set(2, "JavaScript");

// Bilaketa eta ezabaketa
boolean badago = zerrenda.contains("Java"); // true
zerrenda.remove("C++"); // Objektu bidez ezabatu
zerrenda.remove(0); // Indize bidez ezabatu
```

---

## 4. Lista linealak arakatzea

Lista baten elementu guztietatik igarotzeko (iteratzeko) hainbat bide daude Javan.

- **Oinarrizko `for` trakesa:** Indize bidez arakatzea `size()` metodoa muga gisa erabiliz.
- **`for-each` egitura:** Syntax laburragoa eta irakurgarriagoa bilduma osoa sekuentzialki arakatzeko.
- **`Iterator` interfazea:** Bilduma bat arakatzeko objektu berezia (`java.util.Iterator`), tamaina aurretik jakin gabe elementuak segurtasunez kentzeko edo iteratzeko egokia.

```java
import java.util.ArrayList;
import java.util.Iterator;

public class ArakatuExemploa {
    public static void main(String[] args) {
        ArrayList<String> arrayListString = new ArrayList<>();
        arrayListString.add("A");
        arrayListString.add("B");
        arrayListString.add("C");

        // 1. Oinarrizko for erabiliz
        for (int i = 0; i < arrayListString.size(); i++) {
            System.out.println(arrayListString.get(i));
        }

        // 2. For-each egitura erabiliz
        for (String katea : arrayListString) {
            System.out.println(katea);
        }

        // 3. Iterator erabiliz
        Iterator<String> it = arrayListString.iterator();
        while (it.hasNext()) {
            String s = it.next();
            System.out.println(s);
        }
    }
}
```

---

## 5. Lista ordenatuak

`ArrayList` baten dauden elementuak ordenatzeko `java.util.Collections` klaseak eskaintzen dituen tresnak erabiltzen dira.

- **Goranzko ordenazioa (`sort`):** `Collections.sort(lista)` erabiliz, elementuen orden naturala jarraituz (zenbakiak txikitik handira, kateak alfabetikoki).
- **Beheranzko ordenazioa (`Comparator.reverseOrder`):** `Collections.sort(lista, Collections.reverseOrder())` erabiliz.
- **Objektu pertsonalizatuen ordenazioa:** Objektu konplexuak konparatzeko `Comparator` interfazearen `compare` metodoa berridatzi (overriding) daiteke.

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;

public class OrdenatuExemploa {
    public static void main(String[] args) {
        ArrayList<String> katak = new ArrayList<>();
        katak.add("Zebra");
        katak.add("Ahuntza");
        katak.add("Lehoia");

        // Gorantz ordenatu (A-Z)
        Collections.sort(katak);

        // Beherantz ordenatu (Z-A)
        Comparator<String> konp = Collections.reverseOrder();
        Collections.sort(katak, konp);
    }
}
```

---

## 6. Ilarak eta Pilak (Queue eta Stack)

Egitura linealak kudeatzeko bi modu berezi dira, sartzeko eta ateratzeko ordenaren arabera definitzen direnak.

- **Ilara (Queue - FIFO):** *First Input, First Output*. Sartzen den lehen elementua ateratzen den lehena da (adibidez, sarrera salmentako ilara bat).
- **Pila (Stack - LIFO):** *Last Input, First Output*. Sartzen den azken elementua ateratzen den lehena da (adibidez, plater edo liburu pila bat).

| Egitura | Mota | Funtzionamendua | Javako erabilera nagusia |
| :--- | :--- | :--- | :--- |
| **Ilara** | FIFO | Lehenengoa sartzen -> Lehenengoa ateratzen | `Queue` interfazea / `LinkedList` edo custom class |
| **Pila** | LIFO | Azkenengoa sartzen -> Lehenengoa ateratzen | `Stack` klasea edo `ArrayList` bidez egokitua |

> **Oharra:** Javan, pila edo ilara pertsonalizatuak erraz sortu daitezke `ArrayList` klasetik herentzia (inheritance) erabiliz edo konposizio bidez metodoak egokituz (`push`, `pop`, `enqueue`, `dequeue`).