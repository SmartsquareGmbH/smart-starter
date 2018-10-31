# Smartquare Entwicklungsprozess
Dieses Repository definiert einen einheitlichen Entwicklungsprozess innerhalb der Smartsquare GmbH auf technischer Ebene. Eine Guideline zur Vor- und Nachbereitung eines Projektes kann der [Projekt-Guideline](https://github.com/SmartsquareGmbH/guidelines/) entnommen werden. Die Projekttemplates in diesem Repository können gerne als Basis genommen werden und enthalten bereits vorkonfigurierte Analysetools.

## Code Formatter :closed_book:
Als Code-Formatter sollte der IntelliJ IDEA Standard genutzt werden. Falls Anpassungen erforderlich sind, sollten diese gemeinsam abgestimmt und anschließend hier importiert werden.  

## Statische Codeanalyse :chart_with_upwards_trend:
Zur statischen Codeanalyse werden in den Projekttemplates [PMD](https://pmd.github.io/), [Checkstyle](http://checkstyle.sourceforge.net/) und [FindBugs](http://findbugs.sourceforge.net/) für Java, sowie [Detekt](https://github.com/arturbosch/detekt) und [KTLint](https://ktlint.github.io/) für Kotlin verwendet. 

### Architektur
Für die Analyse der Architektur ist im Projekttemplate kein Standard hinterlegt, jedoch sollte mindestens eines der folgenden Tools verwendet werden. 
- [JDepend](https://github.com/clarkware/jdepend)
- [Arch Unit](https://www.archunit.org/)
- [Structure 101](https://structure101.com/)
- [Degraph](http://blog.schauderhaft.de/degraph/)

### Code Coverage 
Wir möchten uns in diesem Dokument nicht auf eine minimale Code Coverage festlegen, jedoch sollte jeder Entwickler auch durch die Code Coverage prüfen, ob zusätzlich zum TDD Zyklus Tests implementiert werden müssen. Die Coverage wird in den Beispielprojekten durch JaCoCo ermittelt.

## Code Review :cop:
Um die Qualität unserer Software stetig zu steigern sind Code Reviews eine gute Möglichkeit. Ein Code Review sollte _mindestens_ ein mal vor einer Auslieferung oder Projektübergabe stattfinden, bestenfalls jedoch kontinuierlich während der Entwicklung.

### Pull Requests
In der Vergangenheit haben wir gute Erfahrungen damit gemacht Features oder größere Refactorings in Pull Requests zu entwickeln. Eine Entwicklung muss dadurch vor dem Merge in den Entwicklungsbranch ein Code Review durch einen weiteren Mitarbeiter durchlaufen. 

### Mob Review
Mob Reviews sollten, ebenso wie Pull Requests, kontinuierlich in der Entwicklung stattfinden und sind generell vor großen Architekturentscheidungen zu empfehlen. Außerdem hat sich diese Art des Reviews nach Projektabschluss als nützlich erwiesen, um gemachte Fehler zu identifizieren und in der Zukunft zu vermeiden.

## Pair Programming :two_men_holding_hands:
Pair Programming sollte generell nach Belieben praktiziert werden. Gute Erfahrungen haben wir in der Vergangenheit damit gemacht, dass ein Entwickler einen fehlschlagenden Test implementiert, der Zweite den Code Under Test entwickelt und anschließend einen weiteren fehlschlagenden Test implementiert.

## Double Loop - Outside In Development :loop:
Optimalerweise sollte die Entwicklung behaviour-driven oder acceptence-test-driven stattfinden. Dabei kann beispielsweise ein Feature mit [Cucumber](https://cucumber.io/) spezifiert werden und anschließend test-driven entwickelt werden. Alternative Bilbiotheken für dieses Vorgehensmodell wären [JGiven](http://jgiven.org/) und [JBehave](https://jbehave.org/).
![ATDD Zyklus](https://www.planetgeek.ch/wp-content/uploads/2012/06/Clean-ATDD-cycle.png)

## Dokumentation :page_with_curl:
″Working Software Over Comprehensive Documentation″, das ist auch unsere Ansicht als Smartsquare GmbH, jedoch erachten wir ein gutes JavaDoc und eine minimale Architekturdokumentation als sehr sinnvoll.
### Architekturdokumentation
Um Dritten einen Überblick über die Anwendung und ihren Kontext zu geben sollte ein Architekturdokumentation gepflegt werden. In dieser Dokumentation sollte beschrieben werden in welchem Kontext die Anwendung existiert, warum sie existiert und welche Schnittstellen zu anderen Systemen existieren. Die Dokumentation sollte vorzugsweise als *.adoc verfasst werden.
Ein Template nach arc42 findet sich [hier](https://smartsquare.github.io/archdoc).
### JavaDoc
Das JavaDoc sollte verwendet werden um einem Dritten den Einstieg in die API eines Projektes zu erleichtern. Das bedeuted, dass package-infos, öffentliche Klassen und Methoden zu dokumentieren sind insofern eine nötige Komplexität erreicht ist. 

## Continuous Integration :arrows_counterclockwise:
Als CICD Plattform sollte vorzugsweise der interne TeamCity Server gewählt werden. Nachdem ein TeamCity Projekt angelegt wurde und der erste Build durchgelaufen ist, kann anhand [dieser Dokumentation](https://confluence.jetbrains.com/display/TCD9/IntelliJ+IDEA) das Code Coverage Reporting aktiviert werden.
