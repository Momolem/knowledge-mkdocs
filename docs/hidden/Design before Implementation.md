---
aliases: 
share: true
tags:
  - cleancode
title: Design before Implementation
---
# Design before Implementation

>**Warum?**
>Vor der Umsetzung muss eine Lösung entworfen werden. Andernfalls findet kein konsequentes Nachdenken über die Lösung statt.

Die Aufgabe eines Entwicklers besteht darin, Anforderungen in Code zu übersetzen. Dazu ist es erforderlich, eine Lösung für die Anforderungen zu entwickeln. Es muss nachgedacht werden. Wie kann das aber auf gute Weise geschehen, wenn Entwickler direkt ins Codieren springen?

In trivialen Fällen mag es möglich sein, direkt Code zu schreiben. Dennoch wird auch beim unmittelbaren Sprung ins Codieren über die Lösung nachgedacht. Allerdings geschieht dies eher unbewusst, vor allem aber _während_ der Umsetzung. Der Entwickler denkt ein wenig nach, codiert, denk nach, codiert, usw. Es fehlt hier ein konsequentes Durchdenken der Lösung, getrennt von der Umsetzung.

Spätestens, wenn eine Gruppe von Entwicklern gemeinsam als Team arbeiten möchte, muss der Entwurf zeitlich getrennt von der Umsetzung stattfinden. Andernfalls ist keine flüssige arbeitsteilige Vorgehensweise möglich.

Der Entwurf ermöglicht es dem Team bzw. einem einzelnen Entwickler, bereits vor der Codierung über wichtige Prinzipien nachzudenken. Es entstehen bspw. erst gar keine Methoden oder Klassen mit mehreren Verantwortlichkeiten, da schon auf der Ebene des Entwurfs über das [[undefineddocs/hidden/Single Responsibility Principle|Single Responsibility Principle]] nachgedacht werden kann. Damit erspart sich das Team den Refaktorisierungsaufwand der entsteht, wenn „drauf los“ codiert wird.

Siehe auch [](https://flow-design.info/)[https://flow-design.info](https://flow-design.info).