# Entwicklungsumgebung

Es gibt [viele](https://de.wikipedia.org/wiki/Liste_von_Integrierten_Entwicklungsumgebungen) [integrierte Entwicklungsumgebungen/IDEs](  https://de.wikipedia.org/wiki/Integrierte_Entwicklungsumgebung). Zwei werden sich für das Development von Adempiere favorisiert. Unabhängig davon für welche IDE man sich entscheidet, die Wahl des Versionsverwaltung ist nicht frei, denn die zentrale Ablage für das Adempiere Projekt ist git.

## Konfigurationsmanagement

zum [Softwarekonfigurationsmanagement/SCM](https://de.wikipedia.org/wiki/Software-Configuration-Management) gehört die Versionsverwaltung von Ergebnissen, Quellen und Dokumenten, Change-Management und Änderungsverfolgung, Build und Deployment. 

Die zentrale Versionsverwaltung und das Change-Management befinden sich auf GitHub unter https://github.com/adempiere/adempiere.

### Versionsverwaltung

Es gibt unzählige [Version Control Systeme/VCS](http://de.wikipedia.org/wiki/Versionsverwaltung VCSe (Version Control System%29). Neben lokalen Systemen [Unix-SCCS](http://de.wikipedia.org/wiki/SCCS) und den klassischen zentralen Systemen [CVS](http://www.cvshome.org/) oder [Apache Subversion](http://subversion.apache.org/) gibt es die verteilten DVCSe (Distributed Version Control System). Einen guten Einblick bietet der folgende [Artikel](http://www.heise.de/developer/artikel/Die-neue-Freiheit-bei-der-Versionskontrolle-1224755.html).

Neuere Systeme zur Versionsverwaltung sind verteilt. Es gibt keinen eindeutigen Server mit dem Sourcecode-Repository. Bekannte DVCS-Vertreiter sind Mercurial hg, Git und Bazaar.  

### Github

TODO, Themen PR, ...

### Cherry-picking

Beispiel: Issue https://github.com/adempiere/adempiere/issues/2231

Der erste [PR 2232](https://github.com/adempiere/adempiere/pull/2232) wurde nicht integriert, -> Closed with unmerged commits.
Denn die commits fielen zeitlich mit der Relrasefreigabe von 3.9.1 zusammen. Im zweiten Anlauf mußten die commits aus dem pull 2232 rausgepickt werden und in einem neuen PR bereitgestellt werden. Die dabei entstehenden Konflikte müssen aufgelöst werden. Diesen Vorgang nennt man cherry-picking.

PR 2232 besteht aus mehreren commits. Hier das cherry-picking im cmd-line modus:

* schon beim ersten commit gibt es Konfilkte

```cmd
ad391> git cherry-pick --strategy=recursive --strategy-option=theirs 76187c581a0275aad3ede6e58445d7e25543cc5d
error: addinfo_cache failed for path 'zkwebui/.classpath'
error: addinfo_cache failed for path 'org.adempiere.pos/.classpath'
error: addinfo_cache failed for path 'org.adempiere.crm/.classpath'
error: addinfo_cache failed for path 'base/src/org/compiere/model/MRequestUpdate.java'
error: addinfo_cache failed for path 'base/src/org/compiere/model/MRequestProcessorRoute.java'
error: addinfo_cache failed for path 'base/src/org/compiere/model/MRequestProcessorLog.java'
error: addinfo_cache failed for path 'base/.classpath'
error: addinfo_cache failed for path 'JasperReports/.classpath'
U       JasperReports/.classpath
U       base/.classpath
U       org.adempiere.crm/.classpath
U       org.adempiere.pos/.classpath
U       zkwebui/.classpath
error: commit is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
```

* Auflösung im Editor oder in diesem Fall mit der "theirs"-Strategie und anschliessendem commit, einmal für die updates, dann für die renames:

```cmd
ad391> git commit
U       JasperReports/.classpath
U       base/.classpath
U       org.adempiere.crm/.classpath
U       org.adempiere.pos/.classpath
U       zkwebui/.classpath
error: commit is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

ad391>git commit -a
[dev+2231 cddcb3a] avoid cyclic project dependences between base, project, request
 Date: Wed Dec 19 11:24:02 2018 +0100
 87 files changed, 260 insertions(+), 280 deletions(-)
 rename {org.adempiere.request/src/main/java => base/src}/org/compiere/apps/Request.java (100%)
 rename {org.adempiere.project/src/main/java => base/src}/org/compiere/model/CalloutProject.java (100%)
 rename {org.adempiere.request/src/main/java => base/src}/org/compiere/model/CalloutRequest.java (100%)
 rename {org.adempiere.request/src/main/java => base/src}/org/compiere/model/MChangeRequest.java (100%)
 rename {org.adempiere.request/src/main/java => base/src}/org/compiere/model/MContactInterest.java (100%)
```

* die restlichen commits (ohne Konflike):

```cmd
ad391>git cherry-pick --strategy=recursive --strategy-option=theirs 4beca5aca3fc8d3266e3f86a56f9bd69cef19bf7
[dev+2231 250bb1a] eclipse project name same to git name
 Date: Thu Dec 20 13:39:13 2018 +0100
 1 file changed, 1 insertion(+), 1 deletion(-)

 ...
 
ad391>git cherry-pick --strategy=recursive --strategy-option=theirs 61c7429a087729e02b83c6a1e439ebfa7bdcbe0d
[dev+2231 97d929c] remove request+project from build
 1 file changed, 2 deletions(-)

```

## https://de.wikipedia.org/wiki/Eclipse_(IDE%29

## https://de.wikipedia.org/wiki/IntelliJ_IDEA


