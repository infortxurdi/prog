# Oinarrizko Programazioa — 1. Gaia: Ariketak

---

## 1. Blokea — Pantailaratzea (`System.out`)

**Helburua:** `System.out.println()` eta `System.out.print()` erabiltzea ondo menperatzea, oraindik daturik irakurri gabe.

1. Egin `HolaMundua` klasea. Programak `"Kaixo mundua!"` mezua aterako du pantailan.
2. Egin `AurkezpenaKlasea`. Programak, lerroz lerro, zure izena, zure ikastetxea eta zure taldearen izena aterako ditu pantailan (hiru `println` desberdin erabiliz).
3. Egin `PrintVsPrintln` klasea. Erabili `print()` lau aldiz eta `println()` bat, ondorioztatzeko zein den bien arteko aldea (kurtsorearen lerro-jauzia).

> ➔ **Oharra:** Bloke honetan ez dago daturik irakurtzen — helburua da kodea idatzi, konpilatu eta exekutatzeko erritmoa hartzea.

---

## 2. Blokea — Aldagaiak eta datu-motak

**Helburua:** Aldagaiak deklaratu, balioa eman eta pantailaratzea, oraindik teklatutik ezer irakurri gabe.

1. Honako programa hau aldatu, konpilatu eta funtzionatu dezan:
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

2. Zergaitik ez du konpilatzen programa honek? Zuzendu, funtzionatu dezan:
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

3. Honako programa honek akatsak ditu, topatu eta zuzendu funtzionatu dezan:
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

4. Zer aurkeztuko du pantailan kode honek?
   ```java
   int zkia = 5;
   zkia += zkia - 1 * 4 + 1;
   System.out.println(zkia);
   zkia = 4;
   System.out.println(zkia);
   ```

5. Egizu `Luzeera` programa bat Javan, $3\text{ m}$-ko erradio-zirkunferentzia baten luzera kalkulatu dezan eta pantailan agertu. Formula hurrengoa da:
   $$L = 2 \cdot \pi \cdot r$$

6. Egizu `AZALERAZIR` programa bat Javan, $5.2\text{ cm}$-ko erradioa duen zirkunferentzia baten azalera kalkulatu dezan eta pantailan agertu. Formula:
   $$A = \pi \cdot r^2$$

7. Egizu `TRUKEA` programa bat Javan, $a$ eta $b$ aldagaiak izanda, beraien balioak elkar trukatzen dituenak eta pantailan hurrengoa agertu behar da:
   ```text
   Hasieran a-ren balioa hurrengoa da: 5
   Hasieran b-ren balioa hurrengoa da: 3
   ************************************
   Trukea egin eta gero horrela geratzen dira datuak:
   a= 3
   b= 5
   ```

> ➔ **Oharra:** Ariketa honetan (`TRUKEA`) ez dago daturik irakurtzen oraindik; helburua da ulertzea aldagai batek balio bakarra gordetzen duela une bakoitzean.

---

## 3. Blokea — Datuen sarrera (`Scanner`: `nextInt`, `nextDouble`, `next`)

**Helburua:** Erabiltzaileari datuak eskatzea. Bloke honetan ez dugu erabiliko `nextLine()` ez eta parseorik ere; `nextInt()`, `nextDouble()` eta `next()` (hitz bakarrekoak) nahikoa dira.

1. Egin `Agertuosoa` klasea; klase horrek, teklatutik balio oso bat (`int`) hartu, eta idatzi egingo du pantailan.
2. Egin `Agertuhamartarra` klasea; klase horrek, teklatutik balio hamartar bat (`double`) hartu, eta idatzi egingo du pantailan.
3. Egin `Agertukarakterea` klasea; klase horrek, teklatutik karaktere bat (`char`) hartu, eta idatzi egingo du pantailan.
4. Egin `Agertukatea` klasea; klase horrek, teklatutik karaktere-kate bat (`String`) hartu, eta idatzi egingo du pantailan.
5. Egin programa bat erabiltzaileari eskatzen diona: izena, lehenengo abizena eta bigarren abizena (hiruak `next()` erabiliz, banan-banan). Datuok jasotakoan, agurtu erabiltzailea pantailan, adibidez:
   ```text
   Sartu zure izena: Maite
   Sartu zure lehenengo abizena: Uriarte
   Sartu zure bigarren abizena: Urrutia
   Kaixo Maite Uriarte Urrutia!!!!
   ```

> ➔ **Oharra:** Izena + abizenak ariketan ez da behar `nextLine()` bakarra ere: hiru `next()` eginda (hitz bakoitzeko bat) nahikoa da, baina ez izen-abizen konposatuak irakurtzeko. Baina izen-abizen konposatua dugunean `nextLine()` erabiltzen badugu abizena hartzeko… zer gertatzen da?

---

## 4. Blokea — Eragile aritmetikoak eta konstanteak

**Helburua:** Kalkulu errealagoak egitea, konstanteak erabiliz eta emaitzak formatu jakin batekin ateraz (`printf`, `%.2f` estiloa).

1. Egin `BiZenbakiak` klasea. Eskatu erabiltzaileari bi zenbaki oso eta atera pantailan bien batuketa, kenketa, biderketa eta zatiketa.
2. Sortu `Ekuazioa` programa bat $Z$-ren balioa kalkulatzen duena, $X$ balio bat ematen diogunean. Ekuazioa:
   $$Z = 3X^2 + 7X - 15$$
   Eskatu erabiltzaileari $X$-ren balioa (`double`), eta atera $Z$-ren balioa pantailan.
3. Egin `Notak` programa bat erabiltzaileari eskatzeko teklatutik 3 nota (osoak edo hamartarrak izan daitezke) eta atera notaren batez bestekoa.
4. Egin programa bat erradioa eskatzen duena (zenbaki dezimala). Erradioa dugunean, atera hurrengo kalkuluak, $\pi = 3.141592654$ balioko konstante bat erabiliz:
   - Zirkunferentziaren perimetroa ($2 \cdot \pi \cdot R$)
   - Zirkuluaren azalera ($\pi \cdot R^2$)
   - Esfera baten azalera ($4 \cdot \pi \cdot R^2$)
   - Esferaren bolumena ($\frac{4}{3} \cdot \pi \cdot R^3$)

   *Emaitza guztiak bi dezimalekin atera behar dira.*
   *Konstanteak `final` hitzarekin adierazten dira Javan, adibidez:* `final double PI = 3.141592654;`

5. Egin `Segundoak` programa bat kalkulatzeko sartutako segundotan (zenbaki osoa) zenbat ordu, minutu eta segundo dauden. Erabiltzaileari eskatu segundoak, eta programak esan behar du zenbat ordu, minutu eta segundo diren.
   - Zatidura hartzeko: `/`
   - Hondarra hartzeko: `%`
6. Egin `Beherapenak` programa bat beherapenetan azken prezioa kalkulatzeko. Eskatu prezio originala eta deskontuaren ehunekoa ($\%$), eta programak kalkulatu behar du zenbat ordaindu behar den.

---

## 5. Blokea — Ariketa integratuak (aurrekoen nahasketa)

**Helburua:** Bloke honetan ariketa bakoitzak datuen sarrera, aldagaiak, eragileak eta irteera formatuarekin nahastu behar dira, ikasitako guztia praktikan jartzeko.

1. Egin `SoldataKalkulua` programa. Eskatu erabiltzaileari ordu-kopurua eta orduko prezioa (biak izan daitezke dezimalak), eta atera zenbat kobratuko duen guztira, bi dezimalekin.
2. Egin `BEZarekin` programa. Eskatu produktu baten prezioa (BEZik gabe) eta BEZaren ehunekoa (adibidez $21$), eta atera pantailan: prezioa BEZik gabe, BEZaren zenbatekoa eta azken prezioa BEZarekin, guztiak bi dezimalekin.
3. Egin `GradutanBihurketa` programa. Eskatu tenperatura bat gradu Celsiustan (`double`), eta bihurtu Fahrenheit-etara, formula hau erabiliz:
   $$F = C \cdot \frac{9}{5} + 32$$
   Atera emaitza bi dezimalekin.
4. Egin `LaukizuzenaEtaTriangelua` programa. Eskatu laukizuzen baten oinarria eta altuera, eta atera bere azalera eta perimetroa. Ondoren, oinarri eta altuera berberak erabiliz kalkulatu triangelu baten azalera ($\text{oinarria} \cdot \text{altuera} / 2$).
5. Egin `GasolinaGastua` programa. Eskatu bidaia baten distantzia ($\text{km}$), ibilgailuaren batez besteko kontsumoa ($\text{litro}/100\text{km}$) eta litroko prezioa (€), eta kalkulatu bidaiak zenbat kostatuko duen gasolinatan, bi dezimalekin.