---
aliases: 
share: true
tags:
  - cleancode
title: Error Measurement
---
# Error Measurement

>**Warum?**
>Nur wer weiß, wie viele Fehler auftreten, kann sein Vorgehen so verändern, dass die Fehlerrate sinkt.

Während der Softwareentwicklung passieren Fehler. Die passieren in allen Phasen: falsch verstandene oder unklar formulierte Anforderungen führen zu Fehlern genauso wie fehlerhafte Implementierungen. Am Ende ist alles ein Fehler, was dazu führt, dass der Kunde eine Software erhält, die nicht seinen Anforderungen entspricht. Iteratives Vorgehen und Reflexion sind zwei Bausteine, die dazu dienen, den Prozess zu verbessern. Um jedoch zu erkennen, ob tatsächlich eine Verbesserung eintritt, muss eine Messgröße vorliegen, an der man eine Entwicklung zum Besseren überhaupt ablesen kann.

Das Messen der Fehler kann durch Zählen oder durch Zeitnahme erfolgen. Dabei steht nicht die Präzision im Vordergrund, solange die Messmethode vergleichbare Daten liefert. Die Entwicklungstendenz über mehrere Iterationen hinweg soll ersichtlich werden. Ferner geht es nicht darum, die Verantwortlichkeit für einen Fehler zu klären. Am Ende ist es egal, wer den Fehler verursacht hat, so lange das Team daraus lernt und seinen Prozess verbessert.

Welche Fehler sind zu messen? Es sind nicht die Fehler, die während der Entwicklung auftreten. Die sind nicht zu vermeiden und führen hoffentlich dahin, dass am Ende einer Iteration ein fehlerfreies Produkt ausgeliefert wird. Vielmehr geht es um die Fehler, die nach einer Iteration zurückgemeldet werden vom Kunden bzw. seinem Stellvertreter (z.B. [[Product Owner|Product Owner]] oder Support). Das sind Fehler, die die Umsetzung neuer Anforderungen behindern. Zu messende Fehler sind also die, die auftreten, wenn man glaubt, dass es sie nicht geben dürfte ;-) Wann im Prozess ein Team diesen Punkt erreicht und flucht, weil da wieder so ein Fehler der sonstigen Arbeit dazwischenfunkt, ist teamindividuell zu bestimmen.

Weiter geht es beim [[../Grade/Blauer Grad|blauen Grad]].