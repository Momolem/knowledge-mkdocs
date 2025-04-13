---
share: true
aliases:
  - Single Level of Abstraction (SLA)
tags:
  - cleancode
linter-yaml-title-alias: Single Level of Abstraction (SLA)
title: Single Level of Abstraction (SLA)
---
# Single Level of Abstraction (SLA)

>**Warum?**
>Die Einhaltung eines Abstraktionsniveaus fördert die Lesbarkeit

Eine Codezeile kann auf verschiedenen Abstraktionsniveaus liegen. Die Zuweisung eines Wertes an eine Variable liegt auf einem niedrigeren Abstraktionsniveau als etwa ein Methodenaufruf. Schließlich kann sich hinter dem Methodenaufruf weit mehr Logik befinden als in der Zuweisung einer Variable. Selbst Methodenaufrufe können auf unterschiedlichen Abstraktionsniveaus stehen. Der Aufruf einer Methode aus einem Framework steht auf einem anderen Niveau, als der Aufruf einer Methode der Anwendung.

Damit Code gut zu lesen und zu verstehen ist, sollte in einer Methode nur ein Abstraktionsniveau verwendet werden. Andernfalls fällt es dem Leser schwer, Essentielles von Details zu unterscheiden. Wenn Bitpfriemeleien erforderlich sind, sollten diese nicht mit dem Aufruf von Methoden vermischt werden.

Hilfreich als Analogie ist der Blick auf Artikel in der Tageszeitung: dort steht zu oberst das Allerwichtigste, die Überschrift. Aus ihr sollte in groben Zügen hervorgehen, wovon der Artikel handelt. Im ersten Satz des Artikels wird dies auf einem hohen Abstraktionsniveau beschrieben. Je weiter man im Artikel fortschreitet, desto mehr Details tauchen auf. So können wir auch unseren Code strukturieren. Der Name der Klasse ist die Überschrift. Dann folgen die öffentlichen Methoden auf hohem Abstraktionsniveau. Diese rufen möglicherweise Methoden auf niedrigerem Niveau auf, bis zuletzt die „Bitpfriemelmethoden“ übrig bleiben. Durch diese Einteilung kann ich als Leser der Klasse entscheiden, welchen Detaillierungsgrad ich mir ansehen möchte. Interessiert mich nur grob, wie die Klasse arbeitet, brauche ich mir nur die öffentlichen Methoden anzuschauen. In ihnen wird die Funktionalität auf einem hohen Abstraktionsniveau gelöst. Interessieren mich weitere Details, kann ich tiefer einsteigen und mir die privaten Methoden ansehen.