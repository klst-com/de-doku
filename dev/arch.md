# Architektur vs. Anatomie

In der Informatik gibt es den Bergiff der [Softwarearchitektur](https://de.wikipedia.org/wiki/Softwarearchitektur). Der Begriff Anatomie ist im Softwarekontext nicht gebräuchlich. Dabei ist die heute verfügbare Software oft schlecht dokumentiert und die ursprünglichen Architekturentscheidungen nicht mehr im Detail nachvollzielbar. Reifere Systeme sind in einem evolutionären Prozess gewachsen. Das gilt auch für ADempiere. 

Wenn hier die Architektur dokumentiert wird, dann sind es meist nicht Ergebnisse von Entwurfsentscheidungen, sondern die anatomischen Entdeckungen, die bei der Pflege und Weiterentwicklung des Systems angefallen sind.

Anatomie | Software Architetktur
-------- | -------------
![](http://www.vitamindmangel.net/wp-content/uploads/vitd3_abbau1.jpg) | ![](../.gitbook/assets/Bcab4_PT_image002.gif)

## Client-Server-Architektur

ADempiere is als [Client-Server-System](http://de.wikipedia.org/wiki/Client-Server-Modell) aufgebaut, bestehend aus zwei oder drei Schichten. Siehe auch [Schichtenarchitekturen nach Anzahl der Schichten](http://de.wikipedia.org/wiki/3-Tier-Architektur#Schichtenarchitekturen_nach_Anzahl_Schichten).

Wie viele [ERP](https://de.wikipedia.org/wiki/Enterprise-Resource-Planning)-Systeme ist ADempiere als [verteiltes 3-tier System](https://de.wikipedia.org/wiki/Schichtenarchitektur#Drei-Schichten-Architekturen_bei_verteilten_Systemen) aufgebaut. 

Die klassische 3-Tier-Architektur am Beispiel [SAR ERP](https://de.wikipedia.org/wiki/SAP_ERP)

![](../.gitbook/assets/Bcab4_PT_image002.gif)

es gibt diese drei Schichten:
* auf Client-Seite gibt es mehrere Web-GUI Varianten
* Applikationsserver
* DBMS oder Datenbank-Schicht

Zu einer 3-Tier-Architektur bei ADempiere gab es die [Überlegungen](http://www.adempiere.com/Adempiere_Architecture_3_tier).

Anatomie | Software Architetktur
-------- | -------------
![Anatomie](http://www.vitamindmangel.net/wp-content/uploads/vitd3_abbau1.jpg) | [[images/Bcab4_PT_image002.gif]]

## Datenbank-Schicht

http://www.adempiere.com/Table_Prefix