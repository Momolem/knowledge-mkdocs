---
share: true
aliases:
  - You Ain’t Gonna Need It
  - YAGNI
tags:
  - cleancode
linter-yaml-title-alias: You Ain’t Gonna Need It
title: You Ain’t Gonna Need It
---
$# You Ain’t Gonna Need It 

>**Warum?**
Dinge die niemand braucht, haben keinen Wert. Verschwende an sie also keine Zeit.

Das YAGNI-Prinzip (_You Ain´t Gonna Need It_) ist eines der einfachsten in der Softwareentwicklung – und doch wohl das nach dem [[./DRY|DRY]]-Prinzip am häufigsten verletzte Prinzip. Deshalb steht YAGNI nicht nur am Anfang des [[../Grade/Roter Grad|roten Grades]], sondern auch hier gegen Ende des Weges durch das [[../index#Wertesystem|Wertesystem]].

Geschuldet ist das YAGNI-Prinzip dem in der Softwareentwicklung besonderen Verhältnis von Anforderungsgenauigkeit und Produktmaterialität. Anforderungen sind notorisch ungenau oder wechselnd und das Produkt, in dem sie umgesetzt werden sollen, immateriell. Im Vergleich zum Maschinen- oder Gebäudebau ist das Material also unendlich flexibel und kann sich prinzipiell mit vergleichsweise wenig Aufwand an quasi jede Anforderung anpassen lassen. Hohe Volatiliät bzw. Ungenauigkeit trifft also auf hohe Flexibilität. Das scheint zunächst einmal ideal.

Die Praxis zeigt jedoch, dass gerade in diesem Verhältnis der Keim des Misserfolges vieler Projekte liegt. Kurzfristig betrachtet, versuchen die Projekte mit dem Naheliegenden auch das Richtige zu tun:

-   Ungenaue Anforderungen werden oft kompensiert durch Produkte, die versuchen, die Ungenauigkeit zu kompensieren. Die Immaterialität von Software wird dazu genutzt, so breit und flexibel zu implementieren, dass auch noch unbekannte oder schwammige Anforderungen quasi schon im vorauseilenden Gehorsam erfüllt werden.
-   Ständig wechselnde Anforderungen werden im Produkt möglichst schnell nachgeführt, weil das dank seiner Immaterialität möglich ist.

Langfristig ist solches Verhalten allerdings kontraproduktiv:

-   Der vorauseilende Gehorsam führt zu Breite und Flexibilität, die nicht wirklich gebraucht werden. Er realisiert Features, die keine Anwendung finden.
-   Schnelle Umbauten an Software aufgrund wechselnder Anforderungen führen zu Qualitätserosionen im Code. Software ist zwar immateriell und flexibel – aber nicht jede Softwarestruktur ist evolvierbar oder auch nur verständlich.

Unklare und wechselnde Anforderungssituationen vor dem Hintergrund der hohen grundsätzlichen Flexibilität von Software führen schnell zu unnötigen Aufwänden und sprödem Code. Eine große Anzahl von Projekten, die ihre Budgetgrenzen gesprengt haben, und eine noch größere Zahl von Projekten, die schon nach wenigen Jahren unwartbar geworden sind, sind dafür beredtes Zeugnis.

[[../index|CCD]] als professionelle Softwareentwickler sehen es als ihre Pflicht, sich solcher Entwicklung jeden Tag entgegen zu stemmen. Angesichts der nicht zu leugnenden Natur von Software – sie ist und bleibt immateriell -, liegt der Ansatz dafür beim Umgang mit den Anforderungen. Das ist der Ursprung des YAGNI-Prinzips.

Das YAGNI-Prinzip ist wie ein scharfes Messer: Wer sie anwendet, schneidet ein Problem in kleine Würfel des unmittelbar Nötigen. Nach dem YAGNI-Prinzip wird nur das unzweifelhaft und unmittelbar Nutzbringende implementiert. Alles andere… nun, das kommt später. Insofern geht YAGNI Hand in Hand mit der Regel „Entscheide so spät wie möglich“ des [Lean Software Development](http://en.wikipedia.org/wiki/Lean_software_development#Decide_as_late_as_possible).

Das YAGNI-Prinzip ist relevant auf allen Ebenen der Softwareentwicklung und in allen Phasen. Wann immer Sie sich Fragen „Sollte ich diesen Aufwand wirklich treiben?“ oder „Brauchen wir das wirklich?“ – und sei es auch nur ganz verschämt und leise im Hinterkopf -, dann ist das ein Anwendungsfall für das YAGNI-Prinzip. Es besagt: Wenn im Zweifel, entscheide dich gegen den Aufwand.

Das klingt leicht, ist aber schwer. Daher auch die häufigen Zuwiderhandlungen. Es gibt viele Kräfte, die der Entscheidung gegen einen Aufwand widersprechen. „Ach, das ist doch gar nicht soviel Aufwand“ oder „Wenn wir jetzt nicht vorausschauen, dann können wir in Zukunft nicht mehr anders“ sind nur zwei naheliegende Begründungen für Aufwand, auch wenn Zweifel an seinem Nutzen bestehen. Das betrifft architektonische Entscheidungen (z.B. Soll schon mit einer verteilten Architektur begonnen werden, auch wenn die heutige Last sie noch nicht bräuchte?) wie lokale Entscheidungen (z.B. Soll der Algorithmus schon jetzt optimiert werden, auch wenn er im Augenblick noch keine Performanceprobleme macht?).

Der Kunde bezahlt nur für unmittelbaren Nutzen. Was er heute nicht klar spezifizieren kann, nutzt ihm nicht. Es in der Implementation voraussehen zu wollen, investiert also Aufwand ohne Nutzen zu generieren. Wenn der Kunde später einmal genauer weiß, was er will, dann – und nicht früher! – ist es Zeit, seinem Willen nachzukommen. Wo immer aber ein Projekt versucht, diesen Willen vorwegzunehmen riskiert es, von der morgigen Willensrealität des Kunden widerlegt zu werden. Ein Feature – funktional oder nicht-funktional -, das heute ohne klare Anforderung implementiert wird, interessiert den Kunden morgen vielleicht schon nicht mehr. Oder es ist ihm nicht mehr so wichtig wie ein anderes Feature.

Das bedeutet für die Softwareentwicklung:

-   Ausschließlich klare Anforderungen implementieren.
-   Der Kunde priorisiert seine klaren Anforderungen.
-   Die klaren Anforderungen in der Reihenfolge ihrer Priorisierung umsetzen.
-   Entwicklungsprozess und Codestruktur im Großen und Kleinen so aufsetzen, dass keine Angst aufkommt, sich ändernde und neue Anforderungen zu realisieren.

[[../index|CCD]] als professionelle Entwickler kommunizieren diese Vorgehensweise unmissverständlich dem Kunden gegenüber. Dadurch werden sie:

-   servicewillig, denn sie müssen dem Kunden keine klare Anforderung abschlagen
-   verantwortungsbewusst, weil sie das Budget nur für klar formulierten Nutzen einsetzen
-   beschützend dem Code gegenüber, weil sie ihn gegen Überladung mit letztlich Unnötigem bewahren

YAGNI ist deshalb nicht nur ein Prinzip, das jeder Entwickler befolgen soll, sondern auch ein Prinzip für Projekte und Teams, also auf Organisationsebene. YAGNI ist immer in Anschlag zu bringen, genauso wie [[./DRY|DRY]]. Wenn im Zweifel, dann verschiebe die Entscheidung falls möglich. Ansonsten entscheide dich gegen den Aufwand. Das entspannt und entschlackt und führt schneller zum Erfolg.