---
aliases: 
share: true
tags:
  - cleancode
title: Automated Unit Tests
---
 
# Automated [[undefineddocs/hidden/Unit Test|Unit Tests]]

>**Warum?**
>Nur automatisierte Tests werden auch wirklich konsequent ausgeführt. Je punktgenauer sie Code testen, desto besser.

Im [[undefineddocs/hidden/Orangener Grad|Orangenen Grad]] haben wir [[undefineddocs/hidden/Integration Tests|Integration Tests]] eingeführt, nun geht es um [[undefineddocs/hidden/Unit Test|Unit Tests]]. Im Gegensatz zu [[undefineddocs/hidden/Integration Tests|Integrationstests]] wird bei [[undefineddocs/hidden/Unit Test|Unit Tests]] eine einzelne Funktionseinheit (vor allem Klassen, aber auch Methoden oder Komponenten) isoliert getestet. Dazu ist es erforderlich, diese Funktionseinheit von ihren Abhängigkeiten befreien zu können. Sollen [[undefineddocs/hidden/Unit Test|Unit Tests]] im Nachhinein für bestehenden Code ergänzt werden, sind häufig Refaktorisierungen erforderlich. Wir haben durch die [[undefineddocs/hidden/Integration Tests|Integrationstests]] die Sicherheit, dass wir dabei keine Fehler einbauen.

Automatisierte Tests bieten zweifachen Nutzen:

-   Sie sparen Zeit
-   Sie nehmen Angst

Je stärker eine Codebasis in Veränderung begriffen ist, desto eher ist die Zeitersparnis zu spüren. Denn wo Code sich verändert, muss immer wieder Neues und auch Altes (Regressionstests) getestet werden. Da spart Automatisation einfach Zeit. Und je komplexer der Code, desto größer ist die Angstreduktion. Denn wenn komplexer Code verändert werden soll – um Funktionalität hinzuzufügen, ihn zu optimieren oder schlicht zu korrigieren –, da besteht hohe Gefahr, ungewollt Fehler einzuführen. Kleinschrittige automatisierte Tests decken diese jedoch auf, sodass kein Grund zur Angst besteht, zu „verschlimmbessern“.

Siehe auch unter [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/).