---
title:  "Wie ich zum Bloggen kam"
---
Vor fast einem Jahr fing ich an, mit dem Gedanken zu spielen, eine Website aufzumachen. Sie sollte zunächst nur eine Referenzseite sein, die ich zum Beispiel bei Bewerbungen hätte vorlegen können, um dicke Pluspunkte bei meinen potentiellen Arbeitgebern zu kassieren. Dank dem mir schon vertrauten WordPress und meinen bereits vorzeigbaren Projekten, die ich auf der Seite dann vorgestellt hätte, wäre das nur eine Sache von ein paar Tagen gewesen.
<!--more-->

## Programmiererei

Doch um möglichst viel rauszuhauen, entschied ich mich dazu, ein eigenes Theme für die Seite zu programmieren, anstatt auf ein bereits vorhandenes zuzugreifen. Dabei habe ich auch gehofft mit der Entwicklung eines WordPress-Themes zum ersten Mal einen umfangreicheren Einblick in eine größere Software zu erhalten. Den bekam ich zwar auch, nur legte er mir keinerlei interessante Konzepte offen, von denen ich etwas hätte lernen können. Das äußerte sich darin, dass ein Großteil der Theme-Programmierung darin bestand, die jeweils richtige Funktion für die Ausgabe einer bestimmten Variable zu finden und einzusetzen. Und um ein wirklich gescheites Theme zu implementieren, bedarf es vieler dieser Funktionen. Das Resultat ist dann ein ekliger Mischcode bestehend aus PHP und HTML:

	echo "<!DOCTYPE html>\n",
		'<html xmlns="http://www.w3.org/1999/xhtml" ',
		  language_attributes (), ">\n",
		"<head>\n",
		'<meta http-equiv="content-type" ',
		  'content="', get_bloginfo ( 'html_type' ),
		  '; charset=', get_bloginfo ( 'charset' ), "\" />\n";
	wp_head ();
	echo '<title>', get_bloginfo (), wp_title ( '/', 0 ), "</title>\n",
		"</head>\n";

Diese Art der Theme-Entwicklung wollte ich mir nicht antun und ich suchte nach einem besseren Konzept. Und mit <a href="http://www.webholics.de/2007/08/14/xslt-als-template-engine-in-php-teil-1/">XSLT</a> fand ich eine Möglichkeit, Themes sehr elegant umzusetzen. Das fand ich schon klasse. Aber als ich erfuhr, dass XSLT auch von modernen Browsern verarbeitet werden kann, bin ich aus den Latschen gekippt. Schon kam ich mir wie ein verdammter Revolutionär vor, der mit dieser Technik wieder Action in die langweilige Webentwickler-Szene bringt. Mein Plan war es, eine Blog-Software zu schreiben, die von Anfang an auf clientseitiges XSLT setzt und die Vorteile dieser Technologie mit anderen Systemen potenziert. Alle generierbaren Unterseiten sollten mithilfe eines Caching-Systems in einzelne XML-Dateien zwischengespeichert werden. Bei einem normalen Seitenaufruf würden diese nur noch ausgelesen werden; der Webserver müsste weder PHP-Code noch Datenbankabfragen ausführen. Zusätzlich sollte jede dieser Cache-Dateien komprimiert gespeichert und so auch an den <a href="http://www.homepage-performance.de/http-gzip-website-komprimierung.html">Besucher gesendet werden</a>. So ein System würde zig Vorteile bieten und vor allem dem clientseitigen XSLT zum Durchbruch verhelfen; vorausgesetzt alle würden es nutzen.. :D

Also verwarf ich das Theme vorerst und arbeitete mich in XSLT ein. Mit der Zeit wurden meine XSLT-Dateien aber immer größer und unübersichtlicher, was auf Kosten der Wartbarkeit ging. Darum begann ich mit der Entwicklung einer eigenen XML-Sprache, die einem die Arbeit mit XML erleichtern sollte; also eine Art <a href="https://de.wikipedia.org/wiki/Sass_%28Stylesheet-Sprache%29">Sass</a> für XML. Den dazugehörigen Compiler, programmierte ich kurioserweise in XSLT. Damit konnte ich sicherstellen, dass überall, wo XSLT unterstützt wurde, auch meine XML-Sprache benutzbar war. Doch während der Entwicklung des Compilers, begann mich eine Eigenart der XML-Syntax zunehmend zu nerven:
										<code><h1>Nerven</h1></code>
										Warum wird denn der Elementname sowohl im öffnenden als auch im schließenden Tag genannt? Die einmalige Nennung deklariert den Elementnamen doch schon eindeutig! So legte ich mein aktuelles Projekt wieder auf Eis und nahm mir vor, diese und weitere Kunstfehler mit einer alternativen XML-Syntax zu beseitigen. Doch soweit kam es natürlich nicht.

## Zeitspiel

Denn plötzlich stand das Informatikstudium vor der Tür und hat mir seitdem konsequent meine Zeit weggefressen. Selbst manche Wochenenden muss ich zu Hause verbringen, um im Stoff mitzukommen. Das liegt vielleicht auch an meinem nur fast optimalen Zeitmanagement, am kaputten Schlafrhythmus oder an der fehlenden Anwesenheitspflicht in der Uni. Jedenfalls schaffe ich es zur Zeit nicht, regelmäßiger meinem Hobby nachzugehen. Das ist natürlich vor allem jetzt ärgerlich, wo ich doch tausend Projekte am Laufen habe. Aber die ganze Tüftelei der letzten Zeit war nicht umsonst; sie hat mir gezeigt, dass ich inzwischen vielleicht das Zeug dazu habe, einen interessanten Blog zu führen.

Ich programmiere schon seit vielen Jahren. Aber die Art, wie ich dieses Mal Probleme anging, hat mir gefallen. Jedes Mal, wenn mich die Makel einer Software besonders aufregten, packte ich das Problem an der Wurzel und versuchte es selbst besser zu machen. Dabei hangelte ich mich von Projekt zu Projekt in immer tiefere Softwareebenen, in der Hoffnung irgendwann wieder emporzusteigen und mit den verbesserten Tools die Kacke so richtig zum Dampfen zu bringen.

Wenn ich so darüber schreibe, muss ich an Blogger wie <a href="http://keksa.de/">keksa</a> und <a href="http://pyropeter.eu/41yd.de/">Eddy Sino</a> denken. Sie haben mich in ihren aktiven Zeiten wahnsinnig inspiriert; das ging weit über das Technische hinaus. Sie haben mich mit ihrer Leidenschaft und ihrer echten(!) Nerdheit motiviert, mein Ding durchzuziehen. Ich will andere Menschen ebenso inspirieren können und hoffe, das mir das eines Tages gelingen wird. Ich fange also an zu bloggen. Und ich werde fürs erste nicht viel Zeit haben. Trotzdem versuche ich, meine interessanteren Projekte und Gedankengänge hier darzulegen. Vielleicht werde ich ja noch irgendwann darüber bloggen, wie ich meinen Blog programmiere. Und selbst wenn nicht: meinen potentiellen Arbeitgebern kann ich diesen Blog dann immer noch unter die Nase reiben.
