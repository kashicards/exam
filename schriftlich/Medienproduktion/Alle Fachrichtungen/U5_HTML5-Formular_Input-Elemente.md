---
title: HTML5-Formular Input-Elemente
tags:
  - Medienproduktion/Alle-Fachrichtungen/HTML5-Formular
kapitel: Alle Fachrichtungen
bereich: Medienproduktion
status: erledigt
---
# HTML5-Formular Input-Elemente

> [!summary]
> Interaktive Eingabefelder in HTML, z. B. für Text, Passwörter oder Dateien.


- formular attribute
- input type
- zusätzliche attribute validierung 
- erstelle fomular dass bedingung x erfüllt
- quellcode kriegen, was kann man für eingaben tätigen, welche beschränkungen etc
- 2geteilt
	- theoretisch
		- nenne 3 anwendungsfälle
			- login
			- terminvereinbarung
			- bestellung
		- gefahren bei formularen
	- praktisch
		- code vervollständigen damit x passiert
		- grafik mit formular und dazu quellcode
		- fehlerhaftes form

- form
	- attribute
		- action - ziel-url bzw dateiname
		- get/post - binärdaten, header, get beschränkt

> [!warning] 28.04.2025



## Einführung

>[!summary]  Definition
>HTML5-Formulare machen Webseiten interaktiv. Sie ermöglichen es Nutzern, Daten einzugeben – z. B. bei einem Rückmeldeformular – die dann an einen Server gesendet werden. Damit sind sie ein wichtiges Kommunikationsmittel zwischen Website und Benutzer.

---

## Grundstruktur eines Formulars

```html
<form action="ziel-url" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
  <input type="submit" value="Absenden">
</form>
```

## Gängige Input-Typen

| Typ      | Beschreibung                                                   | Beispiel                                                  |
| -------- | -------------------------------------------------------------- | --------------------------------------------------------- |
| text     | Einfaches Texteingabefeld                                      | `<input type="text" name="name">`                         |
| password | Passworteingabe, Eingabe wird verborgen                        | `<input type="password" name="passwort">`                 |
| number   | Eingabe von Zahlen, kann mit min/max/step eingeschränkt werden | `<input type="number" name="alter" min="18">`             |
| email    | Validiert eine Mail-Adresse                                    | `<input type="email" name="email">`                       |
| date     | Datumsauswahl                                                  | `<input type="date" name="geburtsdatum">`                 |
| checkbox | Auswahlfeld (mehrere möglich)                                  | `<input type="checkbox" name="akzeptieren">`              |
| radio    | Auswahl einer von mehreren Optionen                            | `<input type="radio" name="geschlecht" value="männlich">` |
| file     | Datei-Upload                                                   | `<input type="file" name="upload">`                       |
| submit   | Button zum Absenden                                            | `<input type="submit" value="Absenden">`                  |
| reset    | Button zum Zurücksetzen                                        | `<input type="reset" value="Zurücksetzen">`               |
| search   | Spezielles Textfeld für Suchbegriffe                           | `<input type="search" name="suche">`                      |

### Attribute für Input-Felder
| Attribut                 | Pflicht / Freiwillig | Bedeutung                                                                       | Beispiel                                           |
| ------------------------ | -------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------- |
| `name`                   | **Pflicht**          | Name des Feldes – wird beim Absenden an den Server mitgesendet                  | `<input type="text" name="username">`              |
| `id`                     | **Freiwillig**       | Eindeutige Kennung – besonders für Verknüpfung mit `<label>` wichtig            | `<input type="text" id="email">`                   |
| `placeholder`            | **Freiwillig**       | Platzhaltertext im Eingabefeld (nur optische Hilfe, keine echte Eingabeprüfung) | `<input type="text" placeholder="Dein Name">`      |
| `value`                  | **Freiwillig**       | Vorgabewert, der beim Laden bereits eingetragen ist                             | `<input type="text" value="Max Mustermann">`       |
| `required`               | **Freiwillig**       | Macht das Feld zu einem Pflichtfeld für den Benutzer (HTML5-Validierung)        | `<input type="email" required>`                    |
| `min`, `max`             | **Freiwillig**       | Begrenzen erlaubte Zahlen- oder Datumsbereiche                                  | `<input type="number" min="1" max="10">`           |
| `minlength`, `maxlength` | **Freiwillig**       | Definieren die erlaubte Mindest- oder Maximalanzahl von Zeichen                 | `<input type="text" minlength="3" maxlength="20">` |
| `step`                   | **Freiwillig**       | Gibt die Schrittweite für Zahlenfelder an (z.B. 0.5 oder 10er-Schritte)         | `<input type="number" step="0.5">`                 |
| `pattern`                | **Freiwillig**       | Validiert Eingaben über einen regulären Ausdruck                                | `<input type="text" pattern="[A-Za-z]{3,}">`       |
## Label 

Ein korrekt verbundenes `<label>` verbessert die Barrierefreiheit. Es zeigt dem Nutzer, was in ein Eingabefeld gehört – besonders wichtig für Screenreader.

```html
<label for="username">Benutzername:</label> <input type="text" id="username" name="username">
```

- Das `for`-Attribut im Label verweist auf die `id` des Eingabefeldes.
    
- Erhöht die Benutzerfreundlichkeit, besonders bei Assistenztechnologien.
    

---

## Gruppierung von Formularfeldern

Verwende `<fieldset>` und `<legend>`, um verwandte Eingaben logisch zu gruppieren.

```html
<fieldset>   
	<legend>Persönliche Daten</legend>   
	<label for="vorname">Vorname:</label>   
	<input type="text" id="vorname" name="vorname">   
	<label for="nachname">Nachname:</label>   
	<input type="text" id="nachname" name="nachname"> 
</fieldset>
```
---

## Textarea

```html
<textarea name="kommentar" rows="4" cols="50" placeholder="Dein Kommentar"></textarea>`
```
---

## Dropdown-Menüs

```html
<select name="anrede">   
	<option value="herr">Herr</option>   
	<option value="frau">Frau</option>   
	<option value="weitere">Weitere</option> 
</select>
```
---

## Submit & Reset Buttons

- **Absenden**:
    ```html 
    <input type="submit" value="Absenden">`
    ```
    
- **Zurücksetzen**:
	  ```html
	  <input type="reset" value="Zurücksetzen">
	  ```

---

## Formulareigenschaften

| Attribut         | Funktion                                                                          | Detaillierte Erklärung                                                                                                                                                                                                                                                                     | Beispiel                               |
| ---------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------- |
| `action`         | Gibt die Ziel-URL an, an die die Formulardaten gesendet werden.                   | - **Absolut**: Daten werden an eine komplette URL geschickt (`https://example.com/save.php`).<br>- **Relativ**: Daten bleiben auf derselben Domain (`/api/save.php`).<br>- **Leer**: Senden an dieselbe Seite (Seiten-Reload).                                                             | `<form action="/api/reviews.php">`     |
| `method="get"`   | Formulardaten werden an die URL angehängt und über die URL-Parameter übermittelt. | - **Sichtbar** in der Adresszeile (`/search?q=term`).<br>- **Ungeeignet** für vertrauliche Daten (Login etc.).<br>- **Cache-fähig** und über URL teilbar.- **Längenbeschränkung** je nach Browser (z.B. 2048 Zeichen).<br>- Typisch für **Suchformulare**, **Filter**.                     | `<form action="/search" method="get">` |
| `method="post"`  | Formulardaten werden im HTTP-Body übertragen (nicht sichtbar in der URL).         | - **Geeignet** für vertrauliche oder viele Daten.<br>- Keine sichtbaren Formulardaten in der Adresszeile.- **Nicht cache-fähig**.<br>- Typisch für **Login-Formulare**, **Datei-Uploads**, **Kontaktformulare**.<br>- **Beliebige Datenmenge** (abhängig vom Server).                      | `<form action="/login" method="post">` |
| `accept-charset` | Gibt an, welche Zeichenkodierung für die Datenübertragung verwendet wird.         | - **Standard:** UTF-8 (unterstützt internationale Zeichen, Emojis, Umlaute).<br>- Falls z.B. ältere Systeme erforderlich sind: ISO-8859-1.- Verhindert Encoding<br>-Fehler bei Sonderzeichen.<br>- Besonders wichtig bei **mehrsprachigen Formularen** oder **internationalen Webseiten**. | `<form accept-charset="UTF-8">`        |

### Wichtige Unterschiede `GET` vs. `POST`

| Merkmal      | `GET`                                               | `POST`                                              |
| ------------ | --------------------------------------------------- | --------------------------------------------------- |
| Sichtbarkeit | Daten sind **sichtbar** in der URL                  | Daten sind **unsichtbar** (HTTP-Body)               |
| Sicherheit   | **Unsicher** (nichts Vertrauliches)                 | **Sicherer** (für vertrauliche Infos)               |
| Datenmenge   | Begrenzt (z.B. 2048 Zeichen)                        | Größere Datenmengen möglich (z.B. bei Dateiuploads) |
| Caching      | Ja (Seite kann im Browser-Cache gespeichert werden) | Nein (Server verarbeitet neue Anfrage)              |
| Nutzung      | Suchformulare, Navigation, Filter                   | Logins, Formulare mit Dateiuploads, sensible Daten  |

### Komplettes Beispiel-Formular (Best Practice)

```html
<form action="/api/reviews.php" method="post" accept-charset="UTF-8">
  <label for="username">Benutzername:</label>
  <input id="username" name="username" type="text" required>

  <label for="review">Bewertung:</label>
  <textarea id="review" name="review" minlength="10" maxlength="500" required></textarea>

  <button type="submit">Absenden</button>
</form>
```


---

## Fragen & Antworten

**Welches HTML-Element wird verwendet, um ein Formular zu erstellen?**  
```html
<form>
```

**Welcher Input-Typ wird für die Eingabe eines Passworts verwendet?**  
```html
<input type="password">
```

**Was ist die Standard-Breite eines input-Feldes?**  
So breit wie nötig (standardmäßig angepasst durch den Browser)

**Was bewirkt das Attribut `placeholder`?**  
Zeigt einen Hilfetext, der verschwindet, wenn der Nutzer tippt.

**Welches Attribut macht ein Feld verpflichtend?**  
```html
required
```

**Was macht das `pattern`-Attribut?**  
Validiert die Eingabe anhand eines regulären Ausdrucks.