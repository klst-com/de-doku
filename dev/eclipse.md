# Entwicklungsumgebung

Allgemeines zu [Eclipse als IDE in wikipedia](https://de.wikipedia.org/wiki/Eclipse_%28IDE%29). Man sollte sich für eine neuere Version entscheiden. Älter als [V.4.7/Oxygen](https://de.wikipedia.org/wiki/Eclipse_%28IDE%29#Versionen) sollte die IDE nicht sein.

## Anbindung an Git

Mit [EGit](http://eclipse.org/egit) ist die Anbindung der IDE an beliebige git-Versionsverwalungssysteme gegeben.

## Adempiere in eclipse

Die vielen Verzeichnisse im git-[Repository](https://de.wikipedia.org/wiki/Repository) entsprechen in eclipse den Projekten in einem Workspace.

* zuerst soltte man also ein eclipse workspace, z.B. ```Adempiere39``` anlegen
* dann aus dem Repository den entsprechenden Branch kopieren / in git Terminologie wird dieser Vorgang "cloning" genannt, siehe [Github forking](ide.md#forking)

![](../.gitbook/assets/CheckoutAdempiereFromGitInEclipse.png)

* es dauert ein wenig bis die ca. 2GB kopiert werden

![](../.gitbook/assets/CloningAdempiereFromGithubIntoNewEclipseWorkspace.PNG)

* Nach dem Klonen werden die eclipse Projekte importiert/erstellt. Zu einer Fehlentwicklung gehört m.E. die Definition von adempiere als Ganzes als eclipse Projekt mit Unterprojekten. Aber auch die git-Unterverzeichnisse sind eclipse Projekt.

![](../.gitbook/assets/ImportAdempiereProjectsFromGit.PNG)