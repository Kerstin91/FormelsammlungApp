How to build an App - Tutorial
===============================

(Die ganzen Informationen findet ihr auch unter: http://cordova.apache.org/docs/en/2.9.0/guide_
getting-started_android_index.md.html#Android%20Platform%20Guide)

Eine eigene App zu gestalten hört sich im ersten Moment sehr gewaltig und aufwendig an. Doch die Formelsammlung als 
App wurde lediglich mit der Strukturierungssprache HTML und der Gestaltungsumgebung CSS entwickelt. Bei der 
Entwicklungen der App waren keine besonderen Kenntnisse der Programmierung vorhanden. Aber durch die im
Internet zur Verfügung stehende Selfhtml-Webseite kann auf relativ einfache Weise eine eigene Webseite gestaltet 
werden. Explizite Beschreibungen und Beispielcodes können durchgelesen und angeschaut werden. Der folgende Link 
verweist auf die Selfhtml-Webseite: http://de.selfhtml.org/.

Damit LehrerInnen ihre Zeit nicht mit der Gestaltung der App verbringen, wird
der Code als Open-Source-Produkt bereitgestellt. Am Ende dieses Tutorials soll folgendes eingerichtet sein und 
kreiert werden:
* Die Entwicklungsumgebung Cordova
* Die erste produzierte App
* Die App auf dem Smartphone testen

Downloads:
----------
Für die Entwicklung einer App habe ich folgende folgende Pakete benötigt, die unter den entsprechenden Links oder 
durch Befehle im Terminal heruntergeladen beziehungsweise installiert werden können:
* Das Android SDK, das unter folgenden Link runtergeladen werden kann:
  http://developer.android.com/sdk/index.html
* JAVA wird durch den Terminal installiert: `sudo apt-get install openjdk-7-jdk`
* Cordova wird durch den Terminal installiert: `sudo npm install -g cordova`
* ANT wird über `sudo apt-get install ant` installiert

Wichtig hierbei ist, dass das Verzeichnnis, in der das SDK gespeichert wurden, auffindbar ist. Da die Android 
SDK-Datei als ZIP-Datei runtergeladen wird, muss diese noch entpackt werden. Der Inhalt dieser Datei besteht aus 
dem Programm Eclipse und dem SDK.
Nun wurden alle Pakete, die für die Entwicklung einer App benötigt werden, installiert und können verwendet werden.

Vorbereitungen:
---------------
Durch das Tool Cordova können neue Projekte auf verschiedenen Platformen gebaut werden. In diesem Fall ist es die
Android-Platform auf dem die App produziert wird. Bevor jedoch mit Cordova gearbeitet werden kann, müssen die 
SDK-tools und -platform-tools in eine PATH-Umgebung eingebunden werden. Dies geschieht mit folgendem Befehl, der 
in den Terminal eingegeben werden muss:

`export PATH=/<Hier muss das Verzeichnis angegeben werden, in dem sich die SDK-platform-tools  befinden>/adt-bundle-linux-x86-2013103/sdk/platform-tools:ZAn dieser Stelle muss wieder das Verzeichnis  angegeben werden, in dem sich die SDK-tools befinden>:$PATH$`

Danach muss JAVA und ANT noch in die PATH-Umgebung hinzugefügt werden: 
`export PATH=$JAVA_HOME/bin:$ANT_HOME/bin:$PATH`

Es empfiehlt sich die PATH-Umgebungen zu speichern, damit diese nicht bei jedem Neustart des Terminals eingegeben 
werden müssen.

Der Debbuging-Modus:
-------------------
Der letzte Schritt, bevor Cordova verwendet werden kann, ist den Debugging-Modus auf dem Smartphone zu aktivieren. 
Dieser wird benötigt, um die App auf dem Smartphone testen zu können. Das geht bei Android 4.2.2 wie folgt: 
Das siebenmalige Touchen auf die "Build-Nummer", das unter Einstellungen und weiter bei "Über das Telefon" am 
unteren Ende zufinden ist, aktiviert die Entwicklerfunktionen.

Cordova - Die App erstellen:
--------------------------
Folgender Befehl erzeugt die App:

         cordova create app com.formelsammlung.app Formelsammlung

Es empfiehlt sich, den Terminal in dem Verzeichnis zu  öffnen, in dem die App später einmal verwaltet werden soll. 
Das erste Argument "app" wird der Name des von Cordova erzeugten Ordners heißen und enthält das Unterverzeichnis WWW, 
in dem die eigentliche Entwicklung stattfindet. com.formelsammlung.app und Formelsammlung können beliebig gewählt 
werden. Das letzte Argument Formelsammlung gibt der App ihren Namen.

Die Android-Platform erzeugen:
Die Erzeugung der Android-Platform muss nun im selben Verzeichnis stattfinden. Daher müssen die nachfolgenden Befehle 
alle in diesem Bereich ausgeführt werden: `cd app`.

Wichtig bei dem nächsten Schritt ist, dass das SDK von dem Rechner unterstützt wird und bereits installiert wurde, 
sonst kann die Platform nicht erstellt werden: `cordova add android platform`

Dies kann einige Minuten in Anspruch nehmen. Durch die Benachrichtigung im Terminal "platform build successfully", 
kann die App auf dem Smartphone gebaut werden.

Eine App bauen:
---------------
Cordova erzeugt durch die im WWW-Ordner enthaltene index.html-Datei ein Standardprojekt, was nun getestet werden kann. 
Um das Projekt zu bauen wird folgender Befehl in den Terminal eingegeben: `cordova build`

Hierbei ist wichtig, dass der Debugging-Modus in der Entwickleroption aktiviert ist, sonst kann das Projekt auf dem 
Smartphone nicht gebaut und getestet werden.
Wenn dieser Befehl erfolgreich ausgeführt wurde, folgt nun der letzte Schritt: Cordova soll auf Android laufen und 
zur Vefügung stehen. Dies wird mit folgendem Befehl ausgeführt: `cordova run android`

Jetzt können die zur Verfügung gestellten Daten von eingefügt werden. Natürlich kann sie für den individuellen Einsatz 
im Unterricht beliebig verändert werden. Dabei ist der Kreativität keine Grenzen gesetzt.

Viel Spaß damit und ich hoffe, dass ich ein wenig helfen konnte.
Für Verbesserungsvorschläge wäre ich sehr dankbar:), zum Beispiel in dem Sie
dieses Repository "forken" und dann ein Pull-request formulieren.

