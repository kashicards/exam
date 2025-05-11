---
title: DTD-XML
tags:
  - Medienproduktion/Alle-Fachrichtungen/DTD-XML
kapitel: Alle Fachrichtungen
bereich: Medienproduktion
status: erledigt
---
# DTD/XML

> [!summary]
> Definition von Dokumentenstrukturen für XML-Dateien mittels Document Type Definition (DTD).
## XML (Extensible Markup Language)

> [!summary]  Definition
> XML ist keine festgelegte Dokumentenstruktur, sondern eine **Metasprache** zur Definition beliebiger Auszeichnungssprachen.  
> → Wird z. B. für Textdokumente, Vektorgrafiken, multimediale Präsentationen oder Datenbanken eingesetzt.

---

### Regeln und Standards

XML unterliegt nur wenigen festen Regeln. Stattdessen können durch XML eigene Standards definiert werden.

- Klassisch: **DTD (Document Type Definition)**
    
- Modernere Alternativen (ebenfalls XML-basiert):
    
    - XML Schema
        
    - RELAX NG
        

---

### Vorteile von Textdateien gegenüber Binärdateien

Warum XML häufig genutzt wird:

- Inhalte sind **für Menschen lesbar** und mit jedem Texteditor bearbeitbar
    
- Plattformunabhängigkeit
    
- Auch für nicht-technische Nutzer verständlich
    
- Einfacher Austausch mit anderen Programmen oder Versionen
    

> [!info]  
> XML beschreibt **nur die Struktur** der Daten, nicht deren Darstellung.  
> Für Darstellung sind z. B. **XSLT-Dateien** zuständig.

---

### Aufbau von XML

- Hierarchisch aufgebaut (Elemente in anderen Elementen)
    
- Tags werden in spitzen Klammern `<>` geschrieben
    
- Elemente können **Attribute** enthalten
    
- Entweder: öffnendes und schließendes Tag  
    Oder: selbstschließendes Element (`<element />`)
    

#### Beispiel – XML-Deklaration:

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
```

> [!note]
> 
> - `encoding="utf-8"`: Zeichensatz
>     
> - `standalone="yes"`: Kein externes Formatdokument wird verwendet
>     

---

#### Beispiel – XML-Struktur:

```xml
<comics>
  <comic language="en-US">
    <publisher>Marvel</publisher>
    <series>The Amazing Spider-Man</series>
    <issue>1</issue>
    <publicationDate>1963-03-01</publicationDate>
    <characters>
      <character>Spider-Man</character>
      <character>Uncle Ben</character>
      <character>Aunt May</character>
    </characters>
    <price currency="USD">0.12</price>
  </comic>
</comics>
```

> [!tip]  
> Jedes XML-Dokument hat genau **ein Wurzelelement** (hier: `<comics>`), das alle anderen Elemente einschließt.

> [!example]  
> Die Struktur eines XML-Dokuments lässt sich wie ein Baum darstellen:  
> ![XML-Baum](https://openbook.rheinwerk-verlag.de/it_handbuch/bilderklein/klein15_001.png)

---

### Attribute

```xml
<comic language="en-US">
```

> [!warning]  
> Attribute sollten **nicht für komplexe Inhalte** verwendet werden – besser als eigenständige Elemente strukturieren:

**Alternative:**

```xml
<comic>
  <language>en-US</language>
</comic>
```

---

### Entity-Referenzen

> [!danger]  
> Bestimmte Zeichen dürfen nicht direkt verwendet werden und müssen ersetzt werden:

|Zeichen|Ersatz (Entity)|Bedeutung|
|---|---|---|
|`<`|`&lt;`|less than|
|`>`|`&gt;`|greater than|
|`&`|`&amp;`|Ampersand|
|`'`|`&apos;`|Apostroph|
|`"`|`&quot;`|Anführungszeichen|

> [!tip]  
> Alternativ können Unicode-Zeichen direkt angegeben werden:
> 
> - Dezimal: `&#174;`
>     
> - Hexadezimal: `&#xAE;`
>     

---

### CDATA – Rohtext einbinden

> [!info]  
> Normaler Text = PCDATA (parsed character data)  
> Rohtext ohne Interpretation = CDATA

```xml
<codeblock>
  <![CDATA[
    <cover file="simpsons_178.png" type="image/png" />
  ]]>
</codeblock>
```

---

### Kommentare

```xml
<!-- Dies ist ein Kommentar -->
```

> [!note]  
> Kommentare dienen der Dokumentation und werden von Parsern ignoriert.

---

### Wohlgeformtheit (Well-formedness)

> [!important]  
> Ein XML-Dokument muss **wohlgeformt** sein, um verarbeitet werden zu können.

#### Regeln:

- Genau **ein Wurzelelement**
    
- Korrekte **Verschachtelung**
    
- Jedes Element hat ein Start- und End-Tag oder ist selbstschließend (`<element />`)
    
- Attribute: `name="wert"` (Anführungszeichen sind Pflicht!)
    
- Erlaubte Zeichen in Namen:
    
    - Buchstaben, Ziffern, Unterstriche (`_`), Bindestriche (`-`), Punkte (`.`)
        
    - Kein Ziffern-Beginn
        
    - Groß-/Kleinschreibung ist relevant
        
- Sonderzeichen wie `<`, `>`, `&`, `"`, `'` müssen durch Entity-Codes ersetzt werden
    
- CDATA ermöglicht, Sonderzeichen zu verwenden, ohne dass sie interpretiert werden
    

---
## Document Type Definition (DTD)

> [!summary] Definition 
> Eine DTD (Document Type Definition) legt fest, wie ein XML-Dokument strukturiert sein darf.  
> Sie bestimmt:
> 
> - Welche **Elemente** erlaubt sind
>     
> - In welcher **Reihenfolge** diese vorkommen dürfen
>     
> - Welche **Attribute** die Elemente besitzen
>     
> - Welche **Werte** die Attribute haben dürfen
>     

---

### 1. DTD einbinden

Um eine XML-Datei an eine DTD zu binden, verwendet man die `<!DOCTYPE>`-Deklaration vor dem Wurzelelement.

#### Möglichkeiten:

- **System-ID**: Zeigt auf eine DTD-Datei per Pfad oder URL
    
    ```xml
    <!DOCTYPE comics SYSTEM "comics.dtd">
    ```
    
    ```xml
    <!DOCTYPE comics SYSTEM "http://example.com/comics.dtd">
    ```
    
- **Public-ID**: Verweist auf eine standardisierte DTD
    
    ```xml
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN">
    ```
    
    Mit zusätzlicher URL für den Validator:
    
    ```xml
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
        "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    ```
    

> [!note]  
> Die DTD liegt in der Regel als `.dtd`-Datei vor.

---

### 2. Elemente definieren (`<!ELEMENT>`)

#### Grundsyntax

```dtd
<!ELEMENT name (Inhalt)>
```

Beispiel:

```dtd
<!ELEMENT titel (#PCDATA)>
```

> [!info]  
> `#PCDATA` bedeutet: Das Element enthält normalen Text (Parsed Character Data).

---

#### Reihenfolge festlegen

```dtd
<!ELEMENT comic (publisher, format, issue, title, subtitle?, cover?, authors, price)>
```

> [!tip] Regeln zur Reihenfolge:
> 
> - Die Elemente müssen in dieser Reihenfolge auftreten.
>     
> - `?` = optional (0 oder 1 Mal)
>     
> - `+` = mindestens 1 Mal
>     
> - `*` = beliebig oft (auch 0 Mal)
>     

---

#### Alternativen (`|`)

```dtd
<!ELEMENT anschrift (postfach | strasse)>
```

> [!info]  
> Es darf **entweder** `<postfach>` **oder** `<strasse>` enthalten sein.

---

#### Verschachtelte Gruppen

```dtd
<!ELEMENT anschrift (name, (postfach | (strasse, hausnr)), plz, ort)>
```

> [!tip]  
> Kombination von Gruppen und Alternativen ist erlaubt.  
> Dies erlaubt komplexe Strukturvarianten innerhalb eines Elements.

---

#### Text und Elemente kombinieren

```dtd
<!ELEMENT absatz ((#PCDATA | fett | kursiv)+)>
```

> [!info]  
> Text und Elemente können im selben Inhalt vorkommen.  
> Praktisch für formatierten Text, wie z. B. Fließtext mit Fettdruck oder Kursivschrift.

---

### 3. Wiederholungen (`?`, `+`, `*`)

|Symbol|Bedeutung|
|---|---|
|`?`|optional (0 oder 1 Mal)|
|`+`|mindestens 1 Mal|
|`*`|beliebig oft, auch 0 Mal|

#### Beispiel:

```dtd
<!ELEMENT person (anrede, titel*, vorname+, name, geburtsname?)>
```

> [!info]  
> Erlaubt mehrere Vornamen, beliebig viele Titel, und optionalen Geburtsnamen.

---

### 4. Attribute definieren (`<!ATTLIST>`)

#### Grundsyntax

```dtd
<!ATTLIST element attributname attributtyp standardwert>
```

#### Beispiel:

```dtd
<!ATTLIST comic language CDATA #REQUIRED>
<!ATTLIST comic isbn CDATA #IMPLIED>
```

> [!important]  
> Diese Deklaration besagt:
> 
> - `language` muss angegeben werden.
>     
> - `isbn` ist optional.
>     

---

#### Attributtypen

| Typ       | Beschreibung                             | Beispielwert       |
| --------- | ---------------------------------------- | ------------------ |
| CDATA     | Beliebiger Text                          | "Text"             |
| (A\|B\|C) | Nur einer dieser Werte erlaubt           | "A"                |
| NMTOKEN   | Ein einzelnes gültiges XML-Wort          | "name123"          |
| NMTOKENS  | Liste von NMTOKENs                       | "haus garten dach" |
| ID        | Einzigartige Kennung im Dokument         | "elem1"            |
| IDREF     | Verweis auf ein Element mit ID           | "elem1"            |
| IDREFS    | Liste von IDREFs                         | "id1 id2"          |
| ENTITY    | Verweis auf externes Objekt (z. B. Bild) | "bild1"            |
| ENTITIES  | Liste von Entities                       | "bild1 bild2"      |
| NOTATION  | Festgelegte Darstellung (z. B. gif, png) | "png"              |

---

#### Standardwerte für Attribute

| Standardwert | Bedeutung                                                  |
| ------------ | ---------------------------------------------------------- |
| `#REQUIRED`  | Attribut **muss** angegeben werden                         |
| `#IMPLIED`   | Attribut ist optional (kein Standardwert)                  |
| `#FIXED`     | Attribut hat festen Wert (wenn angegeben, dann nur dieser) |
| `"Wert"`     | Wenn kein Wert angegeben ist, wird dieser verwendet        |

Beispiel:

```dtd
<!ATTLIST bild typ CDATA "png">
```

> [!info]  
> Wenn `typ` nicht angegeben wird, wird `"png"` verwendet.

---

### 5. Beispielhafte vollständige DTD

```xml
<!ELEMENT comics (comic+)>
<!ELEMENT comic (publisher, format, issue, title, subtitle?, cover?, authors, price)>
<!ATTLIST comic language CDATA #REQUIRED
                  isbn     CDATA #IMPLIED>

<!ELEMENT publisher (#PCDATA)>
<!ELEMENT format    (#PCDATA)>
<!ELEMENT issue     (#PCDATA)>
<!ATTLIST issue original CDATA #IMPLIED>

<!ELEMENT title     (#PCDATA)>
<!ELEMENT subtitle  (#PCDATA)>

<!ELEMENT cover     EMPTY>
<!ATTLIST cover file CDATA #REQUIRED
                   type CDATA #REQUIRED>

<!ELEMENT authors   (author+)>
<!ELEMENT author    (#PCDATA)>
<!ATTLIST author role CDATA #REQUIRED>

<!ELEMENT price     (#PCDATA)>
<!ATTLIST price currency CDATA #REQUIRED>
```

> [!tip] Strukturhinweis:
> 
> - Immer zuerst das Wurzelelement deklarieren
>     
> - Dann zugehörige Attribute
>     
> - Danach alle untergeordneten Elemente
>     
> - Attribute folgen direkt nach dem zugehörigen Element
>     

---

### 6. Wann reicht DTD aus?

> [!info]
> 
> - Für **einfache XML-Strukturen** ist DTD meist ausreichend
>     
> - Für **komplexe Validierungen** (z. B. Zahlenbereiche, Datumsformate) ist **XML Schema** besser geeignet
>     

---


