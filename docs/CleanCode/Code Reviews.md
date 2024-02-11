---
aliases: 
share: true
tags:
  - cleancode
title: Code Reviews
---
---
aliases: 
share: true
tags: [cleancode]
title: Code Reviews
---
tags: #cleancode 

# Code Reviews

>**Warum?**
>Vier Augen sehen mehr als zwei. Wenn der eine Entwickler dem anderen seinen Code erklärt, tauchen meist Details auf, die bislang nicht bedacht wurden.

Reviews kommen vereinfacht in zwei Spielarten daher: als kontinuierlicher Prozess beim [Pair Programming](Pair%20Programming.md), als eigenständiger Prozessschritt beim Code Review. Das Ziel ist in beiden Fällen das gleiche: der Code soll von einem zweiten Entwickler begutachtet werden. Dies beugt der „Betriebsblindheit“ vor. Schon die Tatsache dass ein Entwickler seinen Code einem anderen Entwickler vorstellt und beschreibt, führt zu Aha Erlebnissen.

In der Regel wird erst durch die Diskussion mit anderen Entwicklern deutlich, wo die Stärken und Schwächen einer Codebasis liegen. Gerade der Prozess der ständigen Verbesserung bedingt es, sich mit der Sichtweise anderer Entwickler auseinander zu setzen.

Selbstverständlich ist nicht nur der Quellcode eine geeignete Basis für Reviews. Sie bieten eine günstige Möglichkeit, die Ergebnisse jeder Entwicklungstätigkeit zu überprüfen, sofern sie in einem „lesbaren“ Ergebnis münden. Neben rein informellen Reviews, wie dem [Pair Programming](Pair%20Programming.md) oder der Begutachtung durch eine zweite Person gibt es auch das formale Review mit einem Reviewprozess sowie entsprechenden Rollen. Weitere bekannte Arten des Review sind z.B. [Walkthrough](Walkthrough.md), [Technisches Review](Technisches%20Review.md), [Peer Review](Peer%20Review.md) und [Inspektion](Inspektion.md).

Reviews ergänzen dynamische Tests, wie z.B. den automatischen [Unit Test](./Unit%20Test.md) oder den automatischen Integrationstest aus dem [Gelben Grad](./Gelber%20Grad.md) bzw. [Orangenen Grad](./Orangener%20Grad.md) Im Gegensatz zu diesen Tests, sind Reviews auch sehr gut geeignet, Fehler in den Anforderungen zu finden. Auch können sie bereits sehr früh im Entwicklungsprozess eingesetzt und Fehler dadurch auch sehr früh gefunden werden. Und um so früher Fehler gefunden werden, um so günstiger ist auch deren Beseitigung.

An den orangen Grad schließt sich der [Gelbe Grad](./Gelber%20Grad.md) an.