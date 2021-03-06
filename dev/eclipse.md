# Entwicklungsumgebung

Allgemeines zu [Eclipse als IDE in wikipedia](https://de.wikipedia.org/wiki/Eclipse_%28IDE%29). Man sollte sich für eine neuere Version entscheiden. Älter als [V.4.7/Oxygen](https://de.wikipedia.org/wiki/Eclipse_%28IDE%29#Versionen) sollte die IDE nicht sein.

- V.4.7/Oxygen
- V.4.8/Photon (nach dieser Version gibt es keine Namen mehr, sondern den Erscheinumgsmonat)
- V.4.9/2018-09 : pro Jahr gibt es 4 Versionen -03 -06 -09 und 12
...
- V.4.16/2020-06

## Anbindung an Git

Mit [EGit](http://eclipse.org/egit) ist die Anbindung der IDE an beliebige git-Versionsverwalungssysteme gegeben.

## Welche Eclipse Komponenten sind notwendig?

- zu den [JDT](https://www.eclipse.org/jdt/), [Java Development Tools](https://de.wikipedia.org/wiki/Java_Development_Tools) sollten folgende Komponenten(plugins) installiert sein
- EGit wg. Anbindung an git (s. oben - bereits in JDT)
- [Web Tools Platform](https://www.eclipse.org/webtools/), das Fehlen dieser Komponente wird angezeigt durch

![](../images/eclipse-wst.PNG)

### eclipse Bug 567319 - Parser error while editor

Ich habe eclipse V.4.16/2020-06 , inzwischen mit upgrade auf 4.17 und falle in den [Bug 567319](https://bugs.eclipse.org/bugs/show_bug.cgi?id=567319) - ich bin nicht der einzige, wie man sieht. Der Java Editor stürzt ab, wenn ein bestimmter (Tipp-)Fehler im Code passiert (dpoppelte Klammern): 

        Amount allowancesTotalAmount = testDoc.getAllowancesTotal()();
 
Der Fehler wird erst mit V4.19, also in der Dezember Verion 2020-06 behoben sein. 

## java

Für den build wird JDK 1.8 benötigt. Aktuell ``jdk-8u241``. 

JRE genügt nicht! Wer es dennoch versucht, bekommt

```
BUILD FAILED
...
com.sun.tools.javac.Main is not on the classpath.
Perhaps JAVA_HOME does not point to the JDK.
It is currently set to "C:\Program Files\Java\jre1.8.0_241"
```

## Adempiere in eclipse

Die vielen Verzeichnisse im git-[Repository](https://de.wikipedia.org/wiki/Repository) entsprechen in eclipse den Projekten in einem Workspace.

* zuerst soltte man also ein eclipse workspace, z.B. ``Adempiere39`` anlegen
* dann aus dem Repository den entsprechenden Branch kopieren / in git Terminologie wird dieser Vorgang "cloning" genannt, siehe [Github forking](ide.md#forking)

![](../.gitbook/assets/CheckoutAdempiereFromGitInEclipse.png)

* es dauert ein wenig bis die ca. 2GB kopiert werden

![](../.gitbook/assets/CloningAdempiereFromGithubIntoNewEclipseWorkspace.PNG)

* Nach dem Klonen werden die eclipse Projekte importiert/erstellt. Zu einer Fehlentwicklung gehört m.E. die Definition von adempiere als ein eclipse Projekt. Also ohne nested projects. Dies ist [nicht im developer-guide](https://adempiere.gitbook.io/docs/v/develop/developer-guide) dokumentiert. In eclipse gibt es folgende Möglichkeiten:

  * importieren des Hauptprojektes ``adempiere`` als ein Projekt (no nested projects)
  * importieren der git-Unterverzeichnisse als mehrere Projekte, also  ``base``, ``client``, ... usw.
  * importieren des Hauptprojektes und der Unterprojekte

![](../.gitbook/assets/ImportAdempiereProjectsFromGit.PNG)

Die git-Unterverzeichnisse sind manchmal als eclipse Projekte definiert, manchmal nicht. Oft ist die Definition von ``.project`` und ``.classpath`` nicht korrekt oder nicht aktuell, weil import Alternative b oder c gar nicht vorgesehen sind. 

### adempiere als ein Projekt

- Verwendet ant builder

### mehrere Projekte

- cycles in the build path: dieses Problem wurde in [issue 2231](https://github.com/adempiere/adempiere/issues/2231) und [pull 2400](https://github.com/adempiere/adempiere/pull/2400) diskutiert. Eclipse stuft eine zyklische Projektstuktur als Fehler ein und verweigert den build. Dieses Standardverhalten muss angepasst werden. 

