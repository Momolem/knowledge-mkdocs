---
share: true
tags:
  - cleancode
aliases:
  - Dependency Inversion Principle (DIP)
linter-yaml-title-alias: Dependency Inversion Principle (DIP)
title: Dependency Inversion Principle (DIP)
---
 
# Dependency Inversion Principle (DIP)

>[!question] **Warum?**
>Punktgenaues Testen setzt Isolation von Klassen voraus. Isolation entsteht, wenn Klassen keine Abhängigkeiten von Implementationen mehr enthalten – weder zur Laufzeit, noch zur Übersetzungszeit. Konkrete Abhängigkeiten sollten deshalb so spät wie möglich entschieden werden. Am besten zur Laufzeit.

Auch das Dependency Inversion Principle ([DIP](https://drive.google.com/file/d/0BwhCYaYDn8EgMjdlMWIzNGUtZTQ0NC00ZjQ5LTkwYzQtZjRhMDRlNTQ3ZGMz/view)) ist ein [[undefineddocs/hidden/SOLID|SOLID]] Prinzip. Es besagt folgendes:
-   High-Level Klassen sollen nicht von Low-Level Klassen abhängig sein, sondern beide von Interfaces.
-   Interfaces sollen nicht von Details abhängig sein, sondern Details von Interfaces.

Verwendet eine High-Level Klasse eine Low-Level Klasse unmittelbar, so ergibt sich eine starke Kopplung zwischen beiden. Spätestens beim Versuch, die High-Level Klasse isoliert zu testen, wird man auf Schwierigkeiten stoßen. Aus diesem Grund sollte die High-Level Klasse von einem Interface abhängig sein, das wiederum von der Low-Level Klasse implementiert wird. So kann die Low-Level Klasse im Unit Test durch ein _Mockup_ ersetzt werden.

Um zur Laufzeit die invertierte, abstrakte Abhängigkeit mit einem konkreten Objekt aufzulösen, bieten sich im Prinzip drei Möglichkeiten:

-   mittels Konstruktorparameter „per Hand“
-   Einsatz eines Inversion of Control Containers ([[undefineddocs/hidden/Inversion of Control Container|IoC]] Container) wie etwa Castle Windsor
-   Dependency Lookup

Im [gelben Grad](https://www.notion.so/Clean-Code-Developer-bb88b9ccb7d040c4a45f408e73b9d1c2) injizieren wir die Abhängigkeiten zunächst nur über die Parameter der Konstruktoren. Dies ist anfangs die einfachste Lösung und funktioniert mit einer handvoll Klassen ganz gut. Später im [grünen Grad](https://www.notion.so/Clean-Code-Developer-bb88b9ccb7d040c4a45f408e73b9d1c2) nutzen wir einen [[undefineddocs/hidden/Inversion of Control Container|IoC]] Container und Dependency Lookup.