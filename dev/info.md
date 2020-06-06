# Infofenster

Infofenster sind festprogrammiert modale [Fenster](../usr/2.0-window.md#infofenster), die sich von ``abstract class Info extends CDialog`` ableiten. ``Info`` stellt auch Methoden z.B. ``showOrder`` zum Anzeigen der Fenster in einem Frame:

```java
public static void showOrder(Frame frame, int WindowNo, String value) {
	Info info = new InfoOrder(frame, false, WindowNo, 0, value, false, false, "");
	AEnv.showCenterWindow(frame, info);
}
```

Außerden werden Infofenster zum Suchen verwendet.
 