---
title: Navigationsarten
tags:
  - Konzeption-und-Gestaltung
---
# Navigationsarten


## 1. Definition der Navigation

>[!summary] Definition
>Navigation bezeichnet die Art und Weise, wie sich Nutzer innerhalb einer digitalen oder physischen Umgebung orientieren und bewegen können. Ziel ist es, Inhalte schnell und effizient zu erreichen.

## 2. Arten der Navigation

### A. Strukturelle Navigation

- Erlaubt den Zugriff auf verschiedene Bereiche einer Website oder Software.
    
- Beispiele:
    
    - Hauptnavigation (z. B. Menüleiste mit Kategorien)
        
    - Footer-Navigation (ergänzende Links am Seitenende)
        
    - Breadcrumbs (Pfad zur aktuellen Seite)
        
- **Vorteile:** Strukturierte und logische Anordnung, verbessert die Nutzerführung.
    
- **Nachteile:** Kann komplex wirken, wenn zu viele Ebenen existieren.
    

### B. Globale Navigation

- Konstant auf jeder Seite verfügbar.
    
- Bietet Zugriff auf zentrale Inhalte und Funktionen.
    
- Beispiel: Hauptmenüs, Header-Menüs.
    
- **Vorteile:** Hohe Benutzerfreundlichkeit, schnelle Orientierung.
    
- **Nachteile:** Kann viel Platz beanspruchen, vor allem mobil.
    

### C. Lokale Navigation

- Ermöglicht das Navigieren innerhalb eines spezifischen Bereichs oder einer Kategorie.
    
- Beispiel: Untermenüs einer Hauptkategorie.
    
- **Vorteile:** Ermöglicht detaillierte Unterteilungen, ideal für umfangreiche Websites.
    
- **Nachteile:** Kann verschachtelt und unübersichtlich werden.
    

### D. Kontextuelle Navigation

- Verlinkt verwandte Inhalte und bietet Querverweise.
    
- Beispiel: "Das könnte Sie auch interessieren"-Links.
    
- **Vorteile:** Fördert das Entdecken relevanter Inhalte, verbessert SEO.
    
- **Nachteile:** Kann ablenken und zu hoher Informationsflut führen.
    

### E. Sequenzielle Navigation

- Führt Nutzer Schritt für Schritt durch einen Prozess.
    
- Beispiel: Checkout-Prozess im Online-Shop.
    
- **Vorteile:** Strukturierte Benutzerführung, ideal für komplexe Abläufe.
    
- **Nachteile:** Wenig Flexibilität, kann frustrierend sein, wenn Nutzer aus dem Prozess ausbrechen wollen.
    

### F. Suchnavigation

- Ermöglicht das gezielte Suchen nach Inhalten.
    
- Beispiel: Suchfelder mit Autovervollständigung.
    
- **Vorteile:** Schneller Zugriff auf spezifische Inhalte, besonders hilfreich für große Websites.
    
- **Nachteile:** Funktioniert nur, wenn Nutzer die richtigen Begriffe eingeben.
    

### G. Adaptive Navigation

- Passt sich dem Nutzungsverhalten an.
    
- Beispiel: Personalisierte Empfehlungen basierend auf früheren Interaktionen.
    
- **Vorteile:** Individuelle Nutzererfahrung, erhöht Engagement.
    
- **Nachteile:** Datenschutzbedenken, hohe technische Anforderungen.
    

## 3. HTML und CSS für Navigation

### Grundlegende HTML-Struktur einer Navigation:

```html
<nav>
  <ul>
    <li><a href="index.html">Startseite</a></li>
    <li><a href="about.html">Über uns</a></li>
    <li><a href="contact.html">Kontakt</a></li>
  </ul>
</nav>
```

### CSS-Beispiel für eine Navigation:

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

### CSS-Positionierung für Navigation:

#### 1. Fixed Navigation

- Bleibt immer sichtbar, auch beim Scrollen.
    

```css
nav {
  position: fixed;
  top: 0;
  width: 100%;
  background-color: #333;
}
```

- **Vorteile:** Immer erreichbar, verbessert Benutzerfreundlichkeit.
    
- **Nachteile:** Kann Inhalt überdecken, nimmt Platz ein.
    

#### 2. Sticky Navigation

- Bleibt oben sichtbar, wenn nach unten gescrollt wird.
    

```css
nav {
  position: sticky;
  top: 0;
  background-color: #333;
}
```

- **Vorteile:** Platzsparender als fixed, verbessert Navigation.
    
- **Nachteile:** Funktioniert nicht in allen Browsern einheitlich.
    

#### 3. Relative Navigation

- Standardverhalten, Navigation bewegt sich mit dem Inhalt.
    

```css
nav {
  position: relative;
}
```

- **Vorteile:** Einfach umzusetzen, keine Überdeckungsprobleme.
    
- **Nachteile:** Navigation verschwindet beim Scrollen.
    

#### 4. Absolute Navigation

- Positioniert Navigation relativ zum ersten positionierten Eltern-Element.
    

```css
nav {
  position: absolute;
  top: 10px;
  left: 50px;
}
```

- **Vorteile:** Flexibel platzierbar.
    
- **Nachteile:** Kann ungewollte Layout-Probleme verursachen.
    

## 4. Best Practices zur Navigation

- Klare und einheitliche Benennung der Menüpunkte.
    
- Nicht zu viele Menüpunkte (max. 7-9 Hauptpunkte).
    
- Nutzerfreundliche Gestaltung (leicht zugänglich, gut sichtbar).
    
- Mobile Optimierung durch responsive Navigation.
    
- Breadcrumbs für bessere Orientierung.
    

## 5. **Fazit**

Effektive Navigation verbessert die Usability und erleichtert den Zugang zu relevanten Informationen. Sie sollte intuitiv, strukturiert und anpassungsfähig sein, um die Nutzererfahrung zu optimieren. Eine durchdachte HTML- und CSS-Umsetzung trägt zur besseren Darstellung und Benutzerfreundlichkeit bei. Die Wahl der richtigen CSS-Positionierung (fixed, sticky, absolute, relative) beeinflusst, wie die Navigation im Layout wirkt und genutzt wird.