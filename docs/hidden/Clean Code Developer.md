---
share: true
aliases:
  - CCD
tags:
  - cleancode
title: Clean Code Developer
---
 
# Clean Code Developer

## Die Grade
- [[undefineddocs/hidden/Roter Grad|Roter Grad]]
- [[undefineddocs/hidden/Orangener Grad|Orangener Grad]]
- [[undefineddocs/hidden/Gelber Grad|Gelber Grad]]
- [[undefineddocs/hidden/Grüner Grad|Grüner Grad]]
- [[undefineddocs/hidden/Blauer Grad|Blauer Grad]]
- [[undefineddocs/hidden/Weißer Grad|Weißer Grad]]
## Wertesystem
### Wandelbarkeit

Wir möchten diesen Abschnitt mit einer provokant anmutenden These beginnen:

**Es gibt keine Softwarewartung!**

Wartung ist ein pro-aktiver Vorgang. In Fertigungsanlagen werden regelmäßig Teile getauscht, bevor diese kaputt sind. Sie werden getauscht, weil Erfahrungswerte zeigen, dass die Zuverlässigkeit beim Weiterbetrieb unter einen kritischen Wert sinken würde. Bevor also die ganze Anlage zum Stillstand kommt, werden die kritischen Teile rechtzeitig vorher getauscht. Jeder Autobesitzer weiß, dass er regelmäßig einen Ölwechsel vornehmen lassen muss. Nicht etwa, weil das Öl zu dem Zeitpunkt aufgebraucht wäre, nicht einmal deshalb, weil das Öl zu dem Zeitpunkt bereits völlig wirkungslos wäre. Nein, es wird getauscht, weil Erfahrungswerte des Herstellers zeigen, dass der Motor durch den rechtzeitigen Ölwechsel geschont wird und somit länger hält.

All das gibt es bei Software nicht. Software ist so, wie sie ist. Meist enthält sie Fehler. Doch auch diese Fehler sind so, wie sie sind. Man kann nichts pro-aktiv unternehmen, um den Zustand der Software zu verbessern.

Natürlich gibt es beim Betrieb der Software pro-aktive Handlungen. So sollte vielleicht regelmäßig geprüft werden, ob die Logdateien noch ausreichend freien Platz auf der Festplatte lassen, ob eine Datenbank überläuft oder der Speicher sich zunehmend füllt. Aber die Software an sich kann nicht pro-aktiv gewartet werden. Jegliche Änderung oder Erweiterung findet statt, um einen Fehler zu beseitigen oder neue bzw. geänderte Anforderungen umzusetzen.

Damit Änderungen möglich sind, muss die Software eine innere Struktur haben, die solche Änderungen begünstigt. Dies bezeichnen wir als Wandelbarkeit. Software wird in der Regel über lange Zeiträume betrieben. Während dieser Zeit ändern sich die Rahmenbedingungen, müssen Features ergänzt werden. Im Idealfall kostet die Implementierung eines Features einen festen Betrag, der unabhängig davon ist, wann das Feature realisiert wird.

In der Praxis steigt der Preis allerdings für ein Feature, je später es realisiert wird. Am Anfang sind Features preiswert, am Ende ist es gar nicht mehr möglich Features zu ergänzen, weil niemand mehr durchblickt. Die Software wird weggeworfen und neu entwickelt. Bis man an diesem Punkt ankommt, steigen die Kosten exponentiell. Das gemeine an exponentiellem Wachstum sind zwei Dinge: 1.) Anfangs erkennt man kaum, dass die Kosten anwachsen. Die Steigerungen sind moderat. 2.) Wenn man dann erkennt, dass die Kosten steigen, ist es zu spät. Die Steigerung schreitet dann plötzlich so schnell voran, dass ein Gegensteuern nicht mehr möglich ist.

Je einfacher die Software an geänderte Rahmenbedingungen angepasst werden kann, desto höher ist ihre Wandelbarkeit. Doch Wandelbarkeit erhält man nicht nachträglich. Sie muss von vorneherein berücksichtigt werden. Die Software muss darauf ausgelegt sein.

Dazu ein Beispiel: Klassen sollten genau eine Verantwortlichkeit haben. Ist eine Klasse für mehr als eine Sache zuständig, ist es schwerer sie zu überblicken. Das behindert Änderungen, denn diese bedingen, dass man den Quellcode versteht, der geändert werden soll. Des weiteren steigt die Kopplung zwischen den Klassen. Plötzlich hängt alles mit allem zusammen. Dies kann nur verhindert werden, indem Funktionseinheiten eine klar definierte Verantwortlichkeit haben und man die Kopplung im Blick behält. Hat man in einem Softwaresystem eine Reihe von Klassen angesammelt, die jeweils für mehrere Dinge verantwortlich sind, ist es im Nachhinein nur schwer möglich, diesen Zustand zu beseitigen. Die Kopplung ist so groß, dass es schwer fällt, einzelne Funktionseinheiten heraus zu lösen. Sollen in diesem Dickicht neue Features realisiert werden, ist das sehr aufwändig. Wenn nicht rechtzeitig begonnen wird, das Dickicht zu lichten, wird die Situation mit jedem mal schlimmer. Ab einem gewissen Punkt ist es dann kaum noch möglich, neue Features zu ergänzen. Der Super-GAU der Softwareentwicklung.

Wir meinen, dass es soweit nicht kommen muss. Berücksichtigt man Wandelbarkeit von vorne herein, kann Software über lange Zeiträume weiter entwickelt werden. Die Kosten pro Feature mögen dabei im Laufe der Zeit leicht ansteigen. Aber keinesfalls exponentiell!

### Korrektheit

Software muss funktional korrekt sein. Ein Buchhaltungsprogramm muss die Buchungen ordnungsgemäß verbuchen, eine Tabellenkalkulation muss richtig rechnen. Und auch die nicht-funktionalen Anforderungen müssen erfüllt sein. Das Programm muss schonend mit Ressourcen wie Speicher, Prozessorzeit, Plattenplatz, etc. umgehen, die Antwortzeiten müssen in einem definierten Rahmen liegen. Erst wenn alle Anforderungen erfüllt sind, ist die erstellte Software korrekt.

Dass Korrektheit erforderlich ist, wird niemand bestreiten. Doch die Frage ist, was konkret dafür getan wird. Es reicht unserer Ansicht nach nicht aus, Software nach deren Erstellung durch eine Testabteilung zu leiten, deren Aufgabe es ist, Fehler zu finden. Wir meinen, Korrektheit muss bereits während der Entwicklung berücksichtigt werden. Bereits die Entwickler müssen sich mit der Frage der Korrektheit auseinandersetzen. Und damit sie das überhaupt können, muss ihnen klar sein, was die Anforderungen sind. Schon daran mangelt es zu oft. Entwickler werden beauftragt, ein Feature zu implementieren, ohne ihnen präzise zu sagen, was die Abnahmekriterien für das Feature sind. Doch hier geht es nicht darum, Schwarzer Peter zu spielen und einen Schuldigen außerhalb der Entwicklungsabteilungen zu suchen. Schließlich ist es die Aufgabe der Entwickler, bei unklaren Anforderungen nachzufragen, statt in ihre Glaskugel zu schauen.

Verglichen mit dem Automobilbau steht die Softwareentwicklung beim Thema Korrektheit schlecht da. Ein Auto besteht aus vielen Teilen, deren Korrektheit jeweils einzeln nachgewiesen und überprüft werden kann. Stellen Sie sich vor, Sie müssten zur Fehlersuche mit einem Meßgerät in der Hand auf der Motorhaube des Autos sitzen, um dort verfolgen zu können, was sich in der Maschine abspielt. Mit Tempo 200 auf der Autobahn. Kommt Ihnen komisch vor? Ein Debugger wird in vielen Fällen genau so eingesetzt. Das halten wir für falsch.

### Produktionseffizienz

Am Ende spielen natürlich auch die Entwicklungszeit und der Preis der Software eine Rolle. Und der ist höher, wenn die Produktion der Software nicht effizient erfolgt. Das beginnt bei manuellen Arbeitsschritten, die nicht automatisiert werden und endet bei hohen Fehlerraten die mehrmaliges Nachbessern erfordern. In letzter Konsequenz bedeutet Produktionseffizienz, dass die Software über Jahre oder gar Jahrzehnte weiterentwickelt werden kann, statt irgendwann wieder von vorne beginnen zu müssen. Gleichzeitig reduziert eine hohe Produktionseffizienz die Anfälligkeit für Fehler.

Die Produktionseffizienz als Wert ist ferner wichtig, um die anderen Werte in ein maßvolles Verhältnis zu setzen. Wer unendlich viel Aufwand für die Korrektheit treibt, macht am Ende auch etwas falsch.

### Kontinuierliche Verbesserung

Ohne Rückschau ist keine Weiterentwicklung möglich. Nur wer reflektiert, wie er eine Aufgabenstellung gelöst hat, kann feststellen, ob der gewählte Weg einfach oder beschwerlich war. Lernen basiert auf Reflexion.

In einer jungen Wissenschaft wie der Informatik ist es wichtig, stets neue Erkenntnisse zu berücksichtigen. Dazu ist Reflexion auf allen Ebenen erforderlich. Angefangen beim Reflektieren über die Implementation beim Pair Programming oder Code Review, das tägliche Reflektieren des Teams, die Reflexion nach jeder Iteration, bis hin zur Reflexion der gesamten Branche über ihr Tun. Ohne Reflexion keine Weiterentwicklung.

### Prinzipien und Praktiken

Das Wertesystem leitet Clean Code Developer in ihrer täglichen Arbeit. Es enthält keine Problemlösungen, sondern definiert Rahmenbedingungen für Problemlösungen. Die vier Werte sind für eine konkrete alltägliche Umsetzung jedoch zu abstrakt. Daher haben wir Bausteine zusammengetragen, die jeweils mindestens einen der Werte befördern. Diese konkreten Bausteine teilen wir in zwei Kategorien: Prinzipien und Praktiken.

#### Prinzipien

Die Clean Code Developer Prinzipien sind die grundlegenden Gesetzmäßigkeiten für die Strukturierung von Software. Sie sind entweder zu anderen Rahmenbedingungen orthogonal oder ihnen übergeordnet. Code sollte immer im Einklang mit einer maximalen Zahl von Prinzipien sein. Natürlich haben sie nicht „die Macht“ von Naturgesetzen, denen niemand zuwiderhandeln kann. Aber sie sind mit ihnen in Bezug auf die Softwareentwicklung gleichauf in ihrer Fundamentalität. Wo ein Prinzip nicht eingehalten wird, tritt also nicht unbedingt sofort ein negativer Effekt ein, aber kurz- bis mittelfristig bleiben Zuwiderhandlungen nicht ohne Schmerz. Der drückt sich in Mühe beim Codeverständnis aus oder im hohen Aufwand, um Änderungen einzubringen. Ultimativ ist er, wenn Software nicht mehr evolvierbar ist. Ob ein Prinzip eingehalten wurde, kann man dem Code immer ansehen.

#### Praktiken

Praktiken sind Techniken und Methoden, die ständig zum Einsatz kommen. Sie beschreiben, was Clean Code Developer praktisch tun. Motto der Praktiken: „Tue es immer so. Jeden Tag, jederzeit.“ Es sind handfeste Handlungsanweisungen, die manchmal des Einsatzes von Werkzeugen bedürfen. Ob einer Praktik gefolgt wird, kann man dem Code nicht immer ansehen.

## Die Tugenden
### Prinzipielles

#### 1. Schätze Variation (Value Variation (VV))

Werte: Wandelbarkeit, Kontinuierliche Verbesserung

#### 2. Tue nur das Nötigste (Do Only What´s Neccessary (DOWN))

Werte: Produktionseffizienz, Wandelbarkeit

- Vorsicht vor Optimierungen! (Prinzip des [[undefineddocs/hidden/Roter Grad|roten Grades]])
- [[undefineddocs/hidden/YAGNI|YAGNI]] (Prinzip des [[undefineddocs/hidden/Blauer Grad|blauen Grades]])
- [[undefineddocs/hidden/KISS|KISS]] (Prinzip des [[undefineddocs/hidden/Roter Grad|roten Grades]])

#### 3. Isoliere Aspekte (Isolate Aspects (IA))

Werte: 
- Wandelbarkeit
- [[undefineddocs/hidden/DRY|DRY]]
- [[undefineddocs/hidden/Separation of Concerns|Separation of Concerns]]
- [[undefineddocs/hidden/Single Level of Abstraction|Single Level of Abstraction]]
- [[undefineddocs/hidden/Single Responsibility Principle|Single Responsibility Principle]]
- [[undefineddocs/hidden/Interface Segragation Principle|Interface Segragation Principle]]
- [[undefineddocs/hidden/Design and Implementation do not Overlapp|Design and Implementation do not Overlapp]]
- [[undefineddocs/hidden/Integration Operation Segregation Principle (IOSP)|Integration Operation Segregation Principle (IOSP)]]

#### 4. Minimiere Abhängigkeiten (Minimize Dependencies (MD))

Werte:
-   Wandelbarkeit
- [[undefineddocs/hidden/Dependency Inversion Principle|Dependency Inversion Principle]]
- [[undefineddocs/hidden/Information Hiding Principle|Information Hiding Principle]]
- [[undefineddocs/hidden/Law of Demeter|Law of Demeter]]
- [[undefineddocs/hidden/Tell do not ask|Tell do not ask]]

#### 5. Halte Versprechen ein (Honor Pledges (HP))

Werte: 
- Wandelbarkeit oder auch: Minimize Surprises
- [[undefineddocs/hidden/Liskov Substitution Principle|Liskov Substitution Principle]]
- [[undefineddocs/hidden/Principle of Least Astonishment|Principle of Least Astonishment]]
- Implementation spiegelt Entwurf
- [[undefineddocs/hidden/Favour Composition over Inheritance|Favour Composition over Inheritance]] (FCoI)

### Praktisches

#### 1. Umarme Unsicherheit (Embrace Uncertainty (EU))

Werte: Wandelbarkeit, Kontinuierliche Verbesserung

Ein Versionskontrollsystem einsetzenAutomatisierte IntegrationstestsAutomatisierte Unit TestsMockups (Testattrappen)Continuous IntegrationInversion of Control Container

#### 2. Fokussiere (Focus (F))

Werte: Produktionseffizienz

KomponentenorientierungTest firstLimit WIP // neu

#### 3. Wertschätze Qualität (Value Quality (VQ))

Werte: Produktionseffizienz

Akzeptiere nur hohe Qualität // neuAutomatisierte Unit TestsReviews

#### 4. Mach fertig (Get Things Done (GTD))

Werte: Produktionseffizienz

Iterative EntwicklungContinuous DeliveryLimit WIP

#### 5. Halte Ordnung (Stay Clean (SC))

Werte: Wandelbarkeit, Korrektheit, Produktionseffizienz

Die Pfadfinderregel beachtenKomplexe RefaktorisierungenEinfache Refaktorisierungsmuster anwendenStatische Codeanalyse (Metriken)Code Coverage AnalyseSource Code Konventionen // ehemals Prinzip

#### 6. Bleib am Ball (Keep Moving (KM))

Werte: Kontinuierliche Verbesserung

Lesen, Lesen, LesenTeilnahme an FachveranstaltungenErfahrung weitergebenTäglich reflektierenRoot Cause AnalysisMessen von FehlernIssue TrackingRegelmäßige Retrospektiven // neu

## Source

[Clean Code Developer](https://clean-code-developer.de/)