# Hier sind einige Probleme, die Sie lösen könnten.

## Problem 1

Es gibt eine Dokumentübersicht. Sie können sie im Browser ansehen, indem sie auf "Editionseinheiten" klicken. Aber wenn man auf ein Dokumententitel klickt, passiert nichts. Wer auch immer diese Seite erstellt hat, ging davon aus, dass das kleine Linksymbol am Anfang jeder Zeile ausreichen würde. Das ist aber nicht sehr praktisch.

### Bitte ändern Sie die Seite so, dass ein Klick auf den Titel oder die gesamte Zeile das entsprechende Dokument öffnet.

Falls Sie nicht weiterkommen, versuchen Sie Folgendes:
1. Finden Sie die Datei, die für die Erstellung der HTML-Datei mit der Tabelle verantwortlich ist. Ein Blick in die Datei `build.xml`, die die XSLTs organisiert, könnte ein guter Anfang sein.
2. Versuchen Sie, das XSLT zu finden, das den bestehenden Link erstellt.
3. Verschieben Sie den Teil, der für den Link verantwortlich ist, an die neue Stelle und passen Sie ihn entsprechend an.

### Am Rendering dieser Tabelle war vorher eine JS-Bibliothek beteiligt. Sie heißt `tabulator`. Bitte finden Sie die Stelle, an der ich den Code auskommentiert habe, der für das Laden dieser Bibliothek verantwortlich ist, und heben Sie die Kommentierung auf. (Sie befindet sich in derselben Datei, mit der Sie gerade gearbeitet haben...) Testen Sie, ob nach einem erneuten build die Links noch funktionieren. Falls nicht, versuchen Sie, sie zu reparieren.

<br/>

**Falls Sie etwas Eigenes ausprobieren möchten:** *Könnten Sie der Tabelle zusätzliche Funktionalität hinzufügen? Was könnte ergänzt werden? Man musst mit `tabulator.js` interagieren, um die Tabelle zu verändern. Denken Sie auch daran, dass die Test-Daten heterogen sind, sodass sie möglicherweise harmonisieren oder einige ausgeschlossen werden müssen.*

## Problem 2

In den Editions-XML-Dateien sind einige Bilder enthalten, die im Frontend nicht angezeigt werden. Nehmen wir als Beispiel ```data/editions/KrausExample.xml```. Versuchen Sie, die Bilder des Dokuments im Frontend anzuzeigen.
1. Finden Sie heraus, wo die Bilder in der XML-Datei verlinkt sind.
2. Finden Sie heraus, wie/wo die Beziehung zwischen Text und Bild in der XML-Datei bestimmt wird.
3. Finden Sie das XSLT, das für das Rendern der Seite mit dem transkribierten Text verantwortlich ist.
4. Fügen Sie ein kleines XSLT-Template hinzu, um das Verhalten so zu ändern, dass das Bild angezeigt wird.
5. Fügen Sie CSS hinzu, um es etwas besser aussehen zu lassen, falls Sie möchten. Die Seite verwendet bereits [Bootstrap](https://getbootstrap.com/). Es ist also bereits etwas CSS enthalten.
*Können Sie ein Problem im TEI-XML identifizieren, das damit zusammenhängt, wie wir Seiten codieren und Bilder/Seiten darstellen?*

## Problem 3

Einige Seiten enthalten Fußnoten. Aber es gibt eine Reihe von Problemen mit ihnen. 
Einige sind mit dem Haupttext verlinkt, andere nicht.
Versuchen Sie:
1. Das XSLT zu finden, das die Fußnoten erstellt.
2. Zu verstehen, welche Elemente in den Editionsdateien davon betroffen sind.
3. Eine bessere Lösung zu finden.
