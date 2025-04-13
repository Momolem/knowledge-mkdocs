---
share: true
aliases:
  - CD
tags:
  - cleancode
title: Continuous Delivery
---
# Continuous Delivery

>**Warum?**
>Als [[undefineddocs/hidden/Clean Code Developer|Clean Code Developer]] möchte ich sicher sein, dass ein Setup das Produkt korrekt installiert. Wenn ich das erst beim Kunden herausfinde, ist es zu spät.

Im [[undefineddocs/hidden/Grüner Grad|grünen Grad]] haben wir den [[undefineddocs/hidden/Continuous Integration|Continuous Integration]] Prozess für Build und Test aufgesetzt. Damit sorgt der [[undefineddocs/hidden/Continuous Integration|Continuous Integration]] Prozess dafür, dass Fehler während der Build- und Testphase schnell entdeckt werden. Wenn z.B. eine Änderung am Code dazu führt, dass eine andere Komponente nicht mehr übersetzt werden kann, weist der [[undefineddocs/hidden/Continuous Integration|Continuous Integration]] Prozess kurze Zeit nach dem Commit der Änderung auf den Fehler hin. Wenn am Ende jedoch ein Setup Programm produziert wird, welches sich aufgrund von Fehlern nicht installieren lässt, haben wir unser Ziel trotzdem nicht erreicht: funktionierende Software die bei unseren Kunden installiert werden kann.

Folglich müssen wir auch die Phasen Setup und Deployment automatisieren, um sie per Knopfdruck ausführen zu können. Nur so können wir sicher sein, dass wir installierbare Software produzieren. Und durch die Automatisierung ist sichergestellt, dass niemand einen wichtigen Schritt, der „zu Fuß“ ausgeführt werden muss, vergisst. So kann jeder im Team zu jedem Zeitpunkt den aktuellen Stand des Produktes installationsfertig produzieren und installieren.

Siehe auch unter [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/).