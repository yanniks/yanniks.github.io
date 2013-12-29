---
layout: post
title: "Neuer Cydia-Tweak: Mobile Substrate Fix für iOS 7"
description: "Startet Mobile Substrate automatisch beim Booten in iOS 7."
category: articles
tags: [cydia, source, quelle, jailbreak, repo, repository, ios7, ios, mobilesubstrate, fix, mobile, substrate]
---

##### Mobile Substrate ist einer der beliebtesten Cydia-Tweaks, die es gibt, nicht zuletzt, weil viele andere Erweiterungen auf diesem Programm aufbauen - leider ist funktioniert Mobile Substrate unter iOS 7 noch nicht so wie es eigentlich sollte.

Die Freude war groß, als der Jailbreak für iOS 7 von den @evad3rs verkündet wurde. Nach 3 Monaten war es endlich möglich, Apples neues, mobiles Betriebssystem iOS 7 von seinen Fesseln zu befreien. Leider legte sich die Freude, als bekannt wurde, dass der Jailbreak mit einigen Problemen verbunden ist.

Da war zum einen die chinesische Cydia-Alternative TaiG, die sich beim "jailbreaken" chinesischen Geräten installierte und dem Nutzer gleich die Gelegenheit gab, sogenannte gecrackte Apps zu installieren. Außerdem lies @saurik (Jay Freeman) verlauten, dass er nichts von dem Jailbreak wusste und Cydia dementsprechend nicht für iOS 7 angepasst war. Auch seine anderen Tweaks wie Mobile Substrate und Winterboard liefen noch nicht zu 100% auf iOS 7.

Inzwischen ist also Cydia angepasst, TaiG wurde aus evasi0n7 entfernt und Mobile Substrate ist immer noch nicht angepasst. Abhilfe schafft nun erstmal mein Tweak, welcher Mobile Substrate beim Hochfahren des Geräts startet. Leider behebt dieser **nicht das Problem mit A7-Geräten wie dem iPhone 5S**, hierfür muss Mobile Substrate neu gebaut werden.
Mein Paket benutzt zum Starten launchctl und rc.d, welches etwas erfahreneren Mac-Usern bekannt sein sollte. Der Source Code ist übrigens [hier](http://github.com/yanniks/mobilesubstrate-ios7-fix) zu finden, meine Cydia-Repo findet ihr unter http://yanniks.de/cydia/ .
