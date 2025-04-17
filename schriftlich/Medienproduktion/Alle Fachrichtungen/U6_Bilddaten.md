---
title: Bilddaten
tags:
  - Medienproduktion/Alle-Fachrichtungen/Bilddaten
kapitel: Alle Fachrichtungen
bereich: Medienproduktion
---
# Bilddaten

> [!summary] Digitale Bildformate (JPEG, PNG, SVG) und deren Eigenschaften wie Auflösung, Komprimierung und Metadaten.

---

## Übersicht & Eigenschaften

|Format|Transparenz|Animation|Komprimierung|Art|Einsatzbereich|Farbraum(e)|
|---|---|---|---|---|---|---|
|**JPEG**|✘|✘|Verlustbehaftet|Rasterbild|Fotos (Web & Print)|RGB, CMYK (eingeschränkt)|
|**PNG-8**|✔ (1-Bit)|✘|Verlustfrei|Rasterbild|Webgrafiken|RGB|
|**PNG-24**|✔ (8-Bit)|✘|Verlustfrei|Rasterbild|Logos, Screenshots|RGB|
|**GIF**|✔ (1-Bit)|✔|Verlustfrei (indiziert)|Rasterbild|Animationen, Web|RGB (indiziert)|
|**SVG**|✔|✔|Verlustfrei (Textbasiert)|Vektorbild|Web, Icons, Logos|RGB (geräteabhängig)|
|**TIFF**|✔ (optional)|✘|Verlustfrei/optional|Rasterbild|Druck, Archivierung|RGB, CMYK, Lab, Grau|
|**EPS**|✔ (teilweise)|✘|Verlustfrei (Vektor)|Vektorbild|Druck, Layout|CMYK, RGB, Sonderfarben|
|**WEBP**|✔ (8-Bit)|✔|Verlustfrei/-behaftet|Rasterbild|Modernes Web|RGB|
|**HEIC**|✔|✘|Verlustbehaftet|Rasterbild|Mobile, Apple-Geräte|RGB|
|**RAW**|✘|✘|Unkomprimiert/minimal|Rasterbild|Fotografie, Nachbearb.|Sensorabhängig (RGB)|

---

## Pixel- vs. Vektorgrafiken

### Pixelgrafiken (Rasterbilder)

- Raster aus Pixeln
    
- Auflösungsabhängig → Qualitätsverlust beim Vergrößern
    
- Typische Formate: JPG, PNG, GIF, TIFF, BMP
    
- Einsatz: Fotos, komplexe Bilder
    

### Vektorgrafiken

- Mathematisch definierte Formen (Kurven, Linien)
    
- Auflösungsunabhängig → beliebig skalierbar
    
- Typische Formate: SVG, AI, EPS, PDF
    
- Einsatz: Logos, Icons, Infografiken
    

---

## Grundlagen: Bilddaten

|Begriff|Erklärung|
|---|---|
|**Auflösung**|Anzahl Pixel in Breite × Höhe (z. B. 1920 × 1080)|
|**dpi / ppi**|Dots/Pixel per Inch – wichtig für Druck (z. B. 300 dpi)|
|**Farbtiefe**|Anzahl darstellbarer Farben pro Pixel (z. B. 24 Bit = 16,7 Mio Farben)|
|**Transparenz**|Möglichkeit, Bildbereiche durchsichtig zu machen|
|**Farbmodelle**|RGB (Web), CMYK (Druck), LAB, Graustufen|
|**Kompression**|Reduziert Dateigröße – verlustfrei (PNG) oder verlustbehaftet (JPG)|
|**Metadaten**|EXIF-Daten: Kamera, Datum, Urheber etc.|

---

## Rechenformel für Bilddatenmenge

> [!info] Formel  
> $Dateigröße (Byte) = Breite × Höhe × Farbtiefe (in Byte)$

> [!example] Beispiel  
> Bild mit 3000 × 2000 Pixeln, 24 Bit (3 Byte) →  
> $3000 × 2000 × 3 = 18.000.000 Byte = 18 MB$

---

### Erweiterte Berechnungsbeispiele

|Eigenschaft|Wert|
|---|---|
|**Bildgröße**|30 cm × 20 cm|
|**Auflösung**|300 dpi|
|**Farbtiefe**|24 Bit (8 Bit pro Farbkanal, RGB → 3 Byte)|

**Umrechnung cm in Pixel (bei 300 dpi):**  
30 cm × 118,11 ≈ **3543 px**  
20 cm × 118,11 ≈ **2362 px**

**Berechnung:**  
$3543 × 2362 × 3 ≈ 25.166.202 Byte ≈ 25,17 MB$

> [!tip] Faustregel  
> Bei **300 dpi, 24 Bit** Farbtiefe ergibt 1 cm² etwa **1,06 MB**.

---

### Beispiel mit CMYK

|Eigenschaft|Wert|
|---|---|
|**Bildgröße**|10 cm × 10 cm|
|**Auflösung**|300 dpi|
|**Farbtiefe**|32 Bit (4 Byte für CMYK)|

> [!example] Beispiel
> $1181 px × 1181 px × 4 = 5.577.124 Byte ≈ 5,58 MB$

---

## Druckoptimierte Bilddaten

- Auflösung: **mind. 300 dpi**
    
- Farbmodus: **CMYK**
    
- Formate: **TIFF, EPS, PDF**
    
- Farbprofil: _ISO Coated v2 300% (ECI)_
    
- Schriften: **eingebettet** oder in **Pfade** umgewandelt
    

---

## Bilddaten für Web & Bildschirm

- Auflösung: **72–144 dpi**
    
- Farbmodus: **RGB**
    
- Formate: JPG (Fotos), PNG (Transparenz), GIF (Animation), SVG (Vektor)
    
- Komprimierung: Möglichst stark, ohne sichtbaren Qualitätsverlust
    
- Responsives Design: Bildgrößen flexibel (CSS, Media Queries)
    

---

## Crossmediale Nutzung von Grafikdaten

### Ziel

> [!warning] Ein und dieselbe Datei soll für Web, Print, Social Media usw. nutzbar sein.

### Anforderungen

- **Hohe Ausgangsqualität** (Originaldateien)
    
- **Verlustfreie Formate** für Bearbeitung (z. B. PNG, TIFF, PSD, AI)
    
- **RGB-Original**, **CMYK-Export**
    
- Farbprofile verwenden (_eciRGB v2_, _ISO Coated v2 300%_)
    
- Einheitliche Bildgrößen, Layoutvorgaben einhalten
    

---

## Best Practice für Crossmedia

1. Originaldatei im verlustfreien Format (z. B. AI, PSD) sichern
    
2. Bearbeitung mit Ebenen & Farbprofilen
    
3. Exporte je nach Medium (z. B. PDF für Print, SVG für Web)
    
4. Mediengerechte Kompression & Formatwahl
    

---

## Formatwahl – Schnellübersicht

|Verwendungszweck|Empfohlenes Format|
|---|---|
|Fotos im Web|**JPG**|
|Transparente Webgrafiken|**PNG**|
|Einfache Web-Animationen|**GIF**|
|Logos & Icons (Web)|**SVG**|
|Druck mit höchster Qualität|**TIFF**, **PDF**|
|Photoshop-Projektdateien|**PSD**|
|Illustrator-Dateien|**AI**, **EPS**|

---

## Metadaten in Bilddateien

> [!summary] Definition  
> **Metadaten** sind zusätzliche Informationen, die in einer Bilddatei gespeichert werden – z. B. Kameraeinstellungen, Aufnahmezeit, GPS-Daten oder Urheberrechte.

### Übersicht: Typen von Bild-Metadaten

|Metadaten-Typ|Beispielhafte Inhalte|Formate mit Unterstützung|
|---|---|---|
|**EXIF**|Kamera, Blende, Belichtungszeit, ISO, GPS, Datum|JPEG, TIFF, RAW|
|**IPTC**|Titel, Beschreibung, Urheber, Copyright, Schlagwörter|JPEG, TIFF, PSD|
|**XMP**|Bearbeitungsverlauf, Farbmarkierungen, Software-Daten|JPEG, PNG, TIFF, PSD, AI, PDF|
|**ICC-Farbprofile**|Farbkalibrierung, z. B. sRGB, AdobeRGB, ISO Coated v2|TIFF, JPEG, PNG, PDF, AI|

### Warum sind Metadaten wichtig?

- **Organisation & Suche** in Datenbanken
    
- **Urheberrecht** & Lizenzinformationen
    
- **Bearbeitung & Softwareverlauf dokumentieren**
    
- **Druckdaten konsistent halten (Farbprofil)**
    
- **Geodaten für Archivierung oder Social Media**
    

### Best Practices für Metadaten

1. **Metadaten bewusst pflegen** (Titel, Urheber, Schlagwörter)
    
2. **Datenschutz beachten**: z. B. GPS-Daten entfernen
    
3. **EXIF, IPTC, XMP standardisiert nutzen**
    
4. **Metadatenfreundliche Tools verwenden** (Photoshop, Lightroom, Bridge)
    
5. **Farbprofile korrekt einbetten**
    

### Tools zur Metadatenbearbeitung

|Tool|Plattform|Funktion|
|---|---|---|
|**Adobe Bridge**|Windows/macOS|Professionelles Metadaten-Management|
|**ExifTool**|Alle OS|Kommandozeile, alles bearbeitbar|
|**XnView MP**|Multiplattform|Lesen/Bearbeiten von EXIF/IPTC/XMP|
|**Darktable / RawTherapee**|Linux/macOS/Windows|RAW-Verwaltung mit Metadatenpflege|

---

## Prüfungsaufgaben

![Aufgabe](https://media.discordapp.net/attachments/965390114601701376/1353085833233829919/Bildschirmfoto_2025-03-12_um_19.png?ex=67feb161&is=67fd5fe1&hm=f932efb456ed5d040be3412120c34fc4d74529fb058f0bddf52eaad01eb833c9&=&format=webp&quality=lossless&width=1115&height=684)
