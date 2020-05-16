# Swing vs SwingX

## java Package javax.swing

[Quelle wikipedia](https://de.wikipedia.org/wiki/Swing_%28Java%29) : Swing ist ein UI-Paket/Package in Java. Es gehört zu den Java Foundation Classes (JFC), die eine Sammlung von Bibliotheken zur Programmierung von grafischen Benutzerschnittstellen UI bereitstellen. Swing baut auf dem älteren [AWT](https://de.wikipedia.org/wiki/Abstract_Window_Toolkit) auf und ist mit den AWT APIs verwoben. 

[Quelle oracle/javase/8](https://docs.oracle.com/javase/8/docs/api/javax/swing/package-summary.html#package.description) : Provides a set of "lightweight" components that, to the maximum degree possible, work the same on all platforms. For a programmer's guide to using these components, see [Creating a GUI with JFC/Swing](https://docs.oracle.com/javase/tutorial/uiswing/index.html), a trail in The Java Tutorial.

## SwingX Package [org.jdesktop](https://pirlwww.lpl.arizona.edu/resources/guide/software/SwingX/index.html?org/jdesktop/swingx/package-summary.html)

[Quelle rheinwerk-verlag.de](http://openbook.rheinwerk-verlag.de/java8/10_030.html) [tutego.de](http://www.tutego.de/blog/javainsel/2015/11/inselraus-die-zusatzkomponentenbibliothek-swingx/) : Die SwingX-Bibliothek erweitert Swing und füget Funktionalität hinzu und stellt ganz neue UI-Komponenten bereit, etwa eine Mischung aus Tabelle und Baum (JXTreeTable).

[Quelle javabeginners.de](https://javabeginners.de/Frameworks/SwingX/index.php) : SwingX ist ein Java-Package ``org.jdesktop`` von SwingLabs, das auf Swing aufsetzt und eine Reihe von Komponenten bereitstellt, die die Swing-Bibliothek erheblich erweitern und ergänzen. 

Nach der Übernahme von Sun durch Oracle wurden alle [SwingLabs Projekte](https://en.wikipedia.org/wiki/SwingLabs) gestoppt.

Beispiele:

* [JXCollapsiblePane](https://javabeginners.de/Frameworks/SwingX/JXCollapsiblePane-Beispiel.php) ist von JPanel abgeleitet. Es bietet dessen Funktionalität, kann jedoch bei Bedarf animiert unsichtbar gesetzt werden.

* [JXFrame](https://javabeginners.de/Frameworks/SwingX/JXFrame-Beispiel.php) ist von JFrame abgeleitet, kann einen solchen problemlos ersetzen und stellt einige Erweiterungen, wie eine StatusBar und einen Zugriffstimer bereit.

* [JXTaskPane](https://javabeginners.de/Frameworks/SwingX/JXTaskPane-Beispiel.php) ist ist ein Container mit dem die schrittweise Abarbeitung von Aufgaben vorgegeben werden kann. Mehrere JXTaskPane werden üblicher- aber nicht norwendigerweise in einem JXTaskPaneContainer zusammengefasst.

* [JXTitledPanel](https://javabeginners.de/Frameworks/SwingX/JXTitledPanel-Beispiel.php) ist von JPanel und JXPanel abgeleitet. Es besitzt eine Titelzeile und einen separat konfigurierbaren Inhaltsbereich.

* JXDatePicker erlaubt Datumseingabe im Textfeld mit Popup-Menü (siehe Vergleich zu VDate)

### VDate vs JXDatePicker

Ein konkretes Beispiel, das die Erweiterungen in SwingX zeigt, ist die Klasse ```org.jdesktop.swingx.JXDatePicker```. 
Im Adempiere swing Client gibt es eine ähnliche Funktionalität, die mit viel Programmieraufwand erstellt wurde. Es sind die Klassen ```org.compiere.grid.ed.VDate``` und ```Calendar```:

![](../.gitbook/assets/VDate.PNG)

Zum Vergleich ein Demo Screenshot mit JXDatePicker:

![](../.gitbook/assets/JXDatePicker.PNG)