---
title: AD-Wandler
tags:
  - Medienproduktion/Schwerpunkt-Digital/AD-Wandler
kapitel: Schwerpunkt Digital
bereich: Medienproduktion
status: in Bearbeitung
---
# A/D-Wandler (Analog-Digital-Wandler)

## 1. Was ist A/D-Wandlung?

> [!summary] Definition
> Die **Analog-Digital-Wandlung (A/D-Wandlung)** ist der Prozess, bei dem ein kontinuierliches analoges Signal (z. B. Spannung, Ton, Temperatur) in eine **digitale Zahlenfolge** umgewandelt wird, die von Computern verarbeitet und gespeichert werden kann.

**Beispielhafte Anwendungen in der Medienproduktion:**

- Mikrofonaufnahmen (Ton → elektrische Spannung)
    
- Digitalisierung von Videosignalen (analoges Lichtsignal → digitale Bilddaten)
    

---

## 2. Warum ist A/D-Wandlung notwendig?

Analoge Signale sind stufenlos – z. B. eine kontinuierliche Änderung der Spannung. Digitale Systeme, wie Computer, arbeiten hingegen nur mit diskreten Werten (Binärzahlen). Ein **AD-Wandler (A/D-Converter)** bildet die Brücke zwischen analoger Welt und digitaler Verarbeitung.

Vorteile:
- Digitalisierung von Informationen
- Digitale Signale
- Datentransport über langstrecken

---
## 3. Ablauf der A/D-Wandlung – Drei Schritte

### 3.1. Abtastung (Sampling)
![analoge und digitale Signale](https://www.arrow.de/-/media/arrow/images/miscellaneous/0/0418_adc_signal_2.jpg?h=318&w=850&hash=B5BEC42FBA9199C811656E51CF9B4148)
- Ein analoges Signal wird in **festen Zeitabständen** gemessen.
    
- Jeder dieser Messwerte wird als sogenanntes **„Sample“** gespeichert.
    
- Die Anzahl der Messungen pro Sekunde nennt man **Samplingrate** (Hz oder S/s = Samples per second).
    
- Eine hohe Samplingrate führt zu einer genaueren digitalen Repräsentation des analogen Signals.
    

> [!info] Formel Abtastrate
> $fs = 1/T$
> 
> $fs$ = Abtastrate bzw. Abtastfrequenz
> $T$ = Dauer der Stichprobe oder die Zeit, die bis zur nächsten Probenahme vergeht

>[!example] Bezug zum Bild
>In der Abbildung sieht man 20 Abtastschritte innerhalb von 1 Sekunde. Ein Abschnitt ist 0.05s lang.
>$fs = 1/T$
>$fs = 1/0.05 = 20 S/s (oder Hz)$

Das ursprüngliche analoge Signal hat eine Frequenz von **1 Hz**, also eine vollständige Schwingung pro Sekunde. Die digitale Abtastung (rote Treppenform) bildet das analoge Signal (blau) noch gut ab, da die Samplingrate ausreichend hoch gewählt wurde.
#### 3.1.1. Nyquist-Shannon-Abtasttheorem

> [!quote]  
> Die Samplingrate muss mindestens doppelt so hoch sein wie die höchste im Signal vorkommende Frequenz, um das analoge Signal korrekt rekonstruieren zu können.

> [!info] Nyquist Theorems
> $f_{Nyquist}$ = $2f_{max}$
> 
> $f_{Nyquist}$ = Nyquist-Frequenz  
> $f_{max}$ = die maximale Frequenz, die im Signal erscheint

> [!example]  
> Ein Signal mit $f_{max}=1Hz$ benötigt mindestens $f_s=2Hz$, um korrekt digitalisiert zu werden.  
> Im Bildbeispiel beträgt die Samplingrate $f_s= 20Hz$ → also **mehr als ausreichend**, um das 1-Hz-Signal gut darzustellen.

#### 3.1.2. Aliasing – Fehlerhafte Signalrekonstruktion

> [!summary] Definition  
> **Aliasing** bezeichnet die fehlerhafte Darstellung eines analogen Signals nach der Digitalisierung, wenn die Samplingrate zu niedrig ist. Dadurch erscheinen im digitalen Signal **falsche Frequenzen**, die im Original nicht vorhanden sind.

> [!example]  
> Ist die Samplingrate langsamer als die doppelte Frequenz des Eingangssignals, können wichtige Signaländerungen nicht erfasst werden.  
> Die Folge: Das rekonstruierte Signal entspricht **nicht mehr dem Original**, sondern sieht stark verzerrt oder verfälscht aus.

![Aliasing](https://www.arrow.de/-/media/arrow/images/miscellaneous/0/0418_aliasing_example.jpg?h=307&w=590&hash=9CE557AF9A1C433862489E36ABC49DB1)

In diesem Beispiel liegt die Samplingrate unter dem Nyquist-Kriterium. Die schwarzen Punkte zeigen die zu seltene Abtastung. Das rekonstruierte digitale Signal (rote Linie) entspricht dadurch **nicht dem Originalsignal** (blaue Kurve). Das digitale System erhält ein **verzerrtes Bild** des analogen Signals.

---

### 3.2. Quantisierung

Bei der Quantisierung wird jeder gemessene Spannungswert einer festen digitalen Stufe zugeordnet. Dies ist notwendig, weil ein A/D-Wandler (Analog-Digital-Wandler) nur eine endliche Anzahl an Stufen besitzt.

> [!note] Begrenzte Auflösung
> 
> - Die Anzahl der verfügbaren Stufen hängt von der Bit-Tiefe des Wandlers ab.
>     
> - Je höher die Bit-Tiefe, desto mehr Stufen und desto genauer die Auflösung.
>     
> - Zusätzlich beeinflusst die Referenzspannung die Schrittweite.
>     


![Auswirkung der Auflösung auf das Signal](https://www.arrow.de/-/media/arrow/images/miscellaneous/0/0418_resolution_example.jpg?h=279&w=466&hash=A475ACD2C6AFE862775E56A7083757A7)


### Bit-Tiefe, Anzahl der Stufen und Schrittweite (bei 5 V Referenz)

| Bit-Tiefe | Anzahl Stufen $N = 2^n$ | Schrittweite $= \frac{5}{N}$ (in V) |
| --------- | ----------------------- | ----------------------------------- |
| 2 Bit     | 4                       | 1.25                                |
| 4 Bit     | 16                      | 0.3125                              |
| 8 Bit     | 256                     | 0.0195                              |
| 10 Bit    | 1024                    | 0.00488                             |
| 12 Bit    | 4096                    | 0.00122                             |
| 16 Bit    | 65536                   | 0.000076                            |
| 18 Bit    | 262144                  | 0.000019                            |
| 20 Bit    | 1048576                 | 0.0000004                           |
| 24 Bit    | 16777216                | 0.00000002                          |

> [!tip] Je höher die Bit-Tiefe, desto kleiner die Schrittweite und desto genauer die Spannungsmessung.

> [!info] Formel zur Ermittlung der Schrittweite
> 
> $Schrittweite = V_{Ref}/N$  
> 
> $Schrittweite$ = Auflösung der einzelnen Stufe in Bezug auf die Spannung  
> $V_{Ref}$ = Spannungsreferenz (Spannungsbereich)  
> $N$ = Anzahl der verfügbaren Stufen
> 
> **Um $N$ zu ermitteln:**  
> $N = 2^n$  
> $n$ = Bit-Tiefe

> [!example] Beispiel  
> Eine Sinuswelle wird im Bereich von 0–5 V gemessen. Der A/D-Wandler besitzt eine Bit-Tiefe von 12 Bit.
> 
> $N = 2^{12} = 4096$  
> $Schrittweite = 5 / 4096 = 0.00122070312$
> 
> Die Schrittweite beträgt somit ca. 0,00122 V (bzw. 1,22 mV).  
> Das digitale System kann daher Spannungsänderungen ab ca. 1,22 mV unterscheiden.
> 
> Hätte der Wandler nur 2 Bit, würde die Schrittweite 1,25 V betragen.  
> Das System könnte dann nur 4 Spannungsstufen abbilden:  
> 0 V, 1,25 V, 2,5 V, 3,75 V, 5 V – sehr ungenau.

> [!warning] Quantisierungsrauschen Da Werte immer auf die nächstliegende Stufe gerundet werden, entsteht ein kleiner Fehler – das sogenannte Quantisierungsrauschen.  
> Je feiner die Schrittweite (also je höher die Bit-Tiefe), desto kleiner das Rauschen und desto besser die Signalqualität.

---

### 3.3. Codierung

Der quantisierte Spannungswert wird anschließend in eine Binärzahl umgewandelt.
festlegung der anzahl der möglichen werte pro abtastung

> [!note] Binäre Darstellung
> 
> - Bei 8 Bit: Werte von 0 bis 255
>     
> - 0 V → 00000000
>     
> - 5 V → 11111111
>     
> - Zwischenwerte z. B. 10010110 → entspricht ca. 2,75 V
>     
> 
> Höhere Bit-Tiefen ermöglichen feinere Abstufungen und damit eine präzisere Digitalisierung.


---

## 4. Technische Kenngrößen von AD-Wandlern

| Kenngröße                       | Bedeutung                                                                                                                                                                               |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Samplingrate/ Abtastrate**    | Anzahl der Abtastungen pro Sekunde (SPS oder S/s oder Hz bei Abtastfrequenz). Höhere Rate = höhere Genauigkeit bei schnellen Signaländerungen, kann also höhere Frequenzen verarbeiten. |
| **Bit-Tiefe / Auflösung**       | Gibt an, wie viele Werte unterschieden werden können (z. B. 16 Bit = 65.536 Stufen).                                                                                                    |
| **Quantisierungsrauschen**      | Fehler durch Rundung der analogen Werte auf feste Stufen.                                                                                                                               |
| **Signal-Rausch-Abstand (SNR)** | Verhältnis zwischen Nutzsignal und Rauschen – wichtig für die Qualität.                                                                                                                 |
| **Wandlungszeit**               | Zeit, die der Wandler für eine Umwandlung eines Werts benötigt.                                                                                                                         |

---

## 5. Typen von AD-Wandlern

|Typ|Eigenschaften|Vor- und Nachteile|
|---|---|---|
|**Flash-Wandler**|Nutzt viele parallele Vergleichsstufen|Sehr schnell, aber hoher Hardwareaufwand|
|**SAR (Successive Approximation Register)**|Arbeitet schrittweise durch Vergleich mit Referenzspannungen|Genau, effizient, weit verbreitet in Mikrocontrollern|
|**Dual-Slope-Wandler**|Misst über Zeit mit Integration|Sehr genau, aber langsam|
|**Delta-Sigma-Wandler**|Arbeitet mit Oversampling und Filterung|Sehr hohe Auflösung, vor allem in Audio-Technik|

---

## 6. Beispiel aus der Praxis: Tonaufnahme im Tonstudio

1. Du sprichst in ein Mikrofon.
    
2. Das Mikrofon erzeugt ein analoges Spannungssignal aus dem Luftdruck.
    
3. Das Signal gelangt in ein Audio-Interface, in dem ein AD-Wandler sitzt.
    
4. Dort wird das Signal **44.100-mal pro Sekunde** abgetastet (Samplingrate einer CD).
    
5. Jeder dieser Punkte wird auf einen **digitalen Wert (z. B. zwischen 0 und 65.535 bei 16 Bit)** quantisiert und codiert.
    
6. Ergebnis: Eine digitale Audiodatei, die gespeichert, bearbeitet und übertragen werden kann.
    

---

## 7. Bedeutung in der Medienproduktion

- **Audio:** Mikrofone, Audio-Interfaces, Aufnahmegeräte
    
- **Video:** Kameras, Digitalisierung von VHS, Fernsehkarten
    
- **Sensorik:** Temperatur, Licht, Bewegung in Mikrocontrollern und Mobilgeräten
    
- **Postproduktion:** Digitale Bearbeitung setzt digitale Eingangsdaten voraus
    
- **Qualitätsfaktoren:** Bit-Tiefe und Samplingrate bestimmen die Bearbeitbarkeit und den Speicherbedarf
    

---

## 8. Beispielrechnung: Auflösung eines AD-Wandlers

**Gegeben:**  
10-Bit-AD-Wandler, Eingangsspannung 0–3,3 V

**Frage:** Wie groß ist die Spannung pro Stufe?

**Rechnung:**
2¹⁰ = 1024 Stufen
→ 3,3 V / 1024 = **0,00322 V** bzw. **3,22 mV pro Schritt**

---

## 9. Prüfungsrelevante Aspekte

- Erklären des Wandlungsprozesses (Abtastung, Quantisierung, Codierung)
    
- Zusammenhang zwischen Auflösung (Bit) und Genauigkeit
    
- Beispielhafte Anwendungen (Audio, Video, Sensorik)
    
- Technische Begriffe korrekt verwenden (z. B. Samplingrate, Quantisierung)
    

---

## 10. Beispielhafte Prüfungsfrage (IHK)

**Frage:**  
Beschreiben Sie die Funktionsweise eines Analog-Digital-Wandlers und nennen Sie zwei Geräte, in denen ein solcher Wandler zum Einsatz kommt.

**Musterantwort:**  
Ein AD-Wandler wandelt ein kontinuierliches analoges Signal (z. B. eine Spannung) in digitale Werte um. Dies erfolgt in drei Schritten: Abtastung (regelmäßiges Messen), Quantisierung (Zuweisung auf feste Wertebereiche) und Codierung (Umwandlung in Binärcode). Geräte mit AD-Wandlern sind zum Beispiel Audio-Interfaces und Digitalkameras.


- bittiefe (bit) * abtastrate hz * audiodauer (sek) * audio kanäle = datenmenge in bit