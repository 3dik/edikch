---
title:  "Hack the Burger King"
lang: de-DE
excerpt: |
  Ich liebe Hackerfilme. Unter anderen mag ich an diesen Hollywoodschinken, dass sie das <a href="http://www.youtube.com/watch?v=RNojBDZeKGA">Hacken so cool aussehen lassen</a>. Nicht dass es das nicht auch in Wahrheit ist. Doch in der Realität versteckt sich die Coolheit eines Hacks meist viel weiter unter der Oberfläche. Zum Verständnis fehlt dem Durchschnittstypen (<a href="http://de.harry-potter.wikia.com/wiki/Muggel">Muggel</a>) dann das Wissen. Man kann ihm das Geile an Buffer Overflows oder Code Injections nicht vermitteln. Aber manchmal findet man etwas Besseres und zeigt ihm etwa wie er noch mehr Burger fressen kann.
---

{% include img.html
	img="razor-and-blade-150x150.jpg"
	caption="Razor und Blade aus dem Film Hackers"
	alt="Zwei Freaks, die einen Laptop vor den Betrachter halten"
	large="razor-and-blade.jpg"
	class="right"
	%}
Ich liebe Hackerfilme. Unter anderen mag ich an diesen Hollywoodschinken, dass sie das <a href="http://www.youtube.com/watch?v=RNojBDZeKGA">Hacken so cool aussehen lassen</a>. Nicht dass es das nicht auch in Wahrheit ist. Doch in der Realität versteckt sich die Coolheit eines Hacks meist viel weiter unter der Oberfläche. Zum Verständnis fehlt dem Durchschnittstypen (<a href="http://de.harry-potter.wikia.com/wiki/Muggel">Muggel</a>) dann das Wissen. Man kann ihm das Geile an Buffer Overflows oder Code Injections nicht vermitteln. Aber manchmal findet man etwas Besseres und zeigt ihm etwa wie er noch mehr Burger fressen kann.

Die Story fing noch in meiner Schulzeit an. Um den wahnsinnig nichts bildenden Unterrichtsstunden zu entfliehen nahm ich mir mit einigen Freunden regelmäßig frei und fuhr mit ihnen in die Burger King-Filiale unserer Stadt. Auf Dauer war das einem von uns zu kostspielig und er suchte das Internet nach Gutscheinen ab. Die hat er auch gefunden - auf einer <a href="https://www.bk-feedback-de.com/">offiziellen Burger King-Umfrageseite</a>. Geht man die dortige Umfrage durch, erhält man am Ende einen Gutscheincode, den man gegen einige vergünstigte Menüs eintauschen kann. Von da an rannten wir bei jedem Besuch die Umfrageseite durch und ernährten uns nur noch von Big Kings.

Der Gutschein-Code war stets sieben Zeichen lang, wobei die beiden Vorderen Buchstaben und die Hinteren Ziffern waren. Dabei fiel uns auf, dass sich die beiden Buchstaben für die Dauer eines Monats nicht änderten. Die in dem einen Monat generierten Codes könnten also beispielsweise stets mit "XZ" beginnen; die Codes des nächsten Monats würden alle mit einer anderen zweistelligen Buchstabenkombination beginnen. Das war ja schön zu wissen, nur brachte uns diese Erkenntnis zunächst überhaupt nichts. Doch praktischerweise verplapperte sich irgendwann eine der Burger King-Mitarbeiterinnen. Sie hat uns versehentlich verraten, wie die Ziffern berechnet werden! Es ist ganz einfach: die fünfstellige Nummer muss durch Drei teilbar sein. Mit diesem Wissen bewaffnet, konnten wir nun noch schneller unsere <del>Codes</del> Burger erhalten.

Aber es war immer noch etwas umständlich sich diese Codes zu generieren. Man musste die aktuelle Buchstabenkombination kennen oder sich von der Umfrageseite besorgen. Und man musste sich eine schöne fünfstellige durch drei teilbare Zahl ausdenken. Wenn ich Rechengenie da mit dem Code "BK60000" und eine halbe Stunde später mit "BK60006" antanzte, wurden die Leute schon etwas misstrauisch. Einem von uns kam deshalb die Idee, einen Online-Gutscheincodegenerator zu basteln. Es wurde nicht lange gefackelt; das Skript war schnell geschrieben, ein Design machten wir auch. Und fertig war <a href="http://bkcode.de/">bkcode.de</a>. Wir mussten nur jeden Anfang eines Monats die neue Buchstabenkombination im Generator festlegen. Die Zahlen hat er sich dann selbst generiert. Von da an musste man nur diese Seite besuchen und erhielt seine Gutscheincodes.

Mit der Zeit hat sich der Codegenerator über Mund-zu-Mund-Propaganda und den Social Networks herumgesprochen. Sogar für einige Backlinks hat es gereicht, worauf wir sehr stolz waren. Wir hätten die Sache noch etwas aufbauschen und mit einer Prise Rebellion verleihen können, von wegen "Billigeres Essen!" und "Burger für die Armen!". Das hätte vielleicht einen Teil der oben erwähnten Coolnes eines <a href="http://www.youtube.com/watch?v=xhpoqjB4NkE">Razor und Blade-Duos</a>.

<h2>Perfektion der Coolness wegen</h2>

Die Website lief schon eine ganze Weile, als jemand zu mir meinte, es wäre cool, wenn sich der Generator diese monatlichen Buchstabenkombinationen selbstständig von der Umfrageseite besorgen würde. Ich hatte hobbymäßig gerade keine Projekte am Laufen und fand, dies wäre eine prima Gelegenheit, um meine bisher gesammelten Programmiererfähigkeiten in einem kleinen Projekt möglichst auszureizen. Mir hat nämlich der Gedanke gefallen, diesen Buchstaben-Extractor komplett unabhängig von der Website, und sogar unabhängig von PHP zu implementieren. Man sollte ihn sowohl aus der Kommandozeile heraus aufrufen, in eine grafische Oberfläche integrieren oder eben doch mittels PHP in eine Website einfügen können. Da hat es sich auch angeboten die Zifferngenerierung des Gutscheincodes gleich mit in den Extractor auszulagern. Damit sollte aus dem übrigens in C++ programmierten Projekt ein kompletter Burger King-Gutscheincode-Generator werden. Ich taufte es originellerweise bkoder.

{% include img.html
	img="survey-error.png"
	alt="Formular mit Fehlermeldung"
	caption="Nach dem ersten unausgefüllten Abschicken"
	class="right"
	%}
Um weiter auf der Fast Food-Kette rumzureiten, erläutere ich, wie sie es mir so einfach machte, bkoder die Buchstaben extrahieren zu lassen. Als erstes eine kurze Info über die Umfrage. Die ist so aufgebaut, dass sie die Zufriedenheit des Kunden mit seinem letzten Burger King-Besuch zu ermitteln versucht. Darum soll er auf der ersten Umfrageseite das Datum des Besuchs und die Nummer der besuchten Filiale angeben, die auf der Rückseite der Quittung zu finden ist. Wer wegen der Nummer auf den Gedanken kommt, die Codes würden sich von Filiale zu Filiale unterscheiden, liegt aber falsch. Im Gegenteil: uns ist schon zu der Zeit, als wir uns den Code noch manuell beschafften, aufgefallen, dass man beide Daten, den Besuchstag und die Restaurantnummer, gar nicht angeben muss. Darauf muss man erst mal kommen. Denn klickt man auf den "Beginnen"-Button ohne die Eingabefelder ausgefüllt zu haben, erscheint dieselbe Seite mit der Meldung, man solle es noch einmal versuchen.

Doch klickt man zwei weitere Male auf den Button, kommt man plötzlich doch weiter und landet auf dem Hauptteil der Umfrage. Hier soll man Multiple-Choice-Fragen, die sich mit dem Burger King-Besuch beschäftigen, beantworten. Praktischerweise kann man im Hauptteil das Antworten genauso umgehen, wobei man hier sogar nur zwei Mal auf den "Weiter"-Button klicken muss. Dafür muss man grob geschätzt um die 20 Fragen auf diese Weise durchgehen, bis dieser Teil der Umfrage abgeschlossen ist. Abschließend werden noch einige Dinge zur eigenen Person abgefragt, was man wieder umgehen kann. Hat man dies geschafft, erscheint endlich die ersehnte Seite mit dem generierten Gutscheincode.

Die Umgehung der Antworten haben die Entwickler dieser Seite womöglich absichtlich eingebaut, um sich durch gutscheincrawlenden Burgerfressern nicht die Statistiken versauen zu lassen. Sonst noch ist auffällig, dass die generierten Zahlenwerte nah beieinander liegen und langsam ansteigen, wenn man die Umfrage mehrfach kurz hintereinander durchgeht. Einige <a href="http://board.raidrush.ws/showthread.php?t=759213">Raid-Rush-User</a> haben die Theorie aufgestellt, der Zahlenwert würde mit jedem generierten Code um Drei ansteigen. Ist diese Theorie richtig, dann kann man die Anzahl der im Monat generierten Codes ermitteln. Sobald ich Anfang Juli weiß, mit welchem Wert diese Code-Iteration beginnt, füge ich hier die ungefähre Code-Anzahl vom Juni ein.

{% include img.html
	img="survey-code.png"
	alt="Ein bisschen Text mit sogenannter Validierungscode"
	caption="Der Gutscheincode, wie er in der Umfrageseite angezeigt wird"
	class="left"
	%}
bkoder konnte sich den Code nun also vollkommen selbständig beschaffen. Weil das Projekt aber auch für den Serverbetrieb geeignet sein sollte, war das noch lange nicht alles. Eine Seite, wie unser Online-Code-Generator sollte auf bkoder zurückgreifen können, indem es das Programm einfach aufruft. Dieses würde den Code einfach über die Standardausgabe zurückgeben. Weil die Codegenerierung aber weiterhin perfomant bleiben sollte, musste ich ein System entwickeln, dass die beiden Buchstaben des Gutscheincodes in einem Cache speichert und auf diesen bei der Generierung zurückgreift. Erst wenn der Cache veraltet, die aktuelle Buchstabenkombination also eine andere ist, sollte bkoder die Umfrage durchgehen und den Cache anschließend aktualisieren.

Das wäre keine große Sache, wenn nicht theoretisch folgendes im Serverbetrieb passieren könnte: ein neuer Monat bricht an und ein neue Buchstabenkombination wird geboren. Als der Cache noch veraltet ist, rufen auf einmal zwei Personen fast zeitgleich die Generator-Website auf. Diese startet also zwei seperate bkoder-Prozesse. Und weil beide, beispielsweise anhand eines Zeitstempels im Cache, merken, dass der gespeicherte Code vom letzten Monat ist, beginnen beide damit die Umfrage durchzugehen. Wenn man Pech hat, sind sie damit auch nahezu gleichzeitig fertig und wollen nun beide den Cache beschreiben. Was jetzt passiert ist aber entweder undefiniert oder ist abhängig vom System, auf dem bkoder läuft.

Es könnte sein, dass sich beide Schreibprozesse gegenseitig behindern und das Programm zum Absturz bringen oder am Ende einen fehlerhaften Cache herausbringen. Austesten, ob das auf dem von uns genutzten System reibungslos funktioniert, wollte ich nicht, weil das Projekt eben auf allen möglichen Systemen laufen sollte. Das Argument, dass so ein Konflikt doch ziemlich unwahrscheinlich wäre, lass ich ebenfalls nicht gelten. Die Generator-Website rankt zwar nicht gerade in den Alexa-Top-100; es ist also unwahrscheinlich, dass jemals zufällig zwei oder gar mehr Seitenaufrufe derartig kurz hintereinander zum Server gelangen. Jedoch sieht das schon anders aus, wenn Angreifer versuchen diese Schwachstelle gezielt auszunutzen, um unseren Code-Generator zu sabotieren. Darauf zu setzen, dass sie gar nicht erst auf die Idee kommen, dass eine solche Schwachstelle existiert, <a href="http://de.wikipedia.org/wiki/Security_through_obscurity">war natürlich keine Option</a>.

Diese und weitere Probleme ließen sich mit der Parallelen Programmierung lösen, in die ich mich prombt einarbeitete. Weil dieser Lösungsansatz jedoch weitere Komplexität und Fehlerquellen nach sich zog, erhöhte es wieder den Umfang des Projektes. Dass ich abschließend auch umfangreiche Konfigurationseinstellungen hinzugefügt habe, hat aus bkoder dann einen Tausendzeiler gemacht. Aber wegen seiner sauberen Programmierung und seiner Flexibilität bin ich dennoch Stolz auf das Endresultat. Wegen letzterem neige ich sogar dazu, es als eine Art Mini-API zu bezeichnen, wobei sich der Einsatzzweck dieser API letztlich sicher immer auf eines beschränken würde: dem Generieren von BK-Gutschein-Codes.

<h2>Leicht schlägt kompliziert</h2>

Also zurück zu unserem Online-Generator. Für den dritten Teil dieser Story muss ich erwähnen, dass wir, noch bevor ich mit der Arbeit an bkoder angefangen habe, eine andere Code-Generator-Website, <a href="http://web.archive.org/web/20111229031340/http://www.bkcodes.com/">www.bkcodes.com</a>, fanden, die es wohl schon vor unserem Exemplar gab. Bis auf die Tatsache, dass unsere Kollegen für die Benutzung der Codes eine [verdammt coole Anleitung]({% asset_path bkcoder-howto.png %}) angefertigt haben, hat uns das anfangs nicht sonderlich gejuckt. Bei so wenigen Besuchern kam das Konkurrenzgefühl eben nicht auf. Doch dann haben wir doch etwas entdeckt, das unser Interesse weckte. Dem, der von uns jeden Monatsanfang den Buchstabencode aktualisierte, ist aufgefallen, dass dieser bei bkcodes.com bereits kurz nach Null Uhr umgestellt wurde. Man könnte meinen, unsere Kollegen würden ebenfalls auf einen Code-Extractor zurückgreifen.

<table class="right">
<tr>
<th>Monat</th><th>Code</th>
</tr>
<tr><td>Januar</td><td>BB</td></tr>
<tr><td>Februar</td><td>LS</td></tr>
<tr><td>März</td><td>JH</td></tr>
<tr><td>April</td><td>PL</td></tr>
<tr><td>Mai</td><td>BK</td></tr>
<tr><td>Juni</td><td>WH</td></tr>
<tr><td>Juli</td><td>FF</td></tr>
<tr><td>August</td><td>BF</td></tr>
<tr><td>September</td><td>CF</td></tr>
<tr><td>Oktober</td><td>CK</td></tr>
<tr><td>November</td><td>CB</td></tr>
<tr><td>Dezember</td><td>VM</td></tr>
</table>
Das könnte man meinen, wenn man nicht weiß, dass die offizielle Umfrageseite einen neuen Buchstabencode nicht schon ab Null sondern erst ab Sechs Uhr am Ersten des Monats verwendet. Die hatten neue Codes also stets schon bevor die Umfrageseite sie hatte! Und damit hatten sie eine ganz andere scheinbar bessere Quelle für die Buchstaben. Kurz bevor ich mit bkoder fertig wurde, versuchte ich durch intensives Googlen diese Quelle zu finden und fand sie auch in irgendeiner Quellcodedatei in den Tiefen des Internets. Die Buchstabencodes sind tatsächlich von vornherein festgelegt und jeder Monat hat einen festen Code, der sich über die Jahre nicht ändert. Der Juni-Code im Jahr 2012 war zum Beispiel "WH" und ist es im Jahr 2013 immer noch. Und nun waren auch wir im Besitz dieser Buchstabenliste.

Das machte bkoder natürlich überflüssig, obwohl ich das Projekt nach dieser Erkenntnis trotzdem vollendete, schon allein weil ich seine saubere Programmierung schätzte. Dafür konnten wir unseren Generator nun endlich perfektionieren. Ein manuelles Aktualisieren des Buchstabencodes gehörte seitdem der Vergangenheit an und unsere Codes waren nun auch unabhängig von der offiziellen Umfrage-Seite. Ist diese offline, können die Leute immer noch unseren Generator aufrufen!

<h2>Aktuelle Lage</h2>

Denen, die dem oberen Link zu bkcodes.com gefolgt sind, ist vielleicht aufgefallen, dass sie auf einem archive.org-Abbild der Website gelandet sind, das keine Codes generieren kann. Das hat den einfachen Grund, dass die <a href="http://www.bkcodes.com/">Originalseite</a> inzwischen offline ist. Weil die Domain aber noch aktiv war und ich noch etwas für den Artikel recherchieren wollte, hoffte ich mit einer Whois-Anfrage die Kontaktdaten des Betreibers zu ermitteln. Hat natürlich geklappt. Nur war ich etwas irritiert: als Registrant war "Burger King Corporation" eintragen. Gehörte der Online-Generator wirklich zu Burger King? Sind wir vermeintlich coolen Hacker auf einen PR-Gag reingefallen?

No. Diese Schmierigen haben etwas anderes verbrochen. Ich hatte bereits eine Ahnung, die ich dank <a href="http://who.is/domain-history/bkcodes.com">Whois-History</a> schnell überprüfen konnte. Als die Seite online war, hat die Domain einem Mister Hofstett aus England gehört. Irgendwann hat Burger King ein <a href="http://www.wipo.int/amc/en/domains/search/text.jsp?case=D2012-0370">UDRP-Verfahren eingeleitet</a> und ihm am 14. April 2012 die Domain abgenommen. Von da an leitete einen die Domain auf eine weiße Seite. Auf eine E-Mail, die ich dem Typen schrieb, antwortete er nicht. Entweder weil er gar nicht existiert; dass er laut UDRP-Bericht garnicht auf das Verfahren reagierte, deutet jedenfalls darauf hin. Oder aber er hielt mich mit meinem grauenhaften Englisch für einen Ermittler, der ihm an dem Kragen will.

Wer mir aber auf eine Mail antwortete war der Admin von <a href="http://bk-code.de/">bk-code.de</a>, einer weiteren Generator-Seite - die Domain hat anders als unsere noch diesen Bindestrich. Von ihm erfuhr ich, dass er neben den Regeln für die Zahlencodes auch die Buchstabenliste von einem Burger King-Mitarbeiter erhalten hat. Damit steht fest, dass Burger King wahrscheinlich einem großen Teil seiner Mitarbeiter die Möglichkeit gegeben hat, sich selbstständig die Codes zu generieren.

Das haben die nun davon. Die Informationen sind schon einige Male an Außenstehende durchgesickert und bereits in mehreren Foren wurde offen über die Codes diskutiert. Die erste Generator-Seite, bkcodes.com, konnten sie wegen dem "bk" in der Domain außergerichtlich wegsperren. Gegen die beiden neuen Seiten könnten sie genauso vorgehen. Doch kann man auch auf andere Adressen zurückgreifen und im Notfall auch auf kostenlose Subdomains, die sich umso leichter einrichten lassen. Der Macher von bk-code.de hat sogar eine passende <a href="https://play.google.com/store/apps/details?id=de.bkcode&feature=search_result">Android-App</a> entwickelt, mein <a href="https://github.com/3dik/bkoder">bkoder</a> ist auch noch nicht verschollen und spätestens mit diesem Artikel stehen alle Infos zur Codegenerierung frei im Web. bkcodes.com habt ihr vielleicht aufgehalten, <a href="http://www.hacker-ethik.de/hacker_manifest.htm">aber ihr könnt uns nicht alle aufhalten</a>. muhahaue
