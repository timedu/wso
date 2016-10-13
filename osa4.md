---
layout: sivu
permalink: /osa4/index.html 
title: 4. Kirjastoista - AngularJS (I)
---

> Olemme tähän mennessä onnistuneesti pystyneet esittämään sovelluksemme dataa käyttöliittymässä ja jopa välittämään käyttöliittymästä tehtyjä muutoksia sovelluslogiikkaan. 
[Mustache](https://mustache.github.io)
 tekee datan esittämisestä näkymässä melko helppoa, mutta kuten olet ehkä huomannut, datan muokkaaminen näkymän kautta ei ole aivan niin helppoa. Ongelmat ilmenevät etenkin sovelluksen kasvaessa, jolloin sen rakenteesta tulee aina vain sekavampi. Rakennetta selkeyttää huomattavasti käyttöliittymän erottaminen sovelluksen datasta, johon jo mainittu MVC-arkkitehtuuri pyrkiikin. Selkeän MVC-arkkitehtuurin aikaansaaminen on kuitenkin yllättävän vaikeaa, jos työkalut eivät ole oikeat.
>
> Apuun tulee suuren suosion saavuttanut [AngularJS](https://angularjs.org)
MVW-[sovelluskehys](https://fi.wikipedia.org/wiki/Ohjelmistokehys). 
Edellisessä lauseessa ei ole kirjoitusvirhettä, Angularia ei voi rajata pelkäksi MVC-sovelluskehykseksi (vaikkakin niin usein tehdään), vaan tarkempi termi onkin "Model View Whatever". Se siis esittää mallia näkymässä ja välittää näkymässä tehtyjä muutoksia takaisin malliin. Mitä mallin ja näkymän rajapinnassa tapahtuu, on ohjelmoijan itsensä päätettävissä.
> 
> Mikä Angularissa on hienoa, on se, että se tekee luonteeltaan staattisesta HTML:stä dynaamista, jolloin malli on sekä helppo esittää näkymässä, että helppo muokata näkymän kautta. Yksinkertaisia sovelluksia voidaan saada aikaan kirjoittamatta riviäkään JavaScriptiä. 

Edellä oleva lainaus on poimittu [kurssilukemiston]({{site.baseurl}}/weso/) luvun 12
([Sovelluksen rakenteen hallinta: AngularJS]({{site.baseurl}}/weso/#12-Sovelluksen-rakenteen-hallinta:-AngularJS)) alusta.

### Tehtävät

Kaikki tämän osan tehtävät on poimittu kurssilukemistosta:

[Tehtävä 4.1 James Bond](tehtava41)   
[Tehtävä 4.2 Elokuvat](tehtava42)   
[Tehtävä 4.3 Elokuvien haku](tehtava43)   
[Tehtävä 4.4 Lomakkeen kelpoistaminen](tehtava44)   
[Tehtävä 4.5 Laskin](tehtava45)   
[Tehtävä 4.6 Pikakirjoitus](tehtava46)   
[Tehtävä 4.7 Muistilista](tehtava47)  

Viimeinen tehtävistä ([4.7](tehtava47)) on muita jonkin verran laajempi muistuttaen ominaisuuksiltaan kurssin edellisten osien tehtävissä eri periaattein toteutettua Puhelinmuistio-sovellusta. Muut tehtävät keskittyvät *AngulaJS*-sovelluskehyksen yksittäisten ominaisuuksien esittelyyn.

[Tehtävässä 4.1](tehtava41) voidaan todeta, miten *AngularJS* hoitaa datan siirtymisen *näkymästä* *malliin* ja päinvastoin ilman JavaScript-koodin kirjoittamista. Tehtävässä tosin laaditaan myös yksinkertainen *kontrolleri*, joka suorittaa *mallin* datan asettamisen alkuarvoonsa.

[Tehtävä 4.2](tehtava42) esittelee *AngularJS* -näkymien muodostamisessa käytettävää template -kieltä, joka syntaksiltaan muistuttaan *Mustachea*. Angularia käytettäessä templatet laaditaan osaksi merkkausta siten, että merkkaukseen sisällytetään Angularin ymmärtämiä ns. direktiivejä, jotka voivat esiintyä lähdekoodissa html -elementtien attribuutteina tai omina elementteinään.

[Tehtävässä 4.3](tehtava43) tulee esiin, miten *mallin* datajoukkoa voidaan suodattaa *näkymässä* ilman JavaScript-koodaamista. [Tehtävässä 4.4](tehtava44) kelpoistetaan käyttäjän lomakkeelle syöttämät tiedot. Perusmuodossaan tämäkin voidaan toteuttaa ilman JavaScriptia. Tehtävässä hyödynnetään kelpoistuksessa myös erästä Angularin laajennusta sekä laaditaan oma kelpoistusta tukeva direktiivi. Viimeksi mainittu edellyttää JavaScript -koodia, mutta se on pohjassa jo melkein valmiina.













