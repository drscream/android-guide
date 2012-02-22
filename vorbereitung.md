# Vorbereitung der Entwicklungsumgebung

## Hardware

Die Entwicklung für Android kann auf verschiedensten Betriebssystemen erfolgen. Die Entwicklungswerkzeuge stehen für Windows, Linux und MacOS X zur Verfügung. Für den Beginn ist auch kein Android Smartphone Vorraussetzung. In der Entwicklungsumgebung (SDK) von Google wird ein Emulator<span class="fn"><a href="http://developer.android.com/guide/developing/tools/emulator.html">Android Emulator</a></span> mitgeliefert.

## Werkzeuge

### Linux Kernel
Das Betriebssystem Android basiert komplett auf offenem Quelltext (Open Source). Der Quelltext<span class="fn"><a href="http://source.android.com/">Android Quelltext</a></span> wird als GIT<span class="fn"><a href="http://git-scm.com/">GIT</a></span> Verzeichnis, für alle Zugänglich, angeboten. Der Linux Kernel bietet die Grundlage für das Android Betriebssystem. Durch Ihn werden unter anderem folgende Funktionen abgebildet:

* Speicherverwaltung
* Prozessverwaltung
* Netzwerk
* Treibermodell

Eine gute Übersicht bietet auch die <a href="#android-architektur">Abbildung 1: Android Architektur <a href="#huether10"><cite>huether10</cite></a></a>.

### Android-Laufzeitumgebung und Bibliotheken

Eine Stufe über dem Linux Kernel befindet sich die Android-Laufzeitumgebung. Die beinhaltet unter anderem die Dalvik VM.

* Android-Laufzeitumgebung: Java Kern Bibliotheken und Dalvik VM 
* Open GL: 2D und 3D Graphik Bibliothek
* WebKit: Webbrowser Engine
* SQLite: Relationale Datenbank
* Media Framework: Audio und Video Framework
* SSL Layer: Bibliotheken für die sichere Datenübertragung

### Anwendungrahmen

Das Android Application Framework<span class="fn"><a href="http://developer.android.com/resources/faq/framework.html">Android Application Framework</a></span> macht dem Entwickler viele Funktionen einfach nutzbar. Der Entwickler kann diese Bibliotheken nutzen und muss einige Funktionen nicht selbst implementieren.

* Activity Manager
* Telephony Manager
* View System
* Location Manager

Es besteht natürlich weiterhin die Möglichkeit auch auf Ressourcen des Kernsystems zuzugreifen. Hierzu werden vom Android Projekt aber auch viele Ressourcen angeboten. Empfehlenswert ist ein Blick in den Quelltexte.

### Java

Dank Java ist es nicht erforderlich sich um die Speicherverwaltung zu kümmern. Dies wird direkt von der Java Virtual Machine<span class="fn"><a href="http://java.sun.com/docs/books/jvms/">Java Virtual Machine</a></span> übernommen. Die Grundlagen in Programmiersprache sollten für die Entwicklung bekannt sein. Hierzu bietet Oracle verschiedenste Java Tutorials<span class="fn"><a href="http://docs.oracle.com/javase/tutorial/">Java Tutorials</a></span> an. Ein sehr Ausführliches Kurs Buch, Java ist auch eine Insel<span class="fn"><a href="http://openbook.galileocomputing.de/javainsel/">Java ist auch eine Insel</a></span> wird von Galileo Computing als kostenloses Online Buch angeboten.

## Entwicklungsumgebung

Da die Programmierung in Java erfolgt, kann jede beliebige Entwicklungsumgebung oder Editor eingesetzt werden. Eclipse<span class="fn"><a href="http://www.eclipse.org/">Eclipse</a></span> ist zu Empfehlen, da hierfür Erweiterungen für die Android Programmierung vorhanden sind. In dieser Dokumentation wird die Vorbereitung der Entwicklungsumgebung unter Linux beschrieben.

### Java Development Kit (JDK)

Es ist zu Empfehlen das JDK aus dem Paketmanagement des Betriebssystems zu installieren. Hier gibt es meist verschiedene Anbieter die JDKs zur Verfügung stellen. Eine sichere Wahl ist aber das JDK von Sun bzw. Oracle.

#### Debian

Unter Debian befindet sich das Sun Java SDK in den <i>non-free</i> Quellen. Hierzu muss eventuell ein zusätzlicher Eintrag in der Datei <i>/etc/apt/sources.list</i> vorgenommen werden. Die Installation erfolgt mit dem Debian Paketmanager <i>aptitude</i>. Als Alternative kann auch <i>apt-get</i> verwendet werden.

<div class="listing" id="sources-listnon-free">
<pre><code>$ echo "deb http://ftp.de.debian.org/debian/ squeeze non-free" >> /etc/apt/sources.list
$ aptitude install sun-java6-sdk</code></pre>
	<p>Hinzufügen non-free Debian Quellen zu sources.list und Installation von Sun Java SDK</p>
</div>


#### Alternative

Sollte kein auf dem System kein Paketmanagement vorhanden sein, ist es auch Möglich das JDK von Oracle Internetseite<span class="fn"><a href="http://www.oracle.com/technetwork/java/javase/downloads">Oracle Internetseite</a></span> herunterzulassen. Da die Seite sehr unübersichtlich wirkt, ist zu Beachten, dass die JDK und nicht JRE Version verwendet wird.


### Android SDK

Das Android SDK liefert kein Skript zur Installation mit. Eine TAR Archiv beinhaltet alle nötigen Dateien, die in den gewünschten Installationspfad entpackt werden. Nach der Installation muss die PATH Variable angepasst werden <a href="#julian10"><cite>julian10</cite></a>. Hierzu wird wie folgt vorgegangen.

<ol>
  <li>Download der aktuellen SDK Version<span class="fn"><a href="http://developer.android.com/sdk/">Android SDK Download</a></span> für Linux</li>

</ol>

### Eclipse

