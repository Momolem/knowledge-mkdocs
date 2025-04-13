---
share: true
aliases:
  - Stub
  - Dummy
  - Fake
tags:
  - cleancode
title: Mockups
---
 
# Mockups

>**Warum?**
>Ohne Attrappen keine einfach kontrollierbaren Tests.

In der Regel verwenden Komponenten andere Komponenten. Will man eine Komponente isoliert testen, müssen diese Abhängigkeiten abgetrennt werden. Dabei interessiert uns nun ausschließlich die Funktionalität der zu testenden Komponente (_System Under Test (SUT)_). Und es interessiert uns, wie die Komponente mit den anderen interagiert.

Beim Isolieren verwenden wir sogenannte Mockups. Diese werden anstelle der echten Komponenten verwendet. So interagiert das System Under Test während der Tests mit gut kontrollierbaren Attrappen statt mit realen Komponenten.

Die Literatur kennt noch andere Bezeichnungen für Attrappen wie _Stub_, _Dummy_ oder _Fake_, die teilweise synonym zu Mockup benutzt werden, aber durchaus für [unterschiedliche Funktionsweisen](http://martinfowler.com/articles/mocksArentStubs.html) stehen. Bevor man ein Mock Framework wie z.B. [Rhino Mocks](https://hibernatingrhinos.com/oss/rhino-mocks) verwendet, sollte man ein Mockup zunächst „per Hand“ implementieren. Dies hilft, den Mechanismus zu verstehen.

Siehe auch unter [Tools](https://clean-code-developer.de/weitere-infos/werkzeuge/).