
=====================================
Tiedonhallintamenetelmät Fenfire 2005
=====================================



------------------------------------------------------------
Fenix / tietämyksen hallinta
------------------------------------------------------------



Lähtökohta
==========

Nykypäivän tietokone ympäristöineen rajoittaa tietotyöläisiä, jotka
joutuvat tyytymään niihin tiedon esitysmalleihin jotka suunnittelija
on tehnyt heidän puolestaan ohjelmistoihin, ja jotka samalla
hajauttavat ja sirpaloivat tietoa eri ohjelmistojen välillä.

Esimerkiksi samainen henkilö voi esiintyä kuutena eri henkilötietona
kuudessa eri ohjelmistossa, kuten osoitekirjassa,
sähköpostisovelluksessa ja projektinhallintasovelluksessa, sekä tämän
lisäksi kyseinen henkilö voi esiintyä lukuisissa tekstidokumenteissa
ilman minkäänlaista yhteyttä näihin henkilötietoihin eri
sovelluksissa.

Kun sovellusten tietomallit eivät ole riittävät, käyttäjä ei voi
laajentaa niitä. Esimerkkinä esitelmä: miten esitelmän pitäjä voi
kirjata saadun kommentin ja kommentin esittäjän tiedot? Hän ei voi
säilyttää tätä tietoa osoitekirja- tai sähköpostisovellukseensa;
mieluumminkin hän luo uuden tekstidokumentin tarkoitusta varten,
jota ei myöskään voi mitenkään liittää mainittuihin sovelluksiin.

Semanttisen webin teknologiat lupaavat tarjota ratkaisun
ongelmaan. Toisin kuin tiedon mallintamiseen suunnitellut edeltävät
teknologiat: tietokannat, XML tai olio-ohjelmointi, semanttinen webbi
rakentuu identiteeteistä jotka vastaavat reaalimaailman
asioita. Semanttisella webillä on siis luonnollista kuvata Maijan
Outlookissa listattu Liisa Nieminen samaiseksi Liisaksi, joka asustaa
myös Matin Mozilla Thunderbirdissä. Teknologia mahdollistaa tämän
päättelyn automaattisesti, esimerkiksi jos heille on annettu sama
kotisivu ja sähköpostiosoite.

Lisäksi semanttinen webbi mahdollistaa tietomallien laajentamisen
huoletta. Palataksemme aikaisempaan esimerkkiin esitelmästä, olisi
mitäänsanomattoman helppoa lisätä annettu kommentti esitelmän
yhteyteen sekä liittää tähän kommenttiin kommentoijan
sähköpostiosoite, joka automaattisesti sisäistettäisiin yhteytenä
kommentin antaneeseen ihmiseen.

Joten, rakenteettoman tekstidokumentin luomisen sijaan, oletettu
tietotyöläisemme vain lisäisi uuden yhteyden, ja näin yhdistäisi
asioita jotka jo ovat järjestelmässä. Sen sijaan, että ilman
yhteyksiä asioiden välillä, tiedot levittäytyisivät ympäri tietokoneen
kovalevyä ja niiden löytäminen olisi paljon kiinni käyttäjän omasta
muistista.


Fenfire
=======

Semanttiseen webbiin perustuva järjestelmä tarjoaisi voimallisen ja
joustavan ympäristön tietotyöläisille. Useissa tapauksissa se
mahdollistaisi tiedon mallintamisen juuri käyttäjän mieltämällä
tavalla, paljon lähempänä itse tietotyön tarpeita, kuin kiinteisiin
malleihin luodut sovellukset ja ohjelmistot ikinä
pystyvät. Rakenteettomat Excel-taulukot tai tekstidokumentit
korvikkeena ohjelmistolle joka vastaisi käyttäjän tarpeita, eivät
olisi enää tarpeellisia.

On suorastaan luonnollista löytää yrityksiä käyttää semanttisen webin
teknologiaa "Semanttisen työpöydän" rakentamiseksi. Fenfire-projekti
on pyrkimys täyttäää tämä yritys. Fenfiren lisäksi olemme tietoisia
kahdesta muusta projektista, jotka työskentelevät asian hyväksi.

- *Gnowsis*, vapaaohjelmisto jota kehittää saksalainen
   tutkimus-instituutti, jonka kanssa meillä on yhteistyötä. Heidän
   näkemyksensä on integroida nykyisten ohjelmistojen
   tietojärjestelmät semanttisen webin muotoon, ja näin mahdollistaa
   käyttäjän luoda yhteyksiä tietojen välille.

   Gnowsisilla on konservatiivinen näkemys käyttöliittymästä, sillä se
   lisää vain kaksi painonappia integroitaviin ohjelmistoihin
   ("selaa", joka avaa valitun asian Gnowsikseen, ja "linkitä", jonka
   avulla voidaan luoda uusia yhteyksiä).

- *Haystack*, on myös vapaaohjelmisto. Se on kehitetty
   tutkimusprojektissa Massachusetts Institute of Technology:n
   tutkimuslaitoksessa. Haystack tarjoaa käyttöliittymän joka
   muistuttaa webbiselainta, ja jossa on laajennettava joukko näkymiä
   jotka sopivat erilaisten tietojen tarkasteluun. Haystackin näkymät
   ovat samankaltaisia kuin nykyisen webin lomakkeet, ja jotka on
   luotu ohjelmoijien tai kokeneiden käyttäjien toimesta erillisellä
   kuvauskielellä. Toisin kuin tavanomaiset lomakkeet, Haystackin eri
   näkymät voivat kuvata samaa lomaketta samaan aikaan.

Kaikesta huolimatta meidän tietojemme mukaan kumpikaan projekteista ei
aseta tavoitteekseen käyttäjän luoda omia integroituja "sovelluksiaan"
käyttämällä paloja toisista ohjelmista ja laajentamalla niitä käyttäen
uusia yhteystyyppejä eri asioiden välillä. Tämä tavoite, jonka me
näemme täysin heijastavan semanttisen webin laajamittaisesti
käyttöliittymässä, ja näin tuoden semanttisen webin *käyttäjälle*
toisin kuin pelkästään *ohjelmoijalle*, on asia joka tekee
Fenfire-projektista yksilöllisen. (Sana "sovellukset" on
lainausmerkeissä, koska kuvaamassamme järjestelmässä ne eivät tule
olemaan yhtä merkittävästi ja yksioikoisella tavalla läsnä mitä ne
tänä päivänä ovat.)

Saavuttaaksemme tämän tavoitteen Fenfire visualisoi yhteydet asioiden
välillä ja tekee tästä olennainen osan käyttöliittymää. Kun jotain
asiaa tarkastellaan järjestelmässä, Fenfire esittää siihen liittyvät
muut asiat tämän ympärillä, yhdistäen nämä viivoin keskellä olevaan
tarkasteltavaan asiaan.

Milloin tahansa Fenfire "sovelluksen" tarvitessa yhdistäää kaksi asiaa
toisiinsa -- esimerkiksi sähköposti lähettäjäänsä -- tai esittää
muistiinpano jostain asiasta -- esimerkiksi sähköpostin tärkeys --
yksinkertaisin asia tehdä tämä on antaa Fenfiren esittää yhteys.

Kun käyttäjän yhdistelemät, hänen itse luomansa yhdistetyypit
esitetään järjestelmässä samalla tavoin, ellei toisin määritelty, nämä
yhteydet eivät ilmesty jonnekkin outoon paikkaan, vaan näkyvät
järjestelmässä aivan samoin kuin mikä tahansa muukin yhteys
"sovelluksien" välillä. Jopa yhteys eri "sovellusten" välillä on
samanlainen kuin yhteys "sovelluksen" sisällä.

Näin ollen "sovellusten" välillä ei esiinny rajoja, ja vain pieniä
rajoitteita tietotyöläisen luoda omia "sovelluksia".

Tarkempaa tietoa Fenfiren toimintatavoista on kuvattuna liitteenä
olevissa artikkeleissa, joissa on myös kuvakaappauksia.



Projektin tavoitellut tulokset
==============================

Fenfiren pohjimmainen tavoite on luoda työpöytäympäristö
tietotyöläisille jossa:

1. tieto on rakentunut yhteyksistä reaalimaailman asioihin, kuten
   ihmisiin, projekteihin, ennemmin kuin keinotekoisiin konsepteihin,
   kuten sovelluksiin ja kansioihin;

2. käyttäjä voi helposti laajentaa käytettäviä yhteyksiä ja näkymiä
   tiedon esittämiseen, ja näin luoda omia "sovelluksia";

3. tieto on jaettavissa ilman kommervenkkejä eri käyttäjien välillä
   tukien täysin versiointia ja yhteistyötä.

Tavoitellut päämäärät Fenix projektille ovat:

- valmistaa ensimmäinen julkaistava versio yhden käyttäjän Fenfire
  järjestelmästä toteuttaen aikaisemmat kohdat 1 ja 2.
- julkaista Fenfire ohjelmisto vapaaohjelmana, rakentaa sen ympärille
  käyttäjäyhteisö ja arvioida käyttökokemuksia ohjelmiston
  jokapäiväisestä käytöstä 

Yhden käyttäjän Fenfire järjestelmä toimii myös yleisenä,
laajennettavana selaimena ja editorina semanttisen webin tiedoille.

Osana yhden käyttäjän Fenfire-järjestelmän julkaisun tavoitetta
jatkamme tutkimustyötä toteusmenetelmistä semanttisen webin
käyttöliittymälle. 


Tulosten tarpeellisuus
======================

Tiedonhallinta on tärkeä huoli useissa nykypäivän organisaatioissa.

Tarve korkeamman tason integraatiolle työpöytäsovelluksissa on
huomattu myös suuryritysten taholta kuten Microsoftin WinFS
teknologiassa, joka tarjoaa yleisen, laajennettavan tietovarasto
ohjelmille ajettavaksi seuraavan sukupolven Windows
käyttöjärjestelmässä. (Vaikkei suoraan yhteensopiva RDF:n kanssa, jota
semanttinen webbi käyttää, WinFS peustuu samankaltaiseen
tietorakenteeseen.)

Mahdollistaen *käyttäjän* mielivaltaisesti laajentaa tietomalleja ja
"sovelluksia", ja tehden tästä tavanomaisen osan käyttäjän
tietokoneella suorittamia toimenpiteitä, on harvinainen
lähestymistapa tietotyöhön. Kuitenkin, käyttäjät tekevät tätä jo nyt,
mutta ilman järjestelmän tarjoamia työkaluja. Uskomme että
annettaessa käyttäjälle mahdollisuus laajentaa ja yhdistellä tietoa
eri sovelluksien välillä tulee siitä merkittävä parannus
tietotyöläisten tiedonhallinnan apuvälineeksi.

Lisäksi semanttinen webbi, joka on vielä tutkimus- ja
kehitysvaiheessa, kasvaa merkittävyydessään. Semanttisessa webissä
semanttinen tieto muodostaa suuren verkon toisiinsakiinnittyvistä
graafeista, eli pienemmistä verkoista. Riittävästi aikaisia käyttäjiä
julkaisee tietoa semanttisessa webissä tänäpäivänä tehdäkseen sen
kiinnostavaksi, mutta huolimatta useista työkaluista erityisillä
aloilla, vain muutamat työkalut mahdollistavat semanttisen tiedon
selaamisen yleisesti. Tälläisiä työkaluja kuitenkin tarvitaan, jotta
semanttisen webin ydinhyöty tiedonkuvauksesta tulee ilmi:
laajennettavuus uusien asioiden ja yhteyksien muodostamisessa.

Fenfire, tarjoten selausmahdollisuuden kaikkeen semanttisen webin
tietoon, voi auttaa käyttäjiä ja kehittäjiä hyödyntämäään toisiinsa
liittyvää rakenteellista tietoa, joka jo nyt on julkaistu
tietoverkossa. Tämä voi auttaa käyttäjiä ymmärtämäään semanttisen
webin tarjoaman hyödyn, joka jo nyt on saatavilla, tarjoten
käyttäjälle kannustimen lisätä tietoa entisestään, ja näin auttaa
tutkijoita saamaan lisää tietoa semanttisesta webistä.

Olemme esitelleet osia Fenfirestä kansainvälisissä workshopeissa ja
konferensseissa, ja näissä vastaanottona on ollut huomattava
kiinnostus hyperrakenteen ja semanttisen webin yhteisöjen keskuudessa.


Tulosten hyödyntäminen ja potentiaaliset sovellukset
====================================================

Uskomme Fenfiren, tai vastaavan järjestelmän tulevaisuudessa voivan
tulla työpöytäympäristöksi mihin tahansa tietokoneeseen, jonka parissa
tehdään tietotyötä. Insinöörit voivat hyödyntää sitä pysyäkseen mukana
ajatuksissaan mahdollisista ratkaisuehdotuksista ongelmiin,
kokeellisista ratkaisuista joita he ovat jo yrittäneet, ja
määräyksistä joita heidän pitää noudattaa; analyytikot voivat
hyödyntää sitä kategorointiin ja keräämiinsä kurssivaihteluihin, ja
tällä tavoin käyttää tietoja kirjoittamissaan raporteissa; taiteilijat
voivat käyttää Fenfireä kirjoittaessaan ylös ideoitaan digitöistään.


Projektin toimenpiteet, aikataulu ja resurssit
==============================================

Projektin yhteydessä julkaisemamme ohjelmisto on hyödyllinen monin
tavoin. Kuitenkin, ensimmäisenä versiona, se on suunnattu asiantuntija
käyttäjille. Uskomme teknologisesti suuntautuneiden käyttäjien
pystyvän hyödyntämään järjestelmää. Seuraavassa julkaisussa hiomme
ohjelmistoa vapaaohjelmistolle tyypillisellä prosessilla, jotta se
olisi helpompi omaksua myös tavallisten käyttäjien keskuudessa.

Lähinpänä käyttäjäryhmänä projektin saatossa julkaistavalle
ohjelmistolle näemme olevan:

- semanttisen webin tutkijat ja kehittäjät, jotka selaavat semanttista
  webbiä ja editoivat sen RDF rakennetta mahdollistamillamme tavoilla;
  ja

- teknisesti suuntautuneet tietotyöläiset jotka tarvitsevat parempia
  työkaluja tiedon käsittelyyn niin suuresti, että haluavat käyttää
  siihen ensimmäisiä Fenfiren versioita.

Uskomme tarjoamamme työkalun olevan heti niin kiinnostava semanttisen
webin kehittäjille, että yhteisö Fenfiren ympärille muodostuu. Kun
nämä kehittäjät tarkemmin tutustuvat Fenfireen, jotkut näistä
alkavat käyttää sitä yleisesti tietotyönsä hallintaan, tarjoten
ydinjoukon Fenfire vapaaohjelman käytölle ja kehitykselle.

Toinen käyttäjäryhmä saattaa käyttää Fenfireä yhdessä Gnowsiksen
kanssa, joka tarjoaa integroidun liittymän olemassaoleviin
työpöytäsovelluksiin hyödyntäen näiden kolmansien sovellusten
tietovarantoja semanttisen webin muodossa. Esimerkiksi käyttäessään
Gnowsista käyttäjät voivat jatkaa edelleen Outlookin käyttäjinä, mutta
samalla hyödyntää näiden tietoja Fenfire järjestelmässä.

Lisäkehitys riippuu vapaaohjelmas-yhteisön muodostumisesta Fenfiren
ympärille. On hyvin vaikea arvioida kuinka pian loppukäyttäjälle
tähtäävä versio Fenfirestä voidaan tehdä; tämä riippuu paljon muiden
kehittäjien osallistumisesta yhteisöstä, ja näiden kehittäjien omista
tarpeista.


Henkilöresurssit

+------------------------+------------------+------------+-----------+
| Henkilö                |   tehtävä        |vuosi 2005  | vuosi 2006|
+========================+==================+============+===========+
| Janne Kujala           | johtaminen       |  120h      | 40h       |
+------------------------+------------------+------------+-----------+
| Benja Fallenstein      | tutkija          | 750h       | 250h      |
+------------------------+------------------+------------+-----------+
| Matti Katila           | tutkija          | 750h       | 250h      |
+------------------------+------------------+------------+-----------+





Projektiin osallistujien aikomukset tulosten hyödyntämisessä ja immateriaalioikeudet
====================================================================================

Projektin tulokset julkaistaan vapaana ohjelmakoodina.
Uskomme Fenfiren ympärille muodostuvan yhteisön, joka käyttää sitä ja
auttaa sen kehityksessä.

Ainoa immateriaali joka projektissa luodaan on oikeus Fenfire
ohjelmakoodiin. Nämä omistaa nykyisin yksityiset henkilöt.

Olemme kuitenkin perustamassa rekisteröityä yhdistystä, joka
tulevaisuudessa omistaa oikeuden Fenfire ohjelmakoodiin ja myös
julkaisee ohjelmiston.

Kaikki Fenfire ohjelmakoodi on ja tulee olemaan lisensoitu vapaasti
GNU General Public Lisenssin ehdoin. Näin yritykset, organisaatiot
kuin yksityisetkin henkilöt voivat käyttää Fenfireä ilman
maksua. Lisenssi mahdollistaa mielivaltaisen ohjelmakoodin muuttelun
ja edelleenlevityksen, muttei mahdollista sen käyttämistä kaupallisiin
johdannaisiin.

Samoin kuin muutama vapaaohjelmin menestyvä yritys kuten Trolltech ja
MySQL AB, yhdistys lisensoi Fenfiren ohjelmakoodia edelleen
halukkaille, joiden tarkoitus on käyttää Fenfireä kaupallisiin
tarkoituksiin. Koska yhdistys ei tee voittoa, kaikki tulo tullaan
käyttämäään Fenfiren kehittämiseen.


Projektin osapuolien tehtävät hyödyntämisessä
=============================================

Rekisteröitävä yhdistys levittää ohjelmistoa, lisensoi sitä, ja mikäli
sen on mahdollista kerätä riittävästi kehitysrahaa, työllistää
kehittäjiä jatkamaan Fenfiren kehitystä. Yhdistys voi myös tarjota
tukea ja muita palveluja ohjelmistoon liittyen.

Mikäli yhden käyttäjän Fenfire ohjelmisto on menestys, Jyväskylän
Yliopiston tutkimusryhmä on suunnitellut jatkavansa tutkimustyötä
monen käyttäjän järjestelmästä, kohdistaen tutkimusta versiointiin ja
käyttäjien väliseen yhteistyöhön Fenfire järjestelmän avulla. Samaan
aikaan kun yhden käyttäjän järjestelmä on hyödyllinen aikaisille
käyttäjille, hyödyllinen järjestelmä isoille organisaatioille
luultavastikkin tarvitsee paremman tuen yhteistyölle. Uskomme tämän
olevan lisättävissä Fenfire järjestelmään yhdessä tai kahdessa
vuodessa. 


Ulkoisen avun tarve hyödyntämisessä
===================================

Rakentaaksemme ensimmäisen julkaistavan Fenfire järjestelmän, kuten
edellä on mainittu, emme tarvitse tukea projektin
ulkopuolelta. Kuitenkin Fenfiren jatkokehitys vakaaksi
loppukäyttäjälle suunnatuksi tuotteeksti ratkaisevasti riippuu
mahdollisuuksistamme luoda vapaaohjelma-yhteisö ohjelmiston ympärille.

