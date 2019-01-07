# Look and Feel

Das Erscheinungsbild (Programm Look&Feel/PLAF) des swing-clients wird von zwei Komponenten bestimmt, aus denen der Adempiere client besteht
* [Java swing](https://de.wikipedia.org/wiki/Swing_(Java))
* jgoodies, das auf Java Metal basiert

Zu einem "look" kann es verschiedene Themen geben. Farben und Schriften bestimmen ein Thema. Für das ursprüngliche Compiere gibt es die Themen CompiereThemeBlueMetal und CompiereThemeIce.

## Java swing look

In Java gibt es nur zwei "looks". Das bekannteste wird "Metal" genannt mit dem "Ocean"-Thema (links im Bild). Und das neuere, aber wenig bekannte "Nimbus".

![](../.gitbook/assets/LaF-Metal+Nimbus.PNG)

Ausserdem können Javaprogramme das Erscheinungsbild der Betriebssysteme annehmen, unter denen sie arbeiten, also Windows, Motif oder GTK unter *nix.

## jgoodies look

[JGoodies Software GmbH](http://www.jgoodies.com/) hat eine jar-Bibliothek bereitgestellt, die Java Metal erweitert. Das "look" hat der Entwickler "Plastik" genannt. Zu Plastik gibt es mehrere Themen.

* ```SkyBluer``` (medium blue primary colors and a light gray window background)
* davon abgeletet ```AbstractSkyTheme: SkyBlue, SkyGreen, SkyKrupp, SkyPink, SkyRed, SkyYellow```
* davon ebenfalls abgeleitet ```DesertBluer: DesertBlue, DesertGreen, DesertRed, DesertYellow, ExperienceBlue, ExperienceGreen, ExperienceRoyale, LightGray, Silver```
* und die dunklen Farben ```InvertedColorTheme: BrownSugar, DarkStar```

Das vervendete ```looks-2.0.4.jar``` ist von 2006 und damit ziemlich veraltet. Der Entwickler stellt inzwischen keine kostenfreie Aktualisierungen bereit _I can no longer provide the libraries at no charge_.