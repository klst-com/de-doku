# Entwurfsmuster (design patterns)

Entwurfsuster sind [Vorlagen zur Problemlösung](https://de.wikipedia.org/wiki/Entwurfsmuster). Für die Softwareentwicklung ist der Begriff Viererbande (Gang of Four, kurz GoF) ein Synonym für objektorientierte Entwurfsuster. Die GoF Autoren verwendeten in ihrem [Buch](https://en.wikipedia.org/wiki/Design_Patterns) nicht Java, sondern C++ and Smalltalk. Java Beispiele findet man unter [java-design-patterns](https://java-design-patterns.com/).

## Observer (Listener)

Listener ist ein Klassiker in GUI-Programmen. Die GoF verwendete noch den Begriff Observer. Inzwischen wird dieses [Verhaltensmuster](https://en.wikipedia.org/wiki/Behavioral_pattern) meistens (event-)Listener genannt. In Java Programmen finden wir oft die Begriffe __ActionListener__ oder __PropertyChangeListener__. Listener ist oft ein Synonym für die Klasse, die einen konkreten Beobachter implementiert. Im Bild ```Observer1``` oder ```Observer2```.

![](https://upload.wikimedia.org/wikipedia/commons/0/01/W3sDesign_Observer_Design_Pattern_UML.jpg)

### ActionListener in Java

In awt ist der [abstrakte Beobachter](https://de.wikipedia.org/wiki/Beobachter_(Entwurfsmuster\)#UML-Diagramm) als Interface bereits definiert ```java.awt.event.ActionListener```. Nur der konkreten Beobachter muß die Methode ```actionPerformed(ActionEvent e)``` implementieren.