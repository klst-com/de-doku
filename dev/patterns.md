# Entwurfsmuster

Entwurfsmuster (design patterns) sind [Vorlagen zur Problemlösung](https://de.wikipedia.org/wiki/Entwurfsmuster). Für die Softwareentwicklung ist der Begriff Viererbande (Gang of Four, kurz GoF) ein Synonym für objektorientierte Entwurfsuster. Die GoF Autoren verwendeten in ihrem [Buch](https://en.wikipedia.org/wiki/Design_Patterns) nicht Java, sondern C++ and Smalltalk. Java Beispiele findet man unter [java-design-patterns](https://java-design-patterns.com/).

## Observer (Listener)

Listener ist ein Klassiker in GUI-Programmen. Die GoF verwendete noch den Begriff Observer. Inzwischen wird dieses [Verhaltensmuster](https://en.wikipedia.org/wiki/Behavioral_pattern) meistens (event-)Listener genannt. In Java Programmen finden wir oft die Begriffe __ActionListener__ oder __PropertyChangeListener__. Listener ist oft ein Synonym für die Klasse, die einen konkreten Beobachter implementiert. Im Bild ```Observer1``` oder ```Observer2```.

![](https://upload.wikimedia.org/wikipedia/commons/0/01/W3sDesign_Observer_Design_Pattern_UML.jpg)

### ActionListener in Java

In awt ist der [abstrakte Beobachter/Observer](https://de.wikipedia.org/wiki/Datei:Beobachterentwurfsmuster.png) als Interface bereits definiert ```java.awt.event.ActionListener```. Nur der konkrete Beobachter/Observer muß die Methode ```actionPerformed(ActionEvent e)``` implementieren.

Die klassisch "altbackene" Implementierung für einen Observer sieht typischerweise so aus: 

* das Interface wird angegeben
* der Observer ```this``` registriert sich beim Subjekt (ein Push-Button) als Listener
* und impementiert die geforderte Methode ```actionPerformed```, bei der das Subjekt erst ermittelt werden muß
* [Quelle](https://dbs.cs.uni-duesseldorf.de/lehre/docs/java/javabuch/html/k100227.html#sectlevel3id035002002)

```java
public class Beispiel3501 extends JFrame implements ActionListener {
...
 		button1.addActionListener(this);
...
   public void actionPerformed(ActionEvent e) {
   ... 
      if (e.getActionCommand().equals("button1")) { // TODO Aktion für button1

```

Eine "moderne" Implementierung (ab Java 8) verwendet Lambdaausdrücke:

* das Interface muss man nicht angegeben und ```actionPerformed``` muß nicht explizit implementiert werden
* denn die Registrierung beim Subjekt enthält bereits den Code für die gewünschte Aktion
* der Code ist kompakter und besser lesbar

```java
public class Beispiel3501_inJava8 extends JFrame { ...

		button1.addActionListener(event -> {
			// TODO Aktion für button1
		});
```

### PropertyChangeListener mit SwingWorker

Der ```PropertyChangeListener```  ist ein weiterer Observer, der weit verbreitet ist. Zusammen mit [SwingWorker](https://en.wikipedia.org/wiki/SwingWorker) zum Beispiel. SwingWorker werden für zeitaufwändige Aufgaben benutzt, damit die GUI bedienbar bleibt, und die Zwischenergebnisse im GUI angezeigt werden. Die SwingWorker-Task/Loader läuft dabei in separaten Threads. Die dabei notwendige Synchronisation mit dem GUI-Thread geschieht über _property change events_. Der SwingWorker schreibt Informationen über seinen Zustand in zwei Properties ab "progress" und "state". Und benachrichtigt den EDT(Event Dispatch Thread), wie der GUI-Thread auch genannt wird.  

Das [SwingWorker Beispiel aus Java 8](https://docs.oracle.com/javase/8/docs/api/javax/swing/SwingWorker.html#publish-V...-) verwendet noch die klassische  Implementierungart, wobei der ```ActionListener``` direkt bei der Registrierung konstruiert wird::

```java
.... JTextArea textArea = new JTextArea();
 final JProgressBar progressBar = new JProgressBar(0, 100);
 PrimeNumbersTask task = new PrimeNumbersTask(textArea, N);
 task.addPropertyChangeListener(
     new PropertyChangeListener() {
         public  void propertyChange(PropertyChangeEvent evt) {
             if ("progress".equals(evt.getPropertyName())) {
                 progressBar.setValue((Integer)evt.getNewValue());
             }
         }
     });
````
Diese Dokumentation stammt noch aus Java 6. Aktuell sollte sie sie aussehen:

```java
...
 JTextArea textArea = new JTextArea();
 PrimeNumbersTask task = new PrimeNumbersTask(textArea, N);
 final JProgressBar progressBar = new JProgressBar(0, 100);
 task.addPropertyChangeListener(event -> {
     progressBar.setValue((Integer)event.getNewValue());
 });
```

### beansbinding statt PropertyChangeListener mit SwingSet3

Im SwingSet3 ```beansbinding-1.2.1.jar``` von [SwingLabs](https://en.wikipedia.org/wiki/SwingLabs) gibt es eine Weterentwicklung als Alternative für einen PropertyChange Observer. Diese ist dann nützlich, wenn mehrere Properties durch GUI-Objekte repräsentiert werden. Beispielsweise

* "state" durch ```Label status``` für ```PENDING, STARTED, DONE```
* "progress" durch ```JProgressBar progressBar```
* die Registrierung beim Subject wird durch das __binding__ zwischen property und ui-Objekt rsetzte

```java
...
        BindingGroup group = new BindingGroup();
        group.addBinding(Bindings.createAutoBinding(READ, task, // lese aus der SwingWorker task
        		BeanProperty.create("progress"),                   // die Property "progress"
        		progressBar, BeanProperty.create("value")));       // und belege damit progressBar Property "value"
        group.addBinding(Bindings.createAutoBinding(READ, task, 
        		BeanProperty.create("state"),
        		status, BeanProperty.create("loadState")));
        group.bind();
````

