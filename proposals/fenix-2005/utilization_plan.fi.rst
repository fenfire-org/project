
=====================================
Tiedonhallintamenetelm�t Fenfire 2005
=====================================



------------------------------------------------------------
Fenix / tiet�myksen hallinta
------------------------------------------------------------



L�ht�kohta
==========

Nykyp�iv�n tietokone ymp�rist�ineen rajoittaa tietoty�l�isi�, jotka
joutuvat tyytym��n niihin tiedon esitysmalleihin jotka suunnittelija
on tehnyt heid�n puolestaan ohjelmistoihin, ja jotka samalla
hajauttavat ja sirpaloivat tietoa eri ohjelmistojen v�lill�.

Esimerkiksi samainen henkil� voi esiinty� kuutena eri henkil�tietona
kuudessa eri ohjelmistossa, kuten osoitekirjassa,
s�hk�postisovelluksessa ja projektinhallintasovelluksessa, sek� t�m�n
lis�ksi kyseinen henkil� voi esiinty� lukuisissa tekstidokumenteissa
ilman mink��nlaista yhteytt� n�ihin henkil�tietoihin eri
sovelluksissa.

Kun sovellusten tietomallit eiv�t ole riitt�v�t, k�ytt�j� ei voi
laajentaa niit�. Esimerkkin� esitelm�: miten esitelm�n pit�j� voi
kirjata saadun kommentin ja kommentin esitt�j�n tiedot? H�n ei voi
s�ilytt�� t�t� tietoa osoitekirja- tai s�hk�postisovellukseensa;
mieluumminkin h�n luo uuden tekstidokumentin tarkoitusta varten,
jota ei my�sk��n voi mitenk��n liitt�� mainittuihin sovelluksiin.

Semanttisen webin teknologiat lupaavat tarjota ratkaisun
ongelmaan. Toisin kuin tiedon mallintamiseen suunnitellut edelt�v�t
teknologiat: tietokannat, XML tai olio-ohjelmointi, semanttinen webbi
rakentuu identiteeteist� jotka vastaavat reaalimaailman
asioita. Semanttisella webill� on siis luonnollista kuvata Maijan
Outlookissa listattu Liisa Nieminen samaiseksi Liisaksi, joka asustaa
my�s Matin Mozilla Thunderbirdiss�. Teknologia mahdollistaa t�m�n
p��ttelyn automaattisesti, esimerkiksi jos heille on annettu sama
kotisivu ja s�hk�postiosoite.

Lis�ksi semanttinen webbi mahdollistaa tietomallien laajentamisen
huoletta. Palataksemme aikaisempaan esimerkkiin esitelm�st�, olisi
mit��nsanomattoman helppoa lis�t� annettu kommentti esitelm�n
yhteyteen sek� liitt�� t�h�n kommenttiin kommentoijan
s�hk�postiosoite, joka automaattisesti sis�istett�isiin yhteyten�
kommentin antaneeseen ihmiseen.

Joten, rakenteettoman tekstidokumentin luomisen sijaan, oletettu
tietoty�l�isemme vain lis�isi uuden yhteyden, ja n�in yhdist�isi
asioita jotka jo ovat j�rjestelm�ss�. Sen sijaan, ett� ilman
yhteyksi� asioiden v�lill�, tiedot levitt�ytyisiv�t ymp�ri tietokoneen
kovalevy� ja niiden l�yt�minen olisi paljon kiinni k�ytt�j�n omasta
muistista.


Fenfire
=======

Semanttiseen webbiin perustuva j�rjestelm� tarjoaisi voimallisen ja
joustavan ymp�rist�n tietoty�l�isille. Useissa tapauksissa se
mahdollistaisi tiedon mallintamisen juuri k�ytt�j�n mielt�m�ll�
tavalla, paljon l�hemp�n� itse tietoty�n tarpeita, kuin kiinteisiin
malleihin luodut sovellukset ja ohjelmistot ikin�
pystyv�t. Rakenteettomat Excel-taulukot tai tekstidokumentit
korvikkeena ohjelmistolle joka vastaisi k�ytt�j�n tarpeita, eiv�t
olisi en�� tarpeellisia.

On suorastaan luonnollista l�yt�� yrityksi� k�ytt�� semanttisen webin
teknologiaa "Semanttisen ty�p�yd�n" rakentamiseksi. Fenfire-projekti
on pyrkimys t�ytt��� t�m� yritys. Fenfiren lis�ksi olemme tietoisia
kahdesta muusta projektista, jotka ty�skentelev�t asian hyv�ksi.

- *Gnowsis*, vapaaohjelmisto jota kehitt�� saksalainen
   tutkimus-instituutti, jonka kanssa meill� on yhteisty�t�. Heid�n
   n�kemyksens� on integroida nykyisten ohjelmistojen
   tietoj�rjestelm�t semanttisen webin muotoon, ja n�in mahdollistaa
   k�ytt�j�n luoda yhteyksi� tietojen v�lille.

   Gnowsisilla on konservatiivinen n�kemys k�ytt�liittym�st�, sill� se
   lis�� vain kaksi painonappia integroitaviin ohjelmistoihin
   ("selaa", joka avaa valitun asian Gnowsikseen, ja "linkit�", jonka
   avulla voidaan luoda uusia yhteyksi�).

- *Haystack*, on my�s vapaaohjelmisto. Se on kehitetty
   tutkimusprojektissa Massachusetts Institute of Technology:n
   tutkimuslaitoksessa. Haystack tarjoaa k�ytt�liittym�n joka
   muistuttaa webbiselainta, ja jossa on laajennettava joukko n�kymi�
   jotka sopivat erilaisten tietojen tarkasteluun. Haystackin n�kym�t
   ovat samankaltaisia kuin nykyisen webin lomakkeet, ja jotka on
   luotu ohjelmoijien tai kokeneiden k�ytt�jien toimesta erillisell�
   kuvauskielell�. Toisin kuin tavanomaiset lomakkeet, Haystackin eri
   n�kym�t voivat kuvata samaa lomaketta samaan aikaan.

Kaikesta huolimatta meid�n tietojemme mukaan kumpikaan projekteista ei
aseta tavoitteekseen k�ytt�j�n luoda omia integroituja "sovelluksiaan"
k�ytt�m�ll� paloja toisista ohjelmista ja laajentamalla niit� k�ytt�en
uusia yhteystyyppej� eri asioiden v�lill�. T�m� tavoite, jonka me
n�emme t�ysin heijastavan semanttisen webin laajamittaisesti
k�ytt�liittym�ss�, ja n�in tuoden semanttisen webin *k�ytt�j�lle*
toisin kuin pelk�st��n *ohjelmoijalle*, on asia joka tekee
Fenfire-projektista yksil�llisen. (Sana "sovellukset" on
lainausmerkeiss�, koska kuvaamassamme j�rjestelm�ss� ne eiv�t tule
olemaan yht� merkitt�v�sti ja yksioikoisella tavalla l�sn� mit� ne
t�n� p�iv�n� ovat.)

Saavuttaaksemme t�m�n tavoitteen Fenfire visualisoi yhteydet asioiden
v�lill� ja tekee t�st� olennainen osan k�ytt�liittym��. Kun jotain
asiaa tarkastellaan j�rjestelm�ss�, Fenfire esitt�� siihen liittyv�t
muut asiat t�m�n ymp�rill�, yhdist�en n�m� viivoin keskell� olevaan
tarkasteltavaan asiaan.

Milloin tahansa Fenfire "sovelluksen" tarvitessa yhdist��� kaksi asiaa
toisiinsa -- esimerkiksi s�hk�posti l�hett�j��ns� -- tai esitt��
muistiinpano jostain asiasta -- esimerkiksi s�hk�postin t�rkeys --
yksinkertaisin asia tehd� t�m� on antaa Fenfiren esitt�� yhteys.

Kun k�ytt�j�n yhdistelem�t, h�nen itse luomansa yhdistetyypit
esitet��n j�rjestelm�ss� samalla tavoin, ellei toisin m��ritelty, n�m�
yhteydet eiv�t ilmesty jonnekkin outoon paikkaan, vaan n�kyv�t
j�rjestelm�ss� aivan samoin kuin mik� tahansa muukin yhteys
"sovelluksien" v�lill�. Jopa yhteys eri "sovellusten" v�lill� on
samanlainen kuin yhteys "sovelluksen" sis�ll�.

N�in ollen "sovellusten" v�lill� ei esiinny rajoja, ja vain pieni�
rajoitteita tietoty�l�isen luoda omia "sovelluksia".

Tarkempaa tietoa Fenfiren toimintatavoista on kuvattuna liitteen�
olevissa artikkeleissa, joissa on my�s kuvakaappauksia.



Projektin tavoitellut tulokset
==============================

Fenfiren pohjimmainen tavoite on luoda ty�p�yt�ymp�rist�
tietoty�l�isille jossa:

1. tieto on rakentunut yhteyksist� reaalimaailman asioihin, kuten
   ihmisiin, projekteihin, ennemmin kuin keinotekoisiin konsepteihin,
   kuten sovelluksiin ja kansioihin;

2. k�ytt�j� voi helposti laajentaa k�ytett�vi� yhteyksi� ja n�kymi�
   tiedon esitt�miseen, ja n�in luoda omia "sovelluksia";

3. tieto on jaettavissa ilman kommervenkkej� eri k�ytt�jien v�lill�
   tukien t�ysin versiointia ja yhteisty�t�.

Tavoitellut p��m��r�t Fenix projektille ovat:

- valmistaa ensimm�inen julkaistava versio yhden k�ytt�j�n Fenfire
  j�rjestelm�st� toteuttaen aikaisemmat kohdat 1 ja 2.
- julkaista Fenfire ohjelmisto vapaaohjelmana, rakentaa sen ymp�rille
  k�ytt�j�yhteis� ja arvioida k�ytt�kokemuksia ohjelmiston
  jokap�iv�isest� k�yt�st� 

Yhden k�ytt�j�n Fenfire j�rjestelm� toimii my�s yleisen�,
laajennettavana selaimena ja editorina semanttisen webin tiedoille.

Osana yhden k�ytt�j�n Fenfire-j�rjestelm�n julkaisun tavoitetta
jatkamme tutkimusty�t� toteusmenetelmist� semanttisen webin
k�ytt�liittym�lle. 


Tulosten tarpeellisuus
======================

Tiedonhallinta on t�rke� huoli useissa nykyp�iv�n organisaatioissa.

Tarve korkeamman tason integraatiolle ty�p�yt�sovelluksissa on
huomattu my�s suuryritysten taholta kuten Microsoftin WinFS
teknologiassa, joka tarjoaa yleisen, laajennettavan tietovarasto
ohjelmille ajettavaksi seuraavan sukupolven Windows
k�ytt�j�rjestelm�ss�. (Vaikkei suoraan yhteensopiva RDF:n kanssa, jota
semanttinen webbi k�ytt��, WinFS peustuu samankaltaiseen
tietorakenteeseen.)

Mahdollistaen *k�ytt�j�n* mielivaltaisesti laajentaa tietomalleja ja
"sovelluksia", ja tehden t�st� tavanomaisen osan k�ytt�j�n
tietokoneella suorittamia toimenpiteit�, on harvinainen
l�hestymistapa tietoty�h�n. Kuitenkin, k�ytt�j�t tekev�t t�t� jo nyt,
mutta ilman j�rjestelm�n tarjoamia ty�kaluja. Uskomme ett�
annettaessa k�ytt�j�lle mahdollisuus laajentaa ja yhdistell� tietoa
eri sovelluksien v�lill� tulee siit� merkitt�v� parannus
tietoty�l�isten tiedonhallinnan apuv�lineeksi.

Lis�ksi semanttinen webbi, joka on viel� tutkimus- ja
kehitysvaiheessa, kasvaa merkitt�vyydess��n. Semanttisessa webiss�
semanttinen tieto muodostaa suuren verkon toisiinsakiinnittyvist�
graafeista, eli pienemmist� verkoista. Riitt�v�sti aikaisia k�ytt�ji�
julkaisee tietoa semanttisessa webiss� t�n�p�iv�n� tehd�kseen sen
kiinnostavaksi, mutta huolimatta useista ty�kaluista erityisill�
aloilla, vain muutamat ty�kalut mahdollistavat semanttisen tiedon
selaamisen yleisesti. T�ll�isi� ty�kaluja kuitenkin tarvitaan, jotta
semanttisen webin ydinhy�ty tiedonkuvauksesta tulee ilmi:
laajennettavuus uusien asioiden ja yhteyksien muodostamisessa.

Fenfire, tarjoten selausmahdollisuuden kaikkeen semanttisen webin
tietoon, voi auttaa k�ytt�ji� ja kehitt�ji� hy�dynt�m���n toisiinsa
liittyv�� rakenteellista tietoa, joka jo nyt on julkaistu
tietoverkossa. T�m� voi auttaa k�ytt�ji� ymm�rt�m���n semanttisen
webin tarjoaman hy�dyn, joka jo nyt on saatavilla, tarjoten
k�ytt�j�lle kannustimen lis�t� tietoa entisest��n, ja n�in auttaa
tutkijoita saamaan lis�� tietoa semanttisesta webist�.

Olemme esitelleet osia Fenfirest� kansainv�lisiss� workshopeissa ja
konferensseissa, ja n�iss� vastaanottona on ollut huomattava
kiinnostus hyperrakenteen ja semanttisen webin yhteis�jen keskuudessa.


Tulosten hy�dynt�minen ja potentiaaliset sovellukset
====================================================

Uskomme Fenfiren, tai vastaavan j�rjestelm�n tulevaisuudessa voivan
tulla ty�p�yt�ymp�rist�ksi mihin tahansa tietokoneeseen, jonka parissa
tehd��n tietoty�t�. Insin��rit voivat hy�dynt�� sit� pysy�kseen mukana
ajatuksissaan mahdollisista ratkaisuehdotuksista ongelmiin,
kokeellisista ratkaisuista joita he ovat jo yritt�neet, ja
m��r�yksist� joita heid�n pit�� noudattaa; analyytikot voivat
hy�dynt�� sit� kategorointiin ja ker��miins� kurssivaihteluihin, ja
t�ll� tavoin k�ytt�� tietoja kirjoittamissaan raporteissa; taiteilijat
voivat k�ytt�� Fenfire� kirjoittaessaan yl�s ideoitaan digit�ist��n.


Projektin toimenpiteet, aikataulu ja resurssit
==============================================

Projektin yhteydess� julkaisemamme ohjelmisto on hy�dyllinen monin
tavoin. Kuitenkin, ensimm�isen� versiona, se on suunnattu asiantuntija
k�ytt�jille. Uskomme teknologisesti suuntautuneiden k�ytt�jien
pystyv�n hy�dynt�m��n j�rjestelm��. Seuraavassa julkaisussa hiomme
ohjelmistoa vapaaohjelmistolle tyypillisell� prosessilla, jotta se
olisi helpompi omaksua my�s tavallisten k�ytt�jien keskuudessa.

L�hinp�n� k�ytt�j�ryhm�n� projektin saatossa julkaistavalle
ohjelmistolle n�emme olevan:

- semanttisen webin tutkijat ja kehitt�j�t, jotka selaavat semanttista
  webbi� ja editoivat sen RDF rakennetta mahdollistamillamme tavoilla;
  ja

- teknisesti suuntautuneet tietoty�l�iset jotka tarvitsevat parempia
  ty�kaluja tiedon k�sittelyyn niin suuresti, ett� haluavat k�ytt��
  siihen ensimm�isi� Fenfiren versioita.

Uskomme tarjoamamme ty�kalun olevan heti niin kiinnostava semanttisen
webin kehitt�jille, ett� yhteis� Fenfiren ymp�rille muodostuu. Kun
n�m� kehitt�j�t tarkemmin tutustuvat Fenfireen, jotkut n�ist�
alkavat k�ytt�� sit� yleisesti tietoty�ns� hallintaan, tarjoten
ydinjoukon Fenfire vapaaohjelman k�yt�lle ja kehitykselle.

Toinen k�ytt�j�ryhm� saattaa k�ytt�� Fenfire� yhdess� Gnowsiksen
kanssa, joka tarjoaa integroidun liittym�n olemassaoleviin
ty�p�yt�sovelluksiin hy�dynt�en n�iden kolmansien sovellusten
tietovarantoja semanttisen webin muodossa. Esimerkiksi k�ytt�ess��n
Gnowsista k�ytt�j�t voivat jatkaa edelleen Outlookin k�ytt�jin�, mutta
samalla hy�dynt�� n�iden tietoja Fenfire j�rjestelm�ss�.

Lis�kehitys riippuu vapaaohjelmas-yhteis�n muodostumisesta Fenfiren
ymp�rille. On hyvin vaikea arvioida kuinka pian loppuk�ytt�j�lle
t�ht��v� versio Fenfirest� voidaan tehd�; t�m� riippuu paljon muiden
kehitt�jien osallistumisesta yhteis�st�, ja n�iden kehitt�jien omista
tarpeista.


Henkil�resurssit

+------------------------+------------------+------------+-----------+
| Henkil�                |   teht�v�        |vuosi 2005  | vuosi 2006|
+========================+==================+============+===========+
| Janne Kujala           | johtaminen       |  120h      | 40h       |
+------------------------+------------------+------------+-----------+
| Benja Fallenstein      | tutkija          | 750h       | 250h      |
+------------------------+------------------+------------+-----------+
| Matti Katila           | tutkija          | 750h       | 250h      |
+------------------------+------------------+------------+-----------+





Projektiin osallistujien aikomukset tulosten hy�dynt�misess� ja immateriaalioikeudet
====================================================================================

Projektin tulokset julkaistaan vapaana ohjelmakoodina.
Uskomme Fenfiren ymp�rille muodostuvan yhteis�n, joka k�ytt�� sit� ja
auttaa sen kehityksess�.

Ainoa immateriaali joka projektissa luodaan on oikeus Fenfire
ohjelmakoodiin. N�m� omistaa nykyisin yksityiset henkil�t.

Olemme kuitenkin perustamassa rekister�ity� yhdistyst�, joka
tulevaisuudessa omistaa oikeuden Fenfire ohjelmakoodiin ja my�s
julkaisee ohjelmiston.

Kaikki Fenfire ohjelmakoodi on ja tulee olemaan lisensoitu vapaasti
GNU General Public Lisenssin ehdoin. N�in yritykset, organisaatiot
kuin yksityisetkin henkil�t voivat k�ytt�� Fenfire� ilman
maksua. Lisenssi mahdollistaa mielivaltaisen ohjelmakoodin muuttelun
ja edelleenlevityksen, muttei mahdollista sen k�ytt�mist� kaupallisiin
johdannaisiin.

Samoin kuin muutama vapaaohjelmin menestyv� yritys kuten Trolltech ja
MySQL AB, yhdistys lisensoi Fenfiren ohjelmakoodia edelleen
halukkaille, joiden tarkoitus on k�ytt�� Fenfire� kaupallisiin
tarkoituksiin. Koska yhdistys ei tee voittoa, kaikki tulo tullaan
k�ytt�m���n Fenfiren kehitt�miseen.


Projektin osapuolien teht�v�t hy�dynt�misess�
=============================================

Rekister�it�v� yhdistys levitt�� ohjelmistoa, lisensoi sit�, ja mik�li
sen on mahdollista ker�t� riitt�v�sti kehitysrahaa, ty�llist��
kehitt�ji� jatkamaan Fenfiren kehityst�. Yhdistys voi my�s tarjota
tukea ja muita palveluja ohjelmistoon liittyen.

Mik�li yhden k�ytt�j�n Fenfire ohjelmisto on menestys, Jyv�skyl�n
Yliopiston tutkimusryhm� on suunnitellut jatkavansa tutkimusty�t�
monen k�ytt�j�n j�rjestelm�st�, kohdistaen tutkimusta versiointiin ja
k�ytt�jien v�liseen yhteisty�h�n Fenfire j�rjestelm�n avulla. Samaan
aikaan kun yhden k�ytt�j�n j�rjestelm� on hy�dyllinen aikaisille
k�ytt�jille, hy�dyllinen j�rjestelm� isoille organisaatioille
luultavastikkin tarvitsee paremman tuen yhteisty�lle. Uskomme t�m�n
olevan lis�tt�viss� Fenfire j�rjestelm��n yhdess� tai kahdessa
vuodessa. 


Ulkoisen avun tarve hy�dynt�misess�
===================================

Rakentaaksemme ensimm�isen julkaistavan Fenfire j�rjestelm�n, kuten
edell� on mainittu, emme tarvitse tukea projektin
ulkopuolelta. Kuitenkin Fenfiren jatkokehitys vakaaksi
loppuk�ytt�j�lle suunnatuksi tuotteeksti ratkaisevasti riippuu
mahdollisuuksistamme luoda vapaaohjelma-yhteis� ohjelmiston ymp�rille.

