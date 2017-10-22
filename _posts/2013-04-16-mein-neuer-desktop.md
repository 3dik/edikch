---
title:  "Mein neuer Desktop"
lang: de-DE
---
So um Weihnachten herum gab mein PC langsam den Geist auf. Ich konnte die Sterbeursache nur vage in den Bereich zwischen Mainboard und Netzteil einordnen, weshalb sich die Reparatur über längere Zeit hätte hinziehen können. Von der Kiste hatte ich aber eh die Schnauze voll. Und so entschied ich mich dafür, mir ein neues System anzuschaffen. Dass ich mir zu der Zeit auch mein erstes Smartphone kaufen wollte, hat sich als interessante Gelegenheit herausgestellt.

Denn ich habe mich schon lange davor von dem Gedanken begeistern lassen, das eigene Desktop-System nicht mehr auf dem heimischen Computer sondern auf dem Smartphone laufen zu lassen. Ich nahm mir also vor, mit einem Android-Handy in die Smartphone-Welt einzusteigen und damit auch meinen alten Rechner zu ersetzen. Bei meinen Internetrecherchen und in meinem Umfeld bin ich mit der Idee vor allem Skepsis gestoßen. Habe erfahren, die Leistung der Handys reiche für ein solches Vorhaben nicht aus, die Geräte würden sich überhitzen und das ganze wäre auch einfach nicht machbar. Dass das erste Smartphone, das dieses Konzept umgesetzt hat, das <a href="http://www.youtube.com/watch?v=ge5UWtV4u7A">Atrix 4g</a>, kommerziell erfolglos war, hat man mir auch an den Kopf geworfen.

{% include img.html
	img="atrix-docking-station-small.jpg"
	large="atrix-docking-station.jpg"
	alt="Bildschirm, Maus, Tastatur und ein Handy, alles miteinander verbunden"
	caption="Atrix 4G an der Dockingstation"
	class="right"
	%}
Doch genau dieses Gerät hab ich mir dann geschnappt! Und tatsächlich hat es nicht lange gedauert, bis ich meinen alten Rechner auf den Dachboden gekickt habe. Yes, ich habe meinen hässlichen Blechkastencomputer durch ein kippenschachtelgroßes Gerät ersetzt, auf dem ein vollständiges Ubuntu installiert ist, welches <a href="http://www.youtube.com/watch?v=3ctIO8CwJsk">parallel</a> neben Android läuft. Beide Systeme nutzen den selben Kernel und Ubuntus Boot-Vorgang dauert praktischerweise nur wenige Sekunden. Dank Micro-HDMI ist das Ding an meinem Fernseher angeschlossen. Dank Micro-USB-OTG-Ausgang kann ich jegliche USB-Peripherie inklusive USB-Hubs anschließen. Und dank Adapter habe ich meine interne Festplatte zu einer Externen gemacht und kann mit dem Smartphone ganz normal auf sie zugreifen. Internet erhalte ich vom WLAN-Router und damit hat mein System auch schon praktisch alles, was ein Desktop eben braucht. Zur Zeit arbeite ich als studentischer Programmierer und es ist schon lässig, wenn ich meinen anfangs noch skeptischen Freunden erzähle, dass ich einen Großteil der Programmierarbeit zu Hause auf meinem Smartphone-Ubuntu erledige. Weil ich ohne Rechner auch keine Lüfter am Start habe, ist es in meinem Zimmer jetzt so leise, dass ich herausgefunden habe, dass mein Fernseher ein leises Rauschen von sich gibt, wenn ich ihn nicht auf Stumm schalte. Dazu spart so ein Handy-Desktop auch ordentlich Platz, den man zum Beispiel für einen freshen Papierkorb nutzen kann.

<h2>Sich den Desktop erhacken</h2>

{% include img.html
	img="atrix-default-desktop-small.jpg"
	large="atrix-default-desktop.png"
	alt="Ein Screenshot, auf dem ein Browser und ein Fenster mit einer Android-Oberfläche zu sehen sind"
	caption="Das unmodifizierte Standard-Webtop"
	class="right"
	%}
Das reicht jetzt aber mit der Angeberei. Vorerst. Denn der Weg zum Desktop war nicht einfach, und perfekt ist das System noch lange nicht. Das fängt bei der bescheidenen Motorola-Software an und hört bei ihr auch wieder auf. Das, was man sieht, wenn man ein frisches Atrix in den Desktop-Modus schaltet, kann man nicht einmal als abgespeckte Ubuntu-Version bezeichnen. Das Webtop, wie es von Motorola genannt wird, ist in meinen Augen gar kein Desktop-System. Es beschränkt sich auf einen Browser und einem Fenster für die Bedienung von Android. Weder Paketverwaltung noch Terminal sind verfügbar. Das Webtop sollte Knast heißen.

Weil andere <a href="http://cpuchip.net/?p=39"> aus dem Knast bereits ausgebrochen sind</a>, konnte ich schnell nachrücken und Terminal und Paketsystem einrichten. Von da an war ich frei wie ein Vogel und konnte mein System nach meinen Wünschen einrichten. Leider spüre ich trotzdem noch immer den eisernen Atem Motorolas. Diese Halunken haben für das Webtop ein Ubuntu 9.04 genommen und dann ohne Rücksicht auf Verluste softwaremäßig darauf rumgehämmert. Für deren winzige Zielgruppe, die mit einem Browser und einem Fenster auskommt, mag das vielleicht nicht so schlimm sein. Für uns Chefnerds ist das bescheiden. Denn das größte Problem dieses Systems ist, dass Teile des Tegra-Grafiktreibers auf eine ganz bestimmte X11-Version ausgerichtet sind. Ohne weiteres kann ich darum nicht auf eine neuere Ubuntu-Version updaten. Das heißt also, ich arbeite zur Zeit auf einer vier Jahre alten Ubuntu-Distribution und surfe auf dem Firefox 3, der nicht einmal Facebook darstellen kann.

Doch noch ist der Plan nicht gescheitert. Die XDA-Community hat es schon geschafft, <a href="http://forum.xda-developers.com/showthread.php?t=1617684">andere Linux-Distributionen</a> zum Laufen zu bringen. Und ich habe auch schon überlegt mir Assemblerkenntnisse anzueignen und mithilfe des teilweise veröffentlichten <a href="http://sourceforge.net/motorola/atrix/home/Home/">Motorola-Quellcodes</a> das gesamte Webtop auseinander zu nehmen und durch eigene Open Source-Software offenzulegen. Ich dachte sogar daran, Schnittstellen für die Kommunikation zwischen Desktop- und Android-Software zu entwickeln. Man stelle sich mal zwei <a href="http://de.wikipedia.org/wiki/Pidgin_%28Instant_Messenger%29">libpurple</a>-Programme vor, jeweils eine für den Desktop- und den Android-Modus. Beide greifen auf dieselbe Bibliothek zurück und ein fließender Übergang zwischen beiden Modi ist problemlos möglich.

{% include img.html
	img="atrix-desktop-ion3-small.jpg"
	large="atrix-desktop-ion3.png"
	alt="Screenshots eines Desktops mit Tiling-Fenstermanager"
	caption="Mein ausgebauter Webtop-Ubuntu-Desktop mit ion3-Fenstermanager"
	class="center"
	%}

<h2>Aussicht</h2>

Jedenfalls habe ich mir also wieder viel zu viel vorgenommen bei dem Versuch, genau das zu bekommen, was ich haben will. Zum Glück scheint zur Zeit jemand Anderes meine Arbeit zu übernehmen. Das <a href="http://ikhaya.ubuntuusers.de/2013/01/02/canonical-praesentiert-das-ubuntu-phone-os/">Ubuntu Phone OS</a> soll einen Desktop-Modus mit sich bringen und beide Benutzermodi ähnlich gut verschmelzen, wie ich es tun wollte. Damit kann ich notfalls auf dieses System setzen, falls ich es nicht schaffe, mein aktuelles richtig in Gang zu bringen. Dieses Rumgefrickel hat mich übrigens auf die Idee gebracht, auch auf meinem Kobo Ebook-Reader ein Desktop-System einzurichten. Immerhin laufen die Geräte auf einer <a href="http://www.chauveau-central.net/pub/KoboTouch/">Open Source-Linux-Firmware</a> und haben diese so unglaublich stromsparenden E-Paper. :D Doch wenigstens etwas Zeit fürs Studium muss auch endlich mal drauf gehen.

Und mit meinem Atrix-Desktop bin ich eigentlich schon sehr zufrieden. Dazu kann ich mich nun außerdem zu den ersten Menschen zählen, die so etwas produktiv eingesetzt haben. Meiner Meinung nach werden derartige Systeme den <a href="http://www.youtube.com/watch?v=wzc0uMXGFBY">herkömmlichen Desktop-Computer auf lange Sicht vollkommen ersetzen</a>. Und mit etwas Glück wird dann nicht mehr Windows sondern Linux an der Spitze der Desktop-Softwarekette stehen.
