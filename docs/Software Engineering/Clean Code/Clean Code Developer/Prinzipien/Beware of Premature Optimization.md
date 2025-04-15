---
aliases: 
share: true
tags:
  - cleancode
title: Beware of Premature Optimization
---
 
# Beware of Premature Optimization

>**Warum?**
>Optimierungen kosten immer viel Aufwand. Wer Vorsicht walten lässt, spart oft wertvolle Ressourcen für das, was dem Kunden wirklich nützt.

> Rules of Optimization:
> 
> Rule 1: Don’t do it.
> 
> Rule 2 (for experts only): Don’t do it yet.
> 
> ~ M.A. Jackson

> More computing sins are committed in the name of efficiency (without necessarily achieving it) than for any other single reason – including blind stupidity. ~ W.A. Wulf

Im Vordergrund steht immer die Verständlichkeit von Code. Optimierter Code ist aber oft alles andere als lesbar. Indem er auf das absolut Notwendige in kürzester Form reduziert ist, mag er zwar die funktionalen und nicht funktionalen Anforderungen des Kunden erfüllen – doch er spiegelt sie meist nicht mehr verständlich wider. Das ist kontraproduktiv im Sinne der meist gewünschten Langlebigkeit einer Software. Donald Knuth schrieb bereits 1974: 
>„_We should forget about small efficiencies, say about 97% of the time: premature optimization is the root of all evil._“ 
>
>(Knuth, Donald. [Structured Programming with go to Statements](http://web.archive.org/web/20130803163743/http://pplab.snu.ac.kr/courses/adv_pl05/papers/p261-knuth.pdf), ACM Journal Computing Surveys, Vol 6, No. 4, Dec. 1974. p.268.)

Die Pfadfinderregel ist also nicht so gemeint, dass immer weiter nach Codeoptimierungen gestrebt werden sollte. Sie bezieht sich vielmehr auf deren Gegenteil: Verständlichkeit und Wandelbarkeit.

Wenn es dem [[../index|Clean Code Developer]] also in den Fingern zuckt, weil er denkt, er könne doch noch ein Quäntchen Performance durch eine Optimierung herausholen, dann sollte er mindestens zweimal überlegen. Zum einen würde er dadurch die Verständlichkeit verschlechtern, zum anderen aber ist es wahrscheinlich, dass solche Optimierung aus mehreren Gründen gar nicht nötig ist. Ist die Performanceschwäche nicht nur punktuell und ein Sonderfall, wird sich die nächste größere Refaktorisierung ihrer wahrscheinlich ohnehin annehmen, denn dann liegt ihr ein grundsätzliches Strukturproblem zugrunde. Oder die nächste Hardwaregeneration bügelt den Performanceknick aus. Oder der Kunde fühlt sich durch ihn gar nicht gestört. Ohnehin muss der Kunde die Forderung nach der Optimierung gestellt haben. Keine Codeveränderung ohne vom Kunden erwarteten Nutzen. Denn nur für ihn ist er bereit zu zahlen.

Der Regel, sich im Zweifelsfall gegen Optimierungen zu entscheiden, liegt somit eine noch fundamentalere zugrunde: YAGNI – _You ain’t gonna need it_. Sie ist in ihrer vollen Ausprägung allerdings erst Bestandteil des [[../Grade/Blauer Grad|Blauer Grad]]

PS: Wenn denn entgegen allen Warnungen und Bedenken gerade eine Performanceoptimierung unumgänglich ist, dann sollte sie immer nur aufgrund einer detaillierten Analyse mit einem Profiler begonnen werden. Denn nur wer mit einem Profiler nachvollziehbar Performance-Engpässe lokalisiert hat, kann während und nach der Optimierung prüfen, ob und inwiefern er sie geweitet hat.