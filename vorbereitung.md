# Vorbereitung der Entwicklungsumgebung

## Hardware

Die Entwicklung für Android kann auf verschiedensten Betriebssystemen erfolgen. Die Entwicklungswerkzeuge stehen für Windows, Linux und MacOS X zur Verfügung. Für den Beginn ist auch kein Android Smartphone Vorraussetzung. In der Entwicklungsumgebung (SDK) von Google wird ein Emulator<span class="fn"><a href="http://developer.android.com/guide/developing/tools/emulator.html">Android Emulator</a></span> mitgeliefert.

## Entwicklungsumgebung

Da die Programmierung in Java erfolgt, kann jede beliebige Entwicklungsumgebung oder Editor eingesetzt werden. Eclipse<span class="fn"><a href="http://www.eclipse.org/">Eclipse</a></span> ist  zu Empfehlen, da hierfür Erweiterungen für die Android Programmierung vorhanden sind. 

### Werkzeuge

#### Quellcode
Das Betriebssystem Android basiert komplett auf offenem Quelltext (Open Source). Der Quelltext<span class="fn"><a href="http://source.android.com/">Android Quelltext</a></span> wird als GIT<span class="fn"><a href="http://git-scm.com/">GIT</a></span> Verzeichnis, für alle Zugänglich, angeboten. Der Linux Kernel bietet die Grundlage für das Android Betriebssystem. Durch Ihn werden unter anderem folgende Funktionen abgebildet:

* Speicherverwaltung
* Prozessverwaltung
* Netzwerk
* Treibermodell

Eine gute Übersicht bietet auch die <a href="#android-architektur">Abbildung 1: Android Architektur <a href="#huether10"><cite>huether10</cite></a></a>.

#### Framework

Das Android Application Framework<span class="fn"><a href="http://developer.android.com/resources/faq/framework.html">Android Application Framework</a></span> macht dem Entwickler viele Funktionen einfach nutzbar. Der Entwickler kann diese Bibliotheken nutzen und muss einige Funktionen nicht selbst implementieren.

* Activity Manager
* Telephony Manager
* View System
* Location Manager

Es besteht natürlich weiterhin die Möglichkeit auch auf Ressourcen des Kernsystems zuzugreifen. Hierzu werden vom Android Projekt aber auch viele Ressourcen angeboten. Empfehlenswert ist ein Blick in den Quelltexte.

#### Java

Dank Java ist es nicht erforderlich sich um die Speicherverwaltung zu kümmern. Dies wird direkt von der Java Virtual Machine<span class="fn"><a href="http://java.sun.com/docs/books/jvms/">Java Virtual Machine</a></span> übernommen. Die Grundlagen in Programmiersprache sollten für die Entwicklung bekannt sein. Hierzu bietet Oracle verschiedenste Java Tutorials<span class="fn"><a href="http://docs.oracle.com/javase/tutorial/">Java Tutorials</a></span> an. Ein sehr Ausführliches Kurs Buch, Java ist auch eine Insel<span class="fn"><a href="http://openbook.galileocomputing.de/javainsel/">Java ist auch eine Insel</a></span> wird von Galileo Computing als kostenloses Online Buch angeboten.

### Installation

### Konfiguration

