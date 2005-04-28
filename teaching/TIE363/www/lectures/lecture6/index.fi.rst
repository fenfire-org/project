===================================================================
Alph: Xanaloginen rakenne ja media -- 6. luento
===================================================================

:Luentoaika: 2005-04-28T10/12


Johdatus
========

Lyhyt `johdatus <../issues/intro-to-xanalogical-media/>`_ xanalogiseen
rakenteeseen ja mediaan. Alph on xanalogisen systeemin
implementaatio. Alph-nimi on per�isin Xanaduun liittyv�st� `runosta
<http://www.metamed.com/culture/culture.htm>`_, jossa Alph on joki
virtaamassa Xanadu-maailmassa. Xanadu itsess��n on mm. rekister�ity
tuotemerkki, jonka takia aiheesta kannattaa puhua xanalogisena
rakenteena/mediana, joka itseasiassa kuvaakin aihetta paremmin.
Xanadu on my�s ilmaus paratiisista tai fantastisesta toiveesta.


Xanaloginen rakenne/media
=========================

Luennon aihe on kattavasti esitetty t��ll�: `Xanaloginen rakenne
<http://xanadu.com.au/ted/XUsurvey/xuDation.html>`_.  Fenfire
toteutusta voit katsastaa `t�st�
<http://himalia.it.jyu.fi/ffdoc/alph/alph.gen.html>`_.  Xanaloginen
linkki on toteutuksena hieman erilainen, kuin artikkelissa on kuvattu,
mutta sit� voi tarkastella `t��lt�
<../../../../../../fenfire/org/fenfire/index/>`_. Ero on l�hinn� siin�
ett� artikkelissa on linkiss� mukana kolmas komponentti, jolla
yhteytt� voidaan kuvata, jota ei Fenfire toteutuksesta l�ydy t�ll�
hetkell�. Toteutus ei ole stabiilissa tilassa t�ll� hetkell� ja kaipaa
hiontaa.


K�sitteet
=========

:Span: Pienin mahdollinen informaatiopala. Esimerkiksi kuva tai yhden
       session aika luotu merkkijonon sarja. Jokainen informaatio on
       yksil�llinen. Kirjaimissa
       pit�� k�ytt�� tunnistamiseen satunnaista tunnistessa identifioimiseen, 
       mutta kuvan tapauksessa voidaan k�ytt�� kuvatiedostosta muodostettua
       hash-tunnistetta. Mik�li toimitaan yhdess� ulottuvuudessa kuten
       tekstiss�, voidaan spanista osoittaa yksitt�isi� kirjaimia
       indeksoimalla; kun taas kuvasta voidaan osoittaa yksitt�isi� pikseleit�
       antamalla x ja y koordinaatit.

:Virtual file (enfilade): Vektori spaneja, eli jono
   informaatiota esim. (viite)tekstijono. Toteutuksena enfilade-teoriassa
   kuitenkin lis�ys- ja poisto-operaatioiden on oltava O(log n), jossa n 
   on k�ytettyjen spanien m��r�. K�yt�nn�ss� t�m� merkitsee balansoitua 
   puuta tietorakenteena, joissa span(eja) l�ytyy lehtisolmuista. T�m�
   j�tettiin luennolla k�sittelem�tt�.

:ContentLinkki: Linkki kahden tai useamman sis�ll�n(content) v�lill�. Sis�lt�
     voi olla enfilade tai span. 


Pohdintaa
=========

Muutama ajatus tekstist�:

- Tiedon pimitt�misell� ei ole ollut hyv�� vaikutusta ratkaisun
  yleistymisess�. 

- Vaikka eri versioista puhutaan, ei mit��n mallia metatiedolle
  versioden v�lill� anneta. Eli puhutaan lyhennetyst� ja pidemm�st� 
  tekstist�, mutta n�iden v�linen yhteys j�� vaisuksi. Toki puute
  voidaan korvata xanalogisella linkill� jolla yhteytt� kuvataan.


Ongelmat:

- Kuten `viimeluennolla <../lecture5>`_ mainittiin, eiv�t
  ongelmat v�ltt�m�tt� ole teknisi�. Sosiaaliset ongelmat globaalisti
  hyv�ksytylle ja standardoidulle median osoitusmuodolle ovat suuret.
  K�yt�nn�ss� tarvitaan riitt�v�n voimakkaita tahoja ideoiden
  eteenp�in viemiseksi. Teknisesti ratkaisut ovat triviaaleja.

- Kaksisuuntaisilla linkeill� on haittapuolensakkin. Jokin taho voi
  tuupata tuubaa tuutin t�ydelt� tukkien linkkien merkityksen
  totaalisesti.

- On ihmisi� jotka eiv�t halua pysyv�� mediaa.

- Vepiss� on paljon dynaamisia sivuja, xanalogisella rakenteella t�t� ei
  voida korvata.


Hy�dyt:

- On sanottu ett� tietokoneilu ilman viittausmahdollisuutta on kuin
  lent�minen Boeing 747:ll� ilman siipi�.




