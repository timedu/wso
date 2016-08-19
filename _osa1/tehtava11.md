---
layout: sivu
title: Tehtävä 1.1
---

## Puhelinmuistio (olio)

Toteuta tehtäväpohjaan funktio `Puhelinmuistio`, joka 
[new](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) 
-operattorilla kutsuttaessa luo puhelinmuistio-olioita. Muistioon voi lisätä ja sieltä voidaan poistaa nimiä ja numeroita. Jokaiseen nimeen voi liittyä useampi numero. Jos samalle henkilölle yritetään asettaa sama numero useampaan kertaan, numero tallennetaan henkilölle vain kerran. Useammalla henkilöllä voi olla sama numero. Funktiolla luotavien olioiden rakenne voidaan esittää seuraavanlaisena UML-luokkana [^1]:

[^1]: JavaScript ei sisällä luokkia, mutta tässä funktiolla luotavien olioiden rakenne noudattaa esitetyn luokan rakennetta.

![Puhelinmuistio-luokka](../img/puhelinmuistio_olio.jpeg "Puhelinmuistio-luokka")

Metodien lisäksi puhelinmuistio-oliolla on tietojen tallettamista varten attribuutti `_henkilot`[^2] . Attribuutti toteutetaan oliona, jossa kutakin muistioon talletettua henkilöä vastaa taulukko-tyyppinen attribuutti henkilön numeroiden tallettamista varten. Esimerkiksi seuraavassa kuvassa `_henkilot` -oliolla on kaksi taulukko-tyyppistä attribuuttia, `Flanders` ja `Bart Simpson`, joista ensimmäinen esiintyy jäljempänä esitettyssä käyttöliittymässä.   

[^2]: Attribuutin ensimmäisenä merkkinä oleva `_` indikoi tässä sitä, että attribuuttiin ei ole tarkoitus viitata olion metodien ulkopuolelta, vaikka se tässä toteutuksessa on mahdollista.

![Henkilot-olio](../img/henkilot_olio.jpeg "Henkilot-olio")

Tässä laadittavalla funktiolla luodaan puhelinmuistio-olioita seuraavasti:

{% highlight javascript %}

var puhelinmuistio = new Puhelinmuistio();

{% endhighlight %}

Oliokaaviona syntynyt tilanne näyttää seuraavanlaiselta:

![Puhelinmuistio-rakenne](../img/puhelinmuistio_rakenne.png "Puhelinmuistio-rakenne")

**Palauta** tehtävästä `Puhelinmuistio`-funktion sisältävä tiedosto `puhelinmuistio.js`. Varmista ennen palauttamista, että tehtäväpohjan sisältämät testit menevät läpi ilman virheilmoituksia.

Tehtäväpohjassa on tässä laadittavaa funktiota käyttävä valmis käyttöliittymä:

![Puhelinmuistion käyttöliittymä](../img/puhelinmuistio_ui.png "Puhelinmuistion käyttöliittymä")

**Numeroiden lisääminen** muistioon tapahtuu kirjaamalla tiedot *Nimi*- ja *Numero*- syötekenttiin ja klikkaamalla *Lisää* -painonappia, minkä jälkeen numero tallentuu muistioon ja kaikki ko. nimeen liittyvät numerot ilmestyvät sivulle. **Numeroiden haku** suoritetaan kirjaamalla hakuehtona toimiva henkilön nimi sivun *Nimi* -kenttään ja klikkaamalla *Etsi*-painonappia. Tämän jälkeen nimeen liittyvät numerot ilmestyvät sivulle samoin kuin numeroita lisättäessä. Kunkin sivulla olevan numeron ohessa on *X* -painonappi, jota klikkaamalla **numero poistuu** sekä sivulta että muistiosta. 

#### Vihjeitä ja lisätietoja

Oheismateriaalin [kohdassa 8.1]({{site.baseurl}}/weso/#8.1-Oliot) on tehtävään liittyvä esimerkki, jossa rakennetaa kirja-olioita muodostava `Kirja`-funktio. Olioiden rakenne esimerkissä on seuraavanlainen:

![Kirja-luokka](../img/kirja_olio.jpeg "Kirja-luokka")

JavaScriptissä ei ole olioden luokkia, mutta oliolla on tiedossa, sen luonut funktio. Jos esimerkin `Kirja`-funktiolla on luotu `kirja`-olio, tilannetta voidaan kuvata seuraavanlaisella oliokaaviolla:

![Kirja-rakenne](../img/kirja_rakenne.jpeg "Kirja-rakenne")

Tehtävän ratkaisussa esim. seuraavat apuveuvot saattavat olla hyödyllisiä:
[Array.prototype.includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes),
[Array.prototype.indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf),
[Array.prototype.push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push),
[Array.prototype.slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice),
[Array.prototype.splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice),
[Object.keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys),
[delete operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete).

