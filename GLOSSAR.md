# Glossar

## A

ACH
: das [Automated Clearing House](https://en.wikipedia.org/wiki/Automated_Clearing_House) ist ein elektronisches Überweisungsnetz, das in den Vereinigten Staaten verwendet wird, ähnlich dem [SWIFT](#s) in Europa

ASI Attribute Set Instance
: TODO (... You need to define a Attribute Set if you want to enable Serial and Lot Number tracking. )

## B

BBAN
: als [Basic Bank Account Number](https://en.wikipedia.org/wiki/International_Bank_Account_Number#Basic_Bank_Account_Number) wird der Teil der [IBAN](#i) ab Position 5 bezeichnet (ohne Länderkennzeichen und ohne die zweistellige Prüfsumme)

BIC
: [Business Identifier Code](https://de.wikipedia.org/wiki/ISO_9362), auch SWIFT-BIC, SWIFT-Code oder SWIFT-Adresse, [siehe (adm)Installation/Banken](adm/1.installation.md#banken)

## C

CRP
: Capacity Requirement Planning, siehe Materialbedarfsplanung [MRP](#m)

CSR
: Client Side Rendering, [web UI](#w)s deren Seiten erst im Browser berechnet werden, siehe [CSR vs server-side-rendering](https://medium.freecodecamp.org/what-exactly-is-client-side-rendering-and-hows-it-different-from-server-side-rendering-bd5c786b340d)

## D

Datenmodell
: [siehe SchemaSpy Analysis of idempiere51.adempiere](https://globalqss.com/idempiere/5.1_20171111/schemaspy/)

DATEV
: [s.Kap Koexistenz mit DATEV](usr/3.datev.md)

Direktlieferung
: ist ein Synoonym für [Streckengeschäft](https://de.wikipedia.org/wiki/Streckengesch%C3%A4ft), siehe [Bestellung](usr/2.4-purchase.md#direktlieferung-streckengeschaeft)

Drop Shipment (en)
: siehe Direktlieferung

## E
## F
## G
## H

HR
: [Human Resources](https://de.wikipedia.org/wiki/Personalwesen) umfasst das Thema [Personal und Gehaltsabrechnung](usr/2.9-hr.md)

## I

IBAN
: die [International Bank Account Number](https://de.wikipedia.org/wiki/Internationale_Bankkontonummer) ist eine standardisierte Notation für Bankkontonummern, die automatisches Abwickeln von Zahlungen emöglicht (siehe auch [Abkürzungsverzeichnis](https://de.iban.com/abkurzungen) im Zahlungsverkehr) 

Interface/Implementation-Pair
: siehe [Entwurfsmuster](dev/patterns#interface-implementation-pair)

## J
## K

KP
: Kapazitätenplanung, Capacity Requirement Planning(en), siehe Materialbedarfsplanung [MRP](#m)

## L

L&F
: als [Look&Feel](https://de.wikipedia.org/wiki/Look_and_Feel) wird das Aussehen und Verhalten der Benutzeroberfäche bezeichnet. Das ["Look" des clients](dev/laf.md) ist umschaltbar.

## M

MBP (de) / MRP (en)
: [Materialbedarfsplanung](https://de.wikipedia.org/wiki/Bedarfsermittlung) / [Material Requirements Planning](https://de.wikipedia.org/wiki/Material_Requirements_Planning) siehe [Produktionsmanagement](usr/2.6-prod.md)

Menü Icons
: [am Beispiel Beschaffung](usr/2.4-purchase.md)

![](../.gitbook/assets/menu-purchase-de.PNG)

**_swing_** | **_web_** | **_Name_**
------- | ------- | ------- 
![](../.gitbook/assets/icons/menuSwing/mWindow.png)   | ![](../.gitbook/assets/icons/menuWeb/mWindow.png)   | Transaktionsfenster 
![](../.gitbook/assets/icons/menuSwing/mProcess.png)  | ![](../.gitbook/assets/icons/menuWeb/mProcess.png)  | Prozess             
![](../.gitbook/assets/icons/menuSwing/mReport.png)   | ![](../.gitbook/assets/icons/menuWeb/mReport.png)   | Report/Bericht      
![](../.gitbook/assets/icons/menuSwing/mWorkFlow.png) | ![](../.gitbook/assets/icons/menuWeb/mWorkFlow.png) | Workflow            
![](../.gitbook/assets/icons/menuSwing/TreeLeaf.gif)  | ![](../.gitbook/assets/icons/menuWeb/TreeLeaf.gif) ohne  | Browser

Alternative icons 

* Transaktionsfenster:

![](icons/feather/layers.svg)

* Prozess:

![](icons/feather/loader.svg)

* Report/Bericht:

![](icons/feather/list.svg)

* Workflow:

![](icons/feather/git-pull-request.svg)

* Browser:

![](icons/feather/monitor.svg)

## N
## O

openTRANS
: [s.Kap Nutzung von openTRANS](usr/4.opentrans.md)

order
: je nach [Transaktionsart](usr/2.4-purchase.md) wird unterschieden zwischen Bestellung (ausgehende Order) [purchase order](https://en.wikipedia.org/wiki/Purchase_order) und Auftrag (eingehende Order) [sales order](https://en.wikipedia.org/wiki/Sales_order)

## P

PAN
: die [Primary Account Number](https://de.wikipedia.org/wiki/Primary_Account_Number) ist Bestandteil einer Zahlungskartennummer. Sie identifiziert eine Bank und wird mit dem [`bank importer`-Programm](adm/1.installation.md#banken) eingelesen

Produktion und Production light
: [s.Kap Warenwirtschaft/Logistik](usr/2.5-mm.md)

## Q
## R
## S 

SKR
: [StandardKontenRahmen](https://de.wikipedia.org/wiki/Kontenrahmen#Standardkontenrahmen) in Deutschland sind die [DATEV](#d)-Kontenrahmen [SKR03 und SKR04](usr/3.datev.md) verbreitet

SSR
: Server Side Rendering, ältere [web UI](#w)s nutzen diese Methode während bei Neueren [CSR](#c) eingesetzt wird

SWIFT
: die [Society for Worldwide Interbank Financial Telecommunication](https://de.wikipedia.org/wiki/SWIFT) leitet Transaktionen zwischen Banken und Institutionen aus über 200 Ländern weiter und wickelt damit den Zahlungsverkehr der angeschlossenen Institute ab

SWIFT-Code
: siehe [BIC](#b)-Code

swing
: Bestandteil von [Java](https://de.wikipedia.org/wiki/Swing_%28Java%29) zur Programmierung von grafischen [UI](#u)s

## T

Tabellenarten
: [s.ADM Übersetzung](adm/2.trl.md#tabellenarten) 

Toolbar
: [siehe idempiere/Toolbar (swing-Client)](http://wiki.idempiere.org/de/Toolbar)

![](http://wiki.idempiere.org/w-de/images/4/4f/Toolbar_-_Window_%28iDempiere_1.0.0%29.png)

die Icons der Toolbar im web-Client sehen anders aus:

![](../.gitbook/assets/Toolbar-web.PNG)

* Alternative icons 

![](../.gitbook/assets/icons/menuKlst/Toolbar.PNG)
 
**_icon_** | **_key_** | **_Beschreibung_**
------- | ------- | ------- 
![](icons/feather/rotate-ccw.svg)  | `<Escape>`  | Änderung rückgängig machen
![](icons/feather/help-circle.svg) | `<F1>`  | Hilfe
![](icons/feather/square.svg)      | `<F2>`  | Neuer Eintrag
![](icons/feather/copy.svg)        | `<Shift><F2>` | Eintrag kopieren
![](icons/feather/trash.svg)       | `<F3>`          | Eintrag löschen
![](icons/feather/trash-2.svg)     | `<Ctrl><D>`    | Ausgewählte Einträge löschen
![](icons/feather/save.svg)        | `<F4>`          | Änderungen speichern
![](icons/feather/refresh-cw.svg)  | `<F5>`          | Erneut abfragen
![](icons/feather/search.svg)      | `<F6>`          | Eintrag suchen
![](icons/feather/paperclip.svg)   | `<F7>`          | Anhang
![](icons/feather/message-square.svg) |       | Chat


## U

UI
: User Interface - Benutzerschnittstellen, die Präsentationsschicht in Adempiere gibt es zwei Implementierungen. Eine JAVA [swing](#s)-UI und die [web-UI](#w).

UOM Unit of Measure 
: [Maßeinheiten](http://wiki.idempiere.org/de/Ma%C3%9Feinheit_%28Fenster_ID-120%29) können für die [Warenwirtschaft](usr/2.5-mm.md) frei definiert werden

## V
## W

web UI
: Benutzeroberfläche [UI](#u), die im Browser präsentiert wird

## X
## Y
## Z

ZK
: mittels [ZK CE](https://de.wikipedia.org/wiki/ZK_OSS) wurde die Adempiere [web UI](w#) entwickelt
