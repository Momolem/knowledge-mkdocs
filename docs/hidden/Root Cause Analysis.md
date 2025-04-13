---
share: true
tags:
  - cleancode
aliases:
  - Root Cause Anaysis
linter-yaml-title-alias: Root Cause Anaysis
title: Root Cause Anaysis
---
 
# Root Cause Anaysis

>**Warum?**
>Symptome behandeln bringt vielleicht schnell eine Linderung – langfristig kostet es aber mehr Aufwand. Wer stattdessen unter die Oberfläche von Problemen schaut, arbeitet am Ende effizienter.

Regel vom ersten Tag als [[undefineddocs/hidden/Clean Code Developer|Clean Code Developer]] an sollte sein, bei Problemen immer intensiv nach der wahren Wurzel des Übels zu suchen. [[undefineddocs/hidden/Clean Code|Clean Code]] Developer geben sich nicht mit einer Symptomkur zufrieden. Beispiel: Die Sortierung von Daten im Speicher ist zu langsam. Eine oberflächliche Kur würde jetzt daran gehen, einzelne Anweisungen oder Anweisungsblöcke zu beschleunigen. Vielleicht wird der Einsatz von unsafe Code probiert, vielleicht eine Parallelisierung. Eine nähere Problemanalyse jedoch hätte ergeben, dass ein suboptimaler Algorithmus die Wurzel des Übels ist. Schwer verständliche Optimierungen auf niedriger Abstraktionsebene können also vermieden werden. Ein besserer Algorithmus ist die saubere Lösung.

Wurzelproblemanalyse ist also ein Dienst an der Verständlichkeit und am Aufwand. Denn bei Kenntnis des Wurzelproblems ist die Bereinigung meist weniger aufwändig als eine Symptomkur. Stößt der [[undefineddocs/hidden/Clean Code|Clean Code]] Developer auf ein Problem, so hält er also als erstes inne, um sich eine Chance zu geben, hinter die Symptome zu schauen.

Die Root Cause Analysis ist auch unter dem Begriff Five Why’s bekannt. Dieser Begriff stammt aus der Terminologie des Toyota Produktions Systems[[Toyota Produktions Systems|Toyota Produktions Systems]] (TPS). Die Grundidee: frage mindestens fünf mal „Warum?“.