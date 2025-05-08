---
title: Navigationsarten
tags:
  - Konzeption-und-Gestaltung/Schwerpunkt-Digital/Navigationsarten
kapitel: Schwerpunkt Digital
bereich: Konzeption und Gestaltung
status: erledigt
---
# Navigationsarten
## 1. Definition der Navigation

> [!summary] Definition  
> Navigation bezeichnet die Art und Weise, wie sich Nutzer innerhalb einer digitalen oder physischen Umgebung orientieren und bewegen können. Ziel ist es, Inhalte schnell und effizient zu erreichen.

 **Website-Navigation** ist der Prozess, wie Nutzer durch eine Website oder Webanwendung geführt werden.  
 
Ziel: Die Navigation soll Nutzern helfen, schnell das zu finden, was sie suchen – ohne sich zu verirren.

Navigation erfolgt typischerweise durch:

- Menüs
- Links
- Buttons
- Suchfelder
- Chatbots (z. B. zur geführten Navigation)


---

## 2. Strukturtypen – Grundlage jeder Navigation

|Strukturtyp|Beschreibung|Vorteile|Nachteile / Grenzen|Einsatzbeispiele|
|---|---|---|---|---|
|Hierarchisch|Baumstruktur mit Haupt-/Unterseiten|Logisch, skalierbar|Komplexität bei vielen Ebenen|Firmenwebsites, Wissensportale|
|Linear|Schritt-für-Schritt durch Inhalte|Klarer Ablauf|Kein freies Springen|Onboarding, Formulare, Tutorials|
|Matrix|Flexible Querverlinkung ohne Hierarchie|Querbrowsing, thematische Vielfalt|Orientierung kann verloren gehen|Wikis, Lernplattformen|
|Sitemap / Megamenü|Komplette Übersicht aller Seiten|Schnellzugriff|Unübersichtlich bei vielen Einträgen|Große Portale|
|Suchfeld|Direkte Eingabe von Suchbegriffen|Schnell bei klarer Vorstellung|Funktioniert nur bei guter Suchfunktion|FAQs, Shops, Datenbanken|

**Weitere Strukturtypen:**
- **Netzstruktur:** viele freie Querverlinkungen
- **See-and-Point:** visuelle Auswahl ohne Menüs
- **Matrixstruktur:** mehrdimensionale Organisation durch Links und Buttons


---

## 3. Navigationsarten im Überblick

|Navigationsart|Beschreibung|Vorteile|Nachteile|
|---|---|---|---|
|Strukturelle Navigation|Zugriff auf verschiedene Bereiche der Website|Strukturierte Nutzerführung|Kann bei vielen Ebenen unübersichtlich wirken|
|Globale Navigation|Immer sichtbar, z. B. Header-Menü|Hohe Benutzerfreundlichkeit|Kann auf mobilen Geräten Platz beanspruchen|
|Lokale Navigation|Navigation innerhalb einer Kategorie oder Unterseite|Detaillierte Unterteilung möglich|Gefahr der Überforderung|
|Kontextuelle Navigation|Verlinkt verwandte Inhalte („Mehr dazu …“)|Fördert Entdecken, verbessert SEO|Kann Nutzer ablenken|
|Sequenzielle Navigation|Schrittweise Führung durch einen Prozess|Ideal für komplexe Abläufe|Eingeschränkte Bewegungsfreiheit|
|Suchnavigation|Durchsuchbare Inhalte mit Autovervollständigung|Schnell bei großer Content-Menge|Nur bei richtigen Suchbegriffen effektiv|
|Adaptive Navigation|Passt sich dem Nutzungsverhalten an|Individuelle Nutzererfahrung|Datenschutzbedenken, technisch anspruchsvoll|

**Zusatz:**
- **Conversational UI (z. B. Chatbot):** Navigation durch Gespräche
- **Gamifizierte Navigation:** Spielerische Gestaltung der Navigation
- **In-Picture-Navigation:** Klickbare Bereiche direkt auf Bildern

---

## 4. Hauptnavigationsarten im Web

|Navigationsart|Funktion / Vorteile|Nachteile / Grenzen|Einsatzbereiche|
|---|---|---|---|
|Hauptnavigation|Zentrale Menüleiste|Begrenzter Platz|Unternehmensseiten, E-Commerce|
|Unternavigation|Ergänzt Hauptnavigation|Überforderung bei schlechter Struktur|Webshops, Infoportale|
|Footer-Navigation|Rechtliche Infos, sekundäre Links|Wird oft übersehen|Impressum, Datenschutz|
|Breadcrumb-Navigation|Pfad zur aktuellen Seite|Nur bei hierarchischen Strukturen sinnvoll|Produktseiten, Blogs, Dokumentationen|
|Burger-Menü (mobil)|Kompaktes Menü-Icon auf Smartphones|Zusätzlicher Klick nötig, weniger auffällig|Mobile Seiten, Apps|
|Sticky Navigation|Fixiert beim Scrollen|Kann Platz kosten|Onepager, lange Seiten|
|Call-to-Action|Visuelle Buttons für Handlung|Nicht zur Orientierung gedacht|Landingpages, Marketing|
|Lineare Navigation|Schrittweise Navigation|Kein freies Springen|Tutorials, Kaufprozesse|

**Zusatz :**
- **Mega-Menü:** Großflächiges Menü mit mehreren Spalten, bei Hover oder Klick
- **Multi-Level-Menü:** Vertikale Navigation mit aufklappbaren Unterpunkten
- **Off-Canvas-Menü:** Menü schiebt sich bei Klick seitlich herein
- **Mobile Button-Menü:** Große Buttons unten für Daumenfreundlichkeit
- **Anchor-Link-Navigation:** Innerhalb einer Seite springen (Onepager)

---

## 5. HTML & CSS für Navigation

### HTML-Grundstruktur

```html
<nav>
  <ul>
    <li><a href="index.html">Startseite</a></li>
    <li><a href="about.html">Über uns</a></li>
    <li><a href="contact.html">Kontakt</a></li>
  </ul>
</nav>
```

### Einfaches CSS-Styling

```css
nav ul {
  list-style-type: none;
  padding: 0;
  background-color: #333;
  display: flex;
}

nav ul li {
  padding: 10px 20px;
}

nav ul li a {
  color: white;
  text-decoration: none;
}

nav ul li a:hover {
  background-color: #555;
}
```

### CSS-Positionierung

#### 1. Fixed Navigation

```css
nav {
  position: fixed;
  top: 0;
  width: 100%;
  background-color: #333;
}
```

Vorteile: Immer sichtbar  
Nachteile: Kann Inhalte überdecken

#### 2. Sticky Navigation

```css
nav {
  position: sticky;
  top: 0;
  background-color: #333;
}
```

Vorteile: Sichtbar beim Scrollen  
Nachteile: Browserkompatibilität beachten

#### 3. Relative Navigation

```css
nav {
  position: relative;
}
```

Vorteile: Einfach umsetzbar  
Nachteile: Scrollt mit dem Inhalt weg

#### 4. Absolute Navigation

```css
nav {
  position: absolute;
  top: 10px;
  left: 50px;
}
```

Vorteile: Frei positionierbar  
Nachteile: Kann zu Layout-Problemen führen

---

## 6. Best Practices für Navigation

- Klare, verständliche Menüpunkte
    
- Maximal 7–9 Hauptpunkte
    
- Einheitliches Design
    
- Responsive Gestaltung für Mobilgeräte
    
- Einsatz von Breadcrumbs bei tiefen Seitenstrukturen
    
- ARIA-Rollen, Tastaturnavigation und ausreichende Kontraste für Barrierefreiheit
    

**Zusätze :**
- Konsistenz: Navigation sollte auf allen Seiten einheitlich bleiben.
- Vermeidung von Überladung: Nicht zu viele Menüpunkte auf einmal zeigen.
- Mobile Optimierung: Touchscreen-freundliche Navigationselemente.

---

## 7. Kontrollfragen zur Selbstüberprüfung

1. Was unterscheidet eine hierarchische von einer Matrixstruktur?
    
2. Warum ist ein Burger-Menü auf dem Desktop nicht ideal?
    
3. Welche Rolle spielt die Zielgruppe bei der Wahl der Navigation?
    
4. Welche Probleme treten bei schlechter Unternavigation auf?
    
5. Warum sind Breadcrumbs nicht für alle Websites geeignet?
    

---

## 8. Mini-Quiz: Was passt wozu?

|Szenario|Lösung|
|---|---|
|Nutzer soll durch 5 Schritte im Kaufprozess geführt werden|Lineare Navigation|
|Themen in einer Wissensdatenbank flexibel anwählen|Matrixstruktur|
|Orientierung auf einem Onepager|Sticky Navigation|
|Mobile Nutzer brauchen Übersicht|Burger-Menü (mobil)|
|Nutzer möchte wissen, wo er sich befindet|Breadcrumb-Navigation|
