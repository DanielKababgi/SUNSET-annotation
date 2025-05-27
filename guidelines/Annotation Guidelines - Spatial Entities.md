# Guidelines für die Annotation von Non-Named Spatial Entities 

## Version 0.5.0

Ziel ist es, in literarischen Prosatexten, die ungefähr zwischen 1784 und 1918 veröffentlicht wurden, alle *Non-Named Spatial Entities* (=NNSE) zu annotieren. Aus diesen soll ein semantisches Netzwerk zu erstellen werden, welches die Raumsemantik in Anlehnung an Juri Lotman (1972) widerspiegelt. Wir definieren NNSE wie folgt:
<!--Warum ungefähr 1784 und 1918? Das klingt nach genauen Zahlen. Ich würde neben NNSE eine deutsche Übersetzung angeben.-->
Unter NNSE wird eine konkret räumlich verortbare Einheit verstanden, die eine eigene Objektregion konstituiert. Dennerlein (2009) definiert Objektregionen "als Bereich rund um ein Objekt \[...], der bei der Lokalisation anderer Objekte im Verhältnis zu ihm eine Rolle spielt. \[...] Ein Beispiel wäre die Region eines Tisches, die nicht nur den realen Standort dieses Tisches bezeichnet, sondern auch den Bereich, in dem sich Menschen normalerweise bei seiner Benutzung aufhalten." Weitere Beispiele sind: *Baum*, *Kirche*, *Berg*, *Straße*. 
<!--Vielleicht wäre es gut, hier unten ganz kurz *Named Spatial Entities* als Abgrenzung einzuführen.-->
Ausgeschlossen sind Objekte und Gegenstände, die von Personen mitgeführt oder genutzt werden können, da sie keine Objektregion erzeugen. Beispiele  für Objekte und Gegenstände sind: *Flasche*, *Werkzeug*, *Besteck*, *Tasche*. In gewissen Kontexten kann ein Begriff, der normalerweise nicht als NNSE verstanden wird (wie z.B. *Flasche*) eine Objektregion erzeugen (z.B. wenn Figuren geschrumpft werden und dann in die *Flasche* einkehren). Begriffe wie *Landstrich*, *Stadt*, *Himmel* oder *Horizont* sind meist nicht verortbar und es muss im Detail evaluiert werden, ob die Begriffe in der jeweiligen Textstelle der Definition von NNSE entsprechen. <!--Warum sind Berg und Straße verortbar, aber Stadt und Landstrich nicht?-->

Resultat dieser Annotation ist die Erstellung eines Datensatzes, mit dem entweder dedizierte ML-Classifier trainiert oder der Einsatz von LLMs evaluiert werden können. Die Annotation funktioniert auf Satzebene.

## Überblick Guidelines

Es werden insgesamt zwei Kategorien für jede NNSE annotiert: *class* und *container*. Für jede der zwei Klassen muss ein Wert aus einer vorher definierten Liste eingetragen werden. Mehr als ein Wert pro Kategorie ist nicht zulässig. Ein Beispiel ist:  

	Über die <Berge> hob sich die Sonne, leuchtete in klarer Majestät in ein freundliches, aber enges Tal und weckte zu fröhlichem Leben die Geschöpfe, die geschaffen sind, an der Sonne ihres Lebens sich zu freuen. (Jeremias Gotthelf, Die Schwarze Spinne[^1]) 

`NNSE: Berge`  
`|--- Class: natural`  
`|--- Container: exterior`   

In dem folgenden Beispiel sind *Fabrik* und *Heerstraßen* keine NNSE, da sie keine konkreten Orte benennen:  
<!--Hier würde ich kurz erklären, warum das keine konkreten Orte sind (metaphorisch verwendet o.ä.)-->
	Friedrich Mergel, geboren 1738, war der einzige Sohn eines sogenannten Halbmeiers oder Grundeigentümers geringerer Klasse im Dorfe B. [...]. Das Ländchen, dem es angehörte, war damals einer jener abgeschlossenen Erdwinkel ohne <Fabriken> und Handel, ohne <Heerstraßen>, wo noch ein fremdes Gesicht Aufsehen erregte und eine Reise von dreißig Meilen selbst den Vornehmeren zum Ulysses seiner Gegend machte \[...\]. (Annette von Droste-Hülshoff, Die Judenbuche[^2])

Für jede Klassen wird eine Definition der einzelnen zulässigen Werte inklusive Beispiel gegeben. Generell sind hier alle Beispiele im Kursiv geschrieben und falls diese länger sind, ist die NNSE unterstrichen.<!--länger?--> Für alle Textstellen ist es möglich, unklare Fälle zu kennzeichnen. Es ist immer möglich, für unbestimmbare Kategorien *unclear* einzutragen. <!--Sind unklare Fälle und unclear jetzt unterschiedliche Fälle?-->

# Kategorie 1: *class*

Für eine tiefergehende literarische Analyse sollen drei *categories* von NNSE analysiert werden. <!--category=class?--> Bei diesen handelt es sich um aus der (Literatur-)wissenschaft heraus motivierte diskrete semantische Räume, die es im *setting[^3]* geben kann. <!--Was ist hier *setting*? Erklären (das würde ich nicht in der Fußnote machen, annotation guidelines sollen als standalone fuunktionieren)--> Diese sind *urban*, *rural* und *natural*. Es wird in der Fachliteratur häufig festgestellt, dass es einen semantischen Unterschied zwischen urbane und ruralen Räumen gibt (siehe Redepenning 2019), der sich auf verschiedene Merkmale beziehen lässt: Anzahl und Diversität der Bevölkerung, Architektur, Gesellschaftskonventionen und Modernisierungstandard.[^4] Zu welcher *category* eine NNSE gehört, ergibt sich aus dem Kontext, in dem sie auftaucht und bestimmt sich darüber, ob viele Strukturen von Menschen errichtet wurden. 


Die Beschreibung der *classes*:
| *classes* | Beschreibung und Beispiele |
|---|---|
| *urban* | Zu dieser *class* gehören NNSE in einer stark urbanisierten Umgebung, also Groß- und Kleinstädte. Auch Stadt- und Industrieparks und ähnliches fallen darunter. Generell ein Raum, der sich überwiegend aus menschengemachte Strukturen konstituiert, der vor allem von einer heterogenen und multiethnischen Bevölkerung mit einer einer modernen Gesellschaftsform bewohnt wird. Der technische Stand ist hoch entwickelt und neu. Beispiele sind: *Der <ins>Marktplatz</ins> in Berlin war gut besucht.*; *Die <ins>Häuser</ins> in dem Slum ragten wie Zähne aus der Stadt.*| <!--Sind die Städte um 1784 modern?-->
| *rural* | Zu dieser *class* gehören NNSE in einer schwächer urbanisierten Umgebung, also Dörfer, Agrarflächen und touristisch erschlossene Gebiete (Skigebiet, etc.). In diesem Raum sind mäßig viele menschengemachten Strukturen zu finden, eine wenig diverse Bevölkerung mit einer traditionellen Gesellschaftsform. Der technische Stand ist veraltet. *Die Ernte auf dem <ins>Feld</ins> war sehr erträglich.*; *Das <ins>Bauernhaus</ins> stand einsam am Rande des Dorfes.* | <!--Selbe Frage: Ist der technische Stand im Dorf um 1784 'veraltet'?-->
| *natural* | Zu dieser *class* gehören NNSE in einer kaum bis gar nicht urbanisierter Umgebung, wie Waldgebiete, Gebirge, Seen oder Wüsten. Einzelne Gebäude oder Infrastrukturen wie Wanderwege und \-hütten und ähnliches fallen darunter. Menschengemachte Strukturen finden sich hier nur vereinzelt wieder, die Bevölkerungsdichte ist extrem niedrig mit kleinen Gruppen (z.B. Familien) oder Einzelpersonen. *Der <ins>Bach</ins> im Wald ist eiskalt.*; *Vor der einsamen <ins>Abtei</ins> im Wald schauert es mir\!* |

In manchen Fällen ist es nötig zu überprüfen, zu welcher *class* die NNSE gehört.<--Überprüfen?--> Im Satz *Der Steg der Stadt reicht bis ins Meer* würde *Steg* als *category urban* klassifiziert werden, da er von Menschen gebaut wurde und Teil der Stadt ist. Bei beweglichen Objekten wie einer Kutsche, die eine Bewegung von A nach B zurücklegen, wird nur dann eine *category* annotiert, wenn im Text expliziert wird, wo der größte Teil dieser Bewegung stattfindet. Bei dem Satz *Die Kutsche fuhr aus Berlin in die Wälder* sind Start- und Endpunkt klar, über den Weg dazwischen ist allerdings nichts bekannt.<!--Was würde man denn als *class* angeben?--> Lautet der Satz hingegen *Die Kutsche fuhr aus Berlin in die Wälder, wobei die Fahrgäste dabei stundenlang nichts als Äcker und Wiesen zu sehen bekamen* ist eindeutig, wo sich das Objekt die meiste Zeit befand. <!--Also *rural*?-->

# Kategorie 2: *container*

Hier wird annotiert, ob eine NNSE einen Innenraum, einen Außenraum, eine Grenze oder eine beweglicher Entitäten darstellen. Die Kategorie *container* orientiert sich an [Dennerlein (2009,  S.71)](https://www.zotero.org/google-docs/?hkQP7m):   
“‚Raum‘ \[kann\] als Container \[verstanden werden\], \[in denen\] Räume durch die Merkmale Objekthaftigkeit, Wahrnehmungsunabhängigkeit, Diskretheit, eine Unterscheidung von innen und außen und die Zuordnung von Menschen und Dingen zu ihnen gekennzeichnet sind”. Weiter: "Jeder Raum ist potentiell wieder in einem größeren Raum enthalten, umgekehrt besteht jeder Raum aus diskreten Einzelräumen" (ebd., S. 60). 
_Objekthaft_ meint, dass Raum gegenständlich ist. _Wahrnehmungsunabhängig_ bennent die Eigenschaft, dass es irrelevant ist, ob Raum gerade durch Sinneseindrücke wahrgenommen wird, da er trotzdem "existiert". Unter _Diskret_ wird die Eigenschaft verstanden, dass Räume sich voneinander abgrenzen lassen. "Die räumliche (territoriale) Welt ist die Summe ihrer diskret begrenzten Raumausschnitte" (Dennerlein 1009, S.58). In dieser Arbeit werden zwei Ebenen von *container* postuliert:
- Die erste Ebene lässt sich nach Alltagswissen als "außen" beschreiben. Diese Ebene kann eine beliebe Anzahl an NNSE beinhalten, die wiederum selbst *container* sein können (z.B. ein *Haus*, eine *Höhle*, etc.).
- Die zweite Ebene lässt sich nach Alltagswissen als "drinnen" beschreiben, ist also in irgendeiner Form nach außen abgegrenzt (durch einen Zaun, Wände, etc.). Auch diese Ebene kann eine bliebige Anzahl an NNSE beinhalten, die theoretisch auch eigene *container* sein können (*Schlafzimmer* im *Haus*). Diese *container*, die auf einer theoretischen dritten Ebene verortet werden könnten, werden allerdings in diesem Modell nicht weiter berücksichtigt und inklusive weiterer NNSE als Teil der zweiten Ebene ohne weiterer Unterscheidung betrachtet.

Relevant für die Klassifizierung ist der *Point of View* der Erzählinstanz zum *Setting*. Diese Überlegung basiert auf Schumacher (2023, S. 44), bei der sie theoretische Überlegungen von Husserl und Kant zusammenführt. Figuren spielen für die Annotation soweit nur für die Zuweisung als Wert für *container* eine Rolle, darüber sind sie im Rahmen dieser Annotation irrelevant. <!--Unklar, warum Figuren hier erwähnt werden.-->

| *container* | Beschreibung und Beispiel |
|---|---|
| *exterior* | Alle NNSE, die sich  auf der ersten Ebene befinden.<!--Ebene?--> Meistens wird es sich um Außenräume handeln. *Wir überqueren die Straße.*; *Treffpunkt ist an der Kirche\!*; *Sie frühstückten an der Sitzecke im Garten*; *Sie betrachtete ihr neues Haus von der anderen Straßenseite.* |
| *interior* | Hierbei handelt es sich um NNSE, die auf der zweiten Ebene zu verorten sind. Meistens wird es sich um eine Art Innenraum handeln. *Das Wohnzimmer war ein einziges Chaos.*; *Der Tisch im Esszimmer war voll mit köstlichen Speisen.*; *Der blinde Mönch irrte durch die Burg.*, *Die Menschen in der <ins>Höhle</ins> sahen Schatten an den Wänden* |
| *threshold* | In Anlehnung an Juri Lotman’s Konzept der Grenze[^5] handelt es sich hier um NNSE, die die Grenze oder Schwelle zwischen *containern* kennzeichnen. *Eine <ins>Tür</ins> zum Haus stand offen.; *Das <ins>Fenster</ins> zum Garten war zerbrochen.* | <!--Meistens zwischen *exterior* und *interior*? Ich würde hier genauer erklären.-->
| *moving* | Hierunter fallen NNSE, die sich gerade in Bewegung befinden. Sie können sowohl auf der ersten als auch der zweiten Ebene verortet sein. *Die Kutsche fährt durch den Wald.*; *Das Schiff auf See ist der Witterung ausgesetzt* | <!--Ist *moving* ein container, oder nicht lieber ein class?-->

## Literaturverzeichnis

- Dennerlein, Katrin. 2009\. *Narratologie des Raumes*. Narratologia. Berlin, New York: Walter de Gruyter. https://doi.org/10.1515/9783110219920.  
- Glucksberg, Sam. 2001\. *Understanding Figurative Language*. Oxford University Press. https://doi.org/10.1093/acprof:oso/9780195111095.001.0001. 
- Lakoff, George, und Mark Johnson. 2011\. *Metaphors We Live by: With a New Afterword*. 6\. print. Chicago, Ill.: Univ. of Chicago Press. 
- Lotman, Juri. 1972\. *Die Struktur literarischer Texte*. Uni-Taschenbücher 103\. München: W. Fink.
- Ryan, Marie-Laure. 2014\. „Space“. In *the living handbook of narratology*. Hamburg: Hamburg University. https://www-archiv.fdm.uni-hamburg.de/lhn/node/55.html\#Herman2005. 
- Schumacher, Mareike K. 2023\. *Orte und Räume in Romanen*. Digitale Literaturwissenschaft. Berlin, Heidelberg: Springer Berlin Heidelberg. https://doi.org/10.1007/978-3-662-66035-5\_1.
- Tally, Robert T. 2018\. „The Space of the Novel“. In *The Cambridge Companion to the Novel*, herausgegeben von Eric Bulson, 1\. Auflage, 152–67. Cambridge University Press. https://doi.org/10.1017/9781316659694.011.
- Redepenning, Marc\. 2019\. „Stadt und Land“. In Dorf: Ein interdisziplinäres Handbuch, herausgegeben von Werner Nell und Marc Weiland, 1\. Auflage, 315–25. Stuttgart: J.B. Metzler. https://doi.org/10.1007/978-3-476-05449-4.

[^1]:  [https://www.projekt-gutenberg.org/gotthelf/spinne/spinne.html](https://www.projekt-gutenberg.org/gotthelf/spinne/spinne.html) 

[^2]:  [https://www.projekt-gutenberg.org/droste/judenbch/judenb1.html](https://www.projekt-gutenberg.org/droste/judenbch/judenb1.html) 

[^3]:  Zur Definition von *setting*, siehe [Ryan 2014, p.7](https://www.zotero.org/google-docs/?QOMzcY): *Setting: the general socio-historico-geographical environment in which the action takes place. In contrast to spatial frames, this is a relatively stable category which embraces the entire text.* Dies grenzt sich von den sogenannten *spatial frames* ab, die konkrete Orte in der Narrative darstellen. Einen ähnlichen Ansatz verfolgt [Tally 2018](https://www.zotero.org/google-docs/?EUBCrY), S. 154, mit der *story world*, die auch bei Ryan als Begriff fällt, allerdings in einem leicht anderen Kontext. Seine Definition ist “*the area in which events of the novel take place*”. Diese Definition ist allgemeiner,aber auch näher an dem *spatial frame* von Ryan orientiert. 

[^4]: Redepenning (2019) liefert einen guten Überblick über semantische Kategorien von Land und Stadt, die allerdings aus der Kulturwissenschaft und der Geographie entnommen wurden.

[^5]:  Siehe [Lotman (1972)](https://www.zotero.org/google-docs/?QrfU4C)
