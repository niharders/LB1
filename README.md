# LB1
Modul 300
Niall Harders
05.03.2018

MultiVM:

1. Ich erstellte einen Ordner im home Laufwerk mit der Bezeichnung lb1
2. In diesen Ordner erstellte ich ein Vagrantfile, mittels dem Befehl vagrant init
3. Danach führte ich mit vagrant up das file aus.
4. Als nächstes zerstörte ich vagrant mittels vagrant destroy -f (bei diesem Befehl bleibt das vagrantfile erhalten)
5. Ich löschte den Inhalt des Vagrantfiles und fügte meinen hinzu
6. Mit vagrant up startet ich das File wieder
7. Via vagrant ssh verband ich mich auf meinen client1 und pingte meinen client2



Bestehende VM aus Vagrant Cloudzum laufen bringen:

1. vagrant destroy -f ausgeführt
2. BOX_IMAGE1 im Vagrantfile erstellen
3. debian/jessie64 als Pfad angegeben
4. Im Vagrantfile beim master die BOX_IMAGE durch BOX_IMAGE1 ersetzt
5. vagrant up ausgeführt
6. Eine Debian Maschine wurde als master erstellt
