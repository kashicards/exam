---
title: ERM
tags:
  - Konzeption-und-Gestaltung/Alle-Fachrichtungen/ERM
kapitel: Alle Fachrichtungen
bereich: Konzeption und Gestaltung
---
# Entity-Relationship-Modell (ER-Modell)

> [!abstract]  Definition
> Das Entity-Relationship-Modell (ER-Modell) ist ein konzeptionelles Modell zur Beschreibung von Daten und deren Beziehungen in einem System. Es bildet die Grundlage für das Design relationaler Datenbanken.

---
## 1. Ziel und Zweck des ER-Modells

- Visualisierung von **Informationsstrukturen**
    
- Ermittlung relevanter **Objekte**, deren **Eigenschaften** und **Beziehungen**
    
- Grundlage für die spätere **relationale Datenbankstruktur**
- **komplexe Datenbankstrukturen** planen und umzusetzen
    

> [!important]  
> Das ER-Modell beschreibt **was** gespeichert werden soll – nicht **wie** es technisch umgesetzt wird.

---

## 2. Grundelemente des ER-Modells

### 2.1 Entitäten & Entitätsmengen

- Eine **Entität** ist ein identifizierbares Objekt der realen Welt.
    
- Eine **Entitätsmenge** ist die Sammlung gleichartiger Entitäten.

> [!example]  
> Entität: _Buch_  
> Entitätsmenge: _Alle Bücher einer Bibliothek_

> [!example] Beispiel
> ![Entitäten](https://blog.assets.studyflix.de/wp-content/uploads/2023/11/Grafische-Darstellung-von-Entitaeten-1-1024x576.png)
### 2.2 Attribute

Merkmale bzw. Eigenschaften von Entitäten oder Beziehungen.

#### Typen von Attributen:

|Typ|Beschreibung|Beispiel|
|---|---|---|
|Einfach|Nicht weiter zerlegbar|Vorname|
|Zusammengesetzt|Besteht aus Teilwerten|Adresse (Straße, Ort, PLZ)|
|Mehrwertig|Mehrere Werte möglich|Telefonnummern|
|Abgeleitet|Kann berechnet werden|Alter aus Geburtsdatum|
|Schlüsselattribut|Dient zur eindeutigen Identifizierung|Kundennummer|

> [!note]  
> Schlüsselattribute werden im ER-Modell **unterstrichen** dargestellt.

> [!example] Beispiel
> ![Attribute](https://blog.assets.studyflix.de/wp-content/uploads/2023/11/Grafische-Darstellung-von-Attributen-1-1024x576.png)
### 2.3 Beziehungen (Beziehungsmengen)

- Beziehungen verbinden Entitäten untereinander.
    
- Die Beziehung selbst kann ebenfalls Attribute haben.
    

> [!example]  
> Ein Kunde **kauft** ein Produkt. → `Kunde` — `kauft` — `Produkt`  
> Kaufdatum könnte als Attribut zur Beziehung `kauft` gehören.

> [!example] Beispiel
> ![Beziehung](https://blog.assets.studyflix.de/wp-content/uploads/2023/11/Grafische-Darstellung-von-Beziehungen-1-1024x576.png)

---

## 3. Kardinalitäten

> [!summary] Definition
> Die **Kardinalität** beschreibt, **wie viele Entitäten** einer Entitätsmenge an einer Beziehung beteiligt sein können.

### 3.1 Bedeutung

|Symbolisch|Beschreibung|Beispiel|
|---|---|---|
|1:1|Eine Entität A ist mit einer Entität B verknüpft|Person – Personalausweis|
|1:n|Eine Entität A ist mit mehreren B verknüpft|Kunde – Bestellungen|
|n:m|Viele A mit vielen B verknüpft|Schüler – Kurse|

> [!important]  
> Die Kardinalität ist entscheidend für die spätere Umsetzung in Tabellen und für das Setzen von Fremdschlüsseln.

### 3.2 Notation im ER-Modell

|Darstellung (grafisch)|Bedeutung|
|---|---|
|`|` (Strich)|
|`0..1` oder `O`|optional, höchstens 1|
|`*` oder `N`|viele (0 oder mehr)|
|`1..*`|mindestens 1|

> [!tip]  
> Manche Notationen (z. B. UML) verwenden Zahlenbereiche wie `0..1`, `1..*`, während andere (z. B. Chen) symbolisch arbeiten (`1`, `N`).

### 3.3 Kardinalität in Worten

- **(0,1)** – Optional, maximal eine Zuordnung
    
- **(1,1)** – Zwingend genau eine Zuordnung
    
- **(0,N)** – Optional, beliebig viele
    
- **(1,N)** – Zwingend mindestens eine

> [!example] Beispiel
> ![Kardinalitäten](https://blog.assets.studyflix.de/wp-content/uploads/2023/11/Beispiel-Kardinalitaet-1n-1-1024x576.png)

---

## 4. Notation: Chen-Modell

| Symbol      | Bedeutung                             |
| ----------- | ------------------------------------- |
| Rechteck    | Entität                               |
| Ellipse     | Attribut                              |
| Raute       | Beziehung                             |
| Linie       | Verknüpfung zwischen Objekten         |
| Doppellinie | Totalität (z. B. zwingende Beziehung) |
| Unterstrich | Schlüsselattribut                     |

> [!example] Beispiel
> 
>![Chen-Modell](https://blog.assets.studyflix.de/wp-content/uploads/2023/11/Chen-Notation-1-1024x576.png)

---

## 5. Schlüsselkonzepte: Primär- & Fremdschlüssel

### 5.1 Primärschlüssel

- Attribut(e), das/die eine Entität eindeutig identifizieren
    
- Wird **unterstrichen** notiert
    
- Muss **eindeutig** und **nicht NULL** sein
    

### 5.2 Fremdschlüssel

- Verweist auf den Primärschlüssel einer anderen Entität
    
- Dient zur **Verknüpfung von Tabellen** im relationalen Modell
    

> [!info]  
> In einer 1:n-Beziehung wird der Fremdschlüssel **auf der n-Seite** eingefügt.

---

## 6. Erweiterte Beziehungen

### 6.1 Rekursive Beziehung

- Eine Entität steht mit sich selbst in Beziehung
    

> [!example]  
> Mitarbeiter betreut Mitarbeiter

### 6.2 Ternäre Beziehung

- Beziehung zwischen drei Entitäten
    

> [!example]  
> Arzt verschreibt Medikament an Patienten

---

## 7. Vom ER-Modell zum relationalen Datenbankmodell

|ER-Element|Relationale Umsetzung|
|---|---|
|Entität|Tabelle|
|Attribut|Spalte|
|Beziehung 1:n|Fremdschlüssel in n-Tabelle|
|Beziehung n:m|Zwischentabelle mit zwei FK|
|Schlüsselattribut|PRIMARY KEY|
|Beziehung mit Attributen|Eigene Tabelle|

> [!hint]  
> Attribute einer Beziehung (z. B. `Kaufdatum`) machen aus einer Beziehung eine **eigene Tabelle** im relationalen Modell.

---

## 8. Schritte

- **Entitäten identifizieren**  
    Reale/abstrakte Objekte, über die Daten gespeichert werden (z. B. Mitarbeiter, Werkstattmeister).
    
- **Entitätstypen bestimmen**  
    Gruppierung ähnlicher Entitäten (z. B. alle Mitarbeiter) → als Rechtecke dargestellt.
    
- **Attribute definieren**  
    Eigenschaften der Entitäten (z. B. Name, Gehalt). Primärschlüssel werden unterstrichen, mehrwertige doppelt umkreist.
    
- **Beziehungen festlegen**  
    Verbindungen zwischen Entitäten (z. B. „hat“ zwischen Werkstattmeister und Mitarbeiter) → als Raute dargestellt.
    
- **Kardinalitäten definieren**  
    Anzahl der beteiligten Entitäten:
    
    - 1:1 – genau eine Beziehung
        
    - 1:n – eine Entität zu vielen
        
    - n:m – viele zu vielen (später: Zwischentabelle)
        

---

## 9. Prüfungsaufgaben

![Aufgabe](https://media.discordapp.net/attachments/965389910666276915/1353099749078859827/Bildschirmfoto_2025-03-22_um_21.15.11.png?ex=67fa2117&is=67f8cf97&hm=d23b06be1308aaa3cf7ecc288fba152f1ba9a96a2638aec4e15289654c9c2b00&=&format=webp&quality=lossless&width=1746&height=1139)


