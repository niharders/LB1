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



Eigener Service auf Basis IaC implementieren

1. vagrant destroy -f ausgeführt
2. Fixe IP für den Master (192.168.1.10) und die Clients (192.168.1.#) angegeben
3. Forwarded Ports angegeben, damit man auf die Webseite kommt. (guest 80, host 8080)
4. Im nächsten Schritt gab ich in, in welchen Ordner auf der VM, die html Seite gespeichert werden sollte
5. In den folgen befehlen sagte ich nur noch, dass man via Shell apache installieren sollte.
