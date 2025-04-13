---
aliases: 
share: true
tags:
  - cleancode
title: Test First
---
# Test First

>**Warum?**
>>Der Kunde ist König und bestimmt die Form einer Dienstleistung. Service-Implementationen sind also nur passgenau, wenn sie durch einen Client getrieben werden.

Wenn Komponentenorientierung fordert, die Kontrakte für Komponenten unabhängig von ihrer Implementation zu definieren, stellt sich die Frage, wie das denn geschehen soll. Durch Diskussion am runden Tisch? Das ist sicherlich ein Weg. Ein besserer ist jedoch, Kontrakte nicht erst lange an einer Tafel zu entwerfen, sondern sie sofort in Code zu gießen. Komponentenkontrakte – oder allgemeiner: jede Codeschnittstelle – dient letztlich anderem Code als API. Es ist daher konsequent und effektiv, von diesem Code ausgehend Schnittstellen zu spezifizieren.

Das ist das Anliegen von _[[Test First|Test First]]_. Test first basiert auf dem Gedanken, dass Funktionseinheiten (Methoden, Klassen, usw.) durch Client-Service-Verhältnisse charakterisiert sind. Diese Verhältnisse drehen sich um die Schnittstelle zwischen Client und Service. Und diese Schnittstelle sollte durch den Client bestimmt werden. Der Client ist als Kunde des Service König. Ihm soll der Service dienen, nach ihm soll sich deshalb die Schnittstelle des Service richten.

Die Definition der Schnittstellen der Codeeinheiten einer Software erfolgt aus diesem Grund von außen nach innen. Außen, an der Benutzeroberfläche, sitzt der ultimative Client, der Anwender. Er definiert die visuelle/haptische Schnittstelle der UI-Codeeinheiten. Die wiederum sind die Clients von darunterliegenden Codeschichten. Die sind dann Clients von tieferliegenden Schichten usw. Die Leistungen und Schnittstellen der tiefsten Codeschichten kann somit nur bestimmt werden, wenn die der darüberliegenden schon bestimmt sind usw.

Das widerspricht dem häufigen Ansatz der bottom-up Definition von Codeeinheiten. Gern fangen Projekte an, eine Datenzugriffsschicht zu definieren und zu implementieren. Das ist verständlich, weil solch fundamentale Funktionalität doch scheinbar die Voraussetzung für alles weitere ist. Aber dieses Vorgehen ist problematisch, wie viele gescheiterte Projekte zeigen:

-   Wer von unten nach oben, von innen nach außen spezifiziert und implementiert, bietet dem Kunden erst sehr spät einen Wert an. Das ist zumindest frustrierend, wenn nicht gar kontraproduktiv.
-   Wer bottom-up in der Spezifikation vorgeht, der spezifiziert ohne genaue Anforderungen des ultimativen Clients, des Benutzers. Was er also spezifiziert läuft Gefahr, am Ende zu allgemein und damit unhandlich zu sein – oder schlicht nicht gebraucht zu werden (eine Verletzung des [[undefineddocs/hidden/YAGNI|YAGNI]]-Prinzips, s.o. und im [[undefineddocs/hidden/Roter Grad|roten Grad]]
-   Wer von unten nach oben implementiert, läuft Gefahr, nicht wirklich zu entkoppeln. Denn wenn tiefere Schichten nötig sind, um darüberliegende zu implementieren, dann werden wahrscheinlich keine wirklich isolierten [[undefineddocs/hidden/Unit Test|Unit Tests]] mit Attrappen eingesetzt und auch keine Inversion of Control.

[[undefineddocs/hidden/Clean Code Developer|Clean Code Developer]] vermeiden diese Probleme jedoch. Sie spezifizieren Schnittstelle nicht nur vor den Implementationen (Contract-first, s.o. Komponentenorientierung), sondern auch von außen nach innen und ganz praktisch durch Codierung. Mit den Mitteln des automatisierten Testens ist es nämlich sehr einfach, Schnittstellen in kleinen Schritten in Form von Tests zu definieren.

Test first fügt dadurch syntaktischen Kontrakten (z.B. Interfaces) eine semantische Seite hinzu. In Ermangelung anderer, formaler Methoden, um Semantik zu spezifizieren, sind Tests der einzige Weg, um Anforderungen zu formalisieren. Wer einem Entwickler eine Komponente zur Implementierung zuweisen will, der tut daher gut daran, nicht nur ihre „Oberfläche“ (API) syntaktisch vorzugeben, sondern auch das gewünschte Verhalten in Form von Tests.

Das hat viele Vorteile:

-   Die Form einer Schnittstelle ist unmittelbar Client-getrieben und damit maximal relevant. [[undefineddocs/hidden/YAGNI|YAGNI]] hat keine Chance.
-   Die Tests sind nicht nur Tests, sondern auch Spezifikationsdokumentation. Nutzer einer Schnittstelle und Implementierer können sie gleichermaßen studieren. Eine separate Dokumentation erübrigt sich weitgehend. Das tut dem [[undefineddocs/hidden/DRY|DRY]]-Prinzip genüge.
-   Die Spezifikationen sind nicht nur passive Texte, sondern ausführbarer Code. Wenn dann eine Implementation vorliegt, kann sie gegen diese Tests geprüft werden. Spezifikation und Test sind damit nicht zeitraubend aufeinanderfolgende Phasen. Das erhöht die Produktivität. Qualitätssicherung ist so der Implementation schon vorgeschaltet.

Siehe auch unter [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/).

Weiter geht’s mit dem [[undefineddocs/hidden/Weißer Grad|weißen Grad]].