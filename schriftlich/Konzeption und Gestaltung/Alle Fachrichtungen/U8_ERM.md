---
title: ERM
tags:
  - Konzeption-und-Gestaltung
---
# ERM (Entity-Relationship-Modell)

> [!warning] 29.04.2025
## Definition

> [!summary]
> Das **Entity-Relationship-Modell (ER-Modell)** ist eine Methode zur **Datenmodellierung**. Es beschreibt die Struktur einer Datenbank durch **Entitäten (Objekte)**, ihre **Attribute** und die **Beziehungen** zwischen ihnen.
## Bestandteile des ER-Modells

### Entitäten

- Eine **Entität** repräsentiert ein **Objekt der realen oder abstrakten Welt**.
    
- Beispiel: _Mitarbeiter, Kunde, Produkt_.
    

### Attribute

- Ein **Attribut** beschreibt eine **Eigenschaft einer Entität**.
    
- Beispiel: _Name, Alter, Preis_.
    

### Beziehungen (Relationen)

- Eine **Beziehung beschreibt die Verbindung** zwischen zwei oder mehreren Entitäten.
    
- Wird durch eine **grafische Darstellung** visualisiert.
    
- Beispiel: Ein _Kunde bestellt ein Produkt_.
    

### Kardinalität

- Bestimmt, **wie viele Entitäten** einer Entitätsmenge einer anderen Entitätsmenge zugeordnet sein können.
    
- Wichtig für die Prüfung!
    
- Häufig genutzte Kardinalitäten:
    
    - **1:1 (eins zu eins)** → Eine Entität ist genau einer anderen Entität zugeordnet.
        
    - **1:N (eins zu viele)** → Eine Entität ist mehreren Entitäten zugeordnet.
        
    - **N:M (viele zu viele)** → Mehrere Entitäten sind mehreren anderen Entitäten zugeordnet.
        

### Primärschlüssel

- Der **Primärschlüssel** dient zur eindeutigen Identifikation einer Entität.
    
- Beispiel: _Kundennummer, Produkt-ID_.
    

## Visualisierung

Ein ER-Diagramm stellt Entitäten als **Rechtecke**, Attribute als **Ovale** und Beziehungen als **Rauten** dar. Linien zeigen Verbindungen zwischen diesen Elementen.

---

>[!info] Wahrscheinlich **keine Normalisierung (Normalformen)** für die Prüfung erforderlich.