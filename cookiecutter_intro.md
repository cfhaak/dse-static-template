# Grundlagen
Dieses Dokument bietet einen Überblick über die Verwendung des DSE-Static Cookiecutters.

<br />

## Was ist der DSE Static Cookiecutter?
+ **[DSE Static Cookiecutter](https://github.com/acdh-oeaw/dse-static-cookiecutter) ist ein “static-site” Generator für TEI/XML-kodierte wissenschaftliche digitale Editionen.** Er basiert auf [cookiecutter](https://github.com/cookiecutter/cookiecutter).
+ Allgemein handelt es sich um eine Sammlung von Prozessen und Informationen, die zum Herstellen simpler, statischer Webseiten verwendet werden können.

<br />

### Was braucht man für eine Website/Webanwendung? & Welches Problem löst DSE-SC?
Um die Daten einer Edition, die als TEI-XML existieren, über einen Server für Benutzer:innen im Browser visuell codiert anzuzeigen, muss: 
+ das XML der edierten Dokumente in [HTML](https://de.wikipedia.org/wiki/Hypertext_Markup_Language) umgewandelt werden
+ das Rendering der HTML mittels CSS konfiguriert werden
+ ein Server aufgesetzt werden

DSE-SC erleichtert einige dieser Aufgaben erheblich. Aber die Benutzung von DSE-SC erfordert etwas Arbeit.
+ Ist DSE-SC ein CMS? → Nein.
+ Ist DSE-SC sehr einfach zu bedienen? → Nein.
+ Sind die Resultate per default schön und gut designed? → Nein.
+ Ist es besonders user-friendly? → Nein.

#### Warum nicht einfach Wordpress? Oder Vue.js oder Astro oder WIX…
Für konventionelle Anwendungen spricht (je nach dem konkreten Fall) einiges. Z.B.:
+ Die Resultate sehen per default besser aus.
+ Die Seiten können komplexere Features teilweise einfacher umsetzen.
+ Datenbanken können leicht eingebunden werden.

#### Sustainability und Minimal Computing
Gegen diese Lösungen spricht allerdings auch einiges:
+ Sie bieten keine, eingeschränkte oder nur sehr komplexe Möglichkeiten, um XML in HTML umzuwandeln.
+ Wartungsarbeiten sind wichtig. Webseiten funktionieren nur so lange, wie die Infrastruktur, die ihnen zugrunde liegt, existiert und gewartet wird.
+ Je Komplexer die Technologien sind, die verwendet werden, desto komplexer wird die Wartung.
+ lock-ins
+ Es handelt sich um dynamische Systeme. Statische Webseiten sind wesentlich portabler.
+ Data first! Was ist das Resultat unsere Forschungsarbeit? Daten oder Website/Anwendung?
+ Ökologie

<br />

### Von den Daten zur Website
Spätestens, wenn das Editieren der TEI-XML Dokumente bereits abgeschlossen wurde, wird es notwendig, die Dateien online zur Verfügung zu stellen.
Da die meisten Menschen (auch Wissenschaftler:innen) nicht gerne XML-Dokumente lesen, müssen wir 
1. das XML irgendwie in HTML umwandeln.
2. das HMTL online zur Verfügung stellen & mit CSS versehen, also eine Website erstellen und hosten.

DSE-SC benutzt zwei grundlegende Technologien um den ersten Schritt durchzuführen, XSLT und Apache Ant.

#### XSLT
+ [TEI](https://tei-c.org/guidelines/)-XML ist der am weitesten verbreitete Standard für Editionsprojekte. Es handelt sich um eine [XML](https://de.wikipedia.org/wiki/Extensible_Markup_Language)-Spezifikation, die im Rahmen der *Text Encoding Initiative* speziell auf das codieren von Texten zugeschnitten wurde.
    + [TEI](https://de.wikipedia.org/wiki/Extensible_Markup_Language), bessere Quelle [hier]
+ Die hier verwendeten [XSL Transformations](https://developer.mozilla.org/en-US/docs/Web/XSLT) beschreiben – basierend auf der [Extensible Stylesheet Language (XSL)](https://www.w3.org/Style/XSL/WhatIsXSL.html) – wie XML-Dokumente in HTML umgewandelt werden sollen.

#### Was ist Ant?
+ „[Apache Ant](https://ant.apache.org/) is a Java library and command-line tool whose mission is to drive processes described in build files as targets and extension points dependent upon each other. The main known usage of Ant is the build of Java applications.“
+ Ant wird hier verwendet, um eine Liste von Arbeitsschritten nacheinander abzuarbeiten. Z.B.:
    + einzelne Subseiten unserer Website zu bauen (also XSL Transformations zu koordinieren)
    + externe Daten zu updaten
    + nicht mehr benötigte Daten zu löschen
+ Wenn Ant lokal im Terminal verwendet wird, sucht es im aktuellen Verzeichnis nach einer buildfile namens ```build.xml``` und versucht, die darin definierten Arbeitsschritte durchzuführen.
+ Arbeitsschritte lassen sich beliebig hinzufügen, modifizieren und entfernen.
+ Die ```buildfile``` folgt einem speziellen XML-Format, im dem sich [verschiedene Tasks](https://ant.apache.org/manual/tasksoverview.html) definieren lassen. Neben einfachen Dateioperationen (löschen, erzeugen etc.) lassen sich auch Skripte oder Binaries ausführen.

<br /><br />

# Hosting
### Was ist Git?
+ [„Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.“](https://git-scm.com/)
+ operiert wie ein append-only Dateisystem
+ Git versioniert Datenzustände
+ Git kann koordinierte Arbeit in Teams unterstützen
+ Standard in der Software-Entwicklung
[Es existiert eine Vielzahl von Git-Clients,](https://git-scm.com/downloads/guis) die lokal installiert werden können. Ich präferiere das Terminal-Tool ```git```, für das ein nützliches [Cheat Sheet](https://training.github.com/downloads/de/github-git-cheat-sheet/) existiert.

### GitHub
+ Ist ein online Service, quasi ein Git-Server.
+ Es bietet viele weitere Funktionalitäten, z.B. online Editoren, GitHub-Pages etc.
+ GitHub bietet umfangreiche Dokumentationen und Tutorials für alle Funktionalitäten / Git, z.B. ein [Manual](https://githubtraining.github.io/training-manual/#/) und die [Docs](https://docs.github.com/en/get-started/using-github-docs)

### [GitHub-Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
+ bietet ein gratis https-Server, der Daten aus einem Repository veröffentlicht.
+ ist kostenlos, die [**Verwendung ist aber eingeschränkt**](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#limits-on-use-of-github-pages) (z.B. ist die gewerbliche Verwendung nicht zulässig).

### GitHub-Workflows
Bei [Workflows](https://docs.github.com/en/actions/writing-workflows/quickstart) handelt es sich um Automatisierungen für
    + das Aufsetzen eines virtuellen Computers (quasi eines Servers)
    + das automatisierte ausführen von Skripten etc. (z.B. das Ausführen von ```ant```)
    + das Präparieren von Daten
Das von [GitHub verwendete yaml-Datei Format](https://docs.github.com/en/actions/writing-workflows/workflow-syntax-for-github-actions) ist gewöhnungsbedürftig und kann am Anfang etwas frustrierend sein. Es hilft sich existierende Beispiele und [die Tutorials](https://docs.github.com/en/actions/use-cases-and-examples/creating-an-example-workflow) anzusehen.