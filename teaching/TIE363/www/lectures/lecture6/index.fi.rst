===================================================================
Alph: Xanaloginen rakenne ja media -- 6. luento
===================================================================

:Luentoaika: 2005-04-28T10/12


Johdatus
========

Lyhyt `johdatus <../issues/intro-to-xanalogical-media/>`_ xanalogiseen
rakenteeseen ja mediaan. Alph on xanalogisen systeemin
implementaatio. Alph-nimi on peräisin Xanaduun liittyvästä `runosta
<http://www.metamed.com/culture/culture.htm>`_, jossa Alph on joki
virtaamassa Xanadu-maailmassa. Xanadu itsessään on mm. rekisteröity
tuotemerkki, jonka takia aiheesta kannattaa puhua xanalogisena
rakenteena/mediana, joka itseasiassa kuvaakin aihetta paremmin.
Xanadu on myös ilmaus paratiisista tai fantastisesta toiveesta.


Xanaloginen rakenne/media
=========================

Luennon aihe on kattavasti esitetty täällä: `Xanaloginen rakenne
<http://xanadu.com.au/ted/XUsurvey/xuDation.html>`_.  Fenfire
toteutusta voit katsastaa `tästä
<http://himalia.it.jyu.fi/ffdoc/alph/alph.gen.html>`_.  Xanaloginen
linkki on toteutuksena hieman erilainen, kuin artikkelissa on kuvattu,
mutta sitä voi tarkastella `täältä
<../../../../../../fenfire/org/fenfire/index/>`_. Ero on lähinnä siinä
että artikkelissa on linkissä mukana kolmas komponentti, jolla
yhteyttä voidaan kuvata, jota ei Fenfire toteutuksesta löydy tällä
hetkellä. Toteutus ei ole stabiilissa tilassa tällä hetkellä ja kaipaa
hiontaa.


Käsitteet
=========

:Span: Pienin mahdollinen informaatiopala. Esimerkiksi kuva tai yhden
       session aika luotu merkkijonon sarja. Jokainen informaatio on
       yksilöllinen. Kirjaimissa
       pitää käyttää tunnistamiseen satunnaista tunnistessa identifioimiseen, 
       mutta kuvan tapauksessa voidaan käyttää kuvatiedostosta muodostettua
       hash-tunnistetta. Mikäli toimitaan yhdessä ulottuvuudessa kuten
       tekstissä, voidaan spanista osoittaa yksittäisiä kirjaimia
       indeksoimalla; kun taas kuvasta voidaan osoittaa yksittäisiä pikseleitä
       antamalla x ja y koordinaatit.

:Virtual file (enfilade): Vektori spaneja, eli jono
   informaatiota esim. (viite)tekstijono. Toteutuksena enfilade-teoriassa
   kuitenkin lisäys- ja poisto-operaatioiden on oltava O(log n), jossa n 
   on käytettyjen spanien määrä. Käytännössä tämä merkitsee balansoitua 
   puuta tietorakenteena, joissa span(eja) löytyy lehtisolmuista. Tämä
   jätettiin luennolla käsittelemättä.

:ContentLinkki: Linkki kahden tai useamman sisällön(content) välillä. Sisältö
     voi olla enfilade tai span. 


Pohdintaa
=========

Muutama ajatus tekstistä:

- Tiedon pimittämisellä ei ole ollut hyvää vaikutusta ratkaisun
  yleistymisessä. 

- Vaikka eri versioista puhutaan, ei mitään mallia metatiedolle
  versioden välillä anneta. Eli puhutaan lyhennetystä ja pidemmästä 
  tekstistä, mutta näiden välinen yhteys jää vaisuksi. Toki puute
  voidaan korvata xanalogisella linkillä jolla yhteyttä kuvataan.


Ongelmat:

- Kuten `viimeluennolla <../lecture5>`_ mainittiin, eivät
  ongelmat välttämättä ole teknisiä. Sosiaaliset ongelmat globaalisti
  hyväksytylle ja standardoidulle median osoitusmuodolle ovat suuret.
  Käytännössä tarvitaan riittävän voimakkaita tahoja ideoiden
  eteenpäin viemiseksi. Teknisesti ratkaisut ovat triviaaleja.

- Kaksisuuntaisilla linkeillä on haittapuolensakkin. Jokin taho voi
  tuupata tuubaa tuutin täydeltä tukkien linkkien merkityksen
  totaalisesti.

- On ihmisiä jotka eivät halua pysyvää mediaa.

- Vepissä on paljon dynaamisia sivuja, xanalogisella rakenteella tätä ei
  voida korvata.


Hyödyt:

- On sanottu että tietokoneilu ilman viittausmahdollisuutta on kuin
  lentäminen Boeing 747:llä ilman siipiä.




