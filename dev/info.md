# Infofenster

Infofenster sind fest programmierte modale [Fenster](../usr/2.0-window.md#infofenster), die sich von ``abstract class Info extends CDialog`` ableiten. ``Info`` stellt auch Methoden z.B. ``showOrder`` zum Anzeigen der Fenster in einem Frame:

```java
public static void showOrder(Frame frame, int WindowNo, String value) {
	Info info = new InfoOrder(frame, false, WindowNo, 0, value, false, false, "");
	AEnv.showCenterWindow(frame, info);
}
```

Einige Infofenster sind wie Formulare ``form`` ausprogrammiert. Auszug aus ``AEnv.actionPerformed``:

```java
...
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

## Eine Alternative sind generische Formulare

Generische Formulare sind ein Zwischending. Nicht voll generische Fenster wie AD_Window, aber auch nicht ganz ausprogrammiert wie die meisten `FormPanel` Implementierungen.
Mit `class GenericFormPanel implements FormPanel` haben wir ein Framework, womit für definierte Fenster mit geringem Aufwand Form Panels mit MiniTables implementiert werden können.

- `UnprocessedDocuments` ist eine Alternative zu Fenster ALL_UNPROCESSED AD_Window_ID = 53087
- `WorkflowActivities` ist eine Alternative zu Fenster WF_ACTIVITIES AD_Window_ID = 298

Die Beispiele bestehen aus ContentPane im BorderLayout 

- at PAGE_START a selectionPanel - die Selektionen sind generisch, wie bei Fenstern (für YN werden erweiterte JXComboBox'en aus swingx genutzt: sie sind 3-wertig und können emojis darstellen)
- at CENTER a mainPanel with scrollable miniTable
- at PAGE_END a statusBar

Das dritte Bespiel ist eine Alternative zu Klasse `org.compiere.apps.search.InfoOrder`

In der Minitable kann man von den Zellen zu den Entities zoomen. Auch dieses Feature ist generisch.

`UnprocessedDocuments`, `WorkflowActivities` und `InfoOrder` werden genauso in AD registriert wie andere Form Komponenten und können

- ins Menü und
- die Berechtigung in Rollen

eingetragen werden

Denn `GenericFormPanel` implementiert die `FormPanel` Schnittstelle.

Ein komplexeres Beispiel mit subPanes ist `InfoBPartner`. Ein kommentierter Screenshot ist unter [Info Geschäftspartner](../usr/2.0-window.md#info-geschaeftspartner) im Benutzerhandbuch.

### geringer Aufwand

... es muss lediglich ein TableSelectionListener für den zoom-Aufruf implementiert und registriert werden. Beispiel `InfoOrder`:

```java
public class InfoOrder extends GenericFormPanel {
...
    protected void registerTableSelectionListener() throws Exception {
...
        miniTable.addMiniTableSelectionListener(event -> {
            Object source = event.getSource();
            if(source instanceof CTable) {
                MiniTable miniTable = (MiniTable)source;
                ListSelectionModel columnSM = miniTable.getColumnModel().getSelectionModel();
                if(columnSM.getAnchorSelectionIndex()==column_index_Record_ID) {
                    zoom(I_C_Order.Table_ID, miniTable, column_index_Record_ID);
                } else {
                    zoom(I_C_BPartner.Table_ID, miniTable, column_index_C_BPartner_ID);
                }
            } else {
                log.config("source NOT CTable:"+source);
            }
        });
    }
```

## MiniTable

Infofenster benutzen [swing table](https://docs.oracle.com/javase/tutorial/uiswing/components/table.html), um die Daten anzuzeigen. MiniTable ist nicht direkt von swing JTable abgeleitet ``class MiniTable extends CTable implements IMiniTable``. Die C*-Komponenten dienen als gemeinsamer Nenner für swing- und web-Client.

Zu einer Fehlentwicklung gehört m.E. mehrere loader. Auch MiniTable hat einen als inner class definiert: ``class Worker extends Thread``. Der Loader in [GridTable](grid-model.md) erfüllt dieselbe Aufgabe! Ein weiterer leader befindet sich im SmartBrowser.
 