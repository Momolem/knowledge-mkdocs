---
aliases: 
share: true
tags:
  - cleancode
title: Iterative Development
---
# Iterative Development

>**Warum?**
>Frei nach von Clausewitz: Kein Entwurf, keine Implementation überlebt den Kontakt mit dem Kunden. Softwareentwicklung tut daher gut daran, ihren Kurs korrigieren zu können.

Natürlich schreitet Softwareentwicklung immer von einer Planung über die Implementation zu einem Test durch den Kunden voran. Irrig ist allerdings die Annahme, ein Projekt käme mit einer Planungsphase und einer Implementationsphase und einer Kundentestphase aus. Das funktioniert – wenn überhaupt – nur in trivialen Szenarien, wo in der Planungsphase alle Anforderungen bekannt sind. In realen Projekten jedoch liefert jede Phase Erkenntnisse für vorhergehende Phasen. Allemal durch den Kundentest ergeben sich Konsequenzen für die Planung und Implementation.

Solche Erkenntnisse können allerdings nur Einfluss auf ein Projekt nehmen, wenn das Vorgehen nicht linear ist. Wenn es von einer späteren Phase keinen Weg zurück zu einer früheren Phase gibt, ist Feedback nutzlos.

Um Feedback in ein Softwareprodukt einfließen lassen zu können, muss der Entwicklungsprozess Schleifen enthalten. Allemal die Schleife von der Kundentestphase zurück zur Planung ist nötig. Das heißt, Softwareentwicklung kann nur iterativ, also in mehreren Durchläufen, über den Anforderungskatalog des Kunden stattfinden. Wer versucht, „mit einem Mal“ (big bang) auszuliefern, handelt dieser Erkenntnis zuwider. Der Softwareentwicklungsprozes ist vielmehr so zu planen, dass er sich durch die Anforderungen „in kleinen Happen durchbeißt“. Jeder dieser Happen sollte nicht größer sein, als dass der Durchlauf von Planung bis Kundentest mehr als 2-4 Wochen dauert. Nur dann kommt das Feedback vom Kunden häufig genug, um nicht allzu lange in der Umsetzung in die Irre zu laufen.

Softwareentwicklung ist damit ein Lernprozess. In seinem Verlauf lernt das Projektteam etwas über die Anforderungen des Kunden. Es hört ihm zu, plant, implementiert, und händigt eine Softwareversion aus, die das Verständnis des Gehörten widerspiegelt. Dann hört das Team wieder zu, plant weiter/erneut nach den aktuellen Erkenntnissen usw. usf. immer im Kreis. Iteration für Iteration. Manchmal wird etwas aus einer früheren Iteration verfeinert, manchmal Neues hinzugefügt.

Doch nicht nur die Entwicklung einer Software ist ein Lernprozess. Lernen sollte auch auf organisatorischer Ebene stattfinden. Das Team sollte nicht nur über den Kunden etwas lernen, sondern auch über sich selbst. Deshalb sollte es auch immer wieder „Haltepunkte“ geben, an denen das Team über sein Vorgehen reflektiert. Die Erkenntnisse aus solcher Retrospektive fließen dann ein in die nächste Iteration der organisatorischen Entwicklung. Hier schließt der blaue Grad an den roten Grad an, zu dem die tägliche persönliche Reflexion gehört.

Natürlich muss jede Iteration auch ein Ende haben. Und damit man weiß ob man fertig ist, muss vorher klar definiert sein, was in der Iteration erreicht werden soll. Die Erreichbarkeit von Zielen kann immer nur geschätzt werden, auch dabei hilft die Reflexion, um die Schätzungen schrittweise soweit zu verbessern, dass sie für die Planung ausreichend genau sind. Doch wann ist das vorher definierte Ziel erreicht? [‚What is done?‘](http://www.hanselminutes.com/119/what-is-done-a-conversation-with-scrum-co-creator-ken-schwaber) Oberstes Ziel ist die Lieferung funktionsfähiger Software an unsere Kunden. Folglich kann das Ziel nur erreicht sein wenn wir auslieferungsfertige Software produziert haben. Das bedeutet insbesondere, dass die Software getestet ist und dass sie per Setup installiert werden kann. Durch [[undefineddocs/hidden/Continuous Integration|Continuous Integration]] stellen wir dies kontinuierlich sicher. Keinesfalls dürfen wir kurz vor Ende einer Iteration entscheiden, dass ein Ziel erreicht ist, obwohl noch nicht alle Tests abgeschlossen sind.

Siehe auch unter [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/).