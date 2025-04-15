---
share: true
tags:
  - cleancode
aliases:
  - Interface Segregation Principle (ISP)
linter-yaml-title-alias: Interface Segregation Principle (ISP)
title: Interface Segregation Principle (ISP)
---
 
# Interface Segregation Principle (ISP)

>[!question] **Warum?**
>Leistungsbeschreibungen, die unabhängig von einer konkreten Erfüllung sind, machen unabhängig.

Das Interface Segregation Principle ([ISP](https://drive.google.com/file/d/0BwhCYaYDn8EgOTViYjJhYzMtMzYxMC00MzFjLWJjMzYtOGJiMDc5N2JkYmJi/view)) ist ein weiteres [[../../SOLID|SOLID]] Prinzip. _Segregation_ bedeutet _Abtrennung_. Das Prinzip besagt, dass ein Client nicht von Details eines Service abhängig sein soll, die er gar nicht benötigt. Je weniger in dessen Interface enthalten ist, desto geringer ist die Kopplung zwischen den beiden Komponenten.

Stellen wir uns vor, wir müssten einen Stecker planen, mit dem ein Monitor an einen Computer angeschlossen werden soll. Wir entscheiden uns, einfach alle Signale die in einem Computer so anfallen, per Stecker zur Verfügung zu stellen. Der hat dann zwar einige Hundert Pins, aber dafür ist er maximal flexibel. Dummerweise ist damit die Kopplung ebenfalls maximal.

Beim Beispiel des Steckers ist es offensichtlich, dass eine Monitorverbindung nur jene Signale enthalten soll, die zur Darstellung eines Bildes auf dem Monitor erforderlich sind. Genauso verhält es sich mit Software Interfaces. Auch sie sollten so klein wie möglich sein, um unnötige Kopplung zu vermeiden. Und genau wie beim Monitorstecker sollte das Interface eine hohe Kohäsion haben: Es sollte nur Dinge enthalten, die wirklich eng zusammen gehören.

Um das Interface Segregation Principle anzuwenden, stehen die beiden Refaktorisierungen [Extract Interface](http://refactoring.com/catalog/extractInterface.html) und [Extract Superclass](http://refactoring.com/catalog/extractSuperclass.html) zur Verfügung.