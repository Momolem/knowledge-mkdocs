---
aliases: 
share: true
tags:
  - cleancode
title: Simple Refactorings
---
 
# Simple Refactorings

>**Warum?**
>Code verbessern ist leichter, wenn man typische Verbesserungshandgriffe kennt. Ihre Anwendungsszenarien machen sensibel für Schwachpunkte im eigenen Code. Als anerkannte Muster stärken sie den Mut, sie anzuwenden.


Um Code immer ein wenig besser zu hinterlassen, als man ihn vorgefunden hat, sind mehr oder weniger große Eingriffe nötig. Die kann ein Clean Code Developer dank des Versionskontrollsystems angstfrei vornehmen. Doch wie macht er sich die Arbeit möglichst einfach?

Das Schlüsselwort lautet „Refaktorisierung“. [[Martin Fowler|Martin Fowler]] hat das [Refaktorisieren/Refactoring](http://www.amazon.de/Refactoring-Studentenausgabe-vorhandener-verbessern-Programmers/dp/3827322782) in seinem gleichnamigen Buch als grundlegende Technik zur Erhöhung der Codequalität beschrieben. Er definiert darin eine Anzahl von Codeveränderungsmustern, um „code smells“, d.h. suboptimale Strukturen oder allgemeiner Missachtungen von Prinzipien, zu bereinigen.

Für den roten Grad ist darin vor allem die Refaktorisierung [Methode extrahieren](http://martinfowler.com/refactoring/catalog/extractMethod.html) relevant, um dem DRY-Prinzip zu genügen. Die wenden Clean Code Developer an, um mehrfach vorkommenden Code in eine Methode zu extrahieren, die statt seiner an den Wiederholungsorten aufgerufen wird.

Als zweite Refaktorisierung sollte bei der Arbeit am roten Grad das [Umbenennen](http://martinfowler.com/refactoring/catalog/renameMethod.html) wo nötig eingesetzt werden. Sie passt zur Pfadfinderregel, denn eine oft anzutreffende „Unsauberkeit“ im Quellcode sind kryptische Namen.

Refaktorisierungen können von Hand angewandt werden, doch es gibt auch Werkzeugunterstützung. Moderne IDEs wie Visual Studio bieten einige Refactoringmuster, weitere Tools listet unsere [Werkzeugliste](https://clean-code-developer.de/weitere-infos/werkzeuge/).

„Refactoring“ wie „Clean Code“ gehören zur [Pflichtlektüre](https://clean-code-developer.de/weitere-infos/literatur/) jedes Clean Code Developers ab dem roten Grad.

Für weitere Informationen siehe auch unter [refactoring-legacy-code.net](http://refactoring-legacy-code.net/category/einfache-refactorings/).