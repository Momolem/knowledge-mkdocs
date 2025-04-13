---
aliases: 
share: true
tags:
  - cleancode
title: Source Code Conventions
---
# Source Code Conventions

>**Warum?**
>Code wird häufiger gelesen als geschrieben. Daher sind Konventionen wichtig, die ein schnelles Lesen und Erfassen des Codes unterstützen.

Wir betrachten die folgenden Aspekte als wichtig:

-   Namensregeln
-   Richtig Kommentieren

Damit wollen wir nicht zum Ausdruck bringen, dass andere Konventionen unwichtig sind, wir wollen nur mit diesen beiden beginnen, weil sie uns elementar erscheinen. Bei allen Code Konventionen ist uns nämlich eines ganz wichtig: es geht weniger um die konkrete Ausgestaltung, sondern um konsequentes Einhalten der Konvention. Und es geht um das Bewusstsein, dass Konventionen notwendig sind.

## Namensregeln

>**Warum?**
>Ohne Namensregeln muss man sich wieder und wieder auf den Stil einzelner Entwickler einstimmen.

Namensregeln sollen den Leser des Codes dabei unterstützen den Code zu verstehen. Da es z.B. hilfreich ist, Felder von lokalen Variablen zu unterscheiden, könnte dies durch eine Namensregel unterstützt werden. Wie eine solche Konvention im Einzelfall aussieht ist Geschmacksache. Manche bevorzugen „this.xyz“ andere „_xyz“. Welche Variante man wählt ist uns nicht wichtig. Uns kommt es darauf an, dass die Konvention konsequent eingehalten wird. Die Notwendigkeit einer Namensregel für z.B. Felder hängt ferner vom Kontext ab. In einer Klasse mit 400 Zeilen wäre uns eine Namensregel, die Felder gegenüber Variablen hervorhebt, sehr wichtig, in überschaubaren Klassen tritt sie dagegen eher in den Hintergrund. Mit Hilfe der [[undefineddocs/hidden/Root Cause Analysis|Root Cause Analysis]] geht der [[undefineddocs/hidden/Clean Code Developer|Clean Code Developer]] der eigentlichen Ursache für die Notwendigkeit einer Namensregel auf den Grund.

## Richtig kommentieren

>**Warum?**
>Unnötige oder gar falsche Kommentare halten beim Lesen auf. Der Code sollte so klar und deutlich sein, dass er möglichst ohne Kommentare auskommt.

Salopp gesagt ist ein Kommentar im Code ein Hinweis darauf, dass der Code noch verbessert werden kann. Typisch für solche Fälle sind 3 Zeilen Code, die mit einem Kommentar überschrieben sind. An der Stelle hilft es wahrscheinlich, die drei Zeilen als Methode zu extrahieren (Refactoring: Extract Method) und den Kommentar als Name der Methode zu verwenden. Ganz allgemein kann der Bedarf an Kommentaren reduziert werden, in dem man gute Namen verwendet für Variablen, Methoden, Klassen, etc.

Statt
```csharp
int laenge; // in mm
```
besser
```csharp
int laengeInMM;
```

Statt
```csharp
public double Preis() {
	// Berechnet den Bruttopreis ...
}
```
besser
```csharp
public Money BruttoPreis() {
	...
}
```

Kommentiert werden sollte nicht was man tut, sondern, wenn überhaupt, wieso man etwas tut.