# Teoria - 5. Gaia: Objektuetara Bideratutako Programazioa Java-n

Dokumentu honen helburua Java lengoaian Objektuetara Bideratutako Programazioaren (OBP) oinarrizko kontzeptu teorigarriak azaltzea da, klaseen definizioa, atributuak, metodoak, kapsulazioa, eraikitzaileak eta objektuen arteko konposizioa era egituratuan aztertuz.

---

## 1. Objektuetara Bideratutako Programazioaren Oinarriak (OBP)

Objektuetara Bideratutako Programazioa (OBP) softwarea diseinatzeko paradigma bat da, non programa elkarrekin komunikatzen diren "objektuen" bilduma gisa egituratzen den.

- **Klasea (Class):** Objektuak sortzeko erabilitako molde edo txantiloia da. Klaseak bere barnean definitzen ditu objektuek izango dituzten ezaugarriak (atributuak) eta egin ditzaketen eragiketak (metodoak).
- **Objektua (Object):** Klase baten instantzia zehatz bat da, exekuzio-garaian memorian leku bat hartzen duena eta berezko egoera duena.
- **Atributuak (State/Attributes):** Objektu baten ezaugarri edo propietateak gordetzen dituzten aldagaiak dira.
- **Metodoak (Behavior/Methods):** Objektuak burutu ditzakeen ekintzak edo eragiketak definitzen dituzten funtzioak dira.

| Ezaugarria | Klasea | Objektua |
| :--- | :--- | :--- |
| **Definizioa** | Datu-mota pertsonalizatuaren molde edo abstraktua. | Memorian instantziatutako elementu zehatza. |
| **Garrantzia** | Ez du memorian espaziorik hartzen (ez bada statiko gisa). | Memorian espazioa hartzen du bere egoera gordetzeko. |
| **Adibidea** | `Taxi`, `Pertsona`, `Kotxea`. | `taxi1` (`BI-1234-AB`), `pertsona1` (`Jon`). |

---

## 2. Kapsulazioa eta Ikusgarritasun Eraldatzaileak

Kapsulazioa OBPren oinarrizko zutabe bat da. Horren bidez, objektu baten barne-aldagaiak kanpoko sarbide ez-baimenduetatik babesten dira, datuen osotasuna bermatzeko.

- **Kapsulazioa:** Objektuaren barne-egitura eta logika izkutatzea da, kanpoko erabilera publikorako interfaze bat bakarrik eskainiz.
- **Sarbide-aldatzaileak (Access Modifiers):** Atributu eta metodoen ikusgarritasun-maila mugatzeko hitz gakoak dira.
- **Getter metodoak (`get`):** Atributu pribatu baten uneko balioa irakurtzeko eta itzultzeko erabiltzen diren metodo publikoak.
- **Setter metodoak (`set`):** Atributu pribatu baten balioa ezartzeko edo aldatzeko erabiltzen diren metodo publikoak (balidazioak barne hartu ditzakete).

| Modifikatzailea | Klase Berean | Pakete Berean | Azpiklaseetan | Kanpotik (Guztientzat) |
| :--- | :---: | :---: | :---: | :---: |
| `private` | **Bai** | Ez | Ez | Ez |
| *(Default)* | **Bai** | **Bai** | Ez | Ez |
| `protected` | **Bai** | **Bai** | **Bai** | Ez |
| `public` | **Bai** | **Bai** | **Bai** | **Bai** |

> **Oharra:** Kapsulazio printzipioa betetzeko, klase baten atributu guztiak `private` gisa deklaratzea gomendatzen da, eta horietara sartzeko `public` diren getter/setter metodoak eskaintzea.

```java
public class Taxi {
    // Atributu pribatuak (Kapsulazioa)
    private String matrikula;
    private String udalerria;
    private int motoreMota; // 0=Ezezaguna, 1=Diesela, 2=Gasolina

    // Setter metodoa balioak ezartzeko
    public void setMatrikula(String matrikula) {
        this.matrikula = matrikula;
    }

    // Getter metodoa balioak lortzeko
    public String getMatrikula() {
        return this.matrikula;
    }

    public void setMotoreMota(int motoreMota) {
        if (motoreMota >= 0 && motoreMota <= 2) {
            this.motoreMota = motoreMota;
        } else {
            this.motoreMota = 0; // Lehenetsitako balioa balio okerra bada
        }
    }

    public int getMotoreMota() {
        return this.motoreMota;
    }
}
```

---

## 3. Eraikitzaileak (Constructors) eta Instantziazioa

Eraikitzailea objektu bat sortzen (`new` eragilearekin) eta memorian partekatzen den unean automatikoki exekutatzen den metodo berezi bat da.

- **Eraikitzaile Lehenetsia (Default Constructor):** Argumenturik jasotzen ez duen eraikitzailea da. Gelaxkak eta atributuak lehenetsitako balioekin hasieratzen ditu.
- **Eraikitzaile Parameterizatua:** Objektua sortzean balio zehatzak jasotzen dituen eraikitzailea.
- **Eraikitzaileen Gainkarga (Overloading):** Klase berak eraikitzaile bat baino gehiago izateko gaitasuna, baldin eta parametro zerrenda (kopurua edo mota) desberdina bada.
- **`this` hitz gakoa:** Uneko instantziari erreferentzia egiten dion erakuslea da. Atributuak eta tokiko aldagaiak izen bera dutenean bereizteko erabiltzen da.

```java
public class Pertsona {
    private String izena;
    private int adina;
    private boolean ezkondua;

    // 1. Lehenetsitako eraikitzailea
    public Pertsona() {
        this.izena = "";
        this.adina = 0;
        this.ezkondua = false;
    }

    // 2. Eraikitzaile parameterizatua
    public Pertsona(String izena, int adina, boolean ezkondua) {
        this.izena = izena;
        this.adina = adina;
        this.ezkondua = ezkondua;
    }
}
```

> **Oharra:** Eskuz eraikitzaile parameterizatu bat idazten denean, Java-k ez du automatikoki lehenetsitako eraikitzailea sortzen. Beharrezkoa izanez gero, explicitoki definitu behar da.

---

## 4. Egoera eta Jokabidea: Metodoak, Balidazioak eta Konstanteak

Objektu batek bere barne-egoera aldatu dezake metodoen bidez, eta negozio-logika konplexua ezarri daiteke balidazio zein laguntza-metodo pribatuen bidez.

- **Instantzia-metodoak:** Objektu zehatz baten egoerarekin lan egiten duten metodoak dira (adib. `bizkortu()`, `geldotu()`).
- **Barne-metodo pribatuak (Helper Methods):** Kanpotik ikusgai ez dauden eta klase barneko logikarako soilik erabiltzen diren metodoak (adib. `sexuaEgiaztatu()`, `sortuNAN()`).
- **Konstanteak (`final static`):** Exekuzio osoan zehar aldatzen ez diren balioak (adib. `SEXUA_LEHENETSIA = 'E'`).
- **`toString()` metodoa:** Objektuaren barne-egoeraren (atributuen balioen) testu-adierazpen bat String formatuan itzultzeko erabiltzen den metodoa.

| Mota Primitiboa / Mota | Lehenetsitako Balioa |
| :--- | :--- |
| `int`, `byte`, `short`, `long` | `0` |
| `float`, `double` | `0.0` |
| `boolean` | `false` |
| `char` | `'\u0000'` |
| Erreferentzia-motak (`String`, Objektuak) | `null` |

```java
public class Kotxea {
    private int abiadura;

    public Kotxea() {
        this.abiadura = 0;
    }

    public int getAbiadura() {
        return this.abiadura;
    }

    public void bizkortu(int gehiago) {
        if (gehiago > 0) {
            this.abiadura += gehiago;
        }
    }

    public void geldotu(int gutxiago) {
        if (gutxiago > 0) {
            this.abiadura -= gutxiago;
            if (this.abiadura < 0) {
                this.abiadura = 0; // Abiadura ez da inoiz negatiboa izango
            }
        }
    }

    @Override
    public String toString() {
        return "Kotxea [Abiadura: " + this.abiadura + " km/h]";
    }
}
```

---

## 5. Objektuen Arteko Erlazioak: Konposizioa eta Agregazioa

Programazio egituratuan software konplexua eraikitzeko, klase ezberdinetako objektuak elkartu eta konbinatu daitezke.

- **Konposizioa ("Batez osatuta dago" / HAS-A):** Klase batek beste klase batzuetako objektuak bere atributu gisa dituenean gertatzen den erlazioa da.
- **Modulartasuna:** Problemak azpi-arazo txikiagotan banatzeko gaitasuna (adib. Data eta Ordua klase independenteak sortzea, ondoreraz Azterketa klase baten barruan erabiltzeko).

```java
// Data klasea
public class Data {
    private int eguna;
    private int hilabetea;
    private int urtea;

    public Data(int eguna, int hilabetea, int urtea) {
        this.eguna = eguna;
        this.hilabetea = hilabetea;
        this.urtea = urtea;
    }

    @Override
    public String toString() {
        return String.format("%02d/%02d/%04d", eguna, hilabetea, urtea);
    }
}

// Ordua klasea
public class Ordua {
    private int ordua;
    private int minutua;

    public Ordua(int ordua, int minutua) {
        this.ordua = ordua;
        this.minutua = minutua;
    }

    @Override
    public String toString() {
        return String.format("%02d:%02d", ordua, minutua);
    }
}

// Azterketa klasea (Konposizioa: Data eta Ordua klaseak barne hartzen ditu)
public class Azterketa {
    private String ikasgaia;
    private String gela;
    private Data data;
    private Ordua ordua;

    public Azterketa(String ikasgaia, String gela, Data data, Ordua ordua) {
        this.ikasgaia = ikasgaia;
        this.gela = gela;
        this.data = data;
        this.ordua = ordua;
    }

    @Override
    public String toString() {
        return ikasgaia + "\t" + gela + "\t" + data.toString() + "\t" + ordua.toString();
    }
}
```

> **Oharra:** Konposizioari esker, `Data` eta `Ordua` bezalako klaseak sistema osoan berrerabili daitezke (adib. azterketetan, hitzorduetan edo egutegietan), kodea bikoiztu gabe.

---

## 6. Objektuen Bildumak eta Erabiltzailearen Interakzioa

Aplikazio errealetan, objektu anitz kudeatzeko array-ak edo bildumak erabiltzen dira, menuen eta balidazio-bucleen bidez kontrolatuta.

- **Objektu-Array-ak:** Mota bereko hainbat objektu-erreferentzia ordenatuta gordetzen dituzten egiturak (adib. `Ikasle[] ikasleak = new Ikasle[kopurua];`).
- **Datuen Balidazioa:** Erabiltzaileak sartutako datuak mugen barruan daudela ziurtatzea objektua sortu edo eguneratu aurretik.

```java
public class IkasleenKudeaketa {
    public static void erakutsiMenu() {
        System.out.println("\n--- MENU NAGUSIA ---");
        System.out.println("1.- Ikasleen datuak kargatzea");
        System.out.println("2.- Datuak prozesatzea");
        System.out.println("3.- Ikasleen datuak erakustea");
        System.out.println("4.- Ikasle baten datuak erakustea");
        System.out.println("0.- Amaiera");
    }
}
```