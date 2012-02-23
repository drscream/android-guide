# Entwicklung

## Übersicht
### Eclipse Projekt
### Emulation

Der Emulator stellt ein vollwertiges Android Betriebssystem für die spezifizierte Version bereit. In Eclipse befindet sich hierzu der Android Virtual Device (AVD) Manager<span class="fn"><a href="http://developer.android.com/guide/developing/devices/managing-avds.html">Android Virtual Device (AVD) Manager</a></span>. AVDs werden mit <span class="figure"><a href="http://www.qemu.org/">Qemu</a></span> virtualisiert und unterstützen viele verschiedene Android Versionen. Im Android SDK Manager können ggf. andere Android Versionen nachinstalliert werden. <a href="#daniel11"><cite>daniel11</cite></a>

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
