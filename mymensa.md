---
layout: page
status: publish
published: true
title: MyMensa
permalink: mymensa/
author:
  display_name: Tom
  login: tom
  email: tom@quist.de
  url: ''
author_login: tom
author_email: tom@quist.de
wordpress_id: 25
wordpress_url: http://quist.de/
date: '2011-02-05 12:45:28 +0100'
date_gmt: '2011-02-05 11:45:28 +0100'
categories: []
tags:
- android
- MyMensa
- Mensa-App
- Studenten-App
- Speiseplan
- Mensaplan
- Kantine
- Essen
- Speisen
- Student
- Studium
- Hunger
- Mensa
- Cafeteria
- Cafe
- Kaffee
- Mahlzeit
- Studieren

screenshots:
- mymensa1.jpeg
- mymensa2.jpeg
- mymensa3.jpeg
- mymensa4.jpeg
- mymensa5.jpeg
---
MyMensa ist die erste und Community Mensa-App im [App Store](https://itunes.apple.com/de/app/mymensa-mensa-speiseplan/id498868290) und im [Android Play Store](https://play.google.com/store/apps/details?id=de.quist.app.mymensa), bei der du Mahlzeiten aus dem Speiseplan deiner Mensa bewerten, kommentieren und fotografieren kannst. Schau dir auf Fotos anderer Benutzer oder deiner Mensa an wie die Mahlzeiten aussehen und wie es anderen geschmeckt hat, noch vor deinem Mensa-Besuch. MyMensa kann auch offline genutzt werden, sobald der Speiseplan ein mal heruntergeladen wurde. Die Android Pro-Version enthält außerdem zusätzlich ein Widget für den Homescreen.  
<iframe src="http://www.facebook.com/plugins/likebox.php?href=http%3A%2F%2Fwww.facebook.com%2Fpages%2FMyMensa%2F119294151461718&amp;width=292&amp;colorscheme=light&amp;show_faces=false&amp;stream=false&amp;header=true&amp;height=62" scrolling="no" frameborder="0" style="border:none; overflow:hidden; width:292px; height:62px;" allowtransparency="true"></iframe>

**Features im Überblick:**

*   Mensaplan vieler deutscher Mensen, teilweise mit **Fotos** der Speisen
*   Speiseplan-Vorschau der nächsten Tage
*   Nutze MyMensa auch **offline**
*   Wähle deine Mensa über eine Google-Maps Karte
*   Widget (nur in der Pro-Version)
*   **Fotografiere** und schau dir die **Fotos** anderer Benutzer an
*   Bewerte Mahlzeiten und erleichtere anderen damit die Qual der Wahl
*   Füge **Kommentare** zu deiner Bewertung hinzu
*   Filter die Mensa-Liste, so dass nur noch deine Mensen zur Auswahl stehen

Eine Liste der unterstützten Mensen findest du hier: [http://mymensa.eu/mensa-list](http://mymensa.eu/mensa-list)

{% for screen in page.screenshots %}<img src="{{ screen | prepend: '/assets/' | prepend: site.baseurl | replace: '//', '/' }}" alt="MyMensa" style="display: inline-block; margin: 5px; border: 1px solid black;"/>{% endfor %}

{% include disqus-comments.html %}