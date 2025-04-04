---
title: Audio in Websites
tags:
  - Medienproduktion
---
# Audio in Websites

## Unterstützte Audioformate im Web

Moderne Webbrowser unterstützen verschiedene Audioformate. Die gängigsten sind:

|Format|Dateiendung|Beschreibung|
|---|---|---|
|MP3|.mp3|Weit verbreitet, hohe Kompatibilität, gute Komprimierung|
|WAV|.wav|Unkomprimiert, hohe Qualität, große Dateigröße|
|OGG|.ogg|Offenes Format, gute Qualität, kleinere Dateigröße|
|AAC|.aac|Bessere Qualität als MP3 bei gleicher Bitrate, oft in mobilen Geräten genutzt|
|FLAC|.flac|Verlustfreie Kompression, hohe Qualität, größere Dateien|

## Einbindung von Audio auf Websites

### HTML-Tags für Audio

Das `<audio>`-Tag ermöglicht das Einbinden von Audio-Dateien direkt in HTML.

Beispiel:

```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
  <source src="audio.ogg" type="audio/ogg">
  Ihr Browser unterstützt kein Audio-Tag.
</audio>
```

### Steuerung mit JavaScript

Audio-Elemente lassen sich mit JavaScript steuern:

```js
const audio = document.querySelector("audio");
audio.play(); // Startet die Wiedergabe
audio.pause(); // Pausiert die Wiedergabe
audio.volume = 0.5; // Setzt die Lautstärke auf 50%
```

## Sicherheitsrichtlinien für Audio-Dateien

### Einschränkungen bei Autoplay

- **Chrome und andere moderne Browser blockieren Autoplay**, es sei denn:
    
    - Der Nutzer hat mit der Seite interagiert (z. B. geklickt).
        
    - Die Wiedergabe erfolgt **stumm** (`muted autoplay`).
        

Beispiel für Autoplay mit Stummschaltung:

```html
<audio autoplay muted>
  <source src="audio.mp3" type="audio/mpeg">
</audio>
```

### Weitere Sicherheitsaspekte

- **CORS-Richtlinien beachten**, wenn Audio von externen Quellen geladen wird.
    
- **Vermeidung schadhafter Dateien**, indem nur sichere Quellen genutzt werden.
    
- **Keine unnötig großen Dateien**, um Ladezeiten zu optimieren.
    

Durch diese Richtlinien kann Audio sicher und effizient in Websites eingebunden werden.