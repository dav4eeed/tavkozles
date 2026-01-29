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
    * $R_1$: $11.9\text{ k}\Omega$ (Bemeneti ellenállás)
    * $R_2$: $99\text{ k}\Omega$ (Visszacsatoló ellenállás)
    * $R_3$: $11.9\text{ k}\Omega$ (Offset kompenzáció)

## 3. Kapcsolási rajz és elméleti összefoglaló
Az invertáló alapkapcsolás elméleti feszültségerősítése ($A_u$) az ellenállások arányából számítható. A negatív előjel a fázisfordítást jelzi.

$$A_u = -\frac{R_2}{R_1}$$

(<img width="855" height="533" alt="invertalo" src="https://github.com/user-attachments/assets/7806de18-d621-43f6-a49a-c99dccdb8714" />)

## 4. Mérési eredmények

### 4.1. Statikus (DC) vizsgálat
A bemenetre kapcsolt $1\text{ V}$ DC feszültség mellett mért adatok:
* **Bemeneti feszültség ($U_{be}$):** $1\text{ V}$
* **Kimeneti feszültség ($U_{ki}$):** $-8.319\text{ V}$

### 4.2. Dinamikus (AC) vizsgálat
A bemeneti szinuszos jelet a függvénygenerátor biztosítja, a jeleket oszcilloszkóppal elemezzük.

**Függvénygenerátor beállításai:**
(<img width="518" height="592" alt="function generator" src="https://github.com/user-attachments/assets/32b20f71-c6d6-4f53-8551-0f8d4f98e61a" />)

**Oszcilloszkópos mérések (CH0: Bemenet, CH1: Kimenet):**
(<img width="1073" height="740" alt="oszcilloszkop" src="https://github.com/user-attachments/assets/269e5cef-f62e-4094-9cf3-55b1bb854772" />)

| Paraméter | CH0 (Sárga) | CH1 (Kék) |
| :--- | :--- | :--- |
| **Csúcstól-csúcsig ($V_{pp}$)** | $1.003\text{ V}$ | $8.379\text{ V}$ |
| **Effektív érték (RMS)** | $354.06\text{ mV}$ | $2.954\text{ V}$ |
| **Frekvencia ($f$)** | $100.000\text{ Hz}$ | $99.999\text{ Hz}$ |

---

## 5. Összehasonlító táblázat (Számított vs. Mért)

Az alábbi táblázat az elméleti úton meghatározott és a valós mérés során kapott értékeket veti össze:

| Megnevezés | Számított (Elméleti) | Mért (Valós) | Eltérés (%) |
| :--- | :--- | :--- | :--- |
| **Feszültségerősítés ($|A_u|$)** | $8.319$ | $8.354$ | $0.42\%$ |
| **Kimeneti feszültség (DC)** | $-8.319\text{ V}$ | $-8.319\text{ V}$ | $0.00\%$ |
| **Kimeneti feszültség ($V_{pp}$)** | $8.319\text{ V}$ | $8.379\text{ V}$ | $0.72\%$ |

## 6. Következtetés
A mérés sikeres volt. A mért értékek és a számított adatok közötti eltérés elhanyagolható (1% alatti), ami igazolja az elméleti összefüggések helyességét. Az oszcilloszkóp ernyőjén látható fáziseltolódás (180°) megerősíti az invertáló jelleget. A TL071 műveleti erősítő a vizsgált tartományban lineáris és stabil működést mutatott.

---
**Mérő aláírása:** ............................................
