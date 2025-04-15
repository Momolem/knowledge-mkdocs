---
aliases: 
share: true
tags:
  - cleancode
title: Statical Code Analysis
---
# Statical Code Analysis

>**Warum?**
>Vertrauen ist gut, Kontrolle ist besser – und je automatischer, desto leichter ist sie.

Wie definiert sich eigentlich die Qualität einer Codeeinheit, z.B. einer Klasse oder Komponente? Reicht es, dass sie funktional die Anforderungen des Kunden erfüllt? Reicht es, dass er schnell genug und skalierbar genug ist? Automatische Tests und schließlich Tests durch den Kunden geben darüber ja Auskunft. Ohne solche Anforderungskonformität hat Software natürlich keine relevante Qualität. Wenn sie dem Kunden nicht nützt, erübrigt sich jede weitere Frage.

Auf der anderen Seite reicht es, entgegen immer noch weit verbreiteter Annahme, allerdings auch nicht, anforderungskonform zu sein. Hohe Qualität ergibt sich nicht allein aus Funktionalität und z.B. Performance. Denn neben den funktionalen und nicht funktionalen Anforderungen gibt es auch noch eine meist unausgesprochene verborgene Anforderung: Kunden wollen auch immer, dass Software nicht nur heute ihre Anforderungen erfüllt, sondern auch noch morgen und übermorgen. Kunden wollen Investitionsschutz durch Wandelbarkeit.

Für Kunden ist diese Anforderung meist implizit. Sie glauben, es sei selbstverständlich, dass ein immaterielles Produkt wie Software sich quasi unendlich und auf Knopfdruck an neue Anforderungen anpassen ließe. Auch Führungskräfte, die nicht aus der Softwareentwicklung stammen, glauben das oft. Und sogar Softwareentwickler selbst!

Größer könnte das Missverständnis über Software jedoch kaum sein. Wandelbarkeit ist weder selbstverständlich im Sinne eines von jedem Softwareentwickler ohnehin verfolgten Zieles, noch ergibt sie sich durch irgendetwas quasi von selbst. Wandelbarkeit ist vielmehr harte Arbeit und muss ständig gegen andere Werte abgewogen werden.

Wenn sonstige Anforderungskonformität sich nun durch (automatisierte) Tests feststellen lässt, wie steht es dann mit der Wandelbarkeit? Lässt sich die Qualität von Code im Hinblick auf seine (Über)Lebensfähigkeit auch automatisch messen? Zum Teil. Nicht alle Aspekte, die Software evolvierbar machen, sind automatisch prüfbar. Ob zum Beispiel Software offen für Erweiterungen durch ein Add-In-Konzept gehalten wird, ist nicht automatisiert erkennbar.

Dennoch gibt es [Metriken](http://en.wikipedia.org/wiki/Software_metric), deren Wert für eine Software sich „ausrechnen“ lässt. [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/) helfen dabei. Diese Tools sollten daher in jedem Softwareprojekt zum Einsatz kommen.

-   Für [[../../Legacy Code|Legacy Code]] können die Tools den Status Quo erheben und somit eine Grundlinie definieren, mit der die weitere Entwicklung des Codes (zum Besseren) verglichen werden kann.
-   Für neuen Code, der mit Wandelbarkeit im Blick geplant wurde, zeigt solch statische Codeanalyse, ob er das Ideal der Planung erfüllt.

[[../index|CCD]] sind nicht damit zufrieden, Code nur automatisiert zu testen. Sie haben auch immer ein Auge auf seine Wandelbarkeit, denn sie wissen, dass Kunden daran genauso interessiert sind – egal, ob sie es explizit gesagt haben oder nicht.

Siehe auch unter [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/).