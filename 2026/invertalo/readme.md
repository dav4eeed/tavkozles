# Mérési Jegyzőkönyv

**Mérést végezte:** Petrus Dávid  
**Helyszín:** Miskolci SZC Kandó Kálmán Informatikai Technikum, V3 labor  
**Dátum:** 2026. január 29.  
**Mérés tárgya:** Invertáló műveleti erősítő alapkapcsolás vizsgálata statikus és dinamikus jelekkel  

---

## 1. A mérés célja
Az invertáló alapkapcsolás működésének, feszültségerősítésének és fázisviszonyainak ellenőrzése egyenáramú (DC) és váltakozó áramú (AC) bemeneti jelek mellett.

## 2. Alkalmazott eszközök és alkatrészek
* **Mérőeszköz:** NI myDAQ (Device: myDAQ1)
* **Szoftver:** NI ELVISmx Instrument Launcher (Oscilloscope, Function Generator)
* **Integrált áramkör:** TL071 műveleti erősítő
* **Ellenállások:** * $R_1 = 11.9\text{ k}\Omega$ (Bemeneti ellenállás)
    * $R_2 = 99\text{ k}\Omega$ (Visszacsatoló ellenállás)
    * $R_3 = 11.9\text{ k}\Omega$ (Offset kompenzáló ellenállás)

## 3. Kapcsolási rajz és elméleti összefoglaló
Az invertáló alapkapcsolás elméleti feszültségerősítése ($A_u$) az ellenállások arányából számítható:

$$A_u = -\frac{R_2}{R_1} = -\frac{99\text{ k}\Omega}{11.9\text{ k}\Omega} \approx -8.3193$$

A negatív előjel a bemeneti és kimeneti jel közötti 180°-os fázisvisszát (invertálást) jelöli.

## 4. Mérési eredmények

### 4.1. Statikus (DC) mérés
A bemenetre kapcsolt $1\text{ V}$ egyenfeszültség esetén mért adatok:
* **Bemeneti feszültség ($U_{be}$):** $1\text{ V}$
* **Mért kimeneti feszültség ($U_{ki}$):** $-8.319\text{ V}$

### 4.2. Dinamikus (AC) mérés
**Függvénygenerátor beállításai:**
* Jelalak: Szinusz
* Frekvencia: $100.00\text{ Hz}$
* Amplitúdó ($V_{pp}$): $1.00\text{ V}$

**Oszcilloszkóppal mért értékek:**
| Paraméter | CH0 (Sárga - Bemenet) | CH1 (Kék - Kimenet) |
| :--- | :--- | :--- |
| **Csúcstól-csúcsig ($V_{pp}$)** | $1.003\text{ V}$ | $8.379\text{ V}$ |
| **Effektív érték (RMS)** | $354.06\text{ mV}$ | $2.954\text{ V}$ |
| **Frekvencia ($f$)** | $100.000\text{ Hz}$ | $99.999\text{ Hz}$ |

## 5. Kiértékelés
A dinamikus mérés során tapasztalt gyakorlati erősítés:
$$A_{u\_praktikus} = \frac{V_{pp\_CH1}}{V_{pp\_CH0}} = \frac{8.379\text{ V}}{1.003\text{ V}} \approx 8.354$$

Az elméleti ($8.319$) és a gyakorlati ($8.354$) erősítés közötti eltérés elhanyagolható, csupán $0.42\%$. Az oszcilloszkóp ábrája alapján az invertálás (fázisfordítás) egyértelműen látható, a kimeneti jel torzításmentes.

---
**Mérő aláírása:** ............................................
