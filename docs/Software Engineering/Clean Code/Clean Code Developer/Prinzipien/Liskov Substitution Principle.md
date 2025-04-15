---
aliases: 
share: true
tags:
  - cleancode
title: Liskov Substitution Principle
---
 
# Liskov Substitution Principle

>[!question] **Warum?**
>Wer mit Erben zu tun hat, möchte keine Überraschungen erleben, wenn er mit Erblassern vertraut ist.

Auch das Liskov Substitution Principle ([LSP](https://drive.google.com/file/d/0BwhCYaYDn8EgNzAzZjA5ZmItNjU3NS00MzQ5LTkwYjMtMDJhNDU5ZTM0MTlh/view)) ist ein [[../../SOLID|SOLID]] Prinzip. Es besagt, dass Subtypen sich so verhalten müssen wie ihr Basistyp. Dies klingt zunächst banal. Am Beispiel von Exceptions wird deutlich, welche Probleme entstehen, wenn das Prinzip verletzt wird: Löst der Basistyp bei der Ausführung einer Methode keine Exception aus, müssen alle Subtypen sich an diese Regel halten. Löst die Methode eines Subtyps dennoch eine Exception aus, würde dies bei Verwendern, die ein Objekt vom Basistyp erwarten, Probleme verursachen, weil sie nicht darauf vorbereitet sind. Wenn der Basistyp an der Stelle keine Exception auslöst, ist der Verwender nicht darauf eingestellt, Exceptions behandeln zu müssen.

Allgemeiner kann man das Prinzip auch so ausdrücken, dass ein Subtyp die Funktionalität eines Basistyps lediglich erweitern, aber nicht einschränken darf. Wenn eine Methode im Basistyp auf einem bestimmten Wertebereich definiert ist, darf der Subtyp diesen Wertebereich übernehmen oder auch erweitern, er darf ihn jedoch keinesfall einschränken.

Aus dem Liskov Substitution Principle ergibt sich ferner die Empfehlung, über Vererbung sehr genau nachzudenken. In den allermeisten Fällen ist die Komposition der Vererbung vorzuziehen (_[[./Favour Composition over Inheritance|Favour Composition over Inheritance]]_). Bei der Vererbung sollte man in jedem Fall über das Verhalten nachdenken, nicht nur über die Struktur. Statt Vererbung als_is-a_ Relation zu betrachten und dabei nur die (Daten-)Struktur zu bedenken, sollte man besser von einer _behaves-as_ Relation ausgehen und das Verhalten der Klasse berücksichtigen.