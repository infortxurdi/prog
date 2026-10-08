# 2. Gaia: Kontrol Egiturak

## 1. Blokea — Baldintzazko egiturak (if, if…else, if… else if… else)

**Helburua:** Baldintzazko egiturak (`if`, `if…else`, `if… else if… else`) erabiltzen ikastea, erabiltzaileak sartutako datuen arabera erabakiak hartzen dituzten programak sortzeko.

### 1.1 POSNEG
Egin `POSNEG` programa. Egin programa jakiteko erabiltzaileak sartu duen zenbakia positiboa edo negatiboa den. Horretarako eskatu erabiltzaileari sartzeko zenbaki oso bat eta sartzen duenean esan negatiboa edo positiboa den.

### 1.2 BALIOABS
Egin `BALIOABS` programa. Programa horrek, teklatutik zenbaki bat irakurri, eta beraren balio absolutua idatziko du pantailan.

### 1.3 BAKBIK
Egin `BAKBIK` programa. Programa horrek, teklatutik zenbaki bat irakurri, eta bakoitia edo bikoitia den idatziko du pantailan.

### 1.4 KALKUBEZ
Egin `KALKUBEZ` programa. Programa horrek kantitate bat irakurriko du teklatutik eta dagokion BEZa erakutsiko du pantailan: kantitate hori 20.000 baino handiagoa baldin bada, BEZa % 16 izango da; bestela, % 7.

### 1.5 MXN
Egin `MXN` programa. Programa horrek, teklatutik zenbaki bat irakurri, eta beraren karratua lortuko du. Karratua 100 baino handiagoa baldin bada, 100 kendu, eta pantailan aterako du; 100 baino txikiagoa baldin bada, aldiz, 100 arte zenbat falta dena aterako du pantailan.

### 1.6 TXIKIAGOHANDIAGO
Egin `TXIKIAGOHANDIAGO` programa. Programa horrek, teklatutik bi zenbaki irakurri, eta handiena idatziko du pantailan. Berdinak baldin badira, argi adierazi beharko du.

### 1.7 Gorputz-masaren Indizea (IMC)
Egin programa bat, zure gorputz-masaren indizea jakinda, zehazten duena zein tartetan dagoen. Horretarako eskatu erabiltzaileari sartzeko, altuera eta pisua.

**Formula:**
$$IMC = \frac{\text{Peso}}{\text{Altura}^2}$$

**Tarteak:**
* **18.5 edo gutxiago:** ARGALA
* **18.6 - 24.9:** ARRUNTA
* **25.0 - 29.9:** GEHIEGIZKO PISUA
* **30.0 edo gehiago:** LODIA

### 1.8 SOLDATARET
Egin `SOLDATARET` programa. Programa horrek teklatutik langile baten soldata irakurri, soldata horren araberako atxikipena kalkulatu, eta soldata garbia aterako du pantailan.

* Soldata < 1000.00, atxikipena: %10
* Soldata = 1000.00, atxikipena: %12
* Soldata > 1000.00, atxikipena: %14

### 1.9 SOLDATARET2
Egin `SOLDATARET2` programa. Programa horrek teklatutik langile baten soldata irakurri, soldata horren araberako atxikipena kalkulatu, eta soldata garbia aterako du pantailan.

* Soldata < 1000.00, atxikipena: %10
* Soldata = 1000.00, atxikipena: %12
* Soldata < 2000.00, atxikipena: %14
* Soldata = 2000.00, atxikipena: %16
* Soldata > 2000.00, atxikipena: %18

### 1.10 SEGUNDO
Egin `SEGUNDO` programa. Programa horrek teklatutik ordua irakurri, eta gehitu egingo dio segundo bat.

**Adibidea:**
* Sartu ordua: `5`
* Sartu minutuak: `43`
* Sartu segundoak: `59`
* *Hurrengo segundoan:* 5 ordu 44 minutu 0 segundo.

### 1.11 TABNOTAK
Egin `TABNOTAK` programaren ordinograma, sasikodea eta programazioa. Programa horrek, teklatutik ikasle baten nota irakurri, eta, letraz aterako du nota, honako taula honen arabera:

| NOTA | KALIFIKAZIOA |
| :--- | :--- |
| $\ge 0$ eta $<3$ | OSO GUTXI |
| $\ge 3$ eta $<5$ | GUTXI |
| $\ge 5$ eta $<6$ | NAHIKOA |
| $\ge 6$ eta $<7$ | ONDO |
| $\ge 7$ eta $<9$ | OSO ONDO |
| $\ge 9$ eta $\le 10$ | BIKAIN |

### 1.12 GAUZAK
Egin `GAUZAK` programa. Programa horrek, kopurua eta alearen prezioa eskatu, eta kopuru horren araberako beherapena kalkulatuko du.

**Kantitatea / Beherapena:**
* $> 100$: %40
* $> 25$ eta $\le 100$: %20
* $> 10$ eta $\le 25$: %10
* $\le 10$: %0

**Adibidea:**
```text
Sartu kopurua: 55
Sartu alearen prezioa: 3.5
Beherapena: %20.0
Ordaindu beharrekoa: 154.0
```

### 1.13 NOTABAL
Egin `NOTABAL` programa. Programa horrek, nota bat hartu, eta zuzena den ala ez esango du. Zuzena izateko, 0 eta 10 artean egon behar du notak.

### 1.14 BISURTE
Egin `BISURTE` programa. Programa horrek, teklatutik urtea eskatu, eta bisurtea den ala ez esango du.

### 1.15 EK2MAILAEK
Egin `EK2MAILAEK` programa. Programa horrek, bigarren mailako ekuazio baten koefizienteak hartu ($a$, $b$ eta $c$-ren balioak), eta ebatzi egingo du ekuazioa. Erro konplexuak baldin baditu, “Erro konplexuak” mezua agertuko da.

**Formula:**
$$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

*Erroa kalkulatzeko:* `Math.sqrt(numero);`

**Probak egin:**
* $a=1, b=-5, c=6 \implies x1=3.0, x2=2.0$
* $a=1, b=2, c=5 \implies \text{erro konplexuak}$
* $a=0, b=3, c=6 \implies \text{ezin da ebatzi}$

### 1.16 HANDI3ZNBK
Egin `HANDI3ZNBK` programa. Programa horrek, hiru zenbaki eskatu, eta handiena –edo handienak– zein den esango du.

### 1.17 TXIKITIKHANDIRA
Egin `TXIKITIKHANDIRA` programa, zenbakiak ordenatzen dituena txikitik handira. Hau egiteko, eskatu sartzeko 3 zenbaki eta sartuta daudenean atera pantailatik zenbakiak ordenaturik.

### 1.18 MENU
Egin `MENU` programaren programazioa. Programa horrek, teklatutik bi zenbaki eskatu, pantailan beheko menua atera, eta aukeraren araberako eragiketa egingo du.

1. Batu
2. Kendu
3. Biderkatu
4. Zatitu
5. Ondarra

---

## 2. Blokea — Switch… case

**Helburua:** Baldintzazko egiturak (`switch...case`) erabiltzen ikastea, erabiltzaileak sartutako datuen arabera erabakiak hartzen dituzten programak sortzeko.

### 2.1 MENUAEGUNAK
Egin `MENUAEGUNAK` ordinograma, sasikodea eta programazioa. Programa horrek, teklatutik bi karaktere eskatu, eta asteko eguna idatziko du pantailan:
* `AL`: Astelehena
* `AA`: Asteartea
* `AZ`: Asteazkena
* `OG`: Osteguna
* `OL`: Ostirala
* `LA`: Larunbata
* `IG`: Igandea
* *Beste edozein karaktere:* Errorea.

### 2.2 MENUAHILABETEAK
Egin `MENUAHILABETEAK` programa. Programa horrek, teklatutik hilabete baten izena eskatu, eta hilabete horren zenbakia idatziko du pantailan.

### 2.3 DIBISAK
Sortu `DIBISAK` programa dibisen aldaketa kalkulatzeko. Hau da, erabiltzaileak sartu behar du € kantitate bat eta gero menu batean aukeratu behar da (`a` = DOLAR, `b` = LIBRA, `c` = YEN) kalkulatu nahi duen. Aukeratu denean moneta bat programak esan behar du sartutako euroak zenbat libra, dolar edo yen diren.

* 1 EURO $\rightarrow$ 1.21 DOLAR
* 1 EURO $\rightarrow$ 0.88 LIBRA
* 1 EURO $\rightarrow$ 127.10 YEN

### 2.4 Gasolindegia
Egin programa bat gasolindegi batentzako. Eskatu erabiltzaileari zenbat litro gasolina bota nahi duen eta aukeratzeko ze motatako gasolina (`Diesel e+`, `Diesel 10e+`, `Gasolina 98`, `Gasolina 95`).

`Diesel e+` eta `Gasolina 98` deskontu batzuk dituzte:
* **Diesel e+:** 35 litro edo gehiago erosten dituen erabiltzaileak, %8aren deskontua izango du.
* **Gasolina 98:** 25 litro edo gehiago erosten dituen erabiltzaileak %10aren deskontua izango du.

**Prezioak:**
* 1 litro Diesel e+: 1.139 euro.
* 1 litro Diesel 10e+: 1.195 euro.
* 1 litro Gasolina 98: 1.349 euro.
* 1 litro Gasolina 95: 1.219 euro.

---

## 3. Blokea — Egitura errepikakorrak

### 3.1 ZNBK100
Egin `ZNBK100` programa. Klase horrek lehen 100 zenbaki osoak jarriko ditu pantailan. *(Egitura guztiak)*

### 3.2 AURKEZTUZNBKW
Egin `AURKEZTUZNBKW` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta 1etik zenbaki horretara bitarteko zenbaki guztiak idatziko ditu pantailan. *(Egitura guztiak)*

### 3.3 AURKEZTUBIKW
Egin `AURKEZTUBIKW` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta 0tik zenbaki horretara bitarteko zenbaki bikoiti guztiak idatziko ditu pantailan.

### 3.4 AURKEZTUZNBKDW
Egin `AURKEZTUZNBKDW` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta zenbaki horretatik 1era bitarteko zenbaki guztiak idatziko ditu pantailan.

### 3.5 AURKEZTUBIKBW
*(GELAN ZUZENDU GABE)* Egin `AURKEZTUBIKBW` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta zenbaki horretatik 0ra bitarteko zenbaki bikoiti guztiak idatziko ditu pantailan. Erabili `While`.

### 3.6 BATUZNBKW (While)
Egin `BATUZNBKW` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta 0tik zenbaki horretara bitarteko zenbaki guztien batura idatziko du pantailan. Erabili `While`.

### 3.7 BATUZNBKW (For)
Egin `BATUZNBKW` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta 0tik zenbaki horretara bitarteko zenbaki guztien batura idatziko du pantailan. Erabili `For`.

### 3.8 BATUZNBK (Do…While)
*(Pendiente zuzentzeko)* Egin `BATUZNBK` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta 0tik zenbaki horretara bitarteko zenbaki guztien batura idatziko du pantailan. Zenbakia negatiboa baldin bada, eskatzen jarraituko du positiboa jaso arte. Erabili `Do…While`.

### 3.9 BATUBIKOITIW
Egin `BATUBIKOITIW` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta 0tik zenbaki horretara bitarteko zenbaki bikoiti guztien batura idatziko du pantailan. Erabili `Do…While`.

### 3.10 BATUBIKOITIF
Egin `BATUBIKOITIF` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta 0tik zenbaki horretara bitarteko zenbaki bikoiti guztien batura idatziko du pantailan. Erabili `For`.

### 3.11 BATUBIKBW
Egin `BATUBIKBW` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta zenbaki horretatik 0ra bitarteko zenbaki bikoiti guztien batura idatziko du pantailan. Erabili `While`.

### 3.12 MULTAULA
Egin `MULTAULA` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta beraren biderkatzeko taula aurkeztuko du.

**Adibidea:**
```text
Sartu zenbakia: 3
3 x 1 = 3
3 x 2 = 6
…
3 x 9 = 27
```

### 3.13 MULTAULAW
Egin `MULTAULAW` klasea. Klase horrek, lehenagokoak bezala egingo du, baina, oraingoan, prozesua errepikatuko du 0 zenbakia sartu arte.

### 3.14 FAKTORIALA
Egin `FAKTORIALA` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta beraren faktoriala kalkulatuko du.

**Adibidea:**
$$5! = 5 \times 4 \times 3 \times 2 \times 1 = 120$$

### 3.15 FIBONACCI
Egin `FIBONACCI` klasea. Klase horrek, teklatutik N zenbaki bat eskatu, eta, Fibonacci-ren segida ($0, 1, 1, 2, 3, 5, 8\dots$) kontuan hartuz, segida horretako lehen N gaiak emango dizkigu.

* $f(0) = 0$
* $f(1) = 1$
* $n > 2$ denean: $f(n) = f(n-1) + f(n-2)$

### 3.16 MAXIMINI
Egin `MAXIMINI` klasea. Klase horrek zenbakiak eskatuko ditu teklatutik, banan-banan, zenbaki bat negatiboa izan arte. Orduan, zenbaki handiena eta txikiena aurkeztuko ditu pantailan –negatiboa kontuan hartu gabe–.

### 3.17 ZNBKLEHENA
Egin `ZNBKLEHENA` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta zenbaki lehena den esango du.

### 3.18 Zenbakia asmatu (Jokoa)
Sortu programa bat non ordenagailuak zenbaki bat pentsatuko duen (0 eta 100 artean) eta erabiltzaileak ordenagailuak pentsatutako zenbakia asmatu behar duen. Programak adierazi behar du zenbakia sartutakoa baino txikiagoa edo handiagoa den. Horretarako, erabiltzaileak bakarrik izango ditu 7 aukera. 7 Aukera egin eta gero ez badu asmatzen **GAME OVER** esan behar du!

**Oharra:** ordenagailuak berak pentsatzeko aleatorioki zenbaki bat erabiliko dugu `Random` funtzioa:
```java
import java.util.Random;

Random rnd = new Random();
int zbkAleatorioa = rnd.nextInt(100) + 1;
```

### 3.19 ZNBKLEHENABAKOITI
Egin `ZNBKLEHENABAKOITI` klasea. Klase horrek, teklatutik zenbaki bat eskatu, zenbaki hori zenbaki bakoitiez zatigarria den esango du.

### 3.20 MULTZNBK100
Egin `MULTZNBK100` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta zenbaki horren lehen ehun multiploak aterako ditu pantailan.

### 3.21 LEHENA100
Egin `LEHENA100` klasea. Klase horrek lehen ehun zenbaki lehenak idatziko ditu pantailan.

### 3.22 ZIFRAK
Egin `ZIFRAK` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta zenbaki horren zifrak idatziko ditu pantailan, banan-banan (alderantziz).

**Adibidea:**
```text
Sartu zenbaki bat: 698
Zenbakia alderantziz: 896
```

---

*(HEMENDIK AURRERA EGIN GABE)*

### 3.23 Expendedor
Egin `Expendedor` Java klasea, bezeroari eurotan duen saldoa teklatutik irakurtzen diona. Ondoren, menu bat erakutsiko da, honako produktuetako bat aukeratzeko:
* `1A`. Kafea (0,43 €)
* `2E`. Freskagarria (1,11 €)
* `4C`. Ura (0,36 €)

Saldoa aukeratutako produktuaren prezioa baino handiagoa edo berdina bada, *"Hemen duzu zure produktua. Eskerrik asko"* mezua agertuko da, eta gainerakoa itzuliko zaio. Gainerakoa osatzen duten txanpon kopuruak adierazi behar dira:
* 2 €
* 1 €
* 50 zentimo
* 20 zentimo
* 10 zentimo
* 5 zentimo
* 2 zentimo
* 1 zentimo

Saldoa produktuaren prezioa baino txikiagoa bada, *"Saldo nahikorik ez"* mezua erakutsiko da eta sartutako saldo osoa itzuliko zaio.
Aukera oker bat sartzen bada, *"Aukera okerra"* mezua erakutsiko da eta sartutako saldo osoa itzuliko zaio.

### 3.24 ERROMAZNBK
Egin `ERROMAZNBK` klasea. Klase horrek, teklatutik 0 eta 999ren arteko zenbaki bat eskatu, eta zenbaki erromatarretan emango du.

### 3.25 MEGABYTE
Egin `MEGABYTE` klasea. Klase horrek, teklatutik zenbaki bat eskatu (B-etan adierazita), eta MB-etan eta kB-etan idatziko du pantailan.

### 3.26 ZNBKZIFRAK
Egin `ZNBKZIFRAK` klasea. Klase horrek zenbaki bat osatzeko zifrak eskatuko ditu. Zifra negatiboa denean, pantailan zenbakia aurkeztu, eta amaitu egingo da klasea.

### 3.27 ZNBKMULT
Egin `ZNBKMULT` klasea. Klase horrek teklatutik zenbaki bat ($N$) eta multiploen kopurua ($M$) eskatuko ditu. Ondoren, klaseak $N$ zenbakiaren lehenengo $M$ multiploak idatziko ditu pantailan.

### 3.28 FAKTONEG
Egin `FAKTONEG` klasea. Klase horrek zenbaki bat eskatuko du. Zenbakia positiboa baldin bada, beraren faktoriala kalkulatuko du zuzenean; negatiboa baldin bada, berriz, zeinua aldatu, eta, ondoren, faktoriala kalkulatuko du.

### 3.29 LEHENAKUB
Egin `LEHENAKUB` klasea. Klase horrek teklatutik zenbakiak eskatuko ditu banan-banan, zenbaki bat negatiboa izan arte. Zenbakia bakoitia baldin bada, lehena denetz aztertuko du; bikoitia baldin bada, berriz, beraren kuboa kalkulatu eta pantailan idatziko du.

### 3.30 ZNBKTARTE
Egin `ZNBKTARTE` klasea. Klase horrek, teklatutik bi zenbaki eskatu, eta euren arteko zenbaki oso guztiak idatziko ditu pantailan.

### 3.31 TARTEBATU
Egin `TARTEBATU` klasea. Klase horrek, teklatutik bi zenbaki eskatu, eta euren arteko zenbaki oso guztien batura idatziko du pantailan.

### 3.32 N10BIKOITI
Egin `N10BIKOITI` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta zenbaki horren osteko hamar bikoitiak idatziko ditu pantailan.

### 3.33 SOLDATAGARBIA
Egin `SOLDATAGARBIA` klasea. Klase horrek urteko soldata gordinak irakurriko ditu, banan-banan, soldata negatibo bat jaso arte. Soldata 10.000 baino handiagoa baldin bada, gainditutako 150ero, %1eko beherapena ezarriko zaio –gehienez %56 izan daiteke beherapena–.

**Adibidea:**
Soldata = 1.330,00 € $\rightarrow$ deskontua = %3

### 3.34 ERRONEW
Egin `ERRONEW` klasea. Klase horrek zenbaki baten erro karratua ebatziko du Newtonen metodoarekin. Errore-tasa jakin bat ($0.000000001$) izango dugu. Pauso bakoitzean kalkulatutako erroari aurreko pausoan kalkulatutakoa kendu behar diogu. Kendura hori errore-tasa baino txikiagoa ez den bitartean, formula hau erabiliko dugu:

$$\text{Erroa} = \frac{\frac{\text{zenbakia}}{\text{aurrekoerroa}} + \text{aurrekoerroa}}{2}$$

### 3.35 ERRONEWT
Egin `ERRONEWT` klasea. Klase horrek aurreko `ERRONEW` klasea hobetu behar du: errore-tasa teklatutik eskatuko du, eta `aurrekoerroa`k, hasieran, 1 balioa izango du.

### 3.36 ERRONEWN
Eratu `ERRONEWN` klasea. Klase horrek `ERRONEW` hobetzen du: hainbat zenbakiren erro karratua ebatzi ahal izango du, eta jasotako zenbakia 0 edo negatiboa denean amaituko da klasea.

### 3.37 HIPOTENUSA
Egin `HIPOTENUSA` klasea. Klase horrek, triangelu baten bi katetoak irakurri, eta hipotenusa kalkulatuko du. Erro karratua kalkulatzeko, Newtonen metodoa erabiliko du.

### 3.38 PITAGORAS
Egin `PITAGORAS` klasea. Klase horrek Pitagoras-en teorema betetzen duten $X$, $Y$ eta $Z$ zenbakiak kalkulatuko ditu. Kontuan hartu: $Y$-ren balioa $X$-rena baino handiagoa da, $Z$ ez da 50 baino handiagoa izango, eta balioek adierazpen hau beteko dute:
$$Z^2 = X^2 + Y^2$$

### 3.39 TRIAFIWA
Egin `TRIAFIWA` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta triangelu bat osatuko du. Erabili `While`.

**Adibidea:**
```text
Sartu zenbakia: 5

1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```

### 3.40 TRIAFIFA
Egin `TRIAFIFA` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta triangelu bat osatuko du. Erabili `For`.

**Adibidea:**
```text
Sartu zenbakia: 5

1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```

### 3.41 TRIAFIWB
Egin `TRIAFIWB` klasea. Klase horrek, teklatutik zenbaki bat eskatu, eta triangelu bat osatuko du. Erabili `While`.

**Adibidea:**
```text
Sartu zenbakia: 5

5 5 5 5 5
4 4 4 4
3 3 3
2 2
1
```