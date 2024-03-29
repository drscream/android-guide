# Vorbereitung der Entwicklungsumgebung

## Hardware

Die Entwicklung für Android kann auf verschiedensten Betriebssystemen erfolgen. Die Entwicklungswerkzeuge stehen für Windows, Linux und MacOS X zur Verfügung. Für die Entwicklung ist kein Smartphone erforderlich, da die Entwicklungsumgebung (SDK) von Google einen Emulator<span class="fn"><a href="http://developer.android.com/guide/developing/tools/emulator.html">Android Emulator</a></span> mitliefert. Für spätere Entwicklungsphasen empfiehlt sich der Test auf einem Android Smartphone.

## Werkzeuge

### Linux Kernel
Das Betriebssystem Android basiert komplett auf offenem Quelltext (Open Source). Der Quelltext<span class="fn"><a href="http://source.android.com/">Android Quelltext</a></span> wird in einem GIT<span class="fn"><a href="http://git-scm.com/">GIT</a></span> Repository, für alle zugänglich, angeboten. Der Linux Kernel bietet die Grundlage für das Android Betriebssystem. Durch ihn werden unter anderem folgende Funktionen abgebildet:

* Speicherverwaltung
* Prozessverwaltung
* Netzwerk
* Treibermodell

Eine gute Übersicht bietet auch die <a href="#android-architektur">Abbildung 1: Android Architektur <a href="#huether10"><cite>huether10</cite></a></a>.

---

### Android-Laufzeitumgebung und Bibliotheken

Eine Stufe über dem Linux Kernel befindet sich die Android-Laufzeitumgebung. Diese beinhaltet unter anderem die Dalvik VM.

* Android-Laufzeitumgebung: Java Kern Bibliotheken und Dalvik VM 
* Open GL: 2D und 3D Graphik Bibliothek
* WebKit: Webbrowser Engine
* SQLite: Relationale Datenbank
* Media Framework: Audio und Video Framework
* SSL Layer: Bibliotheken für die sichere Datenübertragung

### Anwendungsrahmen

Das Android Application Framework<span class="fn"><a href="http://developer.android.com/resources/faq/framework.html">Android Application Framework</a></span> macht dem Entwickler viele Funktionen einfach nutzbar. Der Entwickler kann diese Bibliotheken nutzen und um häufig benötigte Funktionen nicht selbst implementieren zu müssen.

* Activity Manager
* Telephony Manager
* View System
* Location Manager

Es besteht natürlich weiterhin die Möglichkeit auch auf Ressourcen des Kernsystems zuzugreifen. Empfehlenswert ist ein Blick in den Quelltext.

### Java

Dank Java ist es nicht erforderlich sich um die Speicherverwaltung zu kümmern. Dies wird direkt von der Java Virtual Machine<span class="fn"><a href="http://java.sun.com/docs/books/jvms/">Java Virtual Machine</a></span> übernommen. Die Grundlagen in dieser Programmiersprache sollten für die Entwicklung bekannt sein. Hierzu bietet Oracle verschiedenste Java Tutorials<span class="fn"><a href="http://docs.oracle.com/javase/tutorial/">Java Tutorials</a></span> an. Ein sehr Ausführliches Kurs-Buch, "Java ist auch eine Insel"<span class="fn"><a href="http://openbook.galileocomputing.de/javainsel/">Java ist auch eine Insel</a></span> wird von Galileo Computing als kostenloses Online-Buch angeboten.

## Entwicklungsumgebung

Da die Programmierung in Java erfolgt, kann jede beliebige Entwicklungsumgebung oder Editor eingesetzt werden. Eclipse<span class="fn"><a href="http://www.eclipse.org/">Eclipse</a></span> ist zu Empfehlen, da hierfür Erweiterungen für die Android Programmierung vorhanden sind. In dieser Dokumentation wird die Vorbereitung der Entwicklungsumgebung unter Linux beschrieben.

### Java Development Kit (JDK)

Es ist zu Empfehlen das JDK aus dem Paketmanagement des Betriebssystems zu installieren. Hier gibt es meist verschiedene Anbieter die JDKs zur Verfügung stellen. Eine sichere Wahl ist aber das JDK von Sun bzw. Oracle.

#### Debian

Unter Debian befindet sich das Sun Java SDK in den <i>non-free</i> Quellen. Hierzu muss eventuell ein zusätzlicher Eintrag in der Datei <i>/etc/apt/sources.list</i> vorgenommen werden. Die Installation erfolgt mit dem Debian Paketmanager <i>aptitude</i>. Als Alternative kann auch <i>apt-get</i> verwendet werden.

<div class="listing" id="sources-listnon-free">
<code><pre>$ echo "deb http://ftp.de.debian.org/debian/ squeeze non-free" \
	>> /etc/apt/sources.list
$ aptitude update
$ aptitude install sun-java6-sdk</pre></code>
	<p>Hinzufügen non-free Debian Quellen zu sources.list und Installation von Sun Java SDK</p>
</div>


#### Alternative

Sollte auf dem System kein Paketmanagement vorhanden sein, ist es auch Möglich das JDK von der Oracle Internetseite<span class="fn"><a href="http://www.oracle.com/technetwork/java/javase/downloads">Oracle Internetseite</a></span> herunterzuladen. Da die Seite sehr unübersichtlich wirkt, ist zu beachten, dass die JDK und nicht JRE Version verwendet wird.

---

### Android SDK

Das Android SDK liefert kein Skript zur Installation mit. Eine TAR Archiv beinhaltet alle nötigen Dateien, die in den gewünschten Installationspfad entpackt werden. Nach der Installation muss die PATH Variable angepasst werden <a href="#julian10"><cite>julian10</cite></a>. Hierzu wird wie folgt vorgegangen.

<ol>
	<li>Download der aktuellen SDK Version<span class="fn"><a href="http://developer.android.com/sdk/">Android SDK Download</a></span> für Linux</li>
	<li>Das TAR Archiv sollte nach <i>/opt/</i> entpackt werden
	<code><pre>$ tar xfz android-sdk_r16-linux.tgz -C /opt
$ ls /opt/
android-sdk-linux</pre></code></li>
	<li>Die Rechte für das Verzeichnis müssen nach dem Extrahieren angepasst werden. In diesem Beispiel wird eine spezielle <i>android</i> Gruppe erstellt, die das SDK ausführen darf.
	<code><pre>$ addgroup android
$ adduser max.mustermann android
$ chown -R root:android /opt/android-sdk-linux</pre></code></li>
	<li>Um einfach im Terminal die Befehle aufrufen zu können, muss die PATH Variable angepasst werden. Wird die Bash verwendet, kann dies direkt in die Datei <i>~/.bashrc</i> eingetragen werden. Diese Datei befindet sich im Home Verzeichnis des Benutzers.
	<code><pre>$ echo "PATH=$PATH:/opt/android-sdk-linux/tools:\
		/opt/android-sdk-linux/platform-tools" >> ~/.bashrc</pre></code></li>
</ol>

Da in der neuen SDK die Platform-Tools, Beispiele und Dokumentationen nicht mit installiert werden, sollte dies nachgeholt werden. Hierzu wird, via Kommandozeilenbefehl <i>android</i>, der Android SDK Manager<span class="fn"><a href="http://developer.android.com/sdk/adding-components.html">Android SDK Manager</a></span>, gestartet.

<div class="figure" id="android-sdk-manager">
	<img src="http://up.frubar.net/1490/2012-02-22-133432_704x655_scrot.png" width="70%" alt="android-sdk-manager" />
	<p>Bildschirmfoto des Android SDK Manager</p>
</div>

Eines der Werkzeuge in den Android Platform Tools ist <i>adb</i>. Dieses zeigt dem Nutzer eine Liste der per USB Angeschlossenen Android Geräte an. Im Gerät muss hierzu das USB Debugging aktiviert sein.

<code><pre>$ adb devices
List of devices attached
900028b91393      device
</pre></code>

---

### Eclipse

#### Installation

Eclipse bietet die Grafische Oberfläche der Entwicklungsumgebung. Auf der Website werden viele verschiedene Versionen angeboten. Hier ist die Wahl der richtigen Version zu beachten. Da das Paketsystem meist eine alte Version zur Verfügung stellt, sollte diese von der Website<span class="fn"><a href="http://www.eclipse.org/downloads/">Eclipse Website</a></span> heruntergeladen werden. Die Eclipse IDE für Java Entwickler kommt zum Einsatz.

Bei Eclipse handelt es sich ebenso um ein TAR Archiv, welches nach dem entpacken das Programm enthält. Die PATH Variable sollte auch hier wieder erweitert werden.

<code><pre>$ tar xfz eclipse-java-indigo-SR1-linux-gtk-x86_64.tar.gz -C /opt
$ echo "PATH=$PATH:/opt/eclipse" >> ~/.bashrc
</pre></code>

<div class="figure" id="eclipse-screenshot">
	<img src="http://up.frubar.net/1492/2012-02-22-145117_741x600_scrot.png" width="70%" alt="eclipse-screenshot">
	<p>Bildschirmfoto von Eclipse</p>
</div>

#### Android Development Tool (ADT)

Das ADT<span class="fn"><a href="http://developer.android.com/sdk/eclipse-adt.html">Android Development Tool</a></span> ist eine Erweiterung für Eclipse welches die Android Entwicklung erheblich erleichtert. Es bietet unter anderem die Möglichkeit direkt in Eclipse den Android Quelltext zu Debuggen. Das ADT wird in folgenden Schritten installiert.

<ol>
	<li>Über <i>Help -> Install New Software</i> wird über den Button <i>Add</i> die ADT Quelle hinzugefügt.
		<code><pre>https://dl-ssl.google.com/android/eclipse/</pre></code>
	</li>
	<li>Die <i>Developer Tools</i> sind per Check-Box zu wählen. Die Installiert erfolgt durch betätigen des <i>Next</i> Buttons.
		<div class="figure" id="adt-install">
		<img src="http://up.frubar.net/1493/2012-02-22-161557_666x722_scrot.png" width="70%" alt="adt-install">
		<p>Installation von ADT in Eclipse</p>
		</div>
		<br /><br /><br /><br />
	</li>
	<li>Nach erfolgreicher Installation und einem Neustart von Eclipse, muss der Pfad zum Android SDK festgelegt werden. Direkt beim Start wird dieser von einem Wizard abgefragt.
	<div class="figure" id="eclipse-android-sdk-wizard">
		<img src="http://up.frubar.net/1494/2012-02-22-162545_606x494_scrot.png" width="70%" alt="eclipse-android-sdk-wizard">
		<p>Eclipse Wizard für die Android SDK Auswahl</p>
	</div>
	</li>
</ol>
