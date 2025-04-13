---
aliases: 
share: true
tags:
  - cleancode
title: Code Coverage Analysis
---
# Code Coverage Analysis

>**Warum?**
>Traue nur Tests, von denen du weißt, dass sie auch wirklich das Testareal abdecken.

[[undefineddocs/hidden/Unit Test|Unit Tests]] sollten nach Möglichkeit alle Pfade durch unseren Code abdecken. Nur so gewinnen wir das Vertrauen, dass der Code korrekt arbeitet. Um in Erfahrung zu bringen, welche Codebereiche bislang nicht durch Tests abgedeckt sind, bedienen wir uns der _Code Coverage Analyse_. Diese dient dazu, Bereiche im Code aufzudecken, die noch nicht während der automatisierten Tests ausgeführt werden.

[[undefineddocs/hidden/Unit Test|Unit Tests]] sollten eigentlich 100% des zu testenden Codes abdecken. Zwar bedeutet das nicht automatisch, dass genügend Tests existieren, doch weniger als 100% Code Coverage zeigen an, dass es noch Taschen von Code gibt, über die überhaupt noch keine Korrektheitsaussage gemacht werden kann. 100% Codeabdeckung sind deshalb immer anzustreben.

In der Praxis zeigt es sich jedoch, dass 100% Codeabdeckung nicht immer mit unmittelbar vertretbarem Aufwand erreicht werden können. Wie auch sonst im Leben kann die Mühe für die letzten 2,3,4 Prozent überproportional wachsen. Deshalb kann es nach genauer Analyse der Abdeckungslage akzeptabel sein, mit weniger als 100% zufrieden zu sein.

Unterhalb von 90% ist die Abdeckung dann allerdings so löchrig, dass sie als unprofessionell anzusehen ist. Wer also mit automatischen Tests beginnt, sollte immer auch gleichzeitig die Codeabdeckung messen. Sonst lässt sich keine Aussage über die Qualität der Tests machen.

Für die Messung der Codeüberdeckung gibt es zwei einfache Kennzahlen, die als C0- und C1-Kennzahlen bezeichnet werden. Die C0-Kennzahl misst die Anweisungsüberdeckung, wogegen die C1-Kennzahl die Entscheidungsüberdeckung bzw. die Zweigüberdeckung misst.

```csharp
C0 = (Anzahl der getesteten Anweisungen / Anzahl der gesamten Anweisungen) * 100%
```

```csharp
C1 = (Anzahl der getesteten Entscheidungen bzw. Zweige / Anzahl der gesamten Entscheidungen bzw. Zweige) * 100%
```

C1 ist dabei die stärkere Kennzahl, da 100% Entscheidungsüberdeckung bzw. Zweigüberdeckung 100% Anweisungsüberdeckung impliziert. Der Umkehrschluss gilt nicht.

Der Anweisungsüberdeckungstest sowie der Zweigüberdeckungstest arbeiten auf Basis eines [Kontrollflussgraphen](http://de.wikipedia.org/wiki/Kontrollflussgraph) während der Entscheidungsüberdeckungstest direkt auf dem Quellcode basiert. Die Testverfahren Anweisungsüberdeckungstest und Zweigüberdeckungstest sind sehr gut unter [](http://de.wikipedia.org/wiki/Kontrollflussorientierte_Testverfahren)[http://de.wikipedia.org/wiki/Kontrollflussorientierte_Testverfahren](http://de.wikipedia.org/wiki/Kontrollflussorientierte_Testverfahren) beschrieben.

Siehe auch unter [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/).