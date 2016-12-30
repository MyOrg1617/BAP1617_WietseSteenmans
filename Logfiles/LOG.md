# Logboek **Michael Marivoet**

## Week 1 (15/02/16 - 21/02/16)
### Maandag
* Allereerst verdere kennismaking met stagementor, krijgen van een RFID kaart voor toegang tot het gebouw en login gegevens verkregen voor het WiFi netwerk. Verder kreeg ik een presentatie waarin
uitgelegd staat wat Agentschap Wegen & Verkeer/EMT hun functie is binnen de Vlaamse overheid. Nogmaals bespreken/verduidelijken wat er juist allemaal voor functionaliteit verwacht wordt van het project, bekijken wat de stagair
vorig jaar bereikt heeft. Ook is er besproken welke technologieën er gebruikt zullen worden (zie algemene README).
* Arduino code bekeken van vorig jaar en deze al lichtjes aangepast. 

### Dinsdag
* Verder bekijken van het python script van de Raspberry Pi, bekijken hoe we een deurslot zouden kunnen simileren en wat we hiervoor nodig hebben.
* Verder gewerkt aan het herwerken van Arduino code, deze afgewerkt, commentaar toegevoegd over de werking en deze getest of de commando's wel doorkomen.
* Uitzoeken hoe we best data van de analoge pinnen opslaan, zodat we die later kunnen opvragen en tonen in bijvoorbeeld een grafiek (in de frontend).

### Woensdag
* Instellen van de raspberry pi voor SSH en de bestaande python scripts bekijken. Uittesten bestaande code en zien hoe juist en wat er precies door de eReader wordt ingelezen en hoe
Artur dit verwerkt/oplost.
* Ook zitten uitdenken hoe we eventueel de admin accounts laat aanmaken voor de webapplicatie door het inlezen van de eID, waardoor deze geen formulier zou moeten invullen.
* Bekijken van de tutorials omtrent een video gesprek met een Raspberry Pi en een webbrowser, die Rik heeft doogestuurd gisteren.
* In de namiddag wilt de Raspberry Pi niet meer via SSH verbinden en mits ik geen HDMI kabel bij heb. Nog zitten proberen uit te zoeken hoe dit komt, zal ik morgen rechtstreeks bekijken wat het probleem is.

### Donderdag
* Op de virtuele server alle benodigdheden gëinstalleerd (LAMP stack, nodejs, phpmyadmin, etc.).
* Bekijken hoe we communicatie tussen Raspberry Pi en server best kunnen doen, hiervoor onderzoek gedaan omtrent MQTT, CoAP & AMQP protocol.
* Raspberry Pi probleem omtrent SSH was opgelost bij de volgende boot, voor de zekerheid heb ik deze rechstreeks verbonden met
het internet en alles geupdate.
* Verder gelezen omtrent artikels video gesprek & bekijken van het aansluiten van de webcam.

### Vrijdag
* Les: Professionalisering

## Week 2 (22/02/16 - 28/02/16)
### Maandag
* Aanpassing aan arduino seriële commando met oog op het gebruikt van MQTT.
* Verder onderzoek gedaan omtrent MQTT op Raspberry Pi en nodejs. Onderzocht of Node-Red kan gebruikt worden om makkelijker te ontwikkelen.
* Artikel van Rik gelezen omtrent mogelijk gebruik van HTSQL voor het weergeven van data op de webpage.
* Nagedacht over indeling van de tabellen in de MySQL database (opstellen schema later).
* Node-mysql doorgenomen.

### Dinsdag
* Laatste voorlopige aanpassingen aan Arduino code en nog de nodige uitleg over code toegevoegd.
* Nodige Node dependencies geïnstalleerd en Node test projectje gemaakt.
* Onderzoek gedaan naar gebruikers authenticatie met Node en de modules die hiervoor gebruikt kunnen worden.
* Raspberry Pi scipt bekeken en geraak nog altijd niet 100% uit aan de werking. Hiervoor heb ik een e-mail gestuurd naar mijn voorganger.

### Woensdag
* Verder onderzoek gedaan omtrent Raspberry Pi & eID kaart lezen, a.d.h.v. de informatie die ik heb verkregen van mijn voorganger en stagementor. Wou de werking begrijpen vooraleer ik verder ging.
* Opgezocht voor het aanmaken van cron jobs (Raspberry Pi) & daemons.
* Onderzoek gedaan omtrent socket.io voor nodejs, dat in combinatie met MQTT realtime informatie kan geven aan de webclient omtrent de status van de RaspberryPi.

### Donderdag
* Database aangemaakt voor gebruikers en die properties dat deze moet bevatten.
* Mosquitto (MQTT) broker geïnstalleerd op server
* Onderzoek gedaan naar Eclipse paho project, deze biedt een subscriber/publisher libraries aan voor zowel python (Raspberry Pi) als javascript (webapplicatie).

### Vrijdag
* Les: Professionalisering

## Week 3 (29/02/16 - 06/03/16)
### Maandag
* Onderzoek gedaan omtrent het vervangen van de MySQL server op de Raspberry Pi.
* Het aanpassen van de python scripts van mijn voorganger. Dit resulteerde door een onbekende reden in corruptie van de 2de partitie (waar commandfile zich bevindt).
* Tijdens het aanpassen van de python scripts viel de Raspberry Pi uit, na het herstarten van de Raspberry Pi kreeg ik een foutmelding terug en starte hij kdb (kernel debugger) op. De foutmelding gaf weer dat 
hij zijn boot partitie niet meer kon uitlezen. Na enkele artikels te lezen over de foutmelding op het Raspberry Pi forum, kwam ik tot de vaststelling dat GParted of fsck de mogelijkheid bieden om partities 
na te kijken en deze te repareren indien nodig. Hiervoor had ik dus Linux nodig en heb ik deze geïnstalleerd, het gebruiken van deze tools om de partitie op de SD kaart te repareren heeft niet geleidt tot 
resultaten. Hierna heb ik besloten in consensus met mijn stagebegeleider om met een schone lei te beginnen en dus een nieuwe image te installeren voor de Raspberry Pi.

### Dinsdag
* Verder gewerkt aan het repareren/formateren van het microSD kaartje en tot de consensus gekomen dat deze niet meer bruikbaar is, men kan enkel nog van het
kaartje lezen. Na hierover nog verder onderzoek te doen heb ik ontdekt dat dit waarschijnlijk het resultaat is van het bereiken van de maximum
schriijf cycli, hierdoor zet de microSD kaart zich in read only. Ik heb de volgende tools gebruikt om de partities te verwijderen, repareren en formateren.
Diskpart (via windows commandprompt), windows schijfbeheer, fsck (linux), Gparted (linux) &  SDFormatter v4.
* Verder ben ik ook begonnen aan het ontwikkelen van de webapplicatie zijn layout, dit heb ik gedaan terwijl de verschillende programma's/tools bezig waren
met de microSD kaart.

### Woensdag
* Nogmaals geprobeerd de microSD kaart te formatteren met diskpart, nogmaals geen resultaat. Hierna een test gedaan met een ander microSD kaartje waarop een nieuwe image van raspbian staat,
de Raspberry Pi had geen probleem hiermee te booten. Hierna besproken met de stagementor om een nieuwe microSD kaart aan te kopen.
* Mosquitto broker op server uitgetest en goede publisher/subscriber programma voor te testen gezocht en gevonden in de vorm van MQTT.fx, deze beschikt over een simpele en makkelijk GUI.
* Verder gewerkt aan frontend. Sticky footer toegevoegd en bezig geweest met het laden van de gewenste html code in een container d.m.v. angularjs.

### Donderdag
* Verder gewerkt een Raspberry Pi terug opnieuw te installeren (Raspbian Jessie lite image geinstalleerd) SSH enabled, python terug geïntalleerd, XFCE desktop (zonder goodies/extra programma's), etc.. 
Had hier wel enkele problemen met onder andere python te installeren, mits de Raspbian lite image ontbrekende dependencies had (hierdoor kon python, XFCE, etc. niet geïnstalleerd worden).
* Scripts van voorganger gerecupeerd en terug begonnen vanaf het begin met eigen python scripts en de scripts van de voorganger aan te passen.

### Vrijdag
* Les: Professionalisering

## Week 4 (07/03/16 - 13/03/16)
### Maandag
* XFCE verwijderd en LXDE geïnstalleerd, wegens problemen met Xming (reageerde zeer slecht en traag). Ik heb ook na onderzoek vernomen dat XFCE meer resources verbruikt dan LXDE.
* Python libraries geinstalleerd om te kunnen werken met smartcard reader (pyscard), sqlite databases, gpio pinnen raspberry & paho mqtt client. Doordat de ACSCCID driver ontbreekte kon ik nog niet
de pyscard libarary installeren, dze gave de error dat 'winscard.h' ontbreekte.
* Onderzoek gedaan omtrent het gebruiken van systemd om python scripts te doen starten bij het opstarten en ervoor te zorgen dat deze blijven werken bij een onderbreking of probleem.
* Installeren dependency voor smartcard reader library. ACSCCID, dit is een driver voor linux die het mogelijk maakt om met ACS CCID kaartlezers te communiceren. Ik kon deze driver niet installeren
omdat er dependencies waren die de driver nodig had en die ontbreken op het systeem. Dit werdt niet vermeld in het verslag van mij voorganger. Ik ben deze verder bezig geweest met het uitzoeken van welke
dependencies er ontbreken. 

### Dinsdag
* Verder gedaan met het uitzoeken naar ontbrekende dependencies, uiteindelijk bleken de volgende dependencies nodig te zijn:
    * **pcscd:** dit is een smart card deamon voor pcsc-lite. Het laat toe programma's toe om te communiceren met smartccard readers zondat dat deze details nodig heeft over de kaart of lezer.
    * **libusb:** c-library die toelaat programma's toegang te geven aan USB-apparaten.
* De reden waarom deze dependencies niet vermeld werden in de handleiding van mijn voorganger is omdat ik gebruik maakt de de *lite* image van Raspbian Jessie.
* Tijdens het installeren van de pyscard library via pip/PyPA (python package manager) deedt er zich een onbekende error voor en wou deze zich niet installeren. Na verder onderzoek bleek dat er een bug was
die ervoor zorgde dat als setup.py automatisch via pip wordt uitgevoerd deze de installatie niet correct uitvoerde. Om dit op te lossen moet de library handmatig worden gedownload en geïnstalleerd worden.
Dit stond vermeld op de blog van de ontwikkelaar.

### Woensdag
* Jobbeurs expo antwerpen

### Donderdag
* Testen of de smartcard reader werkt met de Raspberry Pi. Deze werkt nog altijd niet 100% wegens nog een onbekende ontbrekende dependency.
* Nog wat verder gewerkt aan frontend en angular-ui router toegevoegd, dit maakt het handig om kleinde stukken html code zeer makkelijk in te laden in een view.
* Begonnen aan backend met express. Hiervoor heb ik onder andere de package.json aangemaakt (zodat backend makkelijk opnieuw kan gegenereerd worden). Gezocht naar mqtt client v
* Uitwerken van topic generatie (mqtt) voor elke Raspberry Pi.

### Vrijdag
* Vrijaf genomen

## Week 5 (14/03/16 - 20/03/16)
### Maandag
* Verder gezocht naar het oplossen van de ontbrekende dependency voor de smart card reader. Ik heb uiteindelijk hiervoor een tutorial gevonden van Gemalto, deze produceert smart card readers
en heeft hiervoor een tutorial document gemaakt. [Link Tutorial](http://support.gemalto.com/fileadmin/user_upload/IAM/FAQ/How_to_install_the_PC-Link_reader_on_Linux.pdf)
* Ik heb ook de tools geïnstalleerd die in de tutorial stonden voor het nakijken of de smart card werkt.

### Dinsdag
* Getest met de tools die ik maandag had geïnstalleerd of de smart card reader wekte, deze functioneerde correct en ik kon mijn eigen eID uitlezen.
* Script voor het uitlezen van het nationaal nummer ontwikkelt door mijn voorganger overgekopieerd en aangepast.
* Onderzoek gedaan op de [sourceforge pagina](http://pyscard.sourceforge.net/) van pyscard of er een manier was om enkel belgische eID kaarten uit te lezen. Dit bleek mogelijk te zijn door de
smart card reader eerst de ATR (Answer To Reset) te lezen van de smartcard en na te kijken of deze een belgische eID is. Hierna zullen de commando's voor het uitlezen van het nationaal nummer worden uitgevoerd.

### Woensdag
* Script voor de smartcard aangepast door het implementeren van het nakijken ATR voor we het nationaal nummer uitlezen. Hierna heb ik de code getest met mijn eID en deze functioneerde perfect.
* Verder heb ik een functie in de pyscard library gevonden die een vorm van event listener implementeert. Deze laat het script slapen tot er een geldige kaart in de reader wordt geplaats. Dit is beter dan mij
origineel idee om elke seconde te gaan pollen of er een kaart aanwezig is, hierdoor voelt het voor de gebruiker aan of alles spontaan werkt in plaats van met een delay.
* Masterscript aangemaakt en hiervoor een service voorzien in  systemd, zodat deze automatisch opstart met het besturingssysteem en er een watchdog aanwezig is om het script te herstarten bij eventueel falen.

### Donderdag
* Onderzoek gedaan naar threading met python. Python beschikt over een threading libary die ook over een timer beschikt.
* Onderzoek gedaan naar een goede python config parser, om gemakkelijk een config file aan te maken en uit te lezen. Uiteindelijk bleek python standaard over een configparser te beschikken die perfect 
voldoet aan wat ik nodig heb.
* Test script om communicatie met de Arduino uit te testen geschreven. Deze communicatie gebeurt over een seriële verbinding.

### Vrijdag
* Les: Professionalisering

## Week 6 (21/03/16 - 27/03/16)
### Maandag
* Opgezocht wat de wettelijke minimum eisen zijn rondom het opslagen van het nationaal nummer. De wetgeving zegt dat Belgische openbare overheden het nationaal nummer wel mogen gebruiken en opslaan.
Men heeft wel vermeld in de opdracht dat het nationaal nummer niet in "plain-text" mag gedaan worden. Als oplossing heb ik hiervoor gevonden dat ik de nationaal nummers hash met (sha512) en dat ik
voor veiligheidsreden alleen de gehashte nationale nummers verstuur naar de database op de Raspberry Pi zonder overige informatie van de gebruiker.
    [Bron 1](http://economie.fgov.be/nl/binaries/eID-IBM_study_nl_tcm325-73359.pdf)
    [Bron 2](https://www.privacycommission.be/sites/privacycommission/files/documents/beraadslaging_RR_09_2013.pdf)
* Hierna heb ik het volgend zitten implementeren in het python script. Het nationaal nummer dat wordt uitgelezen door de smartcard reader wordt gehasht met sha512 hierna wordt er gekeken in de 
database of deze hash voorkomt. Indien deze statement is voldaan, dan zal de deur geopend worden. 

### Dinsdag
* Verder gedaan aan het implementeren van toegang tot installatie met eID. Ik had hier een probleem met toegang te krijgen tot de SQlite database op de Raspberry Pi, dit is opgelost
door eerst dit script te testen en schrijven op mijn eigen PC in plaats vand de Raspberry Pi.
* Script nog wat opgekuist, commentaar toegevoegd en wat extra functionaliteit. Zoals onder andere als men 3x een niet toegestande eID gebruikt, zal de installatie 1 minuut geen validatie toelaten.

### Woensdag
* Verder onderzoek gedaan rondom multithreading met Python en wat de beste praktijken omtrent hiervan zijn. Multithreading geimplementeerd voor het "card_reader script" en "pin_status script".
Het pin status script, verzend de status van de analoge en digitale pinnen naar de server.
* Ondervonden dat er een probleem is met systemd service, deze voert het script niet uit bij het booten, hiervoor heb ik onderzoek gedaan waarom dit kwam. Systemd geeft de error status '203' terug.
Dit zou komen door verschillende problemen, onder andere met de rechten die de file heeft, de volgende oorzaken heb ik al bekeken/opgelost.
    * File kan niet uitgevoerd worden door ontbrekende rechten => chmod +x gebruikt om bestand rechten te geven, dit haalde niets uit.
    * Geen shebang aanwezig in het script => shebang is/was aanwezig.
    * ExecStart aangepast met verwijzing naar python interpreter => dit haalde niets uit.
    * Bestand bevond zich in de Desktop van de Pi user ik heb deze verplaats naar een eigen directory na root => dit haalde niets uit.
* Ik hoop dit probleem op te lossen door dit hiervoor een post op stackoverflow te plaatsen.

### Donderdag
* Begonnen aan het database update script, dit script doet een aanvraag aan de server of er al nieuwe gebruikers zijn sinds de laatste update. Deze datum wordt in het config.ini bestand weggeschreven
opgezocht en elke geupdate indien er een succesvolle aanvraag is geweest.
* Late namiddag Node.js conferentie gevolgt bij Digipolis (Technolgie beurs/meeting Professionalisering)

### Vrijdag
* Vrijaf genomen

## **Paasvakantie (28/03/16 - 10/04/16)**

## Week 7 (11/04/16 - 17/04/16)
### Maandag
* Verder gewerkt een het updatescript en hiervoor een API ontworpen. De Raspberry Pi doet een POST request naar de server met de volgende informatie, het installatie nummer en/of id en
de datum waarop de lokale database laatste een update heeft ontvangen. Hierna zullen alle nieuwe nationalenummers sinds die datum worden verstuurd naar de Raspberry Pi, die deze dan aan
de lokale database toevoegd. 
* [U4VL](http://www.linux-projects.org/modules/news/) oftewel User space Video4Linux. Dit is een set tools met ondersteuning voor Raspberry Pi & WebRTC dit ik wil gaan
gebruiken voor de video/audi chat functionaliteit. Ik heb hierover onderzoek gedaan en deze al op de Raspberry Pi geïnstalleerd. Ik heb hiermee ook al proberen te werken, maar
dit heeft nog geen vruchtbaar resultaat geleverd.
* Voor de webcam is definitief besloten om de Sony (PS3) eye camera te gebruiken, dit om enkele reden. Het kan aangesloten worden via een USB verbinding, wordt ondersteunt door
de Raspberry Pi, heeft een ingebouwde microfoon en tenslotte beschik ik al over de hardware.

### Dinsdag
* Tussentijdse presentatie bachelorproef

### Woensdag
* Verder gewerkt aan de PS3 camera te kunnen laten werken op de Raspberry Pi. Dit is me momenteel niet gelukt, hiervoor ga ik nogmaals de tutorials die de stagebegeleider heeft
doorgestuurd bekijken.
* Ik heb nader besloten eerst verder te werken aan de overige functionaliteit en hierna terug tijd te besteden aan de video/audio chat funcitonaliteit. Ik blijf wel zeker
of het feit dat de Raspberry Pi B+ model niet krachtig genoeg is om dit met vrucht te kunnen realiseren. 

### Donderdag
* Verder de bootcyclus gewerkt, volgende week zal ik bespreken wat er nog van bijkomende informatie moet worden meegegeven eventueel en de bootcyclus hiervoor verder aanpassen. Deze
aanpassingen zullen afhangen van wat de stagementor nog graag aan extra functionaliteit wilt.
* HTTPS voor Node.js onderzocht. Uitgezocht hoe dit moet worden geïmplementeerd en dit dan ook geïmplementeerd. Ik maak momenteel gebruik van een Self Signed Certificate. Dit zelfde
principe zal ik terug opnieuw moeten uitvoeren om het MQTT verkeer ook te encrypteren. Ik had hier wel een probleem met het foutief genereren van de certificaten waardoor er geen
https verbinding kan aangemaakt worden. Ook heb ik onvervonden doordat ik momenteel geen standaard poort gebruik voor http(s) verkeer, ik voor de URL altijd naar het juiste protocol moet
verwijzen indien ik HTTPS verbinding wil maken (= "https://" gebruiken). 

### Vrijdag
* Vrijaf genomen

## Week 8 (18/04/16 - 24/04/16)
### Maandag
* Besproken met stagementor wat er precies nog van informatie in de database moet komen en wat er nog aan functionaliteit zou moeten worden toegevoegd.
* Bootcyclus aangepast, het systeem dat ik nu gebruik waarbij elke Raspberry Pi standaard hetzelfde paswoord krijgt om als validatie te gebruiken voor het 
consumeren van bepaalde services is onveilig. Hier moet ik dus een oplossing worden gevonden. Hiervoor denk ik het volgende systeem te implementeren, alle nieuwe aangemelde installaties
krijgen een boolean waarde dat weergeeft dat ze nieuw zijn en hierdoor limieten hebben in verband met privileges. In de webapplicatie moet de administrator eerst valideren of de installatie
geldig is. 

### Dinsdag
* Feedback gekregen van de stagementor over de bespreking van gisteren. Hij heeft een document opgesteld met de extra verwachte functionaliteit en wat hij verwacht van
data in de master database.
* Bekeken of we niet [MOSCA](https://github.com/mcollina/mosca) kunnen gebruiken i.p.v. Mosquitto als MQTT broker. Dit is een MQTT broker voor Node.js en zou het probleem elimineren
 van een aparte service/server voor de MQTT.
* Om de extra functionaliteit te implementeren en het overzichtelijk te houden ben ik begonnen met het tekenen van flowcharts van de software. Momenteel zijn deze met de hand getekend, maar
deze zullen later gedigitaliseerd worden en toegevoegd worden aan de scriptie.

### Woensdag
* Master database aangepast:
    * Installaties db toegevoegd met de volgende tabellen: Installaties, InstallatieTypes
    * Users db aangepast met bijkomende informatie die de stagementor wou over de gebruikers zoals woonplaats, telefoon zowel landlijn als mobiel nummer. Ook is er een
     systeem gewenst van verschillende security levels voor de gebruikers, met elk een eigen aantal privileges.
     * Data db toegevoegd deze database bevat tabellen voor de data die door de sensoren verzameld wordt
* Nagedacht en onderzoek gedaan naar hoe ik best de data van de sensoren verwerk. De berichten rechtstreeks opslaan in de database en later verwerken naar de juiste tabellen of deze
rechtstreeks verwerken. Hierbij blijft de vraag hoe groot de delay wordt tussen het verwerken van de berichten, wanneer we scalen naar meer dan één Raspberry Pi.

### Donderdag
* Aanpassing gedaan omtrent het updaten van de lokale database met nationale nummers. Hiervoor liet ik de Raspberry Pi bijhouden wanneer de database laatst was geupdate, dit heb ik
verandert naar dat de masterdatabase dit doet en de Raspberry Pi zich moet inloggen.
* De Raspberry Pi krijgt nu tijdens de random bootcyclus een random paswoord toegewezen, deze wordt in combinatie met de installatienummer (deze is uniek) gebruikt om in te loggen en
bepaalde services te kunnen consumeren (zoals updaten van de lokale database met nieuwe nationale nummers).
* Nog altijd geen oplossing bedacht voor het volgende probleem. Wanneer er meerdere Raspberry Pi's in één installatie worden gebruikt hoe ik alleen voor de eerste Raspberry Pi hardcoded
poorten voorzie voor het sturen van het deurslot en voor nazicht of de deur open of toe is. De overige Raspberry's zouden de dan toch niet gebruikte poorten moeten kunnen gebruiken.

### Vrijdag
* Kickstarterdag Ordina (jobbeurs Professionalisering)

## Week 9 (25/04/16 - 01/05/16)
### Maandag
* Verder gewerkt aan bootcyclus, ik had hier problemen met requests module. Deze was al geïnstalleerd omdat ik de python package manager had geïnstalleerd. Door dit handmatig opnieuw te installeren met sudo
command, had ik een ImportError als ik de python package manager wouw gebruiken. Ik heb dit na wat onderzoek met het 
volgende [stackoverflow artikel](http://stackoverflow.com/questions/27341064/how-do-i-fix-importerror-cannot-import-name-incompleteread) kunnen oplossen. Ik wou de nieuwste versie van pyscard downloaden
de ontwikkelaar had namelijk een bug opgelost die ervoor zorgde dat pyscard niet via de package manager geïnstalleerd kon worden. Dit zou handig zijn om eventueel een bash script te ontwikkelen die automatisch 
alles installeerd van dependencies op de Raspberry Pi.
* Probleem met de UV4L deamon, deze crashed om de zoveel tijd. Het is nog ook altijd niet mogelijk om de videofeed van de PS3 eye weer te geven in de browser.
* Na wat onderzoek heb ik door de extra's van UV4L te downloaden het probleem met de crashende deamon voorlopig kunnen oplossen.

### Dinsdag
* Nog altijd niet in staat beeld te krijgen van de PS3 eye. Ik heb hierna besloten om te kunnen testen of ik in staat ben video beeld te verkrijgen motion te installeren. Motion is de library die Artur vorig 
academie jaar heeft gebruikt om videobeelden te kunnen streamen. Deze driver heeft wel het nadeel niet echt in staat te zijn audio live te streamen en geeft geen mogelijkheden voor wederzijdse
communicatie.
* Ik ben ook niet in staat via motion video beelden te streamen naar de browser, ook al gebruik ik de instellingen van Artur aan de hand van hoe hij deze heeft beschreven in zijn scriptie. Ik heb hierna tevergeefs
enkele online tutorials gevolgd met geen resultaat.

### Woensdag
* Wegens weinig resultaat te boeken met de video/audiochat heb ik besloten met te focussen op de webapplicatie. Ik heb besloten een bootstrap template te gebruiken voor de applicatie zelf.
Ik maak hier gebruik van een vrij te gebruiken template die [hier](http://startbootstrap.com/template-overviews/sb-admin/) terug te vinden is. Ik had hiervoor al een eigen template ontworpen, maar deze zoveel
teveel tijd kosten om verder te ontwikkelen.
* Deze heb ik verder liggen aanpassen voor eigen gebruik. Ik heb onder andere de chat/notificatie elementen verwijderd, de overige pagina's van het menu verwijderd. Deze zijn toch niet nodig
mits ik angular-ui-route ga gebruiken. Deze library laat toe dynamisch html content in een container te laden.

### Donderdag
* Nogmaals een poging gevolgd om de webRTC tutorial van UV4L te volgen, ik heb hier ontdekt dat enkel de Raspberry Pi 2 ondersteuning heeft van UV4L voor webRTC. Mits ik momenteel enkel beschik Raspberry Pi
B+. Ik heb verder nog enkele tutorials gevolgd om met motion te werken, maar dit had ook geen resultaat.

### Vrijdag
* Vrijaf genomen

<!--The End-->
