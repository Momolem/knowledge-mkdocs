---
share: true
tags:
  - cleancode
aliases:
  - Keep it simple
  - stupid (KISS)
linter-yaml-title-alias: Keep it simple, stupid (KISS)
title: Keep it simple, stupid (KISS)
---
---
share: true
tags: [cleancode]
aliases: [Keep it simple, stupid (KISS)]
linter-yaml-title-alias: Keep it simple, stupid (KISS)
title: Keep it simple, stupid (KISS)
---
#cleancode 
# Keep it simple, stupid (KISS)

>**Warum?**
>Wer mehr tut als das Einfachste, lässt den Kunden warten und macht die Lösung unnötig kompliziert.

Oder um es mit Albert Einsteins Worten zu sagen: 
>„Alles sollte so einfach wie möglich gemacht werden, aber nicht einfacher.“
 
 Für die Wandelbarkeit des Codes ist zwingende Voraussetzung, dass der Code verständlich ist. Eine einfache, klare und leicht verständliche Lösung sollte daher immer bevorzugt werden. Wenn man seinen eigenen Code nach kurzer Zeit schon nicht mehr versteht, sollten die Alarmglocken klingen. Noch wichtiger aber ist, dass auch andere Entwickler den Code schnell verstehen können. Dabei helfen regelmäßige [Code Reviews](CleanCode/Code%20Reviews.md) und [Pair Programming](Pair%20Programming.md). Sie dienen der Kontrolle, ob tatsächlich die einfachste Lösung verwendet wurde.

Gerade in technischen Details steckt die Versuchung, eine komplizierte Lösung anzustreben. Das Bekannte, naheliegende ist manchmal zu „langweilig“ – und schon hat sich eine komplizierte Lösung eingeschlichen. Wenn die einfache Lösung auch funktioniert, sollte ihr Vorrang gewährt werden. Das gleiche gilt für Datenstrukturen. Wenn ein [IEnumerable](IEnumerable.md) reicht, sollte keine [ICollection](ICollection.md) oder sogar [IList](IList.md) verwendet werden.