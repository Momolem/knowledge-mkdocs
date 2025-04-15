---
aliases: 
share: true
tags:
  - cleancode
title: Automated Integrationtests
---
# Automated Integrationtests

>**Warum?**
>Integrationstests stellen sicher dass der Code tut was er soll. Diese wiederkehrende Tätigkeit nicht zu automatisieren wäre Zeitverschwendung.


Die fundamentale Voraussetzung für jegliche Änderungen am Code haben wir bereits im [[../Grade/Roter Grad|Roten Grad]] durch den Einsatz eines Versionskontrollsystems gelegt. Wir können ohne Sorge Änderungen am Code vornehmen, ganze Dateien und Verzeichnisse löschen, durch das Versionskontrollsystem ist alles wieder abrufbar.

Wenn wir nun Änderungen am Code vornehmen, sollten wir uns sicher sein, dass wir dabei nichts kaputt machen. Und diese Sicherheit können wir nur erlangen, wenn wir nach der Änderung testen, ob die Anwendung sich noch so verhält wie zuvor. Diese Tests nach jeder Änderung per Hand durchzuführen wäre nicht praktikabel, wir müssen sie automatisieren. Ein großes Übel der Softwareentwicklung ist die Angst, bei Änderungen am Code etwas zu übersehen, ein Detail nicht zu berücksichtigen, und dadurch einen Fehler zu verursachen in Code der vorher funktionierte. Dabei spielt es in der Regel sogar nicht mal eine Rolle, ob die Änderungen dazu führen sollen, dass der Code verbessert wird ([[../../Refaktorisieren|Refaktorisieren]]) oder zusätzliche Anforderungen umgesetzt werden sollen. Solange wir nach Durchführen einer Änderung nicht sicher sind, dass alles noch so funktioniert wie zuvor, bleibt die Angst. Diese führt dazu, dass wir Code im Zweifelsfall so belassen, wie er ist, denn er funktioniert ja. Notwendige Refaktorisierungen werden unterlassen, aus Angst Fehler zu machen.

Damit wir uns auch in schon laufenden Projekten (sogenannte _Brownfield_ Projekte, im Gegensatz zu _Greenfield_ „auf der grünen Wiese“) dieses Sicherheitsnetz schaffen können, benötigen wir Verfahren, die auf vorhandenen Code angewendet werden können. Dazu eignen sich automatisierte Integrationstests. Sie setzen entweder ganz oben auf der Benutzerschnittstelle auf und testen die Anwendung durch alle Layer oder setzen weiter unten auf. In jedem Fall werden mehrere Funktionseinheiten im Zusammenspiel getestet.

Bevor wir also Änderungen oder Erweiterungen am Code vornehmen, erstellen wir für die betroffenen Codebereiche Integrationstests. Dabei können Tools und Techniken wie WatiN, UI Automation, etc. verwendet werden. Wünschenswert sind natürlich auch [[../../Unit Test|Unit Tests]], welche einzelne Funktionseinheiten isoliert testen. Dazu muss der Code allerdings Voraussetzungen erfüllen, die vermutlich nicht immer gegeben sind: der Code muss bereits das _ [[../Prinzipien/Single Responsibility Principle|Single Responsibility Principle]]_ berücksichtigen. Andernfalls sind die Abhängigkeiten zwischen den Funktionseinheiten (Komponenten, Klassen oder Methoden) so groß, dass sie nicht isoliert getestet werden können. Das Fernziel ist natürlich eine Codebasis, bei der [[../../Unit Test|Unit Tests]] möglich sind. Mehr noch: wir werden in Zukunft die Tests vor der Implementierung erstellen (_Test first_). Aber um durch Refaktorisierungen dorthin zu gelangen, bedarf es erst der Integrationstests, um sicherzustellen, dass die Anwendung sich noch so verhält wie vor der [[../../Refaktorisieren|Refaktorisierung]].
