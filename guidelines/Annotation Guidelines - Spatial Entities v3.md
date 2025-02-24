# Guidelines für die Annotation von Non-Named Spatial Entities 

## Version 3

Ziel ist es, in literarischen Prosatexten, die ungefähr zwischen 1784 und 1918 veröffentlicht wurden, alle *Non-Named Spatial Entities* (=NNSE) zu annotieren. Ziel ist es, aus diesen ein semantisches Netzwerk zu erstellen, welches die Raumsemantik in Anlehnung an Juri Lotrman (1972) widerspiegelt. Wir definieren NNSE wie folgt:

Unter NNSE wird prinzipiell eine konkret räumlich verortbare Einheit verstanden, die nicht ohne Aufwand von einer oder einer kleinen Anzahl an Personen bewegt werden kann. Auch Gegenstände, die für einen bestimmten Platz gedacht sind, fallen hier rein. Beispiele sind: *Baum*, *Kirche*, *Berg*, *Möbel*, *Tischlampe*, *Straße*, *Stadt*. Ausgeschlossen sind Objekte und Gegenstände, die von Personen mitgeführt oder genutzt werden können. Beispiele  für Objekte und Gegenstände sind: *Flasche*, *Werkzeug*, *Besteck*, *Tasche*. Begriffe wie *Landstrich*, *Himmel* oder *Horizont* sind potentiell verortbar und es muss im Detail evaluiert werden, ob die Begriffe in der jeweiligen Textstelle der Definition von NNSE entsprechen.

Resultat dieser Annotation ist die Erstellung eines Datensatzes, mit dem entweder dedizierte ML-Classifier trainiert oder der Einsatz von LLMs evaluiert werden können. Als Basis werden fünf Sätze als nukleare Einheit verwendet, die annotiert werden sollen. 

## Überblick Guidelines

Es werden insgesamt drei Klassen für jede NNSE annotiert: *category*, *container* und *language use*. Für jede der drei Klassen muss ein Werte aus einer vorher definierten Liste eingetragen werden. Mehr als ein Wert pro Kategorie ist nicht zulässig. Für jede NNSE muss ein Wert für jede der drei Klassen vorhanden sein. Ein Beispiel ist:  

	Über die <Berge> hob sich die Sonne, leuchtete in klarer Majestät in ein freundliches, aber enges Tal und weckte zu fröhlichem Leben die Geschöpfe, die geschaffen sind, an der Sonne ihres Lebens sich zu freuen. (Jeremias Gotthelf, Die Schwarze Spinne[^1]) 

`NNSE: Berge`  
`|--- Category: natural`  
`|--- Container: exterior`  
`|--- Language Use: literal`  

In dem folgenden Beispiel sind *Fabrik* und *Heerstraßen* keine NNSE, da sie keine konkreten Orte benennen:  

	Friedrich Mergel, geboren 1738, war der einzige Sohn eines sogenannten Halbmeiers oder Grundeigentümers geringerer Klasse im Dorfe B. [...]. Das Ländchen, dem es angehörte, war damals einer jener abgeschlossenen Erdwinkel ohne <Fabriken> und Handel, ohne <Heerstraßen>, wo noch ein fremdes Gesicht Aufsehen erregte und eine Reise von dreißig Meilen selbst den Vornehmeren zum Ulysses seiner Gegend machte \[...\]. (Annette von Droste-Hülshoff, Die Judenbuche[^2])

Für jede Klassen wird eine Definition der einzelnen zulässigen Werte inklusive Beispiel gegeben. Generell sind hier alle Beispiele im Kursiv geschrieben und falls diese länger sind, ist die NNSE unterstrichen. Für alle Textstellen ist es möglich, unklare Fälle zu kennzeichnen. Es ist immer möglich, für unbestimmbare Klassen *unclear* einzutragen.

# Class 1: *category*

Für eine tiefergehende literarische Analyse sollen drei *categories* von NNSE analysiert werden. Bei diesen handelt es sich um aus der Literaturwissenschaft heraus motivierte diskrete semantische Räume, die es im *setting[^3]* geben kann. Diese sind *urban*, *rural* und *natural*. Zu welcher *category* eine NNSE gehört, ergibt sich aus dem Kontext, in dem sie auftaucht und bestimmt sich darüber, ob viele Strukturen von Menschen errichtet wurden.. Die Beschreibung der *categories*:
| *category* | Beschreibung und Beispiele |
|---|---|
| *urban* | Zu dieser *category* gehören NNSE in einer stark urbanisierten Umgebung, also Groß- und Kleinstädte. Auch Stadt- und Industrieparks und ähnliches fallen darunter. Generell ein Raum, in dem viele menschengemachte Strukturen vorhanden sind. *Der Marktplatz in Berlin war gut besucht.*; *Die Häuser in dem Slum  ragten wie Zähne aus der Stadt.* |
| *rural* | Zu dieser *category* gehören NNSE in einer schwächer urbanisierten Umgebung, also Dörfer, Agrarflächen und touristisch erschlossene Gebiete (Skigebiet, etc.). In diesem Raum sind mäßig viele menschengemachten Strukturen zu finden. *Die Ernte auf dem Feld war sehr erträglich.*; *Das Bauernhaus stand einsam am Rande des Dorfes.* |
| *natural* | Zu dieser *category* gehören NNSE in einer kaum urbanisierter Umgebung, wie Waldgebiete, Gebirge, Seen oder Wüsten. Einzelne Gebäude oder Infrastrukturen wie Wanderwege und \-hütten und Ähnliches fallen auch darunter. Menschengemachte Strukturen finden sich hier nur vereinzelt wieder. *Der Bach im Wald ist eiskalt.*; *Vor der einsamen Abtei* *im Wald schauert es mir\!* |

In manchen Fällen ist es nötig zu überprüfen, zu welcher *category* die NNSE gehört. Im Satz *Der Steg der Stadt reicht bis ins Meer* würde *Steg* als *categroy urban* klassifiziert werden, da er von Menschen gebaut wurde und Teil der Stadt ist.

# Language Use

Hier wird die Unterscheidung getroffen, ob ein eigentlicher (*literal*) oder ein uneigentlicher (*figurative*) Sprachgebrauch vorliegt. Die Definition von uneigentlichen Sprachgebrauch orientiert sich an [Lakoff und Johnson (2011)](https://www.zotero.org/google-docs/?LWLmLO).[^4] Eine Erläuterung der beiden Werte folgt:

| *language use* | Beschreibung und Beispiel |
|---|---|
| *literal* | Konkreter Gebrauch wäre nach Schumacher “konkret lokalisierbare Einheiten.”[^5] Die NNSE wird nicht von ihrem ursprünglichen Bedeutungskontext in einen anderen Kontext übertragen. *Sie betreten die Kirche im Dorf; Sie standen auf dem Weg; Im Wald neben dem Dorf stehen Bäume*  |
| *figurative* | Figurativer Gebrauch liegt vor, wenn eine NNSE von einem Bedeutungskontext in einen anderen Bedeutungskontext übertragen wird, wobei der neue Kontext auf der ursprünglichen Bedeutung aufbaut. *Lass mal die Kirche im Dorf\!*; *Auf den Weg machen; den Wald vor lauter Bäumen nicht sehen* |

# Container

Hier wird annotiert, ob eine NNSE einen Innenraum oder ob sie einen Außenraum darstellt, wobei zwei weitere Problemfelder \-  das der Grenze und beweglicher Entitäten \- behandelt werden. Die Kategorie *container* orientiert sich an [Dennerlein (2009,  S.71)](https://www.zotero.org/google-docs/?hkQP7m):   
“‚Raum‘ \[kann\] als Container \[verstanden werden\], \[in denen\] Räume durch die Merkmale Objekthaftigkeit, Wahrnehmungsunabhängigkeit, Diskretheit, eine Unterscheidung von innen und außen und die Zuordnung von Menschen und Dingen zu ihnen gekennzeichnet sind”.  
Figuren spielen für die Annotation soweit nur für die Zuweisung als Wert für *container* eine Rolle, darüber sind sie im Rahmen dieser Annotation irrelevant. 

| *container* | Beschreibung und Beispiel |
|---|---|
| *exterior* | Alle NNSE, die nicht nach Dennerlein als Container verstanden werden können, da sie weder objekthaft oder diskret sind. Meistens wird es sich um Außenräume handeln. *Wir überqueren die Straße.*; *Treffpunkt ist an der Kirche\!*; *Sie frühstückten an der Sitzecke im Garten* |
| *interior* | Hierbei handelt es sich um gerade unbewegliche NNSE, in die Figuren hinein gehen können und die physisch von dem restlichen *setting* abgetrennt sind. Meistens wird es sich um eine Art Innenraum handeln. *Das Wohnzimmer war ein einziges Chaos.*; *Der Tisch im Esszimmer war voll mit köstlichen Speisen.* |
| *threshold* | In Anlehnung an Juri Lotman’s Konzept der Grenze[^6] handelt es sich hier um NNSE, die die Grenze oder Schwelle zwischen *interior* und *exterior* kennzeichnen. *Eine Tür zum Haus stand offen.;* Das *Fenster zum Garten war zerbrochen.* **nicht aber** *Die Tür zum Wohnzimmer stand offen.; Die Dachbodenluke klemmte.* |
| *moving* | Hierunter fallen NNSE, die sich gerade in Bewegung befinden. In vielen Fällen werden sich die Werte *interior* und *exterior* nur durch die in der Handlung gerade stattfindende Bewegung unterschieden. *Die Kutsche fährt durch den Wald.; Das Schiff auf See ist der Witterung ausgesetzt* |

## Literaturverzeichnis

[Dennerlein, Katrin. 2009\. *Narratologie des Raumes*. Narratologia. Berlin, New York: Walter de Gruyter. https://doi.org/10.1515/9783110219920.](https://www.zotero.org/google-docs/?gp46DU)  
[Glucksberg, Sam. 2001\. *Understanding Figurative Language*. Oxford University Press. https://doi.org/10.1093/acprof:oso/9780195111095.001.0001.](https://www.zotero.org/google-docs/?gp46DU)  
[Lakoff, George, und Mark Johnson. 2011\. *Metaphors We Live by: With a New Afterword*. 6\. print. Chicago, Ill.: Univ. of Chicago Press.](https://www.zotero.org/google-docs/?gp46DU)  
[Lotman, Juri. 1972\. *Die Struktur literarischer Texte*. Uni-Taschenbücher 103\. München: W. Fink.](https://www.zotero.org/google-docs/?gp46DU)  
[Ryan, Marie-Laure. 2014\. „Space“. In *the living handbook of narratology*. Hamburg: Hamburg University. https://www-archiv.fdm.uni-hamburg.de/lhn/node/55.html\#Herman2005.](https://www.zotero.org/google-docs/?gp46DU)  
[Schumacher, Mareike K. 2023\. *Orte und Räume in Romanen*. Digitale Literaturwissenschaft. Berlin, Heidelberg: Springer Berlin Heidelberg. https://doi.org/10.1007/978-3-662-66035-5\_1.](https://www.zotero.org/google-docs/?gp46DU)  
[Tally, Robert T. 2018\. „The Space of the Novel“. In *The Cambridge Companion to the Novel*, herausgegeben von Eric Bulson, 1\. Aufl., 152–67. Cambridge University Press. https://doi.org/10.1017/9781316659694.011.](https://www.zotero.org/google-docs/?gp46DU)

[^1]:  [https://www.projekt-gutenberg.org/gotthelf/spinne/spinne.html](https://www.projekt-gutenberg.org/gotthelf/spinne/spinne.html) 

[^2]:  [https://www.projekt-gutenberg.org/droste/judenbch/judenb1.html](https://www.projekt-gutenberg.org/droste/judenbch/judenb1.html) 

[^3]:  Zur Definition von *setting*, siehe [Ryan 2014, p.7](https://www.zotero.org/google-docs/?QOMzcY): *Setting: the general socio-historico-geographical environment in which the action takes place. In contrast to spatial frames, this is a relatively stable category which embraces the entire text.* Dies grenzt sich von den sogenannten *spatial frames* ab, die konkrete Orte in der Narrative darstellen. Einen ähnlichen Ansatz verfolgt [Tally 2018](https://www.zotero.org/google-docs/?EUBCrY), S. 154, mit der *story world*, die auch bei Ryan als Begriff fällt, allerdings in einem leicht anderen Kontext. Seine Definition ist “*the area in which events of the novel take place*”. Diese Definition ist allgemeiner,aber auch näher an dem *spatial frame* von Ryan orientiert. 

[^4]:  Lakoff und Johnson entwickelten 1980 die weite Definition für Metaphern: “*The essence of metaphor is understanding and experiencing one kind of thing in terms of another.*” Sam [Glucksberg (2001, S. 9\)](https://www.zotero.org/google-docs/?7Z45ny) kritisiert diese weite Definition, liefert aber auch eine Definition für eigentlichen und uneigentlichen Sprachgebrauch: “*Literal meaning is basic and has unconditional priority. Implicit in this assumption is a corollary assumption: that literal meaning is unproblematic and is context-free, that is, the literal meanings of expressions remain unchanged regardless of context of use. \[...\] Figurative meaning is derived from the literal and can be discovered by discovering the nature of the substitution of the metaphorical for the literal.*”

[^5]:  Siehe [(Schumacher 2023, S. 65\)](https://www.zotero.org/google-docs/?NQs2O2). Dennerlein (2009, S. 48\) versteht konkreten Raum “sinnlich, anschaulich gegeben”.

[^6]:  Siehe [Lotman (1972)](https://www.zotero.org/google-docs/?QrfU4C)
