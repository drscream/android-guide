# Veröffentlichung im Android Market

Der Android Market ist die offizielle Möglichkeit um Anwendungen für Endbenutzer anzubieten. Um viele potentielle Kunden ansprechen zu können ist die Verwendung des Marktes hilfreich. Er bietet Kunden die Möglichkeit Ihre Anwendung zu bewerten, kommentieren und weitere Informationen dazu einzuholen. Entwicklern bietet der Markt statistische Auswertungen der Download- und Benutzerzahlen.

<div class="figure" id="android-market">
	<img src="http://up.frubar.net/1499/2012-02-22-215001_1042x724_scrot.png" alt="android-market" width="70%" />
	<p>Bildschirmfoto des Android Market</p>
</div>

## APK Datei erstellen

Das Android Projekt wird in eine so genannte Android Paket Datei (APK) gespeichert. Diese Datei muss zwingend durch einen Public/Private-Key-Verfahren signiert werden. Den Privaten Schlüssel behält immer der Entwickler, während der öffentliche Schlüssel dem Konsumenten zur Überprüfung zur Verfügung steht.

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
	<li>Die Schlüsselerstellung erscheint nur, falls noch kein Schlüsselpaar vorhanden ist. In diesem Dialog werden die Schlüsselinformationen festgelegt. Die Informationen des Herausgebers sind Pflichtangaben. <br /> Achtung das Ablaufdatum der Lizenz muss nach dem 22. Oktober 2033 sein. Sonst ist es nicht Möglich die Anwendung im Android Market zu veröffentlichen. 
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

## Andorid Market

Nachdem die APK Datei erstell wurde, kann diese im Android Market veröffentlicht werden. Ein Google Konto ist Voraussetzung zur Anbietung von Android Anwendungen, dieses kann unter der <span class="fn"><a href="http://www.google.com/accounts">Google Account Verwaltung</a></span> kostenlos erstellt werden.

Zu beachten ist, dass eine einmalige Entwicklungsgebühr von 25 US-Dollar fällig wird um eine Anwendung im Android Market zu veröffentlichen. 

<ol>
	<li>
		Die Veröffentlichung erfolgt über die <span class="fn"><a href="http://market.android.com/publish">Publish-Funktion</a></span> der Internetseite des Android Market. Eine Anmeldung per Google Benutzer ist nötig. Die Telefonnummer ist eine Pflichtangabe zur Verifizierung des Benutzerzugangs.
		<div class="figure" id="android-market-signin">
			<img src="http://up.frubar.net/1503/2012-02-22-213713_1036x680_scrot.png" width="70%" alt="android-market-signin" />
			<p>Erstellung eines Entwicklerzugang im Android Market</p>
		</div>
	</li>
	<li>Im nächsten Schritt muss die einmalige Zahlung von 25 US-Dollar erfolgen. Dies geschieht einfach via Kreditkarte oder Google Checkout.</li>
	<li>
		In einer einfachen Webmaske kann die APK-Datei, Screenshots, etc. hochgeladen werden. Es sollte eine ausführliche Beschreibung der Anwendung existieren, damit Kunden diese auch finden können.
		<div class="figure" id="android-market-upload">
			<img src="http://up.frubar.net/1504/2012-02-22-214807_1030x680_scrot.png" width="70%" alt="android-market-upload" />
			<p>Veröffentlichung der Android Anwendung</p>
		</div>
	</li>
</ol>