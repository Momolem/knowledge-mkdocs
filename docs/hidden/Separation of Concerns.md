---
share: true
aliases:
  - Separation of Concerns (SoC)
tags:
  - cleancode
linter-yaml-title-alias: Separation of Concerns (SoC)
title: Separation of Concerns (SoC)
---
# Separation of Concerns (SoC)

>**Warum?**
>Wenn eine Codeeinheit keine klare Aufgabe hat, ist es schwer sie zu verstehen, sie anzuwenden und sie ggf. zu korrigieren oder zu erweitern.

Übersetzt mit Trennung der Belange bedeutet dieses Prinzip, dass man nicht mehrere Belange in einer Klasse zusammenfassen soll. Was sind Belange? Belange sind „komplett verschiedene“ Zwecke. Man sagt auch, Belange seien orthogonal zu einander und vor allem orthogonal zur Hauptfunktionalität einer Funktionseinheit. Beispiele für typische Belange sind: Tracing, Logging, Transaktionalität, Caching. Diese Belange sollen nach dem Prinzip der Separation of Concerns in spezialisierte Funktionseinheiten ausgelagert werden.

Das Separation of Concerns Prinzip hängt eng mit dem Single Responsibility Prinzip zusammen. Dabei sind Concerns eine Übermenge von Responsibilities. Jede Responsibility besteht im Idealfall aus genau einem Concern, nämlich ihrer Kernfunktionalität. Oft sind in einer Responsibility jedoch mehrere Concerns vermischt. Da sich dies technisch meist nicht ganz vermeiden läßt, besagt das Prinzip nicht etwa, dass eine Responsibility nur aus einem Concern bestehen darf, sondern dass die Concerns getrennt sein sollten. Innerhalb einer Methode sollte beispielsweise klar erkennbar sein, dass es mehrere Concerns gibt. Ferner sollten die Concerns nicht irgendwie über die Methode verstreut sein, sondern so gruppiert, dass klar ist, was zu einem Concern gehört.

Im [[Domain Driven Design|Domain Driven Design]] versucht man beispielsweise die [[Business Domain|Business Domain]] von der Infrastruktur strikt zu trennen. So darf dort eine Klasse aus der Business Domain keinerlei Infrastruktur, etwa für Datenbankzugriffe, enthalten, sondern soll ausschließlich die Geschäftslogik abbilden. Persistenz ist ein „Concern“ der nichts mit der Business Logik zu tun hat. Separation of Concerns führt zu loser Kopplung und hoher Kohäsion. Die einzelnen Komponenten sind jeweils auf eine Aufgabe, einen Concern, fokussiert und dadurch leicht verständlich. Alle Teile aus denen die Komponente besteht, sind auf diese eine Aufgabe ausgerichtet, dadurch hängen die Teile eng zusammen (hohe [[Kohäsion|Kohäsion]]). Separation of Concerns führt darüber hinaus auch zu gut testbaren Komponenten. Denn wenn der Zweck einer Codeeinheit fokussiert ist, muss weniger breit getestet werden. In Bezug auf die zu testende Codeeinheit sind weniger Testparameterkombinationen zu prüfen. Soll die Trennung der Belange konsequent betrieben werden, muss die Objektorientierung um das Konzept der [[Aspektorientierten Programmierung|Aspektorientierten Programmierung]] (AOP) erweitert werden. Dadurch wird es möglich, Aspekte wie etwa [[Transaktionalität|Transaktionalität]], [[Tracing|Tracing]] oder [[Caching|Caching]] vollständig aus einer Methode herauszuziehen.