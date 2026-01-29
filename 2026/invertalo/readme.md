# Mérési Jegyzőkönyv

**Mérést végezte:** Petrus Dávid  
**Helyszín:** Miskolci SZC Kandó Kálmán Informatikai Technikum, V3 labor  
**Dátum:** 2026. január 29.  
**Mérés tárgya:** Invertáló műveleti erősítő alapkapcsolás vizsgálata statikus és dinamikus jelekkel  

---

## 1. A mérés célja
Az invertáló alapkapcsolás működésének, feszültségerősítésének és fázisviszonyainak ellenőrzése egyenáramú (DC) és váltakozó áramú (AC) bemeneti jelek mellett, NI myDAQ mérőrendszer segítségével.

## 2. Alkalmazott eszközök és alkatrészek
* **Mérőeszköz:** NI myDAQ (Device: myDAQ1)
* **Szoftverek:** NI ELVISmx Oscilloscope, NI ELVISmx Function Generator
* **Integrált áramkör:** TL071 műveleti erősítő
* **Ellenállások:**
    * $R_1$: $11.9\text{ k}\Omega$
    * $R_2$: $99\text{ k}\Omega$
    * $R_3$: $11.9\text{ k}\Omega$

## 3. Kapcsolási rajz és elméleti összefoglaló
Az invertáló alapkapcsolás elméleti feszültségerősítése ($A_u$) az alábbi képlet alapján számítható:
$$A_u = -\frac{R_2}{R_1}$$

![Áramköri elrendezés](invertalo.png)

## 4. Mérési eredmények

### 4.1. Statikus (DC) vizsgálat
A szimuláció/mérés során mért egyenfeszültségek:
* **Bemeneti feszültség ($U_{be}$):** $1\text{ V}$
* **Kimeneti feszültség ($U_{ki}$):** $-8.319\text{ V}$

### 4.2. Dinamikus (AC) vizsgálat
A bemeneti jelet a függvénygenerátor szolgáltatja, a ki- és bemeneti jeleket pedig oszcilloszkóppal monitorozzuk.

**Függvénygenerátor beállításai:**
![Függvénygenerátor](image_27118e.png)
* Jelalak: Szinusz
* Frekvencia: $100.00\text{ Hz}$
* Amplitúdó ($V_{pp}$): $1.00\text{ V}$

**Oszcilloszkópos mérések:**
![Oszcilloszkóp](image_2711ae.png)

| Paraméter | CH0 (Bemenet) | CH1 (Kimenet) |
| :--- | :--- | :--- |
| **Csúcstól-csúcsig ($V_{pp}$)** | $1.003\text{ V}$ | $8.379\text{ V}$ |
| **Effektív érték (RMS)** | $354.06\text{ mV}$ | $2.954\text{ V}$ |
| **Frekvencia ($f$)** | $100.000\text{ Hz}$ | $99.999\text{ Hz}$ |

## 5. Kiértékelés
A mérés során a mért és számított értékek szoros egyezést mutattak.
* **Elméleti erősítés:** $A_{u\_elm} \approx -8.319$
* **Gyakorlati erősítés ($V_{pp}$ alapján):** $A_{u\_prakt} = \frac{8.379\text{ V}}{1.003\text{ V}} \approx 8.354$

Az oszcilloszkóp ábráján megfigyelhető a 180°-os fázisfordítás, amely az invertáló kapcsolás alapvető jellemzője. A kimeneti jel torzításmentes, a TL071-es IC stabilan működik a megadott frekvenciatartományban.

---
**Mérő aláírása:** ............................................
