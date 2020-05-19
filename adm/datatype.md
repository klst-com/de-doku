# Referenzen/Datentypen

Datentypen in Adempiere sind mehr als Datenbankdatentypen (Character, String, Numeric, Date, ...). Jedes Feld ist einer Referenz zugeordnet. Diese Referenzen bestimmen den Datentyp, die Validierung und die Präsentation. In Tabelle AD_Reference gibt es 34 Enträge mit entitytype='D' und validationtype='D'. Siehe [Entering Data](https://adempiere.gitbook.io/docs/v/develop/introduction/getting-started/entering-data-fields-and-buttons)

Es gibt elementare, einfache Referenzen (Yes-No, String) und komplexe wie Adresse oder Lagerort.


## [Yes-No](https://adempiere.gitbook.io/docs/v/develop/introduction/getting-started/entering-data-fields-and-buttons#yes-no)

## [String](https://adempiere.gitbook.io/docs/v/develop/introduction/getting-started/entering-data-fields-and-buttons#string)

## Zeitangaben

### Date

![](../.gitbook/assets/VDate.PNG)

### Date+Time

### Time

## Auswahlfelder

Felder können anhand fest definierten Listen validiert werden (**List**). Es sind ca 300 Validierungslisten definiert. Beispiel: Maßeinheiten werden in verschiedene Typen (es sind 21) eingeteilt:  

![](../.gitbook/assets/RefList.PNG)

Oder gegen den Inhalt von Tabellen (**Table Direct**), Wähungen werden in Tabelle ``C_Currency`` gepflegt:

![](../.gitbook/assets/RefTableDirect.PNG)

Die Präsentation ist in beiden Fällen eine [Combobox](https://docs.oracle.com/javase/tutorial/uiswing/components/combobox.html).

## [Adresse](https://adempiere.gitbook.io/docs/v/develop/introduction/getting-started/entering-data-fields-and-buttons#location-address)

## [Lagerort](https://adempiere.gitbook.io/docs/v/develop/introduction/getting-started/entering-data-fields-and-buttons#locator-wh)