# Smartquare Entwicklungsprozess
Dieses Repository definiert einen einheitlichen Entwicklungsprozess innerhalb der Smartsquare GmbH auf technischer Ebene. Eine Guideline zur Vor- und Nachbereitung eines Projektes kann der [Projekt-Guideline](https://github.com/SmartsquareGmbH/guidelines/) entnommen werden. Die Projekttemplates in diesem Repository können gerne als Basis genommen werden und enthalten bereits vorkonfigurierte Analysetools.

## Code Formatter  :closed_book:
Als Code-Formatter sollte der IntelliJ IDEA Standard genutzt werden. Falls Anpassungen erforderlich sind, sollten diese gemeinsam abgestimmt und anschließend hier importiert werden.  

## Statische Codeanalyse :chart_with_upwards_trend:
Zur statischen Codeanalyse werden in den Projekttemplates [PMD](https://pmd.github.io/), [Checkstyle](http://checkstyle.sourceforge.net/) und [FindBugs](http://findbugs.sourceforge.net/) für Java, sowie [Detekt](https://github.com/arturbosch/detekt) und [KTLint](https://ktlint.github.io/) für Kotlin verwendet. 

### Architektur
Für die Analyse der Architektur ist im Projekttemplate kein Standard hinterlegt, jedoch sollte mindestens eines der folgenden Tools verwendet werden. 
- [JDepend](https://github.com/clarkware/jdepend)
- [Arch Unit](https://www.archunit.org/)
- [Structure 101](https://structure101.com/)
- [Degraph](http://blog.schauderhaft.de/degraph/)

## Code Review :cop:
Um die Qualität unserer Software stetig zu steigern, sind Code Reviews eine gute Möglichkeit. Ein Code Review sollte _mindestens_ ein mal vor einer Auslieferung oder Projektübergabe stattfinden, bestenfalls jedoch kontinuierlich während der Entwicklung.

### Pull Requests
In der Vergangenheit haben wir gute Erfahrungen damit gemacht Features oder größere Refactorings in Pull Requests zu entwickeln. Eine Entwicklung muss dadurch vor dem Merge in den Entwicklungsbranch ein Code Review durch einen weiteren Mitarbeiter durchlaufen. 

### Mob Review
Mob Reviews sollten ggf. nach Projektabschluss durchgeführt werden, um entsprechende Lessons Learned aus einem Projekt zu ziehen. 
