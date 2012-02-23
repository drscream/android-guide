# Entwicklung

## Übersicht
### Eclipse Projekt

Nach dem Start von Eclipse muss ein Projekt speziell für Android erstellt werden. Im Abschnitt Installation wurden die nötigen Eclipse Plugins (ADT) für das Projekt installiert.

<ol>
	<li>Unter <i>File -> New -> Project</i> wird der Wizard zur Projekterstellung ausgewählt.</li>
	<li>Wichtig ist unter dem Reiter <i>Android -> Android Project</i> auszuwählen.
		<div class="figure" id="new-project-wizard">
			<img src="http://up.frubar.net/1507/2012-02-22-191712_613x478_scrot.png" alt="new-project-wizard" width="70%" />
			<p>Wizard zur Erstellung eines neuen Android Projekts in Eclipse</p>
		</div>
	</li>
	<li>Dem Wizard, bis zur Einstellung für die Anwendungsinformationen folgen. Der Name für den Java Paketnamen ist ein Pflichtfeld. Weitere Informationen zu Java Packages sind im Java Workshop<span class="fn"><a href="http://javaworkshop.sourceforge.net/chapter3.html">Java Workshop, Packages</a></span> zu finden. In der SDK Version sollte festgelegt werden welche Android Geräte später unterstützt werden müssen. 
		<div class="figure" id="new-project-wizard-app-info">
			<img src="http://up.frubar.net/1508/2012-02-22-201815_605x557_scrot.png" alt="new-project-wizard-app-info" width="70%" />
			<p>Neues Android Projekt, Anwendungsinformationen festlegen</p>
		</div>		
	</li>
</ol>

### Emulation

Der Emulator stellt ein vollwertiges Android Betriebssystem für die spezifizierte Version bereit. In Eclipse befindet sich hierzu der Android Virtual Device (AVD) Manager<span class="fn"><a href="http://developer.android.com/guide/developing/devices/managing-avds.html">Android Virtual Device (AVD) Manager</a></span>. AVDs werden mit <span class="figure"><a href="http://www.qemu.org/">Qemu</a></span> virtualisiert und unterstützen viele verschiedene Android Versionen. Im Android SDK Manager können andere Android Versionen nachinstalliert werden. <a href="#daniel11"><cite>daniel11</cite></a>

<ol>
	<li>
		In der Menüleiste von Eclipse befindet sich ein Icon des AVD Managers, dieser wird per Klick geöffnet.
		<div class="figure" id="icon-avd">
			<img src="http://up.frubar.net/1505/2012-02-22-201853_1364x668_scrotKopie.png" alt="icon-avd" width="50%" />
			<p>Icon des AVD Managers in Eclipse</p>
		</div>
	</li>
	<li>
		Über den Button <i>New</i> wird ein neues Android Virtual Device erstellt. Im Wizard können die Werte meist auf den Standard Einstellungen belassen werden. Wichtig ist die Auswahl der Android Version (API Level).
		<div class="figure" id="new-avd">
			<img src="http://up.frubar.net/1506/2012-02-22-201935_550x631_scrot.png" alt="new-avd" width="70%" />
			<p>Erstellung einer neues AVDs</p>
		</div>
	</li>
</ol>

### Android Versionen

Der Versions-Code (API Level) ist nicht das selbe wie der Versions-Name (Platform Level). Jeder Versions-Name hat exakt einen Versions-Code. Dies sollte bei der Wahl im Emulator und der Entwicklung beachtet werden. <a href="#gplatform12"><cite>gplatform12</cite></a>

<table>
	<thead>
		<tr><th>Versions-Name (Platform)</th><th>Codename</th><th>Versions-Code (API)</th></tr>
	</thead>
	<tbody>
		<tr><td>Android 1.5</td><td>Cupcake</td><td>3</td></tr>
		<tr><td>Android 1.6</td><td>Donut</td><td>4</td></tr>
		<tr><td>Android 2.1</td><td>Eclair</td><td>7</td></tr>
		<tr><td>Android 2.2</td><td>Froyo</td><td>8</td></tr>
		<tr><td>Android 2.3-2.3.2</td><td>Gingerbread</td><td>9</td></tr>
		<tr><td>Android 2.3.3-2.3.7</td><td>Gingerbread</td><td>10</td></tr>
		<tr><td>Android 3.0</td><td>Honeycomb</td><td>11</td></tr>
		<tr><td>Android 3.1</td><td>Honeycomb</td><td>12</td></tr>
		<tr><td>Android 3.2</td><td>Honeycomb</td><td>13</td></tr>
		<tr><td>Android 4.0-4.0.2</td><td>Ice Cream Sandwich</td><td>14</td></tr>
		<tr><td>Android 4.0.3</td><td>Ice Cream Sandwich</td><td>15</td></tr>
	</tbody>
</table>

### Projektstruktur

Ein Android Projekt beinhaltet eine umfangreiche Ordnerstruktur. Diese Struktur wird automatisch vom Wizard erstellt, es ist dennoch sinnvoll sich diese näher anzusehen. Im Eclipse Package Explorer sind folgende Order zu sehen:

* src
* gen
* Android Version (z.B. Android 2.3.3)
* assets
* res

<div class="figure" id="eclipse-pkg-exlorer">
	<img src="http://up.frubar.net/1510/2012-02-23-155432_1366x746_scrot.png" alt="eclipse-pkg-exlorer" width="50%" />
	<p>Eclipse Package Explorer</p>
</div>

In einem Projekt können noch weitere Ordner vorhanden sein. Dies sind aber die Standard Ordner, die durch den Wizard erstellt werden. Weitere Ordner können sein <i>bin</i>, <i>libs</i> und <i>referenced libraries</i>.

#### Ordner für den Quelltext (<i>src</i>)

Das <i>src</i> Verzeichnis beinhaltet den Quelltext des Android Projekts. Nach Erstellung des Projekts über den Wizard beinhaltet das Verzeichnis ein weiteres Verzeichnis mit dem Paketnamen. In diesem befindet sich die <i>ProjektnameActivity.java</i> Datei mit einigen Zeilen Java Quelltext.

Ein Android Projekt kann mehrere Pakete und Quelltext-Dateien beinhalten. Als Beispiel könnten zwei weitere Pakete mit Java Klassen vorhanden sein. Eines welches HTTP Klassen beinhaltet und ein weiteres Paket in dem Java Models enthalten sind.

* com.android.example.models
* com.android.example.http

#### Ordner der Android Bibliothek (<i>Android Version</i>)

Dieses Verzeichnis beinhaltet die SDK Version des verwendeten Android Projekts. Der Inhalt wurde automatisiert erstellt, die Version ist abhängig von der Auswahl des Projekts.

#### Anlagenverzeichnis (<i>assets</i>)

Standardmäßig befinden sich keine Dateien im <i>assets</i> Verzeichnis. Es existiert um <i>raw</i> Binärdaten zu speichern und über die Anwendung darauf zuzugreifen. Für das Verzeichnis gibt es keine Dateibeschränkung, es kann somit jeder beliebiger Inhalt abgelegt werden.

<i>Assets</i> erhalten keine Ressource IDs, somit muss der Zugriff z.B. über die Java Methode <i>InputStream</i> erfolgen. <a href="#zechner11"><cite>zechner11</cite></a>

#### Ressourcen Ordner (<i>res</i>)

Das <i>res</i> Verzeichnis beinhaltet alle Ressourcen die eine Anwendung benötigt. Es ist der von Google empfohlene Weg um Dateien (Ressourcen) in der Anwendung zu benutzen. Im Quelltext kann auf die Ressource via ID zugegriffen werden. Diese wird automatisch per ADT in der <i>R</i> Klasse hinterlegt.

Ein gutes Beispiel für Ressource Dateien sind Bilder. Diese werden im Verzeichnis abgelegt und per Java Quelltext nur referenziert. Das selbe Verfahren finden auch Anwendung bei Text Ressourcen (z.B. für verschiedene Sprachen).

Im Ressourcen Verzeichnis existieren Unterordner für spezielle Ressourcen Typen. Zum Beispiel soll eine XML-Datei in einem anderen Ordner abgelegt werden, wie eine PNG-Datei. Es ist nicht zulässig Dateien direkt im <i>res</i> Verzeichnis zu speichern.

<table>
	<thead>
		<tr><th>Verzeichnis</th><th>Ressourcen Typ</th></tr>
	</thead>
	<tbody>
		<tr><td><i>anim/</i></td><td>XML Definitionsdateien für Animationen</td></tr>
		<tr><td><i>color/</i></td><td>XML Dateien für Farbdefinitionen</td></tr>
		<tr><td><i>drawable/</i></td><td>Bilddateien (.png, .jpg, .gif) oder XML Dateien mit Bildressourcen</td></tr>
		<tr><td><i>drawable-hdpi/</i></td><td>Selbe wie <i>drawable/</i> jedoch für Hochauflösende Bilder</td></tr>
		<tr><td><i>drawable-ldpi/</i></td><td>Selbe wie <i>drawable/</i> jedoch für Bilder mit niedriger Auflösung</td></tr>
		<tr><td><i>drawable-mdpi/</i></td><td>Selbe wie <i>drawable/</i> jedoch für Bilder mit mittlerer Auflösung</td></tr>
		<tr><td><i>layout/</i></td><td>XML Datei mit der Definition des User-Interfaces</td></tr>
		<tr><td><i>menu/</i></td><td>Menü der Anwendung als XML Datei</td></tr>
		<tr><td><i>raw/</i></td><td>Binärdateien die nicht komprimiert werden</td></tr>
		<tr><td><i>values/</i></td><td>Beliebige XML Dateien, die Strings, Farben oder Integer Werte beinhalten. Das Verzeichnis beinhaltet auch XML Dateien, die auf andere Ressource Dateien verweist. Beispiel Dateien sind:
			<ul><li><i>arrays.xml</i></li><li><i>colors.xml</i></li><li><i>dimens.xml</i></li><li><i>strings.xml</i></li><li><i>style.xml</i></li></ul></td></tr>
	</tbody>
</table>

## Benutzeroberfläche
### Layout
### Bedienschnittstellen
### Bilder
### Startsymbole
### visual Designer

## Anwendungsfunktionen
### Aktivitäten



### Ressourcen
### Klassen
