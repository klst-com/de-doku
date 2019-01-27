# Entwurfsmuster

Entwurfsmuster (design patterns) sind [Vorlagen zur Problemlösung](https://de.wikipedia.org/wiki/Entwurfsmuster). Für die Softwareentwicklung ist der Begriff Viererbande (Gang of Four, kurz GoF) ein Synonym für objektorientierte Entwurfsuster. Die GoF Autoren verwendeten in ihrem [Buch](https://en.wikipedia.org/wiki/Design_Patterns) nicht Java, sondern C++ and Smalltalk. Java Beispiele findet man unter [java-design-patterns](https://java-design-patterns.com/).

## Observer (Listener)

Listener ist ein Klassiker in GUI-Programmen. Die GoF verwendete noch den Begriff Observer. Inzwischen wird dieses [Verhaltensmuster](https://en.wikipedia.org/wiki/Behavioral_pattern) meistens (event-)Listener genannt. In Java Programmen finden wir oft die Begriffe __ActionListener__ oder __PropertyChangeListener__. Listener ist oft ein Synonym für die Klasse, die einen konkreten Beobachter implementiert. Im Bild ```Observer1``` oder ```Observer2```.

![](https://upload.wikimedia.org/wikipedia/commons/0/01/W3sDesign_Observer_Design_Pattern_UML.jpg)

### ActionListener in Java

In awt ist der [abstrakte Beobachter/Observer](https://de.wikipedia.org/wiki/Datei:Beobachterentwurfsmuster.png) als Interface bereits definiert ```java.awt.event.ActionListener```. Nur der konkreten Beobachter muß die Methode ```actionPerformed(ActionEvent e)``` implementieren.

Die klassisch "altbackene" Implementierung für einen ```ActionListener``` sieht so aus: 

* das Interface wird angegeben
* der Observer ```this``` registriert sich beim Subjekt (ein Push-Button) als Listener
* und impementiert die geforderte Methode ```actionPerformed```, bei der das Subjekt erst ermittelt werden muß

```java
public class Beispiel3501 extends JFrame implements ActionListener {
...
 		button1.addActionListener(this);
...
   public void actionPerformed(ActionEvent e) {
   ... 
      if (e.getActionCommand().equals("button1")) { // Aktion für button1

```