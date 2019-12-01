# Grid

Das grid Modell ist ein zentraler Bestandteil im base Subprojekt. Die Klassen stammen noch aus compiere und sind demnach im ```org.compiere.model``` package. Im folgenden Diagramm sind die wichtigsten grid Klassen abgebildet.

* GridWindow modelliert einen Container und besteht oft aus mehreren Reitern (Tabs)
* GridTabs wiederum besteht aus mehreren Feldern, den GridFields
* ein GridField ist die Kombination von Feldattributen, die definieren wie ein Feld dargestellt wird, und Column Attributen, die definieren wie die Felddaten gespeichert werden. Die Metadatentabellen ```AD_colum``` und ```AD_Field``` speichern diese Informationen
* zu GridField, GridTabs und GridWindow existieren Value Objects (VO), Klassen die konkrete Objekte kapseln

![](../.gitbook/assets/GridInADbase.png)

* GridTable wird zum Laden der Daten aus der Datenbank benötigt. Es implementiert das [swing TableModel](https://wiki.byte-welt.net/wiki/JTable_%28Tutorial%29%C2%A9), das nicht mit einer Datenbank Table verwechselt werden sollte. Auch wenn GridTable von eine swing Klasse abgeleitet ist, ist diese Klasse keine UI-Komponente. In swing modelliert TableModel eine Tabelle mit Zellen, für die Präsentation sind andere Klassen verantwortlich, siehe Trennung [Model und View](https://de.wikipedia.org/wiki/Model_View_Controller#Modell_%28model%29).