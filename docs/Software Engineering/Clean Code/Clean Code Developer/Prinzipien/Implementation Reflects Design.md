---
aliases: 
share: true
tags:
  - cleancode
title: Implementation Reflects Design
---
# Implementation Reflects Design

>**Warum?**
>Umsetzung, die von der Planung beliebig abweichen kann, führt direkt in die Unwartbarkeit. Umsetzung braucht daher einen durch die Planung vorgegebenen physischen Rahmen.

Architektur und Implementation sollen nicht überlappen, damit sie das [[./DRY|DRY]]-Prinzip nicht verletzten. So werden Inkonsistenzen vermieden, die dadurch entstehen können, dass auf der einen Seite etwas geändert wird, ohne diese Änderung auf der anderen Seite nachzuführen.

Nichtsdestotrotz macht die Architektur aber ja Aussagen über die Implementation. Nicht ihre Details, aber ihre grundsätzliche Form. Architektur definiert die Strukturelemente und deren Beziehungen innerhalb eines Codesystems. Implementation existiert also auch bei Abwesenheit von Überlappungen nicht unabhängig von Architektur, sondern sozusagen in ihr.

Genau das sollte sich dann aber auch in der Implementation ausdrücken. So wird die leichter verständlich, so kann besser sichergestellt werden, dass die Implementation tatsächlich der Architektur folgt. Die von der Architektur auf verschiedenen Abstraktionsebenen definierten Strukturelemente sollten deshalb nicht in einem großen „Codetopf“ (z.b. eine große Visual Studio Solution) „zusammengerührt werden“. Viel besser auch im Sinne hoher Produktivität und einfacher Testbarkeit ist es, die logischen Strukturen der Architektur so physisch wie möglich zu manifestieren.

1.  Die von der Architektur geplanten Strukturen auf verschiedenen Abstraktionsebenen sollten sich so weitgehend wie möglich in der Codeorganisation widerspiegeln. Das bedeutet zum einen, dass die Architektur als Strukturelemente vor allem physische Codeeinheiten benutzt. Und zum anderen sollen diese Strukturelemente dann aber auch im Quellcode bzw. in der Codeorganisation im Repository klar sichtbar sein.
2.  Bei der Arbeit an der Implementation der Strukturelemente und insbesondere innerhalb von Komponenten sollen Architekturänderungen „im Vorbeigehen“ unmöglich sein. Wer in bzw. an einem Strukturelement arbeitet, also an einem Teil, darf nicht ad hoc die umliegende Struktur, d.h. das Ganze, ändern können. Nur wenn das gewährleistet ist, wächst die Entropie einer Software nicht unkontrolliert. Das ist wichtig, da das Hauptziel von Architektur ist, die Entropie und damit die Komplexität von Software zu minimieren.

Planung muss sein. Implementation darf Planung nicht torpedieren. (Wenn auch Erkenntnisse während der Implementation natürlich auf die Planung zurückwirken dürfen.) Deshalb sind Planung und Implementation zu entkoppeln. Und wo das nicht möglich ist, da sollte die Planung mit Mitteln der Implementation arbeiten und die Implementation physisch die Planung widerspiegeln.