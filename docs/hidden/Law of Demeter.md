---
share: true
aliases:
  - LoD
tags:
  - cleancode
title: Law of Demeter
---
# Law of Demeter

>**Warum?**
>Abhängigkeiten von Objekten über mehrere Glieder einer Dienstleistungskette hinweg führen zu unschön enger Kopplung.

Beim [Law of Demeter](http://www.lieser-online.de/blog/?p=124) geht es darum, das Zusammenspiel von Objekten auf ein gesundes Maß zu beschränken. Man kann es vereinfacht umschreiben mit „Don’t talk to strangers“. Nach dem Law of Demeter soll eine Methode nur folgende andere Methoden verwenden:

-   Methoden der eigenen Klasse
-   Methoden der Parameter
-   Methoden assoziierter Klassen
-   Methoden selbst erzeugter Objekte

Allerdings: Es ist zu berücksichtigen, dass ab und zu auch reine Datenhaltungsklassen Sinn ergeben. Auf diese muss man das Law of Demeter natürlich nicht anwenden. Es kann z.B. durchaus sinnvoll sein, die Konfigurationsdaten in mehrere Klassen hierarchisch zu verteilen, so dass sich am Ende folgender Zugriff auf einen Wert ergeben könnte:

```csharp
int margin = config.Pages.Margins.Left;
```

Würde man hier das Law of Demeter anwenden, wäre nur der Zugriff auf config.Pages gestattet.