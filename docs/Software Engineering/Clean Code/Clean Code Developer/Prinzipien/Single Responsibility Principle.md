---
share: true
aliases:
  - Single Responsibility Principle (SRP)
  - SRP
tags:
  - cleancode
linter-yaml-title-alias: Single Responsibility Principle (SRP)
title: Single Responsibility Principle (SRP)
---
 
# Single Responsibility Principle (SRP)

>[!question]  **Warum?**
>Fokus erleichtert das Verständnis. Eine Klasse mit genau einer Aufgabe ist verständlicher als ein Gemischtwarenladen.

Das Single Responsibility Principle ([SRP](http://web.archive.org/web/20160716150726/http://objectmentor.com/resources/articles/srp.pdf)) ist eines der [[../../SOLID|SOLID]] Prinzipien. Es lautet: Eine Klasse sollte nur **eine** Verantwortlichkeit haben.

Hintergrund des Single Responsibility Principle ist die Überlegung, dass Änderungen oder Erweiterungen der Funktionalität einer Anwendung sich auf wenige Klassen beschränken sollen. Je mehr Klassen angepasst werden müssen, desto größer ist das Risiko, dass sich durch die erforderlichen Änderungen Probleme an Stellen ergeben, die im Kern nichts mit der Erweiterung zu tun haben. Eine Verletzung des Single Responsibility Principle führt zu Kopplung und damit zu erhöhter Komplexität, es wird schwieriger den Code zu verstehen.

---
Sources:
- https://clean-code-developer.de/die-grade/orangener-grad/#Single_Responsibility_Principle_SRP
- https://blog.cleancoder.com/uncle-bob/2014/05/08/SingleReponsibilityPrinciple.html