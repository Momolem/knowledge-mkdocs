---
share: true
aliases: []
tags:
  - cleancode
linter-yaml-title-alias: Tell, don’t ask
title: Tell, don’t ask
---
# Tell, don’t ask

>**Warum?**
>Hohe [[Kohäsion|Kohäsion]] und lose Kopplung sind Tugenden. Öffentliche Zustandsdetails einer Klasse widersprechen dem.

Etwas provokant formuliert, sollten Klassen keine Property Getter haben. Diese verführen den Verwender einer Klasse dazu, anhand von Werten, die ein Objekt liefert, Entscheidungen zu treffen. Statt also dem Objekt mitzuteilen, was es tun soll, wird es befragt, um dann von außen Betrachtungen über den internen Zustand des Objektes anzustellen.

Eines der Kernprinzipien der [[OOP|OOP]] lautet _[[../Prinzipien/Information Hiding Principle|Information Hiding Principle]]_ (siehe dazu auch im [[../Grade/Gelber Grad|gelben Grad]]). Keine Klasse soll Details nach außen tragen, aus denen hervorgeht, wie sie intern implementiert ist. Benötigt eine Klasse für ihre Arbeit einen internen Zustand, wird dieser typischerweise in einem internen Feld abgelegt. Wenn nun dieser Wert auch nach außen sichtbar ist, werden Verwender verleitet, diesen eigentlich internen Zustand des Objektes für eigene Entscheidungen heranzuziehen. Dadurch wird die Klasse schnell zur reinen Datenhaltung degradiert. Eine Implementierung, bei der einem Objekt mitgeteilt wird, was es tun soll, ist in jedem Fall vorzuziehen. Dadurch muss es den Verwender nicht mehr interessieren, wie die Klasse die Aufgabe intern bewerkstelligt.

Als Ergebnis des [Tell don’t ask](http://www.pragprog.com/articles/tell-dont-ask) Prinzips entstehen Objekte mit Verhalten statt „dummer“ Datenhaltungsobjekte. Das Zusammenspiel der Objekte ist lose gekoppelt, da die Objekte keine Annahmen über die kollaborierenden Objekte machen müssen. Aber nicht nur das! Wenn Objekte ihren Zustand nicht veröffentlichen, behalten sie die Entscheidungshoheit. Die Kohäsion des entscheidenden Codes wächst damit, weil er an einem Ort zusammengelegt wird.

Ein typisches Codebeispiel ist im folgenden zu sehen. Statt hier zunächst zu fragen, ob im Logging die Tracemeldungen aktiviert sind (Ask), sollte die Logging Bibliothek direkt angewiesen werden, die Tracemeldung auszugeben (Tell). Die Bibliothek soll dann intern selbst entscheiden, ob die Meldung geloggt wird oder nicht.
```csharp
if (_logger.Trace()) {
	_logger.TraceMsg(„… eine Meldung… „);
}
```