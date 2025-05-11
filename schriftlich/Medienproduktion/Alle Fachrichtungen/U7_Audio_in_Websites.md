---
title: Audio in Websites
tags:
  - Medienproduktion/Alle-Fachrichtungen/Audio-in-Websites
kapitel: Alle Fachrichtungen
bereich: Medienproduktion
status: erledigt
---
# Audio in Websites
>[!summary] Definition
>In Websites wird Audio genutzt, um Inhalte lebendiger zu gestalten – sei es durch Musik, Sprachinhalte, Soundeffekte oder interaktive Elemente. Damit Ton im Web reibungslos funktioniert, braucht es neben dem technischen Einbau auch ein gutes Verständnis der Audio-Grundlagen und der Besonderheiten bei der Bereitstellung für das Web.

---

## 1. Aufbau digitaler Audiodateien

Damit analoger Ton digital gespeichert und wiedergegeben werden kann, wird er in viele kleine Teile zerlegt. Diese Digitalisierung basiert auf drei zentralen Parametern:

> [!definition] Abtastrate (Sampling Rate)
> Sie gibt an, wie oft pro Sekunde ein Messwert (Sample) des analogen Signals genommen wird.  
> Einheit: Hertz (Hz)  
> Beispiel: CD-Qualität = 44.100 Hz (d.h. 44.100 Messungen pro Sekunde)

> [!definition] Bittiefe (Bit Depth)
> Sie gibt an, wie genau jedes einzelne Sample gespeichert wird, also wie viele Werte pro Sample möglich sind.  
> Übliche Werte: 16 Bit (CD), 24 Bit (Studio), 8 Bit (einfache Anwendungen)

> [!definition] Kanäle
> Audio kann monophon (1 Kanal) oder stereophon (2 Kanäle) sein. Mehrkanalformate wie 5.1 Surround sind seltener im Web-Kontext.

---

## 2. Rechenbeispiel: Unkomprimierte Audiodatei

Berechnung der Dateigröße:

```

Dateigröße = Abtastrate × Bittiefe × Kanäle × Dauer

```

**Beispiel:**  
Ein 3-minütiges Stereo-Audio in CD-Qualität (44.100 Hz, 16 Bit):

```

44.100 × 16 × 2 × 180 = 254.016.000 Bit = 31.752.000 Byte ≈ 30,28 MB

```

> [!important] Unkomprimiertes Audio ist sehr speicherintensiv – Komprimierung ist fürs Web fast immer notwendig.

---

## 3. Kompression: Verlustfrei vs. verlustbehaftet

**Verlustfreie Formate:** FLAC, ALAC  
→ Gut für Archivierung, zu groß für Websites.

**Verlustbehaftete Formate:** MP3, AAC, OGG  
→ Entfernen unhörbare Details, sparen stark Speicherplatz.

**Beispiel:**  
MP3-Datei mit 128 kbps für 3 Minuten:

```

128.000 Bit/s × 180 s = 23.040.000 Bit = 2.880.000 Byte ≈ 2,75 MB

```

---

## 4. Audio-Codecs und Web-Kompatibilität

| Format | Codec                | Komprimierung   | Browser-Kompatibilität        | Bemerkung                                |
| :----- | :------------------- | :-------------- | :---------------------------- | :--------------------------------------- |
| MP3    | MPEG-1 Audio Layer 3 | Verlustbehaftet | Alle Browser                  | Standard, universell                     |
| AAC    | Advanced Audio Codec | Verlustbehaftet | Sehr gut, außer Firefox/Linux | Hohe Qualität bei kleinen Datenmengen    |
| OGG    | Vorbis               | Verlustbehaftet | Alle außer Safari             | Open Source, gut komprimierbar           |
| WAV    | PCM                  | Unkomprimiert   | Alle Browser                  | Große Dateien, sehr gute Qualität        |
| Opus   | Opus                 | Verlustbehaftet | Sehr gut                      | Besonders effizient bei Sprache & WebRTC |

> [!tip] Weitere Infos: [MDN Audio Codecs Übersicht](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Audio_codecs)

---

## 5. Vorbereitung fürs Web: Audio komprimieren & streamen

### Schritte zur Vorbereitung

1. Bearbeitung: Audio ggf. kürzen, normalisieren, Stille entfernen.
2. Export: In einem webfreundlichen Format (z. B. MP3, AAC, Opus).
3. Bitrate wählen:
   - Sprache: 64–96 kbps
   - Musik: 128–192 kbps
   - Höhere Bitraten für Premiumqualität

### Streaming-Bedingungen

- Geringe Puffergröße für schnelle Wiedergabe.
- Konstante Bitrate (CBR) für stabileres Streaming.
- Latenzarme Codecs wie Opus bevorzugen.

**Beispiel:** Optimale MP3 für Sprachstreaming

```

64 kbps, mono, 44.100 Hz, 2 Minuten = 64.000 × 120 = 7.680.000 Bit = 960.000 Byte ≈ 0,92 MB

````

---

## 6. Audio in HTML einbinden

Das `<audio>`-Element wird verwendet, um Audio in Webseiten einzubetten:

```html
<audio controls>
  <source src="audio-datei.mp3" type="audio/mpeg">
  <source src="audio-datei.ogg" type="audio/ogg">
  Ihr Browser unterstützt das Audio-Element nicht.
</audio>
````

**Erklärung:**

- `controls`: Zeigt Standard-Bedienelemente an (Play, Pause, Lautstärke).
    
- `<source>`: Gibt alternative Formate an.
    
- Text nach den `<source>`-Elementen: Fallback-Nachricht.
    

### Optional: Autoplay & Loop

```html
<audio src="sound.mp3" autoplay loop muted></audio>
```

**Attribute:**

- `autoplay`: Startet automatisch (nur erlaubt, wenn `muted` gesetzt ist).
    
- `loop`: Spielt die Datei in einer Endlosschleife ab.
    
- `muted`: Startet ohne Ton (erforderlich für Autoplay).
    

> [!tip] Für beste Kompatibilität: Immer MP3 bereitstellen, optional zusätzlich OGG oder AAC.  
> Für professionelle Webprojekte: Technischer Fallback wie z. B. ein Download-Link oder ein JS-Player wie [Howler.js](https://howlerjs.com/).

---

## Fazit

Audio fürs Web sollte möglichst klein und trotzdem qualitativ hochwertig sein. Ein gutes Verständnis von Sampling, Bitraten und Formaten hilft, eine Balance zwischen Dateigröße und Klangqualität zu finden. Wichtige Aspekte sind Browserkompatibilität und Ladezeiten.
