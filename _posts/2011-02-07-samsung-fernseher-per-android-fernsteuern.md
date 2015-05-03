---
layout: post
status: publish
published: true
redirect_from:
- /2011/02/samsung-fernseher-per-android-fernsteuern/
title: SamyGo Remote - Android als Samsung Fernbedienung
author:
  display_name: Tom
  login: tom
  email: tom@quist.de
  url: ''
author_login: tom
author_email: tom@quist.de
wordpress_id: 116
wordpress_url: http://quist.de/?p=116
date: '2011-02-07 16:13:06 +0100'
date_gmt: '2011-02-07 15:13:06 +0100'
categories:
- Android
- SamyGo-Remote
tags:
- fernbedienung
- fernseher
- market
- remote lan control
- samsung
- samygo
- tv
- android
screenshots:
- screenshot3.png
- screenshot5.png
- screenshot4.png
---
![qrcode](http://qrcode.kaywa.com/img.php?s=3&d=https%3a%2f%2fplay.google.com%2fstore%2fapps%2fdetails%3fid%3dde.quist.app.samyGoRemote)

Dank des [SamyGo Projektes](http://samygo.tv/) wurde mein gewöhnlicher Fernseher [Samsung LE37B650](http://www.samsung.de/de/Privatkunden/TVHeimkino/Fernseher/LCDTV/le37b650/LE37B650T2PXZG/detail.aspx) zum High-Tech Gerät. Da er einen Netzwerkanschluss besitzt und von Werk aus Linux darauf läuft, kann man damit einige [Dinge](http://wiki.samygo.tv/index.php5/Content_Library_applications_list) anstellen. So kann man sich zum Beispiel einen Server installieren der Fernbedienungs-Signale auch per LAN annimmt. Dafür installiert man sich beispielsweise über die Content-Library die Anwendung "[Remote Lan Control](http://wiki.samygo.tv/index.php5/Content_Library_applications_list#Remote_LAN_Control)". Wie das geht, wird unten erklärt. Für C-Serie und D-Serie Geräte ist das nicht einmal notwendig, diese haben einen entsprechenden Server von Haus aus installiert.

Da es für die B-Serie momentan nur einen [Client für Windows](http://wiki.samygo.tv/index.php5/Desktop_applications_list#Remote_LAN_Control) gibt und der Android Client für die C-Serie und D-Serie nur auf Samsung Geräten läuft, habe ich einen Android-Client geschrieben. Das Ergebnis sieht folgendermaßen aus und kann ab sofort im [Android Play Store heruntergeladen](https://play.google.com/store/apps/details?id=de.quist.app.samyGoRemote) werden.

{% for screen in page.screenshots %}<img src="{{ screen | prepend: '/assets/' | prepend: site.baseurl | replace: '//', '/' }}" alt="MyMensa" style="display: inline-block; margin: 5px; border: 1px solid black;"/>{% endfor %}

Die App funktioniert nur zusammen mit B-Series Fernsehern (**Edit**: _Jetzt auch für C-Serie und D-Serie Fernseher, ohne "Remote Lan Control"_) von Samsung, da "Remote Lan Control" momentan nur auf diesen Geräten läuft. Für C-Series Geräte gibt es zwar schon eine Ferbedienungs-App von Samsung, die läuft aber auch nur auf Samsung-Geräten. C-Series Geräte unterstützen deshalb schon von Haus aus das Empfangen von Fernbedienungs-Signalen über das Netzwerk (mittels UPnP), <del>aber ich hab keine Ahnung wie ich das genau ansteuere. Falls jemand ein C-Series Gerät besitzt und interesse daran hat, dass die App auch mit diesen Fernsehern läuft, könnte z.B. mit dem [UPnP Inspector](http://coherence.beebits.net/wiki/UPnP-Inspector) versuchen mehr herauszufinden.</del>

***C-Serie Geräte werden jetzt auch unterstützt, und zwar ohne jegliche Modifikation des Fernsehers. Falls du trotzdem eine Anleitung brauchst, dann siehe unten!***

### Anleitung für B-Serie:

Da die [SamyGo Seiten](http://samygo.tv/) momentan etwas unübersichtlich sind, erkläre ich hier noch mal wie man "Remote Lan Control" auf seinem TV laufen lässt. Das Verfahren ist normalerweise relativ sicher, da nach einem Neustart alles wieder beim Alten sein sollte, aber ich übernehme keine Haftung für irgendwelche Schäden die dadurch entstehen.

1.  "Remote Lan Control" herunterladen: [hier](http://download.samygo.tv/B%20Series/Content%20Library%20Applications/Remote%20LAN%20Control%20%28v0.1%29.zip)
2.  Zip-Datei entpacken und auf einen USB-Stick kopieren (USB-Stick sollte in FAT32 formatiert sein)
3.  USB-Stick in den Fernseher einstecken
    *   Wenn der Fernseher an ist, sollte jetzt nach einiger Zeit ein Fenster auftauchen, dort "Content Library" auswählen
    *   Wenn der Fernseher nicht an war oder kein Fenster auftaucht, kann man auch manuell in die Content Library gehen (Knopf "CONTENT" auf der Fernbedienung und dann das Symbol ganz rechts auswählen)
4.  Jetzt links "USB" auswählen und dann auf Spiele (bzw. Games) gehen: ENTER
    *   Falls es keinen Eintrag für "Spiele" gibt, kann man versuchen den Eintrag zu erstellen (Telnet muss dafür laufen). Wie das geht steht [hier](http://wiki.samygo.tv/index.php5/Enable_GAME_menu_option_at_Plasma_series).
5.  Jetzt sollte eine Liste der auf dem USB-Stick verfügbaren Programme auftauchen. Dort "SamyGO Remote" auswählen und ENTER drücken. Dann kann man das Programm laufen lassen. Wenn man will, kann man es auch auf den internen Speicher des Fernsehers kopieren und von dort aus Starten, dann braucht man zukünftig keinen USB-Stick mehr eingesteckt zu haben
    *   Falls jetzt eine Meldung "Nicht Verfügbar" kommt, dann bedeutet dass, dass du eine zu neue Firmware installiert hast. Das letzte Firmware-Update von Samsung hat solche Modifikationen unmöglich gemacht. Damit diese wieder möglich werden, musst du die Firmware downgraden. Wie das geht, steht [hier](http://forum.samygo.tv/viewtopic.php?f=5&t=2038).
6.  Es kommt KEINE Rückmeldung, dass das Programm gestartet wurde, aber es sollte nun gestartet sein
7.  Jetzt noch in der App die IP-Adresse konfigurieren. Die kann man über den Button "Automatisch finden" herausfinden. Falls der Fernseher nicht gefunden wird, ist man entweder nicht mit dem WLAN verbunden, das WLAN ist falsch konfiguriert oder der Fernseher wird nicht unterstützt.

**Kleiner Wermutstropfen:** Das Programm muss bei jedem Neustart des Fernsehers erneut ausgeführt werden. Momentan gibt es noch keine ganz einfache Lösung für das Problem. Die einzige Lösung ist, die Firmware zu modifizieren, die Modifikation auf den Fernseher aufzuspielen und dann mittels gdb (gdbtrick.sh) oder injectso die Applikation im Start-Script starten. Das ist aber nur für fortgeschrittene Benutzer etwas. Vielleicht erkläre ich das irgendwann mal in einem separaten Post. Mehr Informationen gibt's auch [hier](http://wiki.samygo.tv/index.php5/SamyGO_for_DUMMIES#Using_a_SamyGO_app).

### Anleitung für C-Serie und D-Serie:

1.  Fernseher anschalten
2.  Damit die Fernbedienung funktioniert, muss vorher im Menü erst das Empfangen von Remote-Control Signalen über das Netzwerk aktiviert werden. Der entsprechende Menüpunkt befindet sich in den Systemeinstellungen. Falls es so einen Menüpunkt nicht gibt, wird der Fernseher leider nicht unterstützt.
3.  Handy per WLAN mit dem selben Netzwerk wie den Fernseher verbinden
4.  SamyGo Remote starten
5.  Menü -> Einstellungen -> Hostname -> Automatisch finden (Achtung, damit das automatische Finden funktioniert, muss der Fernseher in der selben Broadcast-Domäne wie das Handy sein. Manche Router wie die Fritz!Box haben eine Einstellung, die verhindert, dass Broadcast Pakete weitergeleitet werden. Bei der Fritz!Box muss man im Menüpunkt "Funkeinstellungen" das Häkchen bei "WLAN-Netzwerkgeräte dürfen untereinander kommunizieren" setzen)
6.  Falls ein Gerät gefunden wurde, ist dies an eine Vibration zu spüren. Der entsprechende TV-Typ wird automatisch eingestellt. Falls ihr ein C- oder D-Serie Gerät besitzt, es wurde jedoch B-Serie als Typ eingestellt, dann wird euer Fernseher nicht unterstützt.
7.  Falls kein Gerät gefunden wurde, könnt ihr noch versuchen die IP-Adresse des Fernsehers manuell herauszubekommen und in das Feld einzutragen.
8.  Jetzt müsste die Fernbedienung funktionieren