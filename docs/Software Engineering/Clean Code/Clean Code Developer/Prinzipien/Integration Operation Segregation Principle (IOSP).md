---
aliases: 
share: true
tags:
  - cleancode
title: Integration Operation Segregation Principle (IOSP)
---
 
# Integration Operation Segregation Principle (IOSP)

>**Warum?**
>Ein deutliches Symptom schlecht wandelbaren Codes sind tiefe Hierarchien funktionaler Abhängigkeit. Sie reduzieren die Verständlichkeit und erschweren automatisierte Tests wie Refactoring.

Indem in Methoden verhaltenserzeugende Anweisungen (Logik) gemischt mit Aufrufen anderer Methoden derselben Codebasis steht, ist nicht mehr klar erkennbar, wie Gesamtverhalten entsteht; die Anweisungen sind ja verschmiert über eine u.U. sehr tiefe Hierarchie. Zudem tendieren Methoden mit solcher Mischung dazu, unbegrenzt zu wachsen.

Dem stellt sich das IOSP mit einer klaren Trennung entgegen:

-   Entweder enthält eine Methode nur Logik, d.h. Transformationen, Kontrollstrukturen oder I/O- bzw. allgemeiner: API-Aufrufe. Dann wird sie _Operation_ genannt.
-   Oder eine Methode enthält keinerlei Logik, sondern nur Aufrufe von anderen Methoden derselben Codebasis. Dann wird sie _Integration_ genannt.

Diese strikte Unterscheidung führt zu mehrerlei positiven Effekten:

1.  Methoden tendieren dazu, sehr kurz zu bleiben. Denn mehr als 10, 20 oder 30 Zeilen reine Logik oder ausschließlich Methodenaufrufe „fühlen sich nicht gut an“. Da eine Mischung nicht erlaubt ist, werden weitere kleine Methoden extrahiert.
2.  Kurze Methoden, die nur Logik enthalten, sind leicht zu testen, da sie keine Abhängigkeiten haben.
3.  Kurze Methoden, die nur Logik enthalten, sind vergleichsweise leicht zu verstehen. Der Methodenname kann wirklich bedeutungsstiftend wirken.
4.  Kurze Methoden, die ausschließlich integrieren, sind sehr gut zu verstehen und beschreiben „auf einen Blick“, was geschieht.
5.  Die Korrektheit von Integrationen lässt sich sehr leicht durch Augenscheinnahme prüfen. Es ist lediglich festzustellen, ob Verarbeitungsschritte grundsätzlich in der korrekten Reihenfolge angeordnet sind. Den Rest übernimmt der Compiler – bzw. die Testabdeckung der Operationen.
6.  Integrationen lassen sich leicht durch „Zwischenschieben“ weiterer Methoden erweitern, um neue Anforderungen zu erfüllen. Die Verständlichkeit bleibt dabei erhalten.

Das IOSP lässt sich „aus dem Stand“ von jedem Entwickler guten Willens anwenden. Seine Einhaltung ist durch jedermann leicht zu überprüfen. Integrationen und Operationen unterscheiden sich in der Form deutlich. Weitere Details, insbesondere zur Abgrenzung zum [[./Dependency Inversion Principle|Dependency Inversion Principle]], [findest du bspw. hier](https://ccd-akademie.de/dip-oder-iosp/).