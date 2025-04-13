---
aliases: 
share: true
tags:
  - cleancode
title: Information Hiding Principle
---
 
# Information Hiding Principle

>**Warum?**
>Durch das Verbergen von Details in einer Schnittstelle werden die Abhängigkeiten reduziert.

Beim Design einer Schnittstelle sollte man sich fragen, welche Details außen unbedingt sichtbar sein müssen. Mit Schnittstelle sind hier nicht nur Interfaces im objektorientierten Sinne gemeint, sondern auch implizite Schnittstellen. Jede Klasse hat zwangsläufig eine implizite Schnittstelle – sie enthält alle nach außen sichtbaren Details. Je mehr Details von außen sichtbar sind, desto höher ist die Kopplung zwischen der Klasse und ihren Verwendern. Benutzen die Verwender einer Klasse erstmal ein Detail, wird es schwerer, dieses Detail zu verändern. Dies steht der Wandelbarkeit der Software entgegen.