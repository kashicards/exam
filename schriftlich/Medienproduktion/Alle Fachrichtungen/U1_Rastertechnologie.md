---
title: Rastertechnologie
tags:
  - Medienproduktion/Alle-Fachrichtungen/Rastertechnologie
kapitel: Alle Fachrichtungen
bereich: Medienproduktion
status: erledigt
---
# Rastertechnologie

> [!summary] Definition
> * Befasst sich mit der Darstellung und Verarbeitung von Bildern, die aus einem Raster von Bildpunkten (Pixeln) bestehen.
> * Fokus liegt auf der Strukturierung, Speicherung, Verarbeitung und Visualisierung rasterbasierter Daten.
### 0. Zusammenhang von Datentiefe und Rasterung

> [!summary] Ergänzung zum Thema  
> Auch im Druckraster spielt die **Datentiefe** eine Rolle: Sie bestimmt, **wie fein** Helligkeits- bzw. Tonwertabstufungen dargestellt werden können.

- In einem **digitalen Workflow** (z. B. bei der Belichtung von Druckplatten) werden Bilddaten mit einer gewissen Bit-Tiefe verarbeitet – typischerweise **8 oder 16 Bit pro Farbkanal**.
    
- Diese Bit-Tiefe legt fest, wie viele unterschiedliche Tonwerte für einen Farbkanal vorliegen, die dann bei der **Rasterung in unterschiedlich große Punkte** (AM-Raster) oder **verschiedene Punktdichten** (FM-Raster) umgesetzt werden.
    

**Beispiel:**

- **8 Bit** → 256 Helligkeitsstufen → 256 unterschiedliche Rasterpunktgrößen möglich.
    
- **1 Bit** (wie bei reinen Schwarz/Weiß-Daten) → nur Punkt oder kein Punkt → keine Abstufung möglich.
    

> Fazit:  
> Die Datentiefe beeinflusst im Druck die **Tonwertabstufungen**, die durch Rasterpunkte reproduziert werden können. Je höher die Datentiefe, desto feiner und präziser können Helligkeitsunterschiede im Bild umgesetzt werden.

---
###  1. Bits pro Pixel (bpp)

> [!summary] Definition
> Die Anzahl der **Bits pro Pixel** bestimmt, wie viele **verschiedene Farb- oder Graustufen** ein einzelner Pixel im Rasterbild annehmen kann.

> [!info] Formel
> Mögliche Farbwerte = $2^\text{Bits\ pro\ Pixel}$

Beispiele:

|Bits pro Pixel|Farbanzahl|Typisches Format|
|---|---|---|
|1 bpp|2 Farben|Schwarz/Weiß (Fax, Icons)|
|4 bpp|16 Farben|Alte VGA-Grafiken|
|8 bpp|256 Farben|GIF, Graustufenbilder|
|24 bpp|16,7 Mio.|JPEG, PNG (True Color)|
|32 bpp|16,7 Mio. + Transparenz|PNG mit Alphakanal|

---

### 2. Farbanzahl / Farbtiefe

> [!summary] Definition
> Die **Farbtiefe** bezeichnet, **wie viele verschiedene Farben** ein Pixel darstellen kann – abhängig von der Datentiefe.

Beispiel:

Ein Bild mit 8 Bit Farbtiefe kann **256 Farben** darstellen.  
Ein Bild mit 24 Bit (8 Bit für Rot, Grün, Blau) = **True Color** mit **16.777.216 Farben**.

Anwendung:

- 8 Bit: Icons, einfache Grafiken, animierte GIFs
    
- 24 Bit: Fotos, Screenshots, Webseiten
    

---

### 3. Farbräume (RGB, RGBA, CMYK)

> [!summary] Definition
> Farbräume definieren, **wie Farben dargestellt werden** – also wie die Bit-Tiefe pro Farbkanal aufgeteilt ist.

|Farbraum|Struktur|Beschreibung|
|---|---|---|
|RGB|8 Bit pro Kanal (3×8 = 24)|Standard für Bildschirme (True Color)|
|RGBA|8 Bit pro Kanal + 8 Bit Alpha (4×8 = 32)|Mit Transparenz|
|CMYK|4×8 Bit (32 Bit)|Farbmodell für den Druck (Cyan, Magenta, Yellow, Black)|

---

### 4. Alphakanal / Transparenz

> [!summary] Definition
> Ein zusätzlicher **Alphakanal** speichert Informationen zur **Transparenz** von Pixeln. Wird z. B. bei **32 Bit PNGs** verwendet.

> [!example] Beispiel
> Ein Pixel in RGBA:  
> `R: 255, G: 0, B: 0, A: 128` = halbtransparentes Rot
    
Anwendung:

- Webgrafiken mit Transparenz
    
- UI-Elemente, Logos, Overlays
    

---

### 5. Speicherbedarf / Dateigröße

> [!summary] Definition
> Die Datentiefe beeinflusst direkt den **Speicherbedarf eines Bildes**.

> [!info] Formel
Dateigröße (Bytes) = $\frac{\text{Breite} \times \text{Höhe} \times \text{Bits pro Pixel}}{8}$

> [!example] Beispiel
> Ein Bild mit 1920×1080 Pixeln bei 24 bpp:
> $\frac{\text{1920} \times \text{1080} \times \text{24}}{8}$ =6.220.800 Bytes ≈ 5,93 MB (unkomprimiert)

---

### 6. Farbtabelle / Color Lookup Table (CLUT)

> [!summary] Definition
> Bei Bildern mit **geringer Datentiefe** (z. B. 8 Bit) wird oft eine **Farbtabelle** verwendet, in der bis zu 256 Farben definiert sind.
> Jeder Pixel verweist dann **nur auf einen Index** in dieser Tabelle.

Vorteil:

- Spart Speicherplatz
    

Nachteil:

- Eingeschränkte Farbvielfalt
    

Anwendung:

- GIF-Dateien
    
- Icon-Dateien (.ico)
    

---

### 7. Dithering

> [!summary] Definition
> **Dithering** ist ein Verfahren, das bei geringer Farbtiefe verwendet wird, um **optisch mehr Farben** darzustellen, als eigentlich gespeichert werden können.
> Dabei werden Pixel in bestimmten Mustern so gesetzt, dass unser Auge **Zwischenfarben** wahrnimmt.

> [!example] Beispiel
> Ein Bild mit 4 Farben kann durch Dithering **scheinbar 16** darstellen.

![Dithering](https://www.prad.de/wp-content/uploads/2017/07/schaubild-dithering-jeansmuster-effekt.jpg)

Anwendung:

- GIFs
    
- Alte Computerspiele
    
- Schwarz-Weiß-Druck
    

---

### 8. Rasterformate

> [!summary] Definition
> Rastergrafiken werden in bestimmten Formaten gespeichert, die **Datentiefe** unterschiedlich handhaben.

| Format | Unterstützte Farbtiefe       | Besonderheiten           |
| ------ | ---------------------------- | ------------------------ |
| BMP    | 1–32 Bit                     | Unkomprimiert, riesig    |
| PNG    | 8–32 Bit                     | Verlustfrei, mit Alpha   |
| JPEG   | 24 Bit (ohne Alpha)          | Komprimiert, Fotos       |
| GIF    | 8 Bit mit Farbtabelle        | Animationen, Transparenz |
| TIFF   | flexibel (auch 16 Bit/Kanal) | Hochwertiger Druck       |

---

### 9. Digitalisierung / Scannen

>[!summary] **Definition**
>Beim **Scannen** werden analoge Vorlagen (z. B. Fotos, Dokumente, Zeichnungen) in **digitale Rastergrafiken** umgewandelt. Dabei entstehen aus den kontinuierlichen Tonwerten der Vorlage **diskrete Pixelwerte**, deren Qualität maßgeblich von zwei technischen Parametern bestimmt wird:
>
>- **Auflösung (DPI)** – _Dots per Inch_: Gibt an, wie viele Bildpunkte pro Zoll (2,54 cm) erfasst werden. Höhere DPI-Werte führen zu mehr Bilddetails.
  >  
>- **Farbtiefe / Datentiefe pro Pixel** – Anzahl der Bits zur Darstellung der Farbinformationen eines Pixels. Sie bestimmt, wie viele verschiedene Grau- oder Farbstufen gespeichert werden können.

#### Typische Einstellungen & Anwendungen

| Anwendung                        | Farbtiefe                        | Auflösung (DPI) | Erläuterung                                     |
| -------------------------------- | -------------------------------- | --------------- | ----------------------------------------------- |
| Textdokumente (z. B. Buchseiten) | **1 Bit** (Schwarz/Weiß)         | 300–600 DPI     | Für klare Texterkennung, keine Graustufen nötig |
| Graustufenbilder                 | **8 Bit** (256 Graustufen)       | 300–1200 DPI    | Etwa für Zeichnungen oder Manuskripte           |
| Farbfotos                        | **24 Bit RGB** (8 Bit pro Kanal) | 300–4800 DPI    | Für bildgetreue Digitalisierung von Fotos       |

> [!info] Scans mit hoher DPI und Farbtiefe erzeugen sehr große Dateien. Die Wahl hängt vom Verwendungszweck ab (Archivierung vs. OCR vs. Web).

---

### 10. Histogramme & Bildbearbeitung

>[!summary] **Definition**
>Ein **Histogramm** zeigt die Verteilung von Helligkeits- oder Farbwerten in einem Bild. Es ist ein zentrales Werkzeug in der Bildanalyse und -bearbeitung. Die **Datentiefe pro Kanal** (z. B. 8 Bit oder 16 Bit) beeinflusst direkt die Qualität bei Farbkorrekturen und Retusche:
>
>- Höhere Datentiefe → **mehr Werte zwischen Schwarz und Weiß bzw. zwischen Farbtönen** → feinere Abstufungen, geringere Quantisierungsartefakte.
  >  
>- Niedrige Datentiefe → **sichtbare Stufenbildung** („Banding“) bei Farbverläufen und Nachbearbeitung.


#### Beispiele nach Bit-Tiefe

| Farbtiefe pro Kanal | Gesamt (RGB) | Stufen pro Farbkanal | Anwendung                      | Kommentar                                |
| ------------------- | ------------ | -------------------- | ------------------------------ | ---------------------------------------- |
| 8 Bit (pro Kanal)   | 24 Bit RGB   | 256 Stufen           | Standardfotos, JPEG            | Begrenzter Spielraum für Farbkorrekturen |
| 16 Bit (pro Kanal)  | 48 Bit RGB   | 65 536 Stufen        | High-End-Retusche, RAW-Formate | Hoher Bearbeitungsspielraum ohne Banding |
| 1 Bit (monochrom)   | –            | 2 Stufen             | Fax, OCR                       | Nur Schwarz und Weiß                     |

> **Fazit:** Für professionelle Bildbearbeitung (z. B. in Photoshop) empfiehlt sich **mindestens 16 Bit pro Kanal**, um visuelle Verluste bei Farbkorrekturen zu vermeiden.



## Rasterarten im Druck

![Rastertypen](https://uhl-media.de/shops/2bb51eba-8128-4cf5-96b9-3066f94566f3/images/cms/qualitaet_Info_Druckrasterqualitaet-FM-AM-Rasterung-Druckerei.jpg)

![Rastertypen Vergleich](https://blog.dierotationsdrucker.de/wp-content/uploads/2014/06/Vergleich_druckraster-1024x1024.jpg)

### 1. Tonwert

- Der **Tonwert** beschreibt die Helligkeit eines Bildbereichs, typischerweise als Grauwert zwischen 0 % (weiß) und 100 % (schwarz).
    
- Mit steigendem Tonwert erscheint eine Fläche **dunkler** im Druck.
    

### 2. Amplitude der Rasterpunkte

- Beim **autotypischen Raster (AM-Raster)** wird die Helligkeit durch die **Größe der Rasterpunkte** dargestellt (Amplitude = Fläche).
    
    - **Helle Bildbereiche**: kleine Rasterpunkte
        
    - **Dunkle Bildbereiche**: große Rasterpunkte
        

**Beispiel:**

- 10 % Tonwert → kleiner Punkt (geringe Bedruckung)
    
- 90 % Tonwert → großer Punkt (nahezu volle Flächendeckung)
    

### 3. Rasterfrequenz / Rasterperiode

- Die **Rasterperiode** beschreibt den Abstand der Rasterpunkte zueinander.
    
- Die **Rasterfrequenz** (z. B. 60 Linien/cm) gibt an, wie viele Rasterpunkte pro Längeneinheit angeordnet sind.
    
- Unabhängig vom Tonwert bleibt die Frequenz **konstant** – es ändert sich lediglich die Punktgröße, nicht der Abstand.
    

> **Merksatz:** Im AM-Raster wird die Helligkeit über die Punktgröße, nicht über den Abstand geregelt.

### 4. Rasterpunktverteilung (Vergleichstabelle)

| **Rastertyp**                              | **Merkmale**                                                                                                                                         | **Vorteile**                                                                                                                                                                                | **Nachteile**                                                                                                                                                             |
| ------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Autotypisches Raster (AM-Raster)**       | - Gleichmäßiger Rasterabstand<br>- Tonwertdarstellung über **Punktgröße** (Amplitude)<br>- Standardverfahren im Offsetdruck                          | - Hohe Prozesssicherheit (PSO/ISO 12647)<br>- Bewährte und kostengünstige Technik<br>- Stabile Ergebnisse auch auf einfachen Papieren<br>- Tonwertzunahme leicht messbar und kontrollierbar | - Gefahr von **Moiré-Effekten** und **Rosettenbildung** bei ungünstiger Winkelung<br>- Eingeschränkte Detailzeichnung<br>- Schwächen bei Verläufen in Lichtern und Tiefen |
| **Frequenzmoduliertes Raster (FM-Raster)** | - Gleich große Punkte<br>- Tonwertdarstellung über **Anzahl und Verteilung** der Punkte (Frequenz)<br>- Unregelmäßige, stochastische Punktverteilung | - Sehr feine Details darstellbar- Keine Moirés oder Rosetten<br>- Gleichtöne und Verläufe erscheinen besonders glatt<br>- Ideal für fotorealistische Drucke                                 | - Hoher technischer und finanzieller Aufwand<br>- Höhere Anforderungen an Belichter und Papierqualität<br>- Messtechnisch schwieriger zu kontrollieren                    |
| **Hybrides Raster (XM-Raster)**            | - Kombination aus AM- und FM-Raster                                                                                                                  |                                                                                                                                                                                             |                                                                                                                                                                           |

- AM in Mitteltönen (gleichmäßiger Verlauf)
    
- FM in Lichtern und Tiefen (feine Strukturen)- Rastermodus abhängig vom Tonwertbereich | - Vereint die Vorteile beider Systeme- Sehr hohe Detailwiedergabe- Glatte Flächen und weiche Übergänge in kritischen Bereichen- Keine Moirébildung- Besonders für hochwertige Bildwiedergabe geeignet | - Komplexere RIP- und Druckprozesssteuerung erforderlich- Höherer Kalibrierungsaufwand- Übergangsbereiche zwischen AM und FM müssen exakt abgestimmt sein- Noch keine vollständige Standardisierung vorhanden |
    

### 5. Form der Rasterpunkte

- Rasterpunkte müssen **nicht rund** sein:
    
    - Sie können **elliptisch**, **quadratisch**, **rautenförmig** oder **linienförmig** ausgeprägt sein.
        
- Je nach Druckanforderung kommen auch seltene Formen oder Mischformen zum Einsatz.
    

### 6. Rasterweite

- Die **Rasterweite** beschreibt die Anzahl der Rasterpunkte pro Längeneinheit:
    
    - Einheit: **L/cm** (Linien pro Zentimeter) oder **lpi** (lines per inch)
        
- Eine höhere Rasterweite bedeutet:
    
    - Feineres Raster
        
    - Höhere Detailgenauigkeit
        
    - Anspruchsvollere Druckanforderungen
        
- Abhängig von:
    
    - Druckverfahren
        
    - Druckmaschine
        
    - Bedruckstoff (z. B. Papierqualität)
        

### 7. Rasterwinkel

![Rasterwinkel](https://helpcenter.shirtigo.de/wp-content/uploads/2020/02/512px-CMYK_screen_angles.svg_.png)

#### 7.1 Einfarbiger Druck

- Werden Rasterpunkte **horizontal** angeordnet, entstehen optisch störende Muster.
    
- Das menschliche Auge reagiert empfindlich auf regelmäßige Strukturen.
    
- Durch eine Drehung des Rasters um **45°** (diagonal) erscheinen die Muster weniger auffällig.
    

#### 7.2 Vierfarbdruck (CMYK)

- Bei überlagerten Rastern gleicher Winkel entstehen ungewollte Farbverschiebungen (sog. **Farbdriften**).
    
- Raster der einzelnen Farben werden daher um unterschiedliche Winkel **zueinander versetzt**:
    
    - Typische Winkel: Cyan 15°, Magenta 75°, Schwarz 45°, Gelb 0° oder 90° (da am wenigsten sichtbar)
        
- Dadurch wird eine gleichmäßige Gesamtwiedergabe erzielt und störende Muster reduziert.
    

### 8. Moiré-Effekt

![Moire](https://helpcenter.shirtigo.de/wp-content/uploads/2020/02/800px-Moir%C3%A92-768x225.png)

- Der **Moiré-Effekt** ist ein optisch störendes Interferenzmuster, das bei ungünstiger Überlagerung von Rasterstrukturen entsteht.
    
- Um dies zu vermeiden:
    
    - Rasterwinkelung der einzelnen Farben sinnvoll wählen
        
    - Rasterformen entsprechend anpassen (z. B. elliptisch statt quadratisch)
        
- Besonders kritisch ist die Überlagerung identischer Rasterwinkel bei mehreren Farben.
    
    - Gelb erhält meist den geringsten Winkel, da es am unauffälligsten ist.



### 11. RIP – Raster Image Processor (Erweiterung)

>[!summary] Ein **RIP (Raster Image Processor)** ist eine Hard- oder Software, die digitale Druckdaten in gerasterte Informationen umwandelt. Diese Rasterdaten (z. B. als TIFF, Bitmap oder proprietäres Format) steuern direkt die Belichtungseinheit einer Druckmaschine oder eines Belichters (z. B. CtP oder Digitaldrucksysteme).

#### Aufgaben des RIP:

- Interpretation und Auflösung von Druckdaten (z. B. PDF, PostScript)
    
- Farbraumkonvertierung (z. B. RGB zu CMYK über ICC-Profile)
    
- Überdrucken-Kontrolle und Transparenzreduktion
    
- Anwendung von Rasterverfahren (AM, FM, Hybride)
    
- Separationsgenerierung (CMYK, Sonderfarben)
    
- Auflösung von Ebenen, Effekten und Masken
    

#### Verarbeitung unterschiedlicher Datenarten im RIP:

|**Datentyp**|**Beispiel**|**Verarbeitung**|**Besonderheit**|
|---|---|---|---|
|**Schriftarten**|Eingebettete Fonts in PDF|Umrechnung in Vektorgrafik oder direkte Rasterung|Hohe Präzision nötig, Schriftfehler bei fehlenden Fonts|
|**Vektorgrafiken**|Logos, Liniengrafiken|Vektorbasiert interpretiert und gerastert|Skalierbar ohne Qualitätsverlust|
|**Bilddaten (Pixelbilder)**|Fotos (TIFF, JPEG)|Direkt gerastert, ggf. Farbraumanpassung|Feste Auflösung, Qualitätsverlust bei Skalierung|

#### Bedeutung:

Die Qualität des RIP hat maßgeblichen Einfluss auf die **Druckqualität, Farbtreue** und **Fehlerfreiheit** im Endprodukt. Moderne RIPs enthalten zusätzlich Funktionen zur Vorschau (Softproof), Farbmanagement und Ausschießen.


---

## Fachbegriffe

|Begriff|Bedeutung|
|---|---|
|**Rasterweite**|Anzahl Rasterpunkte pro cm/inch (z. B. 60 l/cm ≈ 150 lpi)|
|**Rasterwinkel**|Winkel, in dem Rasterpunkte gedruckt werden (verhindert Moiré)|
|**Moiré-Effekt**|Störmuster bei überlagernden Rastern|
|**Interpolation**|Verfahren zur Berechnung neuer Pixel beim Skalieren|
|**Aliasing**|Treppenbildung bei schrägen Linien oder Kanten|
|**Anti-Aliasing**|Glättungsverfahren gegen Treppeneffekte|

---

## Praxis in der Druckvorstufe

> [!important]  
> Bilder **immer in Originalgröße** und **passender Auflösung** für das jeweilige Medium anlegen. RGB-Bilder müssen vor dem Druck in **CMYK** konvertiert werden.

## Formeln
>[!info] Formel
> Rastertonwert [%] = (Anzahl der gedruckten Rasterpunkte / Gesamtzahl der Rasterpunkte) * 100

## Prüfungsaufgabe
>[!question] ![Aufgabe](https://cdn.discordapp.com/attachments/965389986646069304/1353105863543619756/Bildschirmfoto_2025-03-22_um_21.39.30.png?ex=68167f09&is=68152d89&hm=9d89466c123cd307cae6c6df9af2f0c20cb96db1807bea6ac8e7c63042c7c7ff&format=webp&quality=lossless&width=1790&height=451)
> ### Aufgabe U1 (10 Punkte)
> 
> **Eine PDF-Datei (CMYK) mit Font-, Grafik- und Bilddaten soll in AM-Rasterung gedruckt werden.**
> 
> #### a) Unterschiedliche Verarbeitung von Font-, Grafik- und Bilddaten im RIP (3 Punkte)
> 
> Im RIP (Raster Image Processor) erfolgt eine differenzierte Verarbeitung je nach Datentyp:
> 
> - **Fontdaten**:  
>   Vektorbasiert, meist als PostScript- oder OpenType-Schriften eingebettet.  
>   → Der RIP rendert sie zu hochauflösenden Bitmaps in der benötigten Auflösung, sodass die Kanten scharf bleiben.
> 
> - **Grafikdaten** (z. B. Logos, Vektorelemente):  
>   Ebenfalls vektorbasiert (z. B. PDF, EPS).  
>   → Der RIP wandelt sie in Rastergrafiken um, angepasst an die Belichtungsauflösung und den Druckraster.
> 
> - **Bilddaten** (z. B. JPEG, TIFF):  
>   Bereits pixelbasiert und in festen Auflösungen vorhanden.  
>   → Der RIP übernimmt diese direkt, prüft aber Farbprofil, Auflösung und skaliert ggf. für die Rasterung.
> 
> #### b) Berechnung des Rastertonwerts bei Helligkeitswert 168 (3 Punkte)
> 
> Gegeben:
> 
> - Datentiefe = 8 Bit → Wertebereich: 0 bis 255
> - Helligkeitswert = 168
> 
> **Rastertonwert (%)** = (168 / 255) × 100  
> → **65,88 %**
> 
> **Ergebnis:**  
> Ein Pixel mit Helligkeit 168 ergibt einen Rastertonwert von **ca. 65,9 %**.
> 
> #### c) Unterschied der Dot-Anordnung in einer Rasterzelle: AM vs. FM (4 Punkte)
> 
> - **AM-Raster (amplitudenmoduliert):**
>   - **Punkte haben variable Größe**, der Abstand ist konstant (z. B. 60 Linien/cm).
>   - **Dunkle Töne**: große Punkte, helle Töne: kleine Punkte.
>   - Punkte sind **regelmäßig in einem festen Rasterwinkel** angeordnet.
>   - → **Steuerung des Tonwerts über Punktgröße (Amplitude)**.
> 
> - **FM-Raster (frequenzmoduliert):**
>   - **Punkte sind gleich groß**, der Tonwert wird über die **Anzahl und Dichte** gesteuert.
>   - Punkte sind **unregelmäßig verteilt** (stochastisch).
>   - → **Steuerung des Tonwerts über Punktverteilung (Frequenz)**.
>   - Eignet sich besonders gut zur Vermeidung von Moirés und für detailreiche Bilder.

> [!question] **Was ist der Hauptzweck einer Rasterung im Druckverfahren?** 
> A) Überführung von Halbtonbildern in druckbare Strukturen 
> B) Besserer Kontrast bei farbigen Flächen 
> C) Farbkorrektur bei Digitalbildern 
> D) Erhöhung der Auflösung von Texten 
> 
> Lösung: **A** 

> [!question] **Was bedeutet „Rasterweite“?** 
> A) Die Dicke der Rasterpunkte 
> B) Der Abstand zwischen Druckfarben 
> C) Die Anzahl der Rasterpunkte pro Inch oder pro Zentimeter 
> D) Die Tiefe der Farbsättigung 
> 
> Lösung: **C** 

 >[!question]  **Welche Rasterart ist typisch für den Offsetdruck?** 
 >A) Stochastisches Raster 
 >B) Autotypisches Amplitudenraster 
 >C) Fraktalraster 
 >D) Halbraster 
 >
 >Lösung: **B** 
 
 > [!question] **Wie unterscheidet sich das frequenzmodulierte Raster (FM) vom amplitudenmodulierten Raster (AM)?** 
 > A) FM hat gleich große Punkte, die unterschiedlich angeordnet sind
 >  B) FM nutzt verschiedene Farben 
 >  C) FM hat größere Rasterweiten 
 >  D) FM ist nur im Tiefdruck möglich 
 >  
 >  Lösung: **A** 
 
 > [!question] **Was passiert bei zu hoher Rasterweite im Druckprozess?** 
 > A) Das Bild wirkt pixelig 
 > B) Der Tonwertumfang steigt 
 > C) Die Druckplatte verschleißt schneller 
 > D) Es kann zu Moiré-Effekten kommen 
 > 
 > Lösung: **D** 
 
 > [!question] **Was ist ein Moiré-Effekt?** 
 > A) Ein Farbverlauf bei Volltonfarben 
 > B) Eine unerwünschte Musterbildung durch Überlagerung von Rasterwinkeln 
 > C) Eine erhöhte Schärfe durch Kantenglättung 
 > 
 > Lösung: **B**
 


