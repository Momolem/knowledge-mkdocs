---
share: true
tags:
  - cleancode
aliases:
  - Favour Composition over Inheritance (FCoI)
linter-yaml-title-alias: Favour Composition over Inheritance (FCoI)
title: Favour Composition over Inheritance (FCoI)
---
 
# Favour Composition over Inheritance (FCoI)

>**Warum?**
>Komposition fördert die lose Kopplung und die Testbarkeit eines Systems und ist oft flexibler.

Für die Wiederverwendung von Funktionalität kennt die Objektorientierte Programmierung ([[OOP|OOP]]) zwei sehr bekannte Kandidaten: Die Vererbung (whitebox – reuse) und die Komposition (blackbox – reuse). Verwendet man Funktionalität wieder durch das Ableiten von einer Klasse, so ist die Subklasse abhängig von der Elternklasse. Dies macht ein System in vielen Fällen unnötig komplex, schlechter testbar und erschwert das Austauschen von Funktionalität zur Laufzeit. [[../index|Clean Code Developer]] hat für das korrekte Ableiten das [[./Liskov Substitution Principle|Liskov Substitution Principle]] bereit, das es dabei zu befolgen gilt.

Bei der Komposition verwendet eine Klasse eine andere. Verwendet man dazu eine klar definierte Schnittstelle, fördert das die Entkopplung. Auch können verschiedene Implementationen einfach ausgetauscht werden. Bevor man sich also der  stellt, fordert Favour Composition over Inheritance, sich die Frage zu stellen, ob man der Komposition nicht Vorrang geben kann.

> „_Because inheritance exposes a subclass to details of its parent’s implementation, it’s often said that ‚inheritance breaks encapsulation_„. (Gang of Four 1995:19)

