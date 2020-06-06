# Infofenster

Infofenster sind festprogrammiert modale [Fenster](../usr/2.0-window.md#infofenster), die sich von ``abstract class Info extends CDialog`` ableiten. ``Info`` stellt auch Methoden z.B. ``showOrder`` zum Anzeigen der Fenster in einem Frame:

```java
public static void showOrder(Frame frame, int WindowNo, String value) {
	Info info = new InfoOrder(frame, false, WindowNo, 0, value, false, false, "");
	AEnv.showCenterWindow(frame, info);
}
```

Einige Infofenster sind wie Formulare ``form`` ausprogrammiert. Auszug aus ``AEnv.actionPerformed``:

```java
...
	else if (actionCommand.equals("InfoAsset") && AEnv.canAccessInfo("ASSET")) {
		org.compiere.apps.search.Info.showAsset(Env.getFrame(c), WindowNo);
	} else if (actionCommand.equals("InfoAccount") && MRole.getDefault().isShowAcct() && AEnv.canAccessInfo("ACCOUNT")) {
		new org.compiere.acct.AcctViewer();
	} else if (actionCommand.equals("InfoSchedule") && AEnv.canAccessInfo("SCHEDULE")) {
		new org.compiere.apps.search.InfoSchedule(Env.getFrame(c), null, false);
	} else if (actionCommand.equals("InfoMRP") && AEnv.canAccessInfo("MRP")) {
		CFrame frame = (CFrame) Env.getFrame(c);
		int m_menu_id = MMenu.getMenu_ID("MRP Info");
		AMenu menu = AEnv.getAMenu(frame);
		AMenuStartItem form = new AMenuStartItem(m_menu_id, true, Msg.translate(Env.getCtx(), "MRP Info"), menu);
		form.start();
	} else if (actionCommand.equals("InfoCRP") && AEnv.canAccessInfo("CRP")) {
		CFrame frame = (CFrame) Env.getFrame(c);
		int m_menu_id = MMenu.getMenu_ID("CRP Info");
		AMenu menu = AEnv.getAMenu(frame);
		AMenuStartItem form = new AMenuStartItem(m_menu_id, true, Msg.translate(Env.getCtx(), "CRP Info"), menu);
		form.start();
	} else if (actionCommand.equals("InfoOrder") && AEnv.canAccessInfo("ORDER")) {
		org.compiere.apps.search.Info.showOrder(Env.getFrame(c), WindowNo, "");
```

Außerden werden manche Infofenster zum Suchen verwendet.

## MiniTable

Infofenster benutzen [swing table](https://docs.oracle.com/javase/tutorial/uiswing/components/table.html), um die Daten anzuzeigen. MiniTable ist nicht direkt von swing JTable abgeleitet ``class MiniTable extends CTable implements IMiniTable``. Die C*-Komponenten dienen als gemeinsamer Nenner für swing- und web-Client.

Zu einer Fehlentwicklung gehört m.E. mehrere loader. Auch MiniTable hat einen als inner class definiert: ``class Worker extends Thread``. Der Loader in [GridTable](../grid-model.md) erfüllt dieselbe Aufgabe! Ein weiterer leader befindet sich im SmartBrowser.
 