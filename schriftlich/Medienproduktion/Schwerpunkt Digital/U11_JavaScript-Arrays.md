---
title: JavaScript-Arrays
tags:
  - Medienproduktion/Schwerpunkt-Digital/JavaScript-Arrays
kapitel: Schwerpunkt Digital
bereich: Medienproduktion
status: erledigt
---
# JavaScript-Arrays

## Was ist ein Array?

>[!summary]
>Ein **Array** (deutsch: Feld) ist eine spezielle Variable in JavaScript, die **mehrere Werte** als geordnete Sammlung von Elementen desselben Typs, unter einem gemeinsamen Namen speichern kann.  


```javascript
let meineListe = ["Apfel", "Banane", "Kirsche"];
```

- Der **Index** beginnt bei `0`.
    
- Zugriff auf einzelne Elemente:
    

```javascript
console.log(meineListe[0]); // Gibt "Apfel" aus
console.log(meineListe[2]); // Gibt "Kirsche" aus
```

---

## Warum Arrays verwenden?

Ohne Arrays müsste man für jeden Wert eine eigene Variable anlegen:

```javascript
let car1 = "Saab";
let car2 = "Volvo";
let car3 = "BMW";
```

Arrays ermöglichen:

- übersichtlicheren Code
    
- einfaches Durchlaufen von vielen Werten
    
- weniger Speicherbedarf
    

---

## Varianten Erstellung von Arrays

### Array-Literal (empfohlen)

```javascript
const cars = ["Saab", "Volvo", "BMW"];
```

### Mehrzeilige Schreibweise

```javascript
const cars = [
  "Saab",
  "Volvo",
  "BMW"
];
```

### Nachträgliches Befüllen

```javascript
const cars = [];
cars[0] = "Saab";
cars[1] = "Volvo";
cars[2] = "BMW";
```

### Nicht empfohlen: `new Array()`

```javascript
const cars = new Array("Saab", "Volvo", "BMW");
```

>[!warning] Achtung bei new Array(...):

Bei einem einzigen numerischen Argument erzeugt new Array(n) ein Array mit dieser Länge, aber ohne initialisierte Werte:
```javascript
const arr = new Array(5);  // [ <5 empty items> ]
console.log(arr.length);   // 5
```

Bei mehreren Argumenten wird stattdessen ein Array mit diesen Werten erzeugt:

```javascript
const arr = new Array("Saab", "Volvo"); // ["Saab", "Volvo"]
console.log(arr.length);                // 2

```
→ Dieses Verhalten kann zu Verwechslungen führen. Verwenden Sie bevorzugt Array-Literale ([]).

Alternativen zur festen Längenvorgabe
Falls ein Array mit definierter Länge sinnvoll vorinitialisiert werden soll:

```javascript
const arr = new Array(5).fill(null); // [null, null, null, null, null]

```

Oder mit berechneten Werten:

```javascript
const arr = Array.from({ length: 5 }, (_, i) => i + 1); // [1, 2, 3, 4, 5]

```


---
---

## Zugriff und Bearbeitung von Array-Elementen

- Zugriff:
    

```javascript
let car1 = cars[0]; // "Saab"
```

- Ändern:
    

```javascript
cars[0] = "Opel";
```

---

## JavaScript Array-Eigenschaften und Methoden

## 1. Länge des Arrays bestimmen

* Mit der `.length`-Eigenschaft kannst du die Anzahl der Elemente im Array ermitteln.

```javascript
let cars = ["BMW", "Audi", "VW"];
console.log(cars.length); // Gibt 3 aus
````

* Zugriff auf das letzte Element:

```javascript
console.log(cars.length - 1); // Gibt den Index des letzten Elements zurück (2 in diesem Fall)
console.log(cars[cars.length - 1]); // Gibt "VW" aus (letztes Element)
```

---

## 2. In String umwandeln

* Mit der Methode `.toString()` kannst du ein Array in einen String umwandeln. Dabei werden die Array-Elemente durch Kommas getrennt.

```javascript
let fruits = ["Apfel", "Banane", "Kirsche"];
console.log(fruits.toString()); // Gibt "Apfel,Banane,Kirsche" aus
```

---


## 3. Sortieren

```javascript
cars.sort();
```

| Fall                                  | Beispielcode                                  | Ergebnis                                                                                    |
| ------------------------------------- | --------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Alphabetische Sortierung              | `cars.sort();`                                | `["Audi", "BMW", "VW"]`                                                                     |
| Numerische Sortierung (aufsteigend)   | `numbers.sort((a, b) => a - b);`              | `[2, 4, 10, 21, 30]`                                                                        |
| Numerische Sortierung (absteigend)    | `numbers.sort((a, b) => b - a);`              | `[30, 21, 10, 4, 2]`                                                                        |
| Sortierung von Objekten (aufsteigend) | `cars.sort((a, b) => a.year - b.year);`       | `[ { name: "BMW", year: 2010 }, { name: "VW", year: 2012 }, { name: "Audi", year: 2015 } ]` |
| Sortierung von Objekten (absteigend)  | `cars.sort((a, b) => b.year - a.year);`       | `[ { name: "Audi", year: 2015 }, { name: "VW", year: 2012 }, { name: "BMW", year: 2010 } ]` |
| Sortierung nach Länge (Strings)       | `fruits.sort((a, b) => a.length - b.length);` | `["Apfel", "Banane", "Dattel", "Kirsche"]`                                                  |

---

## 4. **Array umkehren**

* Mit `.reverse()` kannst du die Reihenfolge der Array-Elemente umkehren.

```javascript
let cars = ["BMW", "Audi", "VW"];
cars.reverse();
console.log(cars); // Gibt ["VW", "Audi", "BMW"] aus
```

---

## 5. **Teil-Array kopieren**

* Mit `.slice()` kannst du ein Teil-Array (eine Kopie) erstellen. Der erste Parameter gibt den Startindex an und der zweite (optional) den Endindex.

```javascript
let cars = ["BMW", "Audi", "VW", "Mercedes"];
let newCars = cars.slice(1, 3); // Kopiert die Elemente mit Index 1 und 2
console.log(newCars); // Gibt ["Audi", "VW"] aus
```

---

## 6. **Zugriff mit `.at()`**

* Die Methode `.at()` ermöglicht den Zugriff auf Array-Elemente, wobei du sowohl positive als auch negative Indizes verwenden kannst.

```javascript
let fruits = ["Apfel", "Banane", "Kirsche", "Dattel"];

console.log(fruits.at(2));   // Gibt "Kirsche" aus (3. Element)
console.log(fruits.at(-1));  // Gibt "Dattel" aus (letztes Element)
console.log(fruits.at(-2));  // Gibt "Kirsche" aus (vorletztes Element)
```

---

## 7. **Index eines Elements mit `.indexOf()`**

* Mit `.indexOf()` kannst du den Index eines bestimmten Elements im Array ermitteln. Wenn das Element nicht gefunden wird, gibt die Methode `-1` zurück.

```javascript
let cars = ["BMW", "Audi", "VW"];
let index = cars.indexOf("Audi");
console.log(index); // Gibt 1 aus (Index von "Audi")

let notFound = cars.indexOf("Mercedes");
console.log(notFound); // Gibt -1 aus (wenn das Element nicht gefunden wird)
```

---

## 8. **Überprüfen, ob ein Element im Array enthalten ist: `.includes()`**

* Mit der Methode `.includes()` kannst du überprüfen, ob ein bestimmtes Element im Array vorhanden ist. Sie gibt `true` zurück, wenn das Element vorhanden ist, andernfalls `false`.

```javascript
let cars = ["BMW", "Audi", "VW"];
console.log(cars.includes("Audi"));  // Gibt true aus
console.log(cars.includes("Mercedes"));  // Gibt false aus
```

---

## Zusammenfassung der wichtigsten Array-Methoden:

| Methode       | Beschreibung                                                  | Beispiel                |
| ------------- | ------------------------------------------------------------- | ----------------------- |
| `.length`     | Gibt die Anzahl der Elemente im Array zurück.                 | `cars.length`           |
| `.toString()` | Wandelt das Array in einen durch Kommas getrennten String um. | `fruits.toString()`     |
| `.sort()`     | Sortiert die Array-Elemente alphabetisch oder numerisch.      | `cars.sort()`           |
| `.reverse()`  | Kehrt die Reihenfolge der Array-Elemente um.                  | `cars.reverse()`        |
| `.slice()`    | Gibt eine flache Kopie eines Teils des Arrays zurück.         | `cars.slice(1, 3)`      |
| `.at()`       | Greift auf ein Array-Element zu, auch mit negativen Indizes.  | `fruits.at(-1)`         |
| `.indexOf()`  | Gibt den Index eines Elements im Array zurück.                | `cars.indexOf("Audi")`  |
| `.includes()` | Überprüft, ob ein bestimmtes Element im Array vorhanden ist.  | `cars.includes("Audi")` |


---

## Elemente hinzufügen und entfernen

In JavaScript sind Arrays dynamisch. Elemente können am **Ende** oder **Anfang** eingefügt bzw. entfernt werden. Dabei wird die Reihenfolge der Elemente automatisch angepasst.

### 1. Hinzufügen von Elementen

#### a) Am Ende mit `.push()`

Fügt ein oder mehrere Elemente **am Ende** des Arrays hinzu. Gibt die **neue Länge** des Arrays zurück.

```javascript
let cars = ["BMW", "Audi"];
cars.push("VW");
console.log(cars); // ["BMW", "Audi", "VW"]
```

#### b) Am Ende über `length`

Auch über den Längenindex (`.length`) kann ein Element am Ende eingefügt werden:

```javascript
cars[cars.length] = "Mercedes";
console.log(cars); // ["BMW", "Audi", "VW", "Mercedes"]
```

#### c) Am Anfang mit `.unshift()`

Fügt ein oder mehrere Elemente **am Anfang** des Arrays ein. Die bestehenden Elemente werden nach rechts verschoben. Gibt die neue Länge zurück.

```javascript
cars.unshift("Ford");
console.log(cars); // ["Ford", "BMW", "Audi", "VW", "Mercedes"]
```

>[!info] Hinweis: `.unshift()` ist ineffizienter als `.push()`, da alle bestehenden Indizes verschoben werden müssen.


### 2. **Entfernen von Elementen**

#### a) Vom Ende mit `.pop()`

Entfernt das **letzte Element** des Arrays und gibt dieses zurück.

```javascript
let last = cars.pop();
console.log(last); // "Mercedes"
console.log(cars); // ["Ford", "BMW", "Audi", "VW"]
```

#### b) Vom Anfang mit `.shift()`

Entfernt das **erste Element** des Arrays und gibt dieses zurück. Alle nachfolgenden Elemente werden nach links verschoben.

```javascript
let first = cars.shift();
console.log(first); // "Ford"
console.log(cars);  // ["BMW", "Audi", "VW"]
```

### 3. **Löcher im Array vermeiden**

Durch direkte Zuweisung an einen höheren Index entstehen **undefinierte (leere) Stellen** zwischen den Einträgen. Dies sollte vermieden werden.

```javascript
cars[6] = "Lemon"; 
console.log(cars); 
// ["BMW", "Audi", "VW", <3 empty items>, "Lemon"]
```

>[!info] Verwende stattdessen Methoden wie `.push()` oder `.splice()`, um Elemente kontrolliert einzufügen.


---

## Array durchlaufen

### Mit `for`-Schleife:

```javascript
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}
```

### Mit `forEach()`:

```javascript
fruits.forEach(function(value) {
  console.log(value);
});
```

```javascript
fruits.forEach(obst => {
  console.log(obst);
});
```

### Mit `for...of`:

```javascript
for (let obst of fruits) {
  console.log(obst);
}
```

---

## Typ und Besonderheiten von Arrays

> [!info] typeof Array gibt `"object"` zurück

Arrays sind spezielle Objekte mit nummerierten Indizes.

- Beispiel für verschiedene Typen in einem Array:
    

```javascript
let gemischt = ["Hallo", 42, true, null];
```

- Arrays können auch Funktionen und weitere Arrays enthalten:
    

```javascript
myArray[0] = Date.now;
myArray[1] = myFunction;
myArray[2] = myCars;
```

---

## Erkennen, ob eine Variable ein Array ist

 Methode 1:

```javascript
Array.isArray(fruits);
```

Methode 2:

```javascript
fruits instanceof Array;
```

---

## Mehrdimensionale Arrays

Ein **mehrdimensionales Array** ist ein Array, das weitere Arrays enthält.

```javascript
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];

console.log(matrix[0][1]); // Gibt 2 aus
console.log(matrix[2][0]); // Gibt 7 aus
```

## Array von Objekten

```javascript
let autos = [
  { marke: "BMW", modell: "X5" },
  { marke: "Audi", modell: "Q3" },
  { marke: "VW", modell: "Golf" }
];

console.log(autos[1].modell); // Gibt "Q3" aus
```

## Verschachtelte Arrays und Objekte

Komplexe Strukturen:

```javascript
const myObj = {
  name: "John",
  age: 30,
  cars: [
    { name: "Ford", models: ["Fiesta", "Focus", "Mustang"] },
    { name: "BMW", models: ["320", "X3", "X5"] },
    { name: "Fiat", models: ["500", "Panda"] }
  ]
};
```

Zugriff auf verschachtelte Werte:

```javascript
for (let i in myObj.cars) {
  console.log(myObj.cars[i].name);
  for (let j in myObj.cars[i].models) {
    console.log(myObj.cars[i].models[j]);
  }
}
```

---

## Wichtige Hinweise

- JavaScript unterstützt **keine** Arrays mit benannten Indizes.
    

```javascript
const person = [];
person["firstName"] = "John"; // → Wird als Objekt behandelt, nicht als Array
```

> [!warning] Folge: Methoden wie `.length` liefern dann falsche Ergebnisse.

---

## Arrays vs. Objekte

> [!quote] Faustregel:

- **Arrays** → nummerierte Indizes
    
- **Objekte** → benannte Indizes
    

---

## Fazit: Warum sind Arrays wichtig?

Arrays sind **essentiell** für die Arbeit mit mehreren Werten.  
Sie machen deinen Code:

- strukturierter
    
- wiederverwendbarer
    
- effizienter
    

Sie sind ein **Grundbaustein moderner JavaScript-Programmierung**, besonders bei Frameworks wie **React**, **Vue** oder **Angular**.
