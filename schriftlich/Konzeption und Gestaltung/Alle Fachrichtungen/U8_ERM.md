---
title: ERM
tags:
  - Konzeption-und-Gestaltung/Alle-Fachrichtungen/ERM
kapitel: Alle Fachrichtungen
bereich: Konzeption und Gestaltung
status: erledigt
---
# Entity-Relationship-Modell  (keine Normalisierung)

> [!abstract]  Definition
> Das Entity-Relationship-Modell (ER-Modell) ist ein konzeptionelles Modell zur Beschreibung von Daten und deren Beziehungen in einem System. Es bildet die Grundlage für das Design relationaler Datenbanken.

## 1. Ziel und Zweck des ER-Modells

- Visualisierung von **Informationsstrukturen**
    
- Ermittlung relevanter **Objekte**, deren **Eigenschaften** und **Beziehungen**
    
- Grundlage für die spätere **relationale Datenbankstruktur**
- **komplexe Datenbankstrukturen** planen und umzusetzen



> [!warning]  
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

| Typ                      | Beschreibung                          | Beispiel                   |
| ------------------------ | ------------------------------------- | -------------------------- |
| Einfach                  | Nicht weiter zerlegbar                | Vorname                    |
| Zusammengesetzt          | Besteht aus Teilwerten                | Adresse (Straße, Ort, PLZ) |
| Mehrwertig               | Mehrere Werte möglich                 | Telefonnummern             |
| Abgeleitet               | Kann berechnet werden                 | Alter aus Geburtsdatum     |
| <u>Schlüsselattribut</u> | Dient zur eindeutigen Identifizierung | <u> Kundennummer </u>      |

> [!note]  
> Schlüsselattribute werden im ER-Modell **unterstrichen** dargestellt.

> [!example] Beispiel
> ![Attribute](https://blog.assets.studyflix.de/wp-content/uploads/2023/11/Grafische-Darstellung-von-Attributen-1-1024x576.png)
### 2.3 Beziehungen (Beziehungsmengen)

- Beziehungen verbinden Entitäten untereinander.
    
- Die Beziehung selbst kann ebenfalls Attribute haben.
    

> [!example]  
> Ein Kunde **kauft** ein Produkt. 
> → `Kunde` — `kauft` — `Produkt`  
> `Kaufdatum` könnte als Attribut zur Beziehung `kauft` gehören.


---

## 3. Kardinalitäten

> [!summary] Definition
> Die **Kardinalität** beschreibt, **wie viele Entitäten** einer Entitätsmenge an einer Beziehung beteiligt sein können.

### 3.1 Bedeutung

| Symbolisch | Beschreibung                                     | Beispiel                 |
| ---------- | ------------------------------------------------ | ------------------------ |
| 1:1        | Eine Entität A ist mit einer Entität B verknüpft | Person – Personalausweis |
| 1:n        | Eine Entität A ist mit mehreren B verknüpft      | Kunde – Bestellungen     |
| n:m        | Viele A mit vielen B verknüpft                   | Schüler – Kurse          |

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
    
- Wird <u>unterstrichen</u> notiert
    
- Muss **eindeutig** und **nicht NULL** sein
- muss unveränderbar sein
- besonders wichtig, um Duplikate zu vermeiden und um Daten integrität zu gewährleisten
    

>[!example]
>
> | Produkt_ID   | Produktname | Preis |
> | ------------ | ----------- | ----- |
> | <u> 001 </u> | Smartphone  | 299€  |
> | <u> 002 </u> | Laptop      | 799€  |
> | <u> 003 </u> | Tablet      | 199€  |

### 5.2 Fremdschlüssel

- Verweist auf den Primärschlüssel einer anderen Entität
    
- Dient zur **Verknüpfung von Tabellen** im relationalen Modell (Verbindungspunkte)
- sollten auf gültige Primärschlüssel zeigen, um die Referenzielle Integrität zu gewährleisten
    
>[!example]
>Betrachte die Tabelle 'Bestellungen', die die 'Kunde_ID' als Fremdschlüssel enthält, die auf die Tabelle 'Kunden' verweist:
>
>| Bestell_ID | Kunde_ID                       | Produkt_ID |
|------------|---------------------------------|------------|
| 1001       | <span style="border-bottom: 1px dashed;">001</span>      | 002        |
| 1002       | <span style="border-bottom: 1px dashed;">002</span>      | 003        |
| 1003       | <span style="border-bottom: 1px dashed;">001</span>      | 001        |


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

> [!question] ![Aufgabe](https://media.discordapp.net/attachments/965389910666276915/1353099749078859827/Bildschirmfoto_2025-03-22_um_21.15.11.png?ex=67fa2117&is=67f8cf97&hm=d23b06be1308aaa3cf7ecc288fba152f1ba9a96a2638aec4e15289654c9c2b00&=&format=webp&quality=lossless&width=1746&height=1139)


**Aufgabe U8 (10 Punkte)**

 a) Erläutern Sie den Begriff „relationale Datenbank“. (2 Punkte)

Eine **relationale Datenbank** ist eine Datenbank, die Daten in Tabellenform speichert. Jede Tabelle (Relation) besteht aus Zeilen (Datensätzen) und Spalten (Attributen). Beziehungen zwischen den Tabellen werden über gemeinsame Schlüssel (z. B. Primär- und Fremdschlüssel) hergestellt.  
Ziel ist es, Daten effizient zu verwalten, Redundanzen zu vermeiden und die Konsistenz der Daten sicherzustellen.

b) In relationalen Datenbanken können unterschiedliche Beziehungen auftreten. Erläutern Sie die Beziehungen: (6 Punkte)

In relationalen Datenbanken gibt es folgende Beziehungstypen:

### **1:1-Beziehung (eins zu eins)**

> Ein Datensatz in Tabelle A ist genau einem Datensatz in Tabelle B zugeordnet – und umgekehrt.  
> **Beispiel:** Jeder Mitarbeiter hat genau einen Dienstausweis.

**Beispieltabelle:**

|  **Mitarbeiter**   |             |
| :----------------: | :---------: |
| **Mitarbeiter_ID** |  **Name**   |
|         1          | Max Müller  |
|         2          | Anna Becker |
|         3          | Tom Schmitt |

---

|**Dienstausweis**|
|:-:|:-:|:-:|
|**Ausweis_ID**|**Mitarbeiter_ID** (FK)|**Ausweisnummer**|
|101|1|A1234|
|102|2|B5678|
|103|3|C9101|

→ Jeder Mitarbeiter besitzt genau einen Ausweis und jeder Ausweis gehört genau zu einem Mitarbeiter.

---

### **1:n-Beziehung (eins zu viele)**

> Ein Datensatz in Tabelle A kann mit mehreren Datensätzen in Tabelle B verknüpft sein, aber jeder Datensatz in Tabelle B gehört nur zu genau einem Datensatz in Tabelle A.  
> **Beispiel:** Ein Autor schreibt mehrere Bücher, aber jedes Buch wird nur von einem Autor geschrieben.

**Beispieltabelle:**

|**Autor**|
|:-:|:-:|:-:|
|**Autor_ID**|**Vorname**|**Nachname**|
|1|Ken|Follett|
|2|Charlotte|Link|
|3|Cornelia|Funke|

|  **Buch**   |                     |               |                   |
| :---------: | :-----------------: | :-----------: | :---------------: |
| **Buch_ID** |      **Titel**      |   **ISBN**    | **Autor_ID** (FK) |
|     101     |  Sturz der Titanen  | 3-7857-2406-3 |         1         |
|     102     | Kinder der Freiheit | 3-7857-2510-8 |         1         |
|     103     |   Das andere Kind   | 3-442-3756-2  |         2         |
|     104     |     Tintenherz      | 3-7915-0465-7 |         3         |

→ Ein Autor kann mehrere Bücher geschrieben haben, aber jedes Buch gehört genau zu einem Autor.

---

### **n:m-Beziehung (viele zu viele)**

> Ein Datensatz in Tabelle A kann mit mehreren Datensätzen in Tabelle B verknüpft sein und umgekehrt. Diese Beziehung wird meist über eine Zwischentabelle realisiert.  
> **Beispiel:** Studenten können mehrere Kurse besuchen, und Kurse werden von mehreren Studenten besucht.

**Beispieltabelle:**

|**Student**|
|:-:|:-:|
|**Student_ID**|**Name**|
|1|Lisa Krause|
|2|David Braun|
|3|Emma Vogel|

|**Kurs**|
|:-:|:-:|
|**Kurs_ID**|**Kursname**|
|201|Mathematik|
|202|Informatik|
|203|BWL|

| **Student_Kurs** (Zwischentabelle) |             |
| :--------------------------------: | :---------: |
|           **Student_ID**           | **Kurs_ID** |
|                 1                  |     201     |
|                 1                  |     202     |
|                 2                  |     201     |
|                 2                  |     203     |
|                 3                  |     202     |

→ Ein Student besucht mehrere Kurse und ein Kurs hat mehrere Studenten.

c) Welche Beziehung besteht zwischen den abgebildeten Tabellen? Kennzeichnen Sie diese Beziehung an einem Beispiel. (2 Punkte)

> [!solution]  
> Zwischen den Tabellen **Autor** und **Buch** besteht eine **1:n-Beziehung**:

- **Begründung:**  
    Ein Autor kann mehrere Bücher schreiben, aber jedes Buch hat genau einen Autor.
    
- **Beispiel:**  
    Der Autor **Ken Follett** (Autor_Nr = 001) hat die Bücher „**Sturz der Titanen**“ (Buch_Nr = 0001) und „**Kinder der Freiheit**“ (Buch_Nr = 0006) geschrieben.
    


