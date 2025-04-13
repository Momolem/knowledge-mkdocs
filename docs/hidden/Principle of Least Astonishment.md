---
aliases: 
share: true
tags:
  - cleancode
title: Principle of Least Astonishment
---
 
# Principle of Least Astonishment

>**Warum?**
>Wenn sich eine Komponente überraschenderweise anders verhält als erwartet, wird ihre Anwendung unnötig kompliziert und fehleranfällig.

Softwareentwicklung ist in hohem Maße ein kreativer Prozess. In diesem Prozess ist es wichtig, in den Fluss einzutauchen (engl. Flow). Wenn man diesen Zustand erreicht hat, sprudelt der Code nur so heraus. Jegliche Störung des Flow führt zu Unterbrechungen und letztlich dazu, dass in der zur Verfügung stehenden Zeit nur wenig Code produziert wird bzw. die Qualität des Code nicht optimal ist. Denn nach jeder Unterbrechung muss der Entwickler erst wieder Fahrt aufnehmen und erneut in den Fluss zu kommen. Überraschungen stellen Störungen dar. Sie führen zu Unterbrechungen und Fehlern. Dazu ein Beispiel: Ist die Tastenbelegung in der Entwicklungsumgebung so gewählt, dass eine übliche Tastenkombination wie z.B. Ctrl-C eine völlig andere Bedeutung hat, behindert dies den Entwickler. Ein Entwickler wird sich jedes mal ärgern, wenn er die „falsche“ Tastenkombination verwendet. Dies behindert kreatives Arbeiten.

Software sollte überraschungsarm implementiert sein. Wenn eine Abfragemethode namens _`GetValue()`_ nicht nur einen Wert liefert, sondern gleichzeitig den Zustand des Systems ändert, wird der Entwickler diese Methode im besten Fall meiden, da er mit bösen Überraschungen rechnet. Im ungünstigen Fall fällt ihm dieses merkwürdige Verhalten nicht rechtzeitig auf. (Abfragemethoden die den Zustand ändern, verstoßen gegen das _[[Command Query Separation|Command Query Separation]]_ Prinzip). Die [[Test-Driven-Development|Test-Driven-Development]] fördert überraschungsarme Schnittstellen, da die Schnittstelle aus der Sichtweise ihrer Verwendung entworfen und implementiert wird.