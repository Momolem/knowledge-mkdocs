---
share: true
tags:
  - cleancode
aliases:
  - Open Closed Principle (OCP)
linter-yaml-title-alias: Open Closed Principle (OCP)
title: Open Closed Principle (OCP)
---
 
# Open Closed Principle (OCP)
>[!question] **Warum?**
>Weil das Risiko, durch neue Features ein bisher fehlerfreies System zu instabilisieren, so gering wie möglich gehalten werden sollte.

Das *Open Closed Principle* ([OCP](https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle)) besagt, dass eine Klasse offen für Erweiterungen sein muss, jedoch geschlossen gegenüber Modifikationen. Es ist ein weiteres der [[undefineddocs/hidden/SOLID|SOLID]]-Prinzipien

Prinzipien. Folgendes Codebeispiel soll verdeutlichen, wo das Problem liegt, wenn das Prinzip nicht befolgt wird:

```csharp
public double Preis() {

    const decimal StammkundenRabatt = 0.95m;

    switch(kundenart) {

        case Kundenart.Einmalkunde:

            return menge * einzelpreis;

        case Kundenart.Stammkunde:

            return menge * einzelpreis * StammkundenRabatt;

        default:

            throw new ArgumentOutOfRangeException();

    }
    
}
```

Das problematische an dieser Form der Implementierung ist, dass die Klasse modifiziert werden muss, wenn eine weitere Art der Preisberechnung erforderlich wird. Die Gefahr dabei ist, dass bei dieser Modifikation Fehler gemacht werden und die bisher schon vorhandenen Funktionen nicht mehr ordnungsgemäß funktionieren. Auch wenn automatisierte [[undefineddocs/hidden/Unit Test|Unit Tests]] und [[undefineddocs/hidden/Integration Tests|Integrationstests]] vorhanden sind besteht das Risiko, neue Bugs zu hinterlassen, weil man keine hundertprozentige Testabdeckung erreichen kann. Gesucht ist also generell ein Verfahren, welches die Klasse erweiterbar macht, ohne dass dazu die Klasse selbst modifiziert werden muss. Dies kann z.B. mit Hilfe des *[[undefineddocs/hidden/Strategy|Strategy Patterns]]* erreicht werden:

```csharp
public interface IPreisRechner {

    double Preis(int menge, double einzelpreis);

}

private IPreisRechner preisRechner;

public double Preis() {
    return preisRechner.Preis(menge, einzelpreis);
} 

public class Einmalkunde : IPreisRechner {

    public double Preis(int menge, double einzelpreis) {
        return menge * einzelpreis;
    }

}
public class Stammkunde : IPreisRechner {

    const decimal StammkundenRabatt = 0.95m;
    
    public double Preis(int menge, double einzelpreis) {
        return menge * einzelpreis * StammkundenRabatt;
    }

}
```

Die konkrete Berechnung des Preises wird über ein Interface in andere Klassen ausgelagert. Dadurch ist es möglich, jederzeit neue Implementierungen des Interfaces zu ergänzen. Damit ist die Klasse offen für Erweiterungen, gleichzeitig aber geschlossen gegenüber Modifikationen. Bestehender Code kann z.B. mit dem [[undefineddocs/hidden/Refaktorisieren|Refactoring]] [Replace Conditional with Strategy](http://www.industriallogic.com/xp/refactoring/conditionalWithStrategy.html) so umgestaltet werden, dass das Open Closed Principle eingehalten wird.