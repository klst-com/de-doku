# Glossar

* [ADempiere Glossary engl.](https://adempiere.gitbook.io/docs/v/develop/glossary)
* [iDempiere Gloasar](https://wiki.idempiere.org/de/Glossar)

## A

ACH
: das [Automated Clearing House](https://en.wikipedia.org/wiki/Automated_Clearing_House) ist ein elektronisches Überweisungsnetz, das in den Vereinigten Staaten verwendet wird, ähnlich dem [SWIFT](#s) in Europa

ASI Attribute Set Instance
: TODO (... You need to define a Attribute Set if you want to enable Serial and Lot Number tracking. )

AP Account Payable
: bezeichnet das Kreditorenkonto bzw. (im plural) die Verbindlichkeiten, [s.Kap Buchhaltung](usr/2.8-acc.md#finanzbuchhaltung)

APC Account Payable Creditmemo 
: Gutschrift vom Kreditor/Lieferant, siehe [Basisbelegart](adm/1.installation.md#basisbelegart)

API Account Payable Invoice 
: Eingangsrechnung vom Lieferanten, siehe [Basisbelegart](adm/1.installation.md#basisbelegart)

APP Account Payable Payment 
: [Zahlung](#z) an Kreditor/Lieferant, siehe [Basisbelegart](adm/1.installation.md#basisbelegart)

AR Account Receivable
: bezeichnet das Debitorenkonto bzw. (im plural) die Forderungen, [s.Kap Buchhaltung](usr/2.8-acc.md#finanzbuchhaltung)

ARI Account Receivable Invoice 
: Ausgangsrechnung an Debitor/Kunden, siehe [Basisbelegart](adm/1.installation.md#basisbelegart)

ARR Account Receivable Receipt 
: Beleg über [Eingangszahlung](#z), siehe [Basisbelegart](adm/1.installation.md#basisbelegart)

Assets
: Vermögensgegenstände, [s.Kap Buchhaltung](usr/2.8-acc.md#anlagenbuchhaltung)

## B

Basisbelegart
: alle Belege werden von wenigen [Basisbelegarten](adm/1.installation.md#basisbelegart) (DocBaseType, 3-stellig, z.B. ARI) abgeleitet

Bankleitzahl
: routingnumber(routingno), bankcode+branchcode, die nationale Bankleitzahl in Deutschland und Österreich [wird seit 2014](https://de.wikipedia.org/wiki/Europ%C3%A4ischer_Zahlungsraum) nicht mehr verwendet. In der [IBAN](#i) existiert sie nachwievor. In England ist [bank sort code](https://www.bundesbank.de/en/tasks/payment-systems/services/bank-sort-codes/) der entsprechende Begriff, in Irland **NSC**/[national sort code](https://en.wikipedia.org/wiki/Sort_code#Sort_codes_of_the_Republic_of_Ireland), in Frankreich wird "Code Guichet" verwendet. Die Schweizer geben jedem Finanzinstitut eine **IID** (Instituts-Identifikation).

Basiskonten
: 83 "abstrakten" Konten/default accounts, siehe [Kontenplan](adm/1-83accts.md)

BBAN
: als [Basic Bank Account Number](https://en.wikipedia.org/wiki/International_Bank_Account_Number#Basic_Bank_Account_Number) wird der Teil der [IBAN](#i) ab Position 5 bezeichnet (ohne Länderkennzeichen und ohne die zweistellige Prüfsumme)

BIC
: [Business Identifier Code](https://de.wikipedia.org/wiki/ISO_9362), auch SWIFT-BIC, SWIFT-Code oder SWIFT-Adresse, siehe [(adm)Installation/Banken](adm/1.installation.md#banken) und [(dev)Referenzdaten/Banken](dev/bankimport.md#banken)

Business English / Wirtschaftsenglisch
: Basic Accounting Terminology / Grundlegende [Fachbegriffe im Rechnungswesen](https://www.controllerakademie.de/wp-content/uploads/2016/08/Vokabeln-Wirtschaftsenglisch-Zingel.pdf)

## C

Cash Journal
: oder Cash Book oder [Cash receipts journal](https://en.wikipedia.org/wiki/Cash_receipts_journal), siehe [Kassenbuch](#k)

CII
: Cross Industry Invoicing - ein Datenmodell für e-Rechnungen

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

e-invoice (elektronische Rechnung)
: [e-invoice](https://github.com/klst-de/e-invoice) Eine elektronische Rechnung ist „... eine Rechnung, die ineinem strukturierten elektronischen Format ausgestellt, übermittelt und empfangen wird, dasihre automatische und elektronische Verarbeitung ermöglicht.“ Eine reine PDF-Datei, oder eine eingescannte Papierrechnung sind somit  keineelektronische Rechnung im Sinne der Richtlinie [2014/55/EU](https://eur-lex.europa.eu/legal-content/DE/ALL/?uri=CELEX:32014L0055).

## F

Fakturierung
: siehe [Rechnungsstellung](usr/2.3-sales.md#rechnungsstellung)

Fixed Assets (Tangible Assets)
: Sachanlagen, [s.Kap Buchhaltung](usr/2.8-acc.md#anlagenbuchhaltung)

## G

(code) Guichet
: siehe [Bankleitzahl](#b) in Frankreich

## H

HR
: [Human Resources](https://de.wikipedia.org/wiki/Personalwesen) umfasst das Thema [Personal und Gehaltsabrechnung](usr/2.9-hr.md)

## I

IBAN
: die [International Bank Account Number](https://de.wikipedia.org/wiki/Internationale_Bankkontonummer) ist eine standardisierte Notation für Bankkontonummern, die automatisches Abwickeln von Zahlungen emöglicht (siehe auch [Abkürzungsverzeichnis](https://de.iban.com/abkurzungen) im Zahlungsverkehr) 

IID
: Instituts-Identifikation, siehe [Bankleitzahl](#b) in der Schweiz

Intangible Assets
: immaterielle Vermögensgegenstände, [s.Kap Buchhaltung](usr/2.8-acc.md#anlagenbuchhaltung)

Interface/Implementation-Pair
: siehe [Entwurfsmuster](adm/patterns.md#interface-implementation-pair)

## J
## K

Kassenbuch
: im [Kassenbuch](https://de.wikipedia.org/wiki/Kassenbuch) werden alle Barzahlungsvorgänge (Bareinzahlungen, Barauszahlungen, Einlagen und Entnahmen) chronologisch aufgezeichnet. Es dient zur Ermittlung des Kassenbestands.

Kontenplan
: [mit Basis- oder Standardkonten/default accounts](adm/1-83accts.md) oder [DATEV SKR Standard Kontenrahmen](usr/3.datev.md#einrichtung-eines-mandanten-mit-standard-kontenrahmen)

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

MMR Material Movement Receipt
: Wareneingangsbeleg, siehe [Basisbelegart](adm/1.installation.md#basisbelegart)

MMS Material Movement Shipment
: Lieferschein an Kunden, Warenausgangsbeleg, siehe [Basisbelegart](adm/1.installation.md#basisbelegart)

## N

NSC
: "national sort code", siehe [Bankleitzahl](#b) in Irland

## O

openTRANS
: [s.Kap Nutzung von openTRANS](usr/4.opentrans.md)

order
: je nach [Transaktionsart](usr/2.4-purchase.md) wird unterschieden zwischen Bestellung (ausgehende Order) [purchase order](https://en.wikipedia.org/wiki/Purchase_order) und Auftrag (eingehende Order) [sales order](https://en.wikipedia.org/wiki/Sales_order)

## P

PAN
: die [Primary Account Number](https://de.wikipedia.org/wiki/Primary_Account_Number) ist Bestandteil einer Zahlungskartennummer. Sie identifiziert eine Bank und wird mit dem [`bank importer`-Programm](adm/1.installation.md#banken) eingelesen

payment 
: siehe [Zahlungsausgang](#z)

Produktion und Production light
: [s.Kap Warenwirtschaft/Logistik](usr/2.5-mm.md)

## Q
## R

receipt 
: [Quittung](https://de.wikipedia.org/wiki/Quittung), oft auch [Einnahmebeleg ARR Account Receivable Receipt](#a) für [Zahlungseingang](#z)

Rechnung
: Der Begriff „Rechnung“ im Sinne von [XRechnung](https://www.xoev.de/de/xrechnung) beschreibt eine Rechnung in elektronischer Form [elektronische Rechnung](#e). Ein  reines PDF oder eine eingescannte Papierrechnung sind somit  keine elektronische Rechnung im Sinne der Richtlinie 2014/55/EU.

RIB
: als [relevé d’identité bancaire](https://fr.wikipedia.org/wiki/Basic_Bank_Account_Number) französiche Bezeichnung für [BBAN](#b)

routingno
: routingnumber(routingno), siehe [Bankleitzahl](#b)

## S 

SKR
: [StandardKontenRahmen](https://de.wikipedia.org/wiki/Kontenrahmen#Standardkontenrahmen) in Deutschland sind die [DATEV](#d)-Kontenrahmen [SKR03 und SKR04](usr/3.datev.md) verbreitet

SSR
: Server Side Rendering, ältere [web UI](#w)s nutzen diese Methode während bei Neueren [CSR](#c) eingesetzt wird

sort code
: bank [sort code](https://en.wikipedia.org/wiki/Sort_code), siehe [Bankleitzahl](#b) in England

SCRDM
: [Supply Chain Reference Data Model](https://www.unece.org/fileadmin/DAM/uncefact/RSM/RSM_SCRDM_v1.0.0.2.pdf) - CII ist ein Teil davon

SWIFT
: die [Society for Worldwide Interbank Financial Telecommunication](https://de.wikipedia.org/wiki/SWIFT) leitet Transaktionen zwischen Banken und Institutionen aus über 200 Ländern weiter und wickelt damit den Zahlungsverkehr der angeschlossenen Institute ab

SWIFT-Code
: siehe [BIC](#b)-Code

swing
: Bestandteil von [Java](https://de.wikipedia.org/wiki/Swing_%28Java%29) zur Programmierung von grafischen [UI](#u)s

## T

Tabellenarten
: [s.ADM Übersetzung](adm/2.trl.md#tabellenarten) 

Tangible Assets (Fixed Assets)
: Sachanlagen, [s.Kap Buchhaltung](usr/2.8-acc.md#anlagenbuchhaltung)

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
![](icons/feather/search.svg)      | `<F6>`          | [Datensatz suchen](usr/2.0-window.md#suche)
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

Wirtschaftsenglisch / Business English
: Grundlegende [Fachbegriffe im Rechnungswesen](https://www.controllerakademie.de/wp-content/uploads/2016/08/Vokabeln-Wirtschaftsenglisch-Zingel.pdf) / Basic Accounting Terminology

## X

XRechnung
: [XRechnung](https://www.xoev.de/de/xrechnung) beschreibt eine Rechnung in elektronischer Form [elektronische Rechnung](#e). Der Standard XRechnung stellt eine [CIUS zur EN 16931](https://github.com/klst-de/e-invoice) dar.

## Y
## Z

Zahlung
: Zahlungseingang mit [Einzahlungen](https://de.wikipedia.org/wiki/Einzahlung) oder Zahlungsausgang mit [Auszahlungen](https://de.wikipedia.org/wiki/Auszahlung), eine Zahlung verändert den [Zahlungsmittelbestand](https://de.wikipedia.org/wiki/Zahlungsmittelbestand). Die Belege für Einzahlungen werden [ARR Account Receivable Receipt](#a) genannt, die für Auszahlungen [APP Account Payable Payment](#a)

Zahlungsmittelbestand
: Summe von Bargeld (Kassenbestand), Buchgeld (Bankguthaben) und Geldersatzmittel (Schecks, Wechsel). Oder Summe der verfügbaren Zahlungsmittel (cash) und Zahlungsmitteläquivalente [cash equivalents](https://en.wikipedia.org/wiki/Cash_and_cash_equivalents)

ZK
: mittels [ZK CE](https://de.wikipedia.org/wiki/ZK_OSS) wurde die Adempiere [web UI](w#) entwickelt
