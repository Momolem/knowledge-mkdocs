---
share: true
aliases:
  - Design and Implementation Don’t Overlapp
tags:
  - cleancode
linter-yaml-title-alias: Design and Implementation Don’t Overlapp
title: Design and Implementation Don’t Overlapp
---
# Design and Implementation Don’t Overlapp

>**Warum?**
>Planungsunterlagen, die mit der Umsetzung nichts mehr gemein haben, schaden mehr, als dass sie nützen. Deshalb nicht die Planung aufgeben, sondern die Chance auf Inkonsistenz minimieren.

Eines der grundlegenden Probleme der Softwareentwicklung sind Implementationen, denen eine vorausgegangene Planung nicht mehr anzusehen ist. Da hängen dann Entwurfsdiagramme an der Wand, die kaum noch etwas mit der Coderealität zu tun haben. Die Ursache dafür ist eine Verletzung des fundamentalen [[undefineddocs/hidden/DRY|DRY]]-Prinzips: Entwurf und Implementation sind Wiederholungen desselben, der Struktur einer Software. Da Implementation auf Entwurf folgt und den Löwenanteil der Arbeit ausmacht, geraten beide schnell aus dem Tritt, wenn Strukturänderungen während der Implementation nicht immer wieder in den Entwurf eingearbeitet werden. Entwurfsdiagramme sind nach Beginn der Implementation sonst bald nichts mehr wert.

Wie kann die Situation verbessert werden? Sollte vielleicht auf Entwurf verzichtet werden, wenn letztlich in der Implementation die „Strukturwahrheit“ liegt? Nein, sicher nicht. Entwurf muss sein. Ohne Planung gibt es keine Zielvorstellung. Aber Entwurf und Implementation müssen dem [[undefineddocs/hidden/DRY|DRY]]-Prinzip gerecht werden. Deshalb sollten Entwurf und Implementation sich so wenig überlappen wie möglich. Ihre Schnittstelle sollte dünn sein. Wenn das der Fall ist, stellen sie keine Wiederholungen mehr dar, sondern beschreiben unterschiedliches. Das bedeutet: Entwurf/Architektur kümmert sich nicht um die Implementation und Implementation kümmert sich nicht um Architektur.

Und wo verläuft diese Trennlinie? Bei den so genannten Komponenten (s.u. Praktiken). Architekten kümmern sich nicht um den internen Aufbau von Komponenten. Für sie sind es Black Boxes, deren Klassenstruktur nicht architekturrelevant ist. Umgekehrt ist für einen Komponentenimplementierer die Architektur irrelevant. Was er zu implementieren hat, ergibt sich aus den Komponentenkontrakten, die seine Komponente importiert und exportiert. Einen größeren Zusammenhang muss er nicht kennen.

Die Aufgabe der Architektur ist es mithin, Software in Komponenten zu zerlegen, deren Abhängigkeiten zu definieren und Leistungen in Kontrakten zu beschreiben. Diese Strukturen werden dann auch einzig durch Architekten gepflegt. Und die Aufgabe der Implementation ist es, die von der Architektur definierten Komponenten zu realisieren. Wie sie das tun, ist nicht architekturrelevant. Ihre innere Struktur ist für die Architektur unsichtbar.