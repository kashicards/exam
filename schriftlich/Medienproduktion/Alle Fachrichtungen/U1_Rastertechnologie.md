---
title: Rastertechnologie
tags:
  - Medienproduktion/Alle-Fachrichtungen/Rastertechnologie
kapitel: Alle Fachrichtungen
bereich: Medienproduktion
---
# Rastertechnologie

> [!summary] Definition
> Die **Datentiefe** (auch **Bit-Tiefe** genannt) beschreibt, **wie viele Bits** zur Darstellung eines einzelnen Pixels (bei Bildern), eines Tonsamples (bei Audio) oder allgemein eines Werts verwendet werden.  
> Je höher die Datentiefe, desto **mehr unterschiedliche Werte** können gespeichert werden.
Perfekt, hier bekommst du eine **vollständige, ausführlich erklärte Liste** aller Aspekte der **Datentiefe**, **die sich auf Rastertechnologie beziehen** – mit **Beispielen**, **Hintergrundwissen** und **praktischen Anwendungen**:

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

Anwendung:

- GIFs
    
- Alte Computerspiele
    
- Schwarz-Weiß-Druck
    

---

### 8. Rasterformate

#### ➤ Erklärung:
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

#### ➤ Erklärung:
> [!summary] Definition
> Beim **Scannen** analoger Bilder entsteht eine **digitale Rastergrafik**. Dabei wird festgelegt:
> - **Auflösung (DPI)** 
> - **Datentiefe pro Pixel**

> [!example] Beispiel
> - Dokumentenscan: 1 Bit (Schwarz-Weiß)   
> - Fotoscan: 24 Bit RGB

---

### 10. Histogramme & Bildbearbeitung

> [!summary] Definition
> Je höher die Datentiefe, desto **feiner** lassen sich Helligkeit und Farben in einem Bild anpassen, ohne dass Verluste (Banding) entstehen.

> [!example] Beispiel
> - 8 Bit: 256 Helligkeitsstufen → schneller sichtbare Stufenbildung   
> - 16 Bit: 65.536 Helligkeitsstufen → glatte Übergänge, ideal für Retusche


## Rasterarten im Druck

![Rastertypen](https://uhl-media.de/shops/2bb51eba-8128-4cf5-96b9-3066f94566f3/images/cms/qualitaet_Info_Druckrasterqualitaet-FM-AM-Rasterung-Druckerei.jpg)
### Autotypisches Raster (AM-Raster)

- Gleichmäßiger Rasterabstand, unterschiedliche Punktgrößen
    
- Verwendung im Offsetdruck
    

### Frequenzmoduliertes Raster (FM-Raster)

- Gleich große Punkte, unregelmäßige Verteilung
    
- Bessere Detailwiedergabe, weniger Moiré
    

### Hybride Raster

- Kombination aus AM- und FM-Raster
    
- Vorteile beider Systeme
    

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

## Prüfungsaufgabe

![Aufgabe](https://media.discordapp.net/attachments/965389986646069304/1353105863543619756/Bildschirmfoto_2025-03-22_um_21.39.30.png?ex=67fec409&is=67fd7289&hm=938dda5de9741aff299b32cf9e7f03593f4084c33600385187644b60ade24de4&=&format=webp&quality=lossless&width=1860&height=469)

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
 


