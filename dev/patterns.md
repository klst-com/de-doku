# Entwurfsmuster

Entwurfsmuster (design patterns) sind [Vorlagen zur Problemlösung](https://de.wikipedia.org/wiki/Entwurfsmuster). Für die Softwareentwicklung ist der Begriff Viererbande (Gang of Four, kurz GoF) ein Synonym für objektorientierte Entwurfsuster. Die GoF Autoren verwendeten in ihrem [Buch](https://en.wikipedia.org/wiki/Design_Patterns) nicht Java, sondern C++ and Smalltalk. Java Beispiele findet man unter [java-design-patterns](https://java-design-patterns.com/).

* Gute Seite zum Thema: https://sourcemaking.com/design_patterns

## Observer (Listener)

Listener sind allgegenwärtige Pattern in GUI-Programmen. Die GoF verwendete den Begriff [Observer](https://sourcemaking.com/design_patterns/observer). Inzwischen wird dieses [Verhaltensmuster](https://en.wikipedia.org/wiki/Behavioral_pattern) meistens (event-)Listener genannt. In Java Programmen finden wir oft die Begriffe __ActionListener__ oder __PropertyChangeListener__. Listener sind aber auch Synonyme für die Klassen, die einen konkreten Beobachter implementieren. Im Bild ```Observer1``` bzw ```Observer2```.

![](https://upload.wikimedia.org/wikipedia/commons/0/01/W3sDesign_Observer_Design_Pattern_UML.jpg)

Das Observer pattern hat also vier Akteure:

* das abstrakte Subjekt/Observable und das konkrete Subjekt (z.B. ein Push-Button)
* den abstrakten Beobachter/Observer/Listener (Interface) und den konkreten Beobachter

### ActionListener in Java

In awt ist der [abstrakte Beobachter/Observer](https://de.wikipedia.org/wiki/Datei:Beobachterentwurfsmuster.png) bereits definiert, als Interface ```java.awt.event.ActionListener```. Nur im konkreten Beobachter/Observer muß die Methode ```actionPerformed(ActionEvent e)``` noch implementiert werden.

Die klassisch "altbackene" Implementierung für einen Observer sieht typischerweise so aus: 

* das Interface wird angegeben [1]
* der Observer ```this``` registriert/attach sich beim Subjekt (ein Push-Button) als Listener [2]
* und implementiert die geforderte Methode ```actionPerformed```, bei der das Subjekt ermittelt werden muß [3]

[Quelle](https://dbs.cs.uni-duesseldorf.de/lehre/docs/java/javabuch/html/k100227.html#sectlevel3id035002002)

```java
public class Beispiel3501 extends JFrame 
                          implements ActionListener { // [1]
...
 		button1.addActionListener(this); // [2]
...
   public void actionPerformed(ActionEvent e) { // [3]
   ... 
      if (e.getActionCommand().equals("button1")) { // TODO Aktion für button1

```

Eine "moderne" Implementierung (ab Java 8) verwendet Lambdaausdrücke:

* das Interface muss man nicht angeben und ```actionPerformed``` muß nicht explizit implementieren
* denn die Registrierung beim Subjekt enthält bereits den Code für die gewünschte Aktion
* der Code ist daher kompakter und besser lesbar

```java
public class Beispiel3501_inJava8 extends JFrame { ...

		button1.addActionListener(event -> {
			// TODO Aktion für button1
		});
```

### PropertyChangeListener mit SwingWorker

Der ```PropertyChangeListener```  ist ein weiteres Observermuster, das weit verbreitet ist. Zusammen mit [SwingWorker](https://en.wikipedia.org/wiki/SwingWorker) zum Beispiel. SwingWorker werden für zeitaufwändige Aufgaben benutzt, damit die GUI nicht blockert und bedienbar bleibt, und damit die Zwischenergebnisse im GUI angezeigt werden. Die SwingWorker-Task/Loader läuft dabei in separaten Threads. Die notwendige Synchronisation mit dem GUI-Thread geschieht über _property change events_. Der SwingWorker schreibt Informationen über seinen Zustand in zwei Properties "progress" und "state". Und benachrichtigt den EDT(Event Dispatch Thread), wie der GUI-Thread auch genannt wird.  
Das [SwingWorker Beispiel aus Java 8](https://docs.oracle.com/javase/8/docs/api/javax/swing/SwingWorker.html#publish-V...-) verwendet noch die klassische  Implementierungart, wobei der ```ActionListener``` direkt bei der Registrierung konstruiert wird::
 
```java
...
 JTextArea textArea = new JTextArea();
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
```
 
Das Dokumentationsbeispiel im aktuellen Java stammt noch aus Java 6 und wurde seitdem nicht aktualisiert. Es sollte inzwischen so aussehen:

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
 
* "state" durch ``Label status`` für ``PENDING, STARTED, DONE``
* "progress" durch ```JProgressBar progressBar```
* die Registrierung beim Subject wird durch das __binding__ zwischen property und ui-Objekt ersetzt
 
```java
 ...
 BindingGroup group = new BindingGroup();
 group.addBinding(Bindings.createAutoBinding(READ, task, // lese aus der SwingWorker task
   BeanProperty.create("progress"),                      // die Property "progress" und
   progressBar, BeanProperty.create("value")));          // belege damit progressBar Property "value"
 group.addBinding(Bindings.createAutoBinding(READ, task, 
   BeanProperty.create("state"),
   status, BeanProperty.create("loadState")));
 group.bind();
```

## Interface/Implementation-Pair

In Java kommt es sehr häufig vor, dass eine Schnittstelle/interface so weit wie möglich von einer (abstrakten) Klasse vorimplementiert wird. Dieses Vorgehen ist unter dem Namen Interface/Implementation-Pair bekannt. 

Beispiele: 

* ``interface java.util.List<E>`` und  ``abstract class java.util.AbstractList<E>``
* ``interface javax.swing.Action`` und ``abstract class javax.swing.AbstractAction``

