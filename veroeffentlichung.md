# Veröffentlichung im Android Markt

Der Android Markt ist die offizielle Möglichkeit um Anwendungen für Endbenutzer anzubieten. Um viele potentielle Kunden ansprechen zu können ist die Verwendung des Marktes hilfreich. Er bietet Kunden die Möglichkeit Ihre Anwendung zu bewerten, kommentieren und weitere Informationen dazu einzuholen. Entwicklern bietet der Markt statistische Auswertungen der Download und Benutzerzahlen.

<div class="figure" id="android-market">
	<img src="http://up.frubar.net/1499/2012-02-22-215001_1042x724_scrot.png" alt="android-market" width="70%" />
	<p>Bildschirmfoto des Android Markt</p>
</div>

## APK Datei erstellen

Das Android Projekt wird in eine so genannte Android Paket Datei (APK) gespeichert. Diese Datei muss zwingend durch einen Public/Private-Key-Verfahren signiert werden. Den Privaten Schlüssel behält immer der Entwickler, während der öffentliche Schlüssel den Konsumenten zur Überprüfung zur Verfügung steht.

Die APK Datei kann auf mehrere verschiedene Arten erstellt werden, zum Beispiel per Kommandozeile via <i>ant</i> oder per Continuous Integration Lösung Jenkins. Das Android Development Tool für Eclipse bietet diese Möglichkeit aber auch.

<ol>
	<li>Mit einem Rechtsklick auf das Projekt öffnet sich das Kontextmenü. In diesem wird unter <i>Android Tools</i> der Menüpunkt <i>Export Signed Application Package</i> ausgewählt. Ein Wizard führt durch die einzelnen Optionen.
		<div class="figure" id="export-signed-application-package">
			<img src="http://up.frubar.net/1495/2012-02-22-202908_1366x768_scrot.png" alt="Export Signed Application Package" width="70%"/>
			<p>Kontextmenü für Export Signed Application Package</p>
		</div>
	</li>
	<li>Sollte noch kein Schlüsselpaar vorhanden sein, wird an dieser Stelle der Pfad und ein Passwort zur Entschlüsselung festgelegt.
		<div class="figure" id="apk-sign-folder">
			<img src="http://up.frubar.net/1496/2012-02-22-203014_605x507_scrot.png" alt="apk-sign-folder" width="70%">
			<p>APK Erstellung, Festlegung des Schlüssel Verzeichnisses</p>
		</div>
	</li>
	<li>Die Schlüsselerstellung erscheint nur, falls noch kein Schlüsselpaar vorhanden ist. In diesem Dialog werden die Schlüsselinformationen festgelegt. Die Informationen des Herausgebers sind Pflichtangaben. <br /> Achtung das Ablaufdatum der Lizenz muss nach dem 22. Oktober 2033 sein. Sonst ist es nicht Möglich die Anwendung im Android Markt zu veröffentlichen. 
		<div class="figure" id="apk-sign">
			<img src="http://up.frubar.net/1497/2012-02-22-203130_605x507_scrot.png" alt="apk-sign" width="70%">
			<p>APK Erstellung, Schlüsselerstellung</p>
		</div>
	</li>
	<li>Im Heimatverzeichnis des Benutzers befindet sich nun eine <i>.apk</i>-Datei.
		<div class="figure" id="apk-file">
			<img src="http://up.frubar.net/1498/2012-02-22-211704_753x251_scrot.png" alt="apk-file" width="70%"/>
			<p>APK Erstellung, Anzeige des Zielverzeichnisses mit APK Datei</p>
		</div>
	</li>
</ol>

## Andorid Markt

https://market.android.com/publish