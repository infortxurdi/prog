# 2. UD: Oinarrizko Kontrol Egiturak Javan

Dokumentu honek gai-zerrendako aurkezpenetan azaltzen diren **eragileak**, **baldintzazko egiturak** eta **egitura errepikakorrak (bukleak)** biltzen ditu, azalpen eta adibide guztiekin.

---

## 1. Eragileak Javan

Eragileak adierazpen boolearrak eraikitzeko erabiltzen dira, eta hauen bidez kontrol-egituren baldintzak ebaluatzen dira.

### 1.1 Eragile Erlazionalak

Bi balio alderatzeko erabiltzen dira. Ebaluazioaren emaitza beti izaten da balio boolear bat (`true` edo `false`).

| Eragilea | Azalpena | Prezentzia Ordenea |
| :--- | :--- | :--- |
| `<` | Txikiagoa | 5 |
| `>` | Handiagoa | 5 |
| `<=` | Txikiagoa edo berdina | 5 |
| `>=` | Handiagoa edo berdina | 5 |
| `==` | Berdina | 6 |
| `!=` | Ezberdina | 6 |

### 1.2 Eragile Logikoak

Adierazpen boolear bat baino gehiago konbinatzeko erabiltzen dira.

| Eragilea | Azalpena | Signifikatua | Prezentzia Ordenea |
| :--- | :--- | :--- | :--- |
| `!` | *Not* (ez) | Ezespena (balioa alderantzikatzen du) | 1 |
| `&&` | *And* (eta) | Konjuntzioa (baldintza guztiak bete behar dira) | 10 |
| `||` | *Or* (edo) | Disjuntzioa (gutxienez baldintza bat bete behar da) | 11 |

---

## 2. Baldintzazko Egiturak

Baldintzazko egiturak programaren exekuzio-fluxua aldatzeko erabiltzen dira, baldintza bat egia ($true$) edo gezurra ($false$) den ebaluatuz.

### 2.1 `if` Sententzia

Kode-bloke bat exekutatzen da **soilik** baldintza betetzen bada ($true$).

> **Oharra:** Exekutatu behar den sententzia lerro bakarra bada, ez dira ezarri behar jarraian `{}` giltzak (aukerakoak dira).

#### Sintaxi orokorra:

```java
if (baldintza) {
    // Baiezkoaren kodea (true denean)
}
```

#### 1. Adibidea (`if` bakuna):

```java
int matematikak = 4;

if (matematikak >= 5) {
    System.out.println("Matematika gainditu duzu.");
}
```

---

### 2.2 `if ... else` Sententzia

Baldintza betetzen ez denean ($false$) exekutatuko den ordezko kode-bloke bat definitzen du.

#### Sintaxi orokorra:

```java
if (baldintza) {
    // Baiezkoaren kodea (true denean)
} else {
    // Ezezkoaren kodea (false denean)
}
```

#### 2. Adibidea (`if ... else`):

```java
int matematikak = 4;

if (matematikak >= 5) {
    System.out.println("Matematika gainditu duzu.");
} else {
    System.out.println("Ez duzu matematika gainditu.");
}
```

---

### 2.3 `if ... else if ... else` Sententzia

Hainbat baldintza jarraian ebaluatzeko erabiltzen da, alternatiba ugari daudenean.

#### Sintaxi orokorra:

```java
if (baldintza1) {
    // baldintza1 TRUE denean
} else if (baldintza2) {
    // baldintza2 TRUE denean
} else {
    // Aurreko baldintza guztiak FALSE direnean
}
```

#### 3. Adibidea (`if ... else if ... else`):

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

### 2.4 `switch` Sententzia

`IF` sententziaren ordezko egitura bat da, kode garbiagoa eta errazagoa lortzeko. Erabiltzen da aldagai edo espresio batek hainbat balio posibleren artean hautatu behar duenean.

* **Gako-hitzak**:
  * `switch`: Aldagaiaren balioa aztertzen hasten da.
  * `case`: Espresioaren balio posible bakoitza ebaluatzen du.
  * `break`: Sententzia-bloke bakoitzaren amaiera adierazten du, kasu batetik hurrengora igaro gabe exekuzioa geldituz.
  * `default`: Aurreko `case` balioetatik bat bera ere betetzen ez denean exekutatzen da.

#### Sintaxi orokorra:

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

#### 1. Adibidea (`switch` kasu independenteekin):

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

#### 2. Adibidea (`switch` kasuak taldekatuz):

Kasu ezberdinek agindu berdina exekutatu behar dutenean, taldekatu daitezke:

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
    case 5: // 4 eta 5 kasuek kode bera exekutatzen dute
        System.out.println("Diploma");
        break;
    default:
        System.out.println("Saririk gabe");
        break;
}
```

---

## 3. Egitura Errepikakorrak edo Bukleak

Bukleak erabiltzen dira sententzia-multzo bat behin edo gehiagotan exekutatu behar denean (0, 1 edo gehiagotan), espresio boolear baten arabera.

> **Kontuz! Bukle amaigabeak (Infinite Loops)**
> 
> Espresio booleanoa beti egiazkoa ($true$) denean gertatzen da. Sententziak etengabe exekutatzen dira eta programa "zintzilik" geratzen da.

### 3.1 `while` Buklea

Sententzia-multzo bat hainbat aldiz exekutatzeko erabiltzen da ($0$ **aldiz edo gehiagotan**).

* Konprobaketa **hasieran** egiten da.
* Baldintza hasieratik gezurra ($false$) bada, barruko aginduak ez dira behin ere exekutatuko.

#### Sintaxia:

```java
while (boolexp) {
    sentencias;
}
```

---

### 3.2 `do ... while` Buklea

`While` buklearen antzeko egitura du, baina konprobaketa **bukaeran** egiten da.

* Egitura honek ziurtatzen du sententzia-multzoa **gutxienez behin** ($\ge 1$) exekutatuko dela.

#### Sintaxia:

```java
do {
    sentencias;
} while (expresion);
```

---

### 3.3 `for` Buklea

Sententzia-multzo bat **kopuru finko eta jakin bat aldiz** exekutatu behar denean erabiltzen da.

Trikimailua hiru zatitan banatzen da:
1. **Hasieratzea (inicialización)**: Kontagailu-aldagaiari hasierako balioa ematen zaio.
2. **Espresio boolearra (boolexp)**: Bukleak jarraituko duen ala ez erabakitzen duen baldintza.
3. **Inkrementua (incremento)**: Iterazio bakoitzaren amaieran kontagailua eguneratzen du.

#### Sintaxia:

```java
for (inicializacion; boolexpresion; incremento) {
    sentencias;
}
```

---

## Bukleen Arteko Konparaketa Egitura

| Buklea | Ebaluazio unea | Gutxieneko exekuzioak | Erabilera nagusia |
| :--- | :--- | :--- | :--- |
| **`while`** | Hasieran | $0$ | Ez dakigunean kodea behin ere exekutatu beharko den. |
| **`do ... while`** | Bukaeran | $1$ | Gutxienez behin exekutatu behar denean (adib. menuak erakusteko edo datuak balioztatzeko). |
| **`for`** | Hasieran | $0$ | Errepikapen kopurua finkoa eta aldez aurretik ezaguna denean. |