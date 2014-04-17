---
layout: post
title: "[Updated] Ubuntu Saucy Installieren"
description: "So aktualisiert ihr euer Ubuntu auf die neuste Version."
modified: 2014-04-17
category: articles
tags: [saucy, ubuntu, release, upgrade, update, new]
---
**Update 17.04.2014:** Anleitung gilt auch für Ubuntu 14.04 LTS.
<br><br>
**Nach der Veröffentlichung von Ubuntu 13.10 Saucy Salamander am heutigen Tage ist es empfehlenswert das Update schnellstmöglich einzuspielen. Hier zeige ich euch, wie ihr vorgehen müsst.**

Das Update ist natürlich nicht nur aus dem Aspekt der neuen Funktionen interessant, Ubuntu-Veröffentlichungen bringen auch neue Programmversionen mit sich, die einerseits die Stabiliät des Systems verbessert, andererseits die Leisung des Computers teilweise vielleicht auch besser ausnutzen kann (Stichwort: 32-bit / 64-bit).
Um das Update nun einzuspielen gibt es mehrere Lösungsansätze unter Ubuntu. Solltet ihr euer Ubuntu via SSH oder Terminal aktualisieren wollen, so könnt ihr den Befehl `sudo do-release-upgrade` nutzen. Das Programm führt euch durch den kompletten Aktualisierungsprozess.

Eine einfachere - und vielleicht auch bequemere Lösung - ist die Aktualisierung über die Software-Aktualisierung. Sucht nach diesem Programm einfach über das Dashboard und öffnet es. Je nach Konfiguration zeigt euch das Programm das Update via Pop-Up an, ansonsten wird im Programmfenster ein Knopf für die Distributionsaktualisierung angeboten. Sollte beides nicht der Fall sein, könnt ihr das Update auch via `sudo update-manager -d` (Kommando im Terminal ausführen) starten.
