---
share: true
aliases:
  - CI
tags:
  - cleancode
title: Continuous Integration
---
# Continuous Integration

>**Warum?**
>Automatisierung und Zentralisierung der Softwareproduktion machen produktiver und reduzieren das Risiko von Fehlern bei der Auslieferung.

Oft wird die Integration der Softwarekomponenten zeitlich nach hinten geschoben und erfolgt aufwendig und fehleranfällig „per Hand“. Eigentlich sollte die Software aber zu jedem Zeitpunkt vollständig lauffähig sein. Mit Continuous Integration bezeichnet man einen Prozess, der dafür sorgt dass der gesamte Code nach der Übermittlung von Änderungen übersetzt und getestet wird.

Der Continuous Integration Prozess ist vor allem für Teams wichtig, denn er sorgt dafür, dass nach der Übermittlung von Änderungen der gesamte Code übersetzt und getestet wird, nicht nur der Teil an dem ein Entwickler gerade gearbeitet hat. Die automatisierten Tests sollten von jedem Entwickler ausgeführt werden bevor er Änderungen in die zentrale [[./Version Control System|Versionskontrolle]] übermittelt. Daran ändert sich durch Continuous Integration nichts. Um sicherzustellen, dass die Tests tatsächlich ausgeführt werden und Fehler frühzeitig erkannt werden, laufen sie in jedem Fall auf dem Continuous Integration Server. Dies entbindet den Entwickler nicht davon die Tests vor dem Commit auszuführen, schließlich behindert fehlerhafter Code der in die [[./Version Control System|Versionskontrolle]] eingecheckt wurde das gesamte Team, möglicherweise sogar weitere Teams. So sorgt der Continuous Integration Prozess dafür dass teamübergreifend sichergestellt wird dass Fehler so früh wie möglich erkannt werden.

Für den Continuous Integration Prozess stehen zahlreiche [Softwaretools](https://clean-code-developer.de/weitere-infos/werkzeuge/) zur Verfügung. Neben dem kontinuierlichen Build und Test, der sofort erfolgt, wenn Änderungen in die [[./Version Control System|Versionskontrolle]] übertragen werden, können durch Continuous Integration auch länger laufende Prozesse, wie z.B. Datenbanktests, automatisiert werden. Diese werden dann z.B. nur nachts ausgeführt. Im grünen Grad wird lediglich der Build- und Testprozess berücksichtigt. Das kontinuierliche Setup und Deployment der Software folgt erst später im [[../Grade/Blauer Grad|blauen Grad]].

[[Martin Fowler|Martin Fowler]] hat einen sehr guten Artikel zu diesem Thema verfasst, nachzulesen unter [](http://www.martinfowler.com/articles/continuousIntegration.html)[http://www.martinfowler.com/articles/continuousIntegration.html](http://www.martinfowler.com/articles/continuousIntegration.html)

Siehe auch unter [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/).