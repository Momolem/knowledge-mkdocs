---
share: true
aliases:
  - Chunking
---
### Superzeichenbildung (Chunking)
- Superzeichen sind hierarchisch organisiert
- Beispiel Memory
	- Erwachsene nutzen Strategien (dritte Reihe von oben, zweite Karte von links)
	- Kinder merken sich vermutlich die Konstellation
	- Ergebnis – Kinder gewinnen in den meisten Fällen

- Beispiele für Superzeichenbildung
	- Wörter anstelle Einzelbuchstaben
	- Bilder (Eindrücke) anstelle des Wortes
	- Sätze anstelle Einzelworte
	- Funktioniert jedoch nur wenn die Informationseinheiten bekannt sind
- Symbolische Namen
	- 6A B7 anstelle 0110 1010 1011 0111
	- bluehands.de anstelle 109.109.201.186

## Chunks im Code
- Schlüsselwörter (class, struct, function) vermitteln den Anfang eines Programmelements
- Trennzeichen (Semikolon, Komma) trennen Programmelemente
- Gruppierungszeichen (Klammern) gruppieren Programmelemente
- Operatoren vermitteln eine Operation auf Argumenten
- Literale werden je nach Kontext als Wert oder Variable interpretiert
- Namen vermitteln eine Semantik
- Argumentpositionen vermitteln eine Rolle

## Kombinieren von Chunks

1. Struktur erkennen: Klasse, Feld, Methode
2. Fachliche Bedeutung erfassen: Konto (Account), Guthaben (balance), Überweisung (Transfer)
3. Ablauf verstehen: Prüfung -> Abbuchung -> Gutschrift
4. Gesamtbild: eine Bankkontoabstraktion

## Was überfordert unser Gehirn

- Eine Operation verarbeitet zu viele Input-Chunks
- Unser Gedächtnis kann die Output-Chunks nicht mehr halten
- Unser Gedächtnis muss Chunks von früheren Berechnungen (Zwischenergebnisse) vorhalten

## Unverständlicher Code analysieren

- Wie viele Chunks muss ich gleichzeitig verarbeiten?
- Kann ich mir unter den Variablen, Methoden, Klassen etwas vorstellen?
- Habe ich echte Abstraktionen oder nur Zusammenfassungen?
- Gibt es Widersprüche zwischen der niedergeschriebenen Logik und den Namen?
- Passt der Datenfluss oder Kontrollfluss zu den Abstraktionen?

## Maßnahmen

- zu viele Chunks gleichzeitig:
    - Zerlegung der Logik in kleinere Schritte
    - (Teil-)Operationen abstrahieren
    - Zwischenergebnisse möglichst früh konsumieren
    - multiple Ergebnisse abstrahieren oder aggregieren
    - falsche Namen korrigieren
    - ungenaue Namen präzisieren
    - Namenskonventionen einhalten
- falsche Abstraktionen
    - Suche nach passenderen Abstraktionen
    - falsche Abstraktionen auflösen und neu gruppieren
- Widersprüche in Logik und/oder Namen
    - Klärung, ob Logik oder Namen das Problem sind

## Möglichkeiten Code Komplexität klein zu halten

- Pair programming
- Code-Reviews
- "Selbstdokumentierender Code"
- Mob Programming, Quality Meetings im Team

#### Diskussion "synchronisiert" chunks