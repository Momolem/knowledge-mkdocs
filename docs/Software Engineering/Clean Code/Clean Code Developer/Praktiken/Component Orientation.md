---
aliases: 
share: true
tags:
  - cleancode
title: Component Orientation
---
# Component Orientation

>**Warum?**
>Software braucht Black-Box-Bausteine, die sich parallel entwickeln und testen lassen. Das fördert Wandelbarkeit, Produktivität und Korrektheit.

Die Prinzipien des [[../index#Wertesystem|CCD-Wertesystems]] haben sich bisher vor allem auf kleinere Codeausschnitte bezogen. Was sollte in einer Methode stehen, was sollte über mehrere verteilt werden? Welche Methoden sollte eine Klasse veröffentlichen? Woher sollte ein Client-Objekt zu einem Service-Objekt kommen? Bisher ging es um Prinzipien für die Softwareentwicklung im Kleinen.

Hat das [[../index#Wertesystem|CCD-Wertesystem]] denn aber nichts zu größeren Strukturen, zur Softwareentwicklung im Großen zu sagen? Wie steht es mit der Softwarearchitektur? Genau hier setzt das Prinzip der Komponentenorientierung an. Bisher haben wir zwar auch schon das Wort „Komponente“ gebraucht, doch eher lax und in einem umgangssprachlichen Sinn. Von nun an jedoch soll _Komponente_ etwas sehr spezifisches beschreiben, das wir für grundlegend für evolvierbare Software halten.

Solange wir Software letztlich nur aus Klassen mit Methoden aufgebaut denken, versuchen wir sozusagen Computer auf Transistorebene zu beschreiben. Das funktioniert letztlich aber nicht, weil wir im Detailreichtum ersticken. Selbst die Klassen in Schichten zusammenzufassen hilft da nicht viel. Wir brauchen vielmehr sowohl ein Beschreibungsmittel für größere Softwarestrukturen. Aber nicht nur das: das Beschreibungsmittel sollte auch ein Implementationsmittel sein – so wie Klassen -, damit das Modell, der Plan, die Beschreibung sich im Code widerspiegelt.

Betriebssystemprozesse sind zwar solche architektonischen Mittel, letztlich sind auch sie jedoch zu groß. Solange die EXE eines Prozesses einer Applikation aus mehreren Hundert oder Tausend Klassen besteht, gewinnen wir nichts.

Hilfe bringt allerdings das Prinzip der Komponentenorientierung. Es besagt, dass ein Anwendungsprozess zunächst einmal aus Komponenten besteht und nicht aus Klassen. Erst die Bausteine der Komponenten sind dann Klassen. Und was ist eine Komponente? Es gibt einige Definitionen für Komponenten, von denen im Kern zwei Kriterien unverbrüchlich erscheinen:

-   Komponenten sind binäre Funktionseinheiten. (Eine Klasse hingegen ist eine Funktionseinheit auf Quellcodeebene.)
-   Die Leistung von Komponenten wird durch einen separaten (!) Kontrakt beschrieben. (Die Leistungsbeschreibung einer Klasse liegt hingegen in ihr. Es ist die Summe ihrer Methodensignaturen.)

Ein [[../index|CCD]] sucht beim Entwurf einer Software nach der Definition der Prozesse also zunächst nach den Komponenten, aus denen die Prozesse bestehen sollten. Er fragt sich, welche „Dienstleistungsblöcke“ machen die Anwendung aus? Und diese Blöcke sieht der [[../index|CCD]] als Black Boxes in Bezug auf ihren Aufbau aus Klassen an. Diese Blöcke sind Assemblies mit wohldefinierter Dienstleistung, aber unbekannter Struktur.

Eine Client-Komponente C weiß daher nichts über die Klassenstruktur ihrer Service-Komponente S. C kennt nur den Kontrakt von S, der unabhängig von der Implementation von S ist. Kontrakte sind insofern für Komponenten das, was Interfaces für Klassen sind. Nicht zufällig bestehen Kontrakte zu einem guten Teil oder gar vollständig aus Interfaces.

Komponenten sind also Elemente der Planung wie auch der Implementation. Um das zu unterstreichen, werden Komponenten physisch unabhängig voneinander implementiert; ein probates Mittel dafür sind _Komponentenwerkbänke_, d.h. separate Visual Studio Solutions je Komponentenimplementation. Das fördert nicht nur die Konzentration auf eine Aufgabe, weil man während der Arbeit an einer Komponente in der IDE nur deren Code sieht. Darüber hinaus fördert es auch konsequente [[../../Unit Test|Unit Tests]] unter Einsatz von Attrappen, da Quellcode anderer Komponenten nicht sichtbar ist. Außerdem steigert solche Codeorganisation die Produktivität, weil Komponenten dank ihrer separaten Kontrakte parallel implementiert werden können. Und schließlich stellt sich eine physische Isolation gegen den schleichenden Zuwachs an Entropie im Code. Denn wo Bindungen zwischen Komponenten nur via Kontrakt aufgebaut werden können, ist die Kopplung lose und kontrolliert.

Zur Komponentenorientierung gehören deshalb nicht nur binäre, größere Codeeinheiten mit separaten Kontrakten, sondern auch die Entwicklung der Kontrakte vor der Implementation (_Contract-first Design_). Denn sobald die Kontrakte definiert sind, die eine Komponente importiert und exportiert, kann die Arbeit an der Komponente unabhängig von allen anderen beginnen.

Siehe auch unter [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/).