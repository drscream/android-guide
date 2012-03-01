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
		<hr />
	</li>
	<li>Dem Wizard, bis zur Einstellung für die Anwendungsinformationen folgen. Der Name für den Java Paketnamen ist ein Pflichtfeld. Weitere Informationen zu Java Packages sind im Java Workshop<span class="fn"><a href="http://javaworkshop.sourceforge.net/chapter3.html">Java Workshop, Packages</a></span> zu finden. Mit der SDK Version sollte festgelegt werden welche Android Geräte später unterstützt werden müssen. 
		<div class="figure" id="new-project-wizard-app-info">
			<img src="http://up.frubar.net/1508/2012-02-22-201815_605x557_scrot.png" alt="new-project-wizard-app-info" width="70%" />
			<p>Neues Android Projekt, Anwendungsinformationen festlegen</p>
		</div>		
	</li>
</ol>

---

### Emulation

Der Emulator stellt ein vollwertiges Android Betriebssystem für die spezifizierte Version bereit. In Eclipse befindet sich hierzu der Android Virtual Device (AVD) Manager<span class="fn"><a href="http://developer.android.com/guide/developing/devices/managing-avds.html">Android Virtual Device (AVD) Manager</a></span>. AVDs werden mit Qemu<span class="fn"><a href="http://www.qemu.org/">Qemu</a></span> virtualisiert und unterstützen viele verschiedene Android Versionen. Im Android SDK Manager können andere Android Versionen nachinstalliert werden. <a href="#daniel11"><cite>daniel11</cite></a>

<ol>
	<li>
		In der Menüleiste von Eclipse befindet sich ein Icon des AVD Managers, dieser wird per Klick geöffnet.
		<div class="figure" id="icon-avd">
			<img src="http://up.frubar.net/1505/2012-02-22-201853_1364x668_scrotKopie.png" alt="icon-avd" width="30%" />
			<p>Icon des AVD Managers in Eclipse</p>
		</div>
	</li>
	<li>
		Über den Button <i>New</i> wird ein neues Android Virtual Device erstellt. Im Wizard können die Werte meist auf den Standard Einstellungen belassen werden. Wichtig ist die Auswahl der Android Version (API Level).
		<div class="figure" id="new-avd">
			<img src="http://up.frubar.net/1506/2012-02-22-201935_550x631_scrot.png" alt="new-avd" width="40%" />
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

---

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
		<tr><th width="20%">Verzeichnis</th><th>Ressourcen Typ</th></tr>
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

---

## Benutzeroberfläche

### Views

In Android erfolgt die Gestaltung der grafische Benutzeroberfläche in XML Dateien. Man bezeichnet diese auch als <i>View</i>. Es handelt sich dabei um den sichtbaren Teil einer <i>Activity</i>.

Wird ein neuer GUI Baustein per visual Designer hinzugefügt, ist dieser als <i>View</i> in der XML Datei abgebildet. Sobald ein <i>View</i> per Java angesprochen werde muss, ist eine Typenkovertierung<span class="fn"><a href="http://www.janeg.ca/scjp/oper/cast.html">Java Cast-Operator</a></span> erforderlich.

<div class="listing">
<code><pre>&lt;TextView
	android:layout_width="fill_parent" 
	android:layout_height="wrap_content"
	android:text="@string/hello"
	/&gt;</pre></code>
<p>Beispiel <i>TextView</i></p>
</div>

### Layout

Bei der Erstellung einer Benutzeroberfläche für Android gibt es verschiedene Layout-Verfahren. Es sollte immer das passende Layout für die Anwendung beziehungsweise die Objekte gewählt werden. Diese Liste beinhaltet nur einen Teil der vorhanden Layout-Verfahren.

<table>
	<thead>
		<tr><th>Layout</th><th>Beschreibung</th></tr>
	</thead>
	<tbody>
		<tr><td><i>LinearLayout</i></td><td>Objekte werden in einer Reihe angeordnet.</td></tr>
		<tr><td><i>RelativeLayout</i></td><td>Es kann die Relation zu anderen Objekten definiert werden.</td></tr>
		<tr><td><i>FrameLayout</i></td><td>Wurde entwickelt um den kompletten Bildschirm zu blockieren. Objekte werden im linken oberen Eck angezeigt.</td></tr>
		<tr><td><i>TableLayout</i></td><td>Objekte können in Spalten und Reihen angeordnet werden.</td></tr>
	</tbody>
</table>

### Bilder
#### Bild in das Projekt hinzufügen

Bilder können via <i>Drag & Drop</i> in das Projekt kopiert werden. Die Bilder sollen in die passenden Ordner im Ressource Verzeichnis kopiert werden. 

Sobald sich ein Bild in Eclipse befindet wird dies automatisch vom ADT erkannt. Das ADT generiert daraufhin die Datei <i>R.java</i> im <i>gen</i> Verzeichnis erneut. In dieser Datei befindet sich nun die Ressource ID für das kopierte Bild.

<div class="listing">
<code><pre>public final class R {
	public static final class drawable {
		public static final int ic_launcher=0x7f020000;
		public static final int tm=0x7f020001;
	}
}</pre></code>
	<p>Auszug aus der generierten <i>R.java</i> Datei</p>
</div>

#### Bild in das Layout einbinden

Das Bild sollte nun in das Layout eingebunden werden. Dies kann entweder über den Eclipse visual Designer geschehen oder durch die Bearbeitung der <i>main.xml</i> Datei im <i>res/layout</i> Verzeichnis.

Als Beispiel wurde eine Datei <i>test.jpg</i> in das Verzeichnis <i>res/drawable-mdpi</i> kopiert. Diese wird in einer <i>main.xml</i> Datei wie folgt angegeben.

<div class="listing">
	<code><pre>&lt;?xml version="1.0" encoding="utf-8"?&gt;
		&lt;LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
			android:orientation="vertical"
			android:layout_width="fill_parent" 
			android:layout_height="fill_parent" &gt;
		&lt;ImageView
			android:id="@+id/test_icon"
			android:layout_width="wrap_content"
			android:layout_height="wrap_content"
			android:layout_gravity="center_horizontal"
			android:src="@drawable/test" /&gt;
		&lt;/LinearLayout&gt;
</pre></code>
<p>Beispiel <i>main.xml</i> Datei mit Verweis auf eine Bilddatei</p>
</div>

---

Ein <i>ImageView</i> beinhaltet unter anderem diese Parameter:

* <i>android:id="@+id/test_icon"</i>: Eine eindeutige ID für die GUI.
* <i>android:layout_gravity="center_horizontal"</i>: Einstellung für die Ausrichtung des Bildes. Details zum <i>LinearLayout</i> ist in der Android Dokumentation<span class="fn"><a href="http://developer.android.com/reference/android/widget/LinearLayout.LayoutParams.html">Android Dokumentation, LinearLayout.LayoutParams</a></span> zu finden.
* <i>android:src="@drawable/test"</i>: Der Parameter ist ein direkter Verweis auf das Bild. Der Verweis erfolgt durch das <i>@</i> Symbol. Die Ressource ID befindet sich in der <i>R.java</i> Datei.
	
### Visual Designer

Eclipse bietet einen Designer an um die Oberfläche für Android zu gestalten. Dieser bietet jedoch nicht den vollen Umfang, wie das bearbeiten der XML Datei.

Um den Designer zu verwenden, muss im <i>res/layout</i> Verzeichnis die gewünschte XML Datei per Doppelklick ausgewählt werden. Mit einem Tab <i>Graphical Layout</i> kann zwischen Designer und XML Datei umgeschaltet werden.

<div class="figure" id="visual-designer">
	<img src="http://up.frubar.net/1522/2012-02-24-154728_1366x746_scrot.png" alt="visual-designer" width="70%" />
	<p>Bildschirmfoto des Visual Designers</p>
</div>

Der Designer ist sehr intuitiv zu bedienen, ist aber nur für einfache grafische Anwendungen geeignet. Die Einstellungen für die einzelnen Elemente sind abhängig vom Layout. Befindet sich ein <i>TextView</i> auf einem <i>LinearLayout</i>, hat dies andere Einstellungen als auf einem <i>RelativeLayout</i>.



## Anwendungsfunktionen
### Aktivitäten (Activity)

<i>Activities</i> bilden die Nutzerfunktionen ab, dies bedeutet es sind Interaktionen mit dem Benutzer. Als Beispiel bietet eine <i>Activity</i> die Liste von Menüpunkten an und reagiert auf das drücken eines Buttons. Diese Aktivitäten sind ein wichtiger Bestandteil der Android Entwicklung und werden für jede Anwendung benötigt. Durch die Interaktion mit dem Benutzer, erstellt die <i>Activity</i> Klasse auch die Fenster.

Fast jede Aktivität besteht aus folgenden Methoden:

* <i>onCreate()</i>: Initialisierung der Aktivität. In der Methode wird festgelegt welches Layout verwendet wird.
* <i>onPause()</i>: Wird verwendet, wenn der Benutzer die Anwendung verlässt. An dieser Stelle sollten die Benutzerdaten gespeichert werden.

Eine <i>Activity</i> wird in einem <i>Activity Stack</i> verwaltet. Dies bedeutet, sobald eine neue <i>Activity</i> hinzukommt wird diese auf dem <i>Stack</i> abgelegt.

<div class="figure" id="activity">
	<img src="http://up.frubar.net/1524/Beginners_Workshop_Activity.png" alt="activity" width="70%" />
	<p>Zusammenspiel <i>Activity</i> und <i>View</i></p>
</div>

#### Lebenszyklus einer Aktivität

<div class="figure" id="activity-lfe-cycle">
	<img src="http://up.frubar.net/1519/Beginners_Workshop_Activity_LC.png" alt="activity-lfe-cycle" width="70%" />
	<p>Lebenszyklus einer Aktivität (Activity) <cite><a href="#woltmann20">woltmann20</a></cite></p>
</div>

---

#### Erstellung der ersten <i>Activity</i>

Nachdem das Projekt per Wizard erstellt wurde, existiert schon die erste <i>Activity</i>. Diese befindet sich in der <i>ProjektnameActivity.java</i> Datei. Wie in der <a href="#activity-lfe-cycle">Abbildung zum Lebenszyklus</a> zu sehen ist, startet jede Aktivität mit der <i>onCreate()</i> Methode.

<div class="listing" id="example-activity">
<code><pre>public class NastyActivity extends Activity {
    /** Called when the activity is first created. */
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main);
    }
}</pre></code>
<p>Beispiel Activity, erstellt vom Wizard</p>
</div>

Die Basisklasse wird über die folgende Zeile geladen. Sie ist zwingend erforderlich, dass das Programm ausgeführt werden kann.

<div class="listing" id="activity-onCreate">
<code><pre>super.onCreate(savedInstanceState);</pre></code>
<p>Aufruf der <i>Activity</i>-Basisklasse</p>
</div>

Standardmäßig hat die <i>Activity</i> kein Kenntnis von der Grafische Bedienoberflächen. Als Entwickler ist es somit nötig die Verbindung zwischen beiden herzustellen. Um die Bedienoberfläche anzeigen zu lassen, ist folgender Quelltext nötig. Bei <i>R.layout.main</i> handelt es sich um die <i>main.xml</i> Datei im Layout Ressourcen Verzeichnis.

<div class="listing" id="activity-show-content">
<code><pre>setContentView(R.layout.main);</pre></code>
<p>Anzeige der Bedienoberfläche über die <i>Activity</i></p>
</div>

---

### Benutzereingabe

Um auf Benutzereingaben reagieren zu können, ist ein <i>Event Listener</i> und <i>Event Handler</i> nötigt.

Als Beispiel für die Tastatur Eingabe, wird die Methode <i>onKeyDown()</i> überschrieben. Diese wird bei jedem Tastendruck aufgerufen und kann somit Aufgaben abfangen und reagieren.

<div class="listing" id="onKeyDown-methode">
<code><pre>@Override
public boolean onKeyDown(int keyCode, KeyEvent event) {
	// TODO Auto-generated method stub 
	return super.onKeyDown(keyCode, event);
}</pre></code>
<p><i>onKeyDown()</i> Methode</p>
</div>

Dieses Beispiel kann auch bei Touch Eingaben angewandt werden. Unter Android wird jede Betätigung des Bildschirms als Eingabe Event verarbeitet.

### Event Handler

Wie in der vorherigen Sektion angesprochen, werden <i>Event Handler</i> benötigt um auf Eingaben reagieren zu können. Der unten gezeigte Quelltext reagiert beim betätigen aller Buttons in der grafischen Bedienoberfläche.

<div class="listing" id="onCreate-toggleButton">
<code><pre>@Override
public void onCreate(Bundle savedInstanceState) {
	super.onCreate(savedInstanceState); 
	setContentView(R.layout.main);
	
	Button toggleButton = (Button)findViewById(R.id.toggleButton); 
	toggleButton.setOnClickListener(new View.OnClickListener() {
		// [...]
		
		public void onClick(View v) {
			// [...]
		} 
	});
	
}</pre></code>
<p>Beispiel Klasse mit Button Listener und Event</p>
</div>

Die Methode <i>findViewById()</i> wird verwendet um Objekte in der aktuellen Benutzeroberfläche zu finden. Die Methode liefert <i>View</i> Klasse zurück, daher muss diese in ein Button-Objekt umgewandelt werden. 

Der Quelltext um auf das Event zu reagieren ist in die <i>Listener</i> Methode eingebettet. Da dies bei mehr Quelltext zu unübersichtlich werden kann, ist Empfohlen die <i>Listener</i> Methoden auszulagern. Hierzu wird um unten genannten Beispiel, eine Private <i>setButtonClickListener()</i> Methode erstellt, die in der <i>onCreate</i> Methode aufgerufen wird.

<div class="listing" id="onCreate-toggleButton">
<code><pre>public class NastyActivity extends Activity {
	/** Called when the activity is first created. */
	@Override
	public void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState); 
		setContentView(R.layout.main);
		
		setButtonClickListener();
	}
	
	private void setButtonClickListener() {
		Button toggleButton = (Button)findViewById(R.id.toggleButton);
		toggleButton.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				// TODO Auto-generated method stub
			}
		});
	}
}</pre></code>
<p>Ausgliederung des Event Listeners in eine eigene Methode</p>
</div>
