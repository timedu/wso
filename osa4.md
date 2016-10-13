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

Viimeinen tehtävistä (4.7) on muita jonkin verran laajempi. 


