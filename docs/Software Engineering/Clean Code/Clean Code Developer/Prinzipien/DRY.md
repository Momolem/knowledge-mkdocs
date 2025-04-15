---
share: true
tags:
  - cleancode
aliases:
  - Don’t Repeat Yourself (DRY)
linter-yaml-title-alias: Don’t Repeat Yourself (DRY)
title: Don’t Repeat Yourself (DRY)
---
 
# Don’t Repeat Yourself (DRY)

>**Warum?**
>Jede Doppelung von Code oder Handgriffen leistet Inkonsistenzen und Fehlern Vorschub.

Das DRY-Prinzip lautet: _Don’t Repeat Yourself_ – Wiederhole dich nicht. Es gilt seit den Anfängen der Softwareentwicklung – sonst gäbe es keine Unterprogramme und keine Datennormalisierung. Dennoch ist es wahrscheinlich das am meisten missachtete Prinzip. Denn nichts ist einfacher, als Code durch Copy&Paste zu wiederholen. Gerade dann, wenn es mal schnell gehen soll, passiert das allzuoft.

[[../index|Clean Code Developer]] üben sich im roten Grad daher darin, dieses Prinzip stets zu beachten. Sie sind sich bewusst, wann sie Code oder andere Artefakte wiederholen. Sie erkennen solche Wiederholungen, die sie selbst oder andere erzeugt haben. Sie bereinigen Wiederholungen durch Refaktorisierungen – wenn keine anderen Prinzipien oder Beschränkungen dagegen sprechen.