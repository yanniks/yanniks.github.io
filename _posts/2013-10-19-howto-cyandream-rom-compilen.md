---
layout: post
title: (HowTo) CyanDream ROM compilen und / oder portieren
description: "CyanDream, eine neue ROM für Android Geräte, compilen und/oder portieren - so geht's"
modified: 2013-10-19
category: articles
tags: [new, rom, cyandream, cyanogenmod, cm, jellybean, android, paranoidandroid, pa]
---

**Auch wenn die ROM noch nicht mit fertigen .zip's ausgeliefert wird, konnt ihr mit einem Ubuntu-Computer, der auf einer 64-bit Architektur aufbaut, CyanDream ganz einfach in wenigen Schritten compilen - so funktioniert's.**
<br><br>
Installiert auf eurem Computer mithilfe von APT (oder eurem bevorzugten Paketmanager) folgende Pakete, um das Ganze zu vereinfachen hier schonmal als fertiges APT-Kommando:
<br>

`sudo apt-get install openjdk-6-jdk git-core python gnupg flex bison gperf build-essential zip curl zlib1g-dev libc6-dev lib32ncurses5-dev ia32-libs x11proto-core-dev libx11-dev lib32readline-gplv2-dev lib32z-dev
  libgl1-mesa-dev g++-multilib mingw32 tofrodos python-markdown
  libxml2-utils xsltproc libx11-dev:i386 lzop
  git gnupg flex bison gperf build-essential
  zip curl libc6-dev libncurses5-dev x11proto-core-dev 
  libx11-dev libreadline6-dev libgl1-mesa-glx 
  libgl1-mesa-dev g++-multilib mingw32 tofrodos 
  python-markdown libxml2-utils xsltproc zlib1g-dev schedtool`
<br><br>
Legt euch nun das Android SDK zu und richtet es ein (befolgt die Schritte 4-7 aus [diesem Tutorial](/articles/tutorial-cyanogenmod-10-1-rom-fur-desire-hd-erstellen/). Den Download gibt's hier: [klick!](http://developer.android.com/sdk/index.html)
<br><br>
Installiert anschließend git-repo, indem ihr folgende Kommandos ausführt:

`mkdir ~/bin`

`PATH=~/bin:$PATH`

`curl https://dl-ssl.google.com/dl/googlesource/git-repo/repo > ~/bin/repo`

`chmod a+x ~/bin/repo`
<br><br>
Erstellt nun ein Verzeichnis eurer Wahl, navigiert im Terminal dorthin und führt von dort aus folgende Kommandos aus:

`repo init -u git://github.com/CyanDreamProject/android.git -b cd-4.3`

`repo sync`
<br><br>
Ab jetzt kommt es darauf an, ob euer Gerät offiziell unterstützt wird. Ob dieses der Fall ist könnt ihr feststellen, indem ihr prüft, ob euer Codename in [dieser Datei](http://raw.github.com/CyanDreamProject/hudson/master/cd-build-targets) auftaucht. Ist dieses der Fall, könnt ihr mit **Abschnitt A** weitermachen. Andernfalls befolgt ab sofort die Kommandos aus **Abschnitt B**.

### Abschnitt A
Gebt nun einfach folgendes Kommando ein, wobei ihr *CODENAME* einfach durch den Codenamen eures Geräts ersetzt.
<br>

`bash jb-build.sh CODENAME`
<br><br>
Das fertige Produkt findet ihr nun im Ordner out/target/product/*CODENAME*. Die Datei, die ihr sucht beginnt folgendermaßen: `CyanDream-1-`

### Abschnitt B
Bitte prüft, ob euer Gerät bereits den CyanogenMod unterstützt. Falls ja, macht hier weiter. Falls ein, fangt dort an und wenn der läuft, arbeitet hier weiter.
<br>
Für CyanDream sind einige Änderungen am CyanogenMod-Gerätebaum nötig. Bennent zu Beginn die Datei cm.dependencies in cd.dependencies um und fügt nach jedem Erscheinen von `"repository": "` `CyanogenMod/` hinzu. Sollte also vorher die Datei so ausgesehen haben:

` {`

`   "repository": "android_kernel_google_msm",`

`   "target_path": "kernel/google/msm",`

`   "branch": "cm-10.2"`

` }`

`]`
<br><br>
So sieht sie nach dem Bearbeiten so aus:

` {`

`   "repository": "CyanogenMod/android_kernel_google_msm",`

`   "target_path": "kernel/google/msm",`

`   "branch": "cm-10.2"`

` }`

`]`
<br><br>
Solltet ihr als Basis die CyanogenMod-Repos benutzen, so müsst ihr normal noch den "Vendor" hinzufügen. Dieser beinhaltet Treiber, die nicht Open Source vorliegen.
Fügt in der cd.dependencies nun je nach Hersteller den Vendor hinzu, [TheMuppets](https://github.com/TheMuppets) stellt für viele Hersteller diese Dateien vorgefertigt zur Verfügung. Als Beispiel könnt ihr die Dateien, die wir für das Nexus 4 vorbereitet haben, vergleichen: [Original](http://raw.github.com/CyanogenMod/android_device_lge_mako/cm-10.2/cm.dependencies) - [CyanDream Version](http://raw.github.com/CyanDreamProject/android_device_lge_mako/cd-4.3/cd.dependencies)
<br><br>
Damit ist schonmal ein Großteil der Arbeit erledigt. bennent nun die Datei cm.mk in cd.mk um, ändert jedes Erscheinen von `vendor/cm` zu `vendor/cyandream` und ändert cm_*CODENAME* zum cd_*CODENAME*. Nun könnt ihr mit dem compilen beginnen. Schiebt eure vorgefertigten Gerätebäume nun in den Ordner device/*HERSTELLER*/*CODENAME* und macht mit Abschnitt A weiter.
<br><br><br>
**Hinweis:** Dieses Tutorials ist während eines Langstreckenfluges entstanden, ohne Internetzugang. Fehler sind inklusive. Ich werde das Ganze bei gelegenheit noch einmal genau prüfen.
