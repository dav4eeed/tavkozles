# Mérési Jegyzőkönyv

**Mérést végezte:** Petrus Dávid  
**Helyszín:** Miskolci SZC Kandó Kálmán Informatikai Technikum, V3 labor  
**Dátum:** 2026. január 29.  
**Mérés tárgya:** Aktív aluláteresztő szűrő frekvenciaátvitelének vizsgálata Bode-analizátorral  

---

## 1. A mérés célja
Egy műveleti erősítővel felépített, visszacsatolt aktív szűrő áramkör frekvenciafüggő erősítésének és fázistolásának vizsgálata NI myDAQ mérőrendszer segítségével.

## 2. Alkalmazott eszközök és alkatrészek
* **Mérőeszköz:** NI myDAQ (Device: myDAQ1)
* **Szoftver:** NI ELVISmx Bode Analyzer
* **Integrált áramkör:** TL071 műveleti erősítő
* **Alkatrészek:**
    * R1: 11.9 kOhm (Bemeneti ellenállás)
    * R2: 99 kOhm (Visszacsatoló ellenállás)
    * R3: 11.9 kOhm (Offset kompenzáció)
    * C1: 10 nF (Visszacsatoló kondenzátor)

## 3. Kapcsolási rajz és elméleti háttér
Az áramkör egy elsőrendű aktív aluláteresztő szűrő. A visszacsatoló ágban elhelyezett kondenzátor miatt az erősítés a frekvencia növekedésével csökken.

<img width="951" height="652" alt="falstad" src="https://github.com/user-attachments/assets/40f1c6bc-78c6-441a-b75b-392026aad664" />   

### Elméleti számítások:
* **Maximális erősítés (A_dB_max):**
  A_u = R2 / R1 = 99k / 11.9k ≈ 8.319
  A_dB = 20 * log10(8.319) ≈ 18.40 dB
* **Törésponti frekvencia (fc):**
  fc = 1 / (2 * π * R2 * C1) ≈ 160.7 Hz
* **Meredekség:** Elsőrendű szűrő esetén a töréspont felett -20 dB/dekád.

## 4. Mérési eredmények (Bode-diagram)
A mérést a Bode Analyzer szoftverrel végeztük 20 Hz és 20 kHz közötti tartományban.

<img width="922" height="737" alt="bode" src="https://github.com/user-attachments/assets/c1b81427-225f-4330-9684-af178382ea40" />


**Mért adatok a kurzornál (f ≈ 159 Hz):**
* **Erősítés (Gain):** 15.40 dB
* **Fázistolás (Phase):** 135.14°
* **Gain (lineáris):** 5.89

## 5. Összehasonlító táblázat

| Megnevezés | Számított (Elméleti) | Mért (Valós) | Eltérés |
| :--- | :--- | :--- | :--- |
| **Max. Erősítés** | 18.40 dB | ~18.2 dB | -1.1% |
| **Törésponti frekvencia** | 160.7 Hz | 158.87 Hz | -1.1% |
| **Fázistolás fc-nél** | 135.00° | 135.14° | +0.1% |
| **Meredekség (fc felett)** | -20 dB/dekád | ~ -19.8 dB/dekád | -1.0% |

## 6. Következtetés
A mérés igazolta, hogy az áramkör aluláteresztő szűrőként működik. A mért 15.40 dB-es erősítés a töréspontnál közelítőleg 3 dB-es csökkenést jelent a DC maximumhoz képest, ami alátámasztja a számított fc értéket. A fázisgörbe 180°-ról indul (invertálás) és a kondenzátor hatására 90° felé tart.

---
**Mérő aláírása:** Petrus Dávid
