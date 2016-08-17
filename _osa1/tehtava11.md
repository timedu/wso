---
layout: sivu
title: Tehtävä 1.1
---

## Puhelinmuistio (olio)

Toteuta tehtäväpohjaan funktio `Puhelinmuistio`, joka luo puhelinmuistio-olioita. Muistioon voi lisätä ja sieltä voidaan poistaa nimiä ja numeroita. Jokaiseen nimeen voi liittyä useampi numero. Jos samalle henkilölle yritetään asettaa sama numero useampaan kertaan, numero tallennetaan henkilölle vain kerran. Useammalla henkilöllä voi olla sama numero. 

Tehtäväpohjassa on tässä laadittavaa funktiota käyttävä valmis käyttöliittymä:

![Puhelinmuistion käyttöliittymä]({{page.url}}/img/puhelinmuistio_ui.png "Puhelinmuistion käyttöliittymä")

**Numeroiden lisääminen** muistioon tapahtuu kirjaamalla tiedot *Nimi*- ja *Numero*- syötekenttiin ja klikkaamalla *Lisää* -painonappia, minkä jälkeen numero tallentuu muistioon ja kaikki ko. nimeen liittyvät numerot ilmestyvät sivulle. **Numeroiden haku** suoritetaan kirjaamalla hakuehtona toimiva henkilön nimi sivun *Nimi* -kenttään ja klikkaamalla *Etsi*-painonappia. Tämän jälkeen nimeen liittyvät numerot ilmestyvät sivulle samoin kuin numeroita lisättäessä. Kunkin sivulla olevan numeron ohessa on *X* -painonappi, jota klikkaamalla **numero poistuu** sekä sivulta että muistiosta. 

Numeroiden lisäämisen tulee tapahtua olion `lisaaNumero` -metodilla, ja puhelinmuistion tulee tarjota metodi `annaNumerot`, jolle annetaan parametrina henkilön nimi. Metodin tulee toimia siten, että sen palauttaman taulukon kautta ei voi muuttaa muistion sisältöä (so. metodi palauttaa numerotaulukon kopion). Puhelinmuistiosta voidaan poistaa numeroita `poistaNumero` -metodilla. Seuraavassa on puhelinmuistio esitetty UML-luokkana:

![Puhelinmuistio-luokka](../img/puhelinmuistio_olio.jpeg "Puhelinmuistio-luokka")

Metodien lisäksi puhelinmuistio-oliolla on tietojen tallettamista varten attribuutti `_henkilot` (, jonka ensimmäisenä merkkinä oleva `_` indikoi tässä sitä, että attribuuttiin ei ole tarkoitus viitata olion metodien ulkopuolelta, vaikka se JavaScript-ohjelmissa on mahdollista). Attribuutti toteutetaan oliona, jossa kutakin muistioon talletettua henkilöä vastaa taulukko-tyyppinen attribuutti henkilön numeroiden tallettamista varten. Esimerkiksi seuraavassa kuvassa `_henkilot` -oliolla on kaksi taulukko-tyyppistä attribuuttia - edellä esitettyä käyttöliittymää vastaava `Flanders` ja sen lisäksi `Bart Simpson`:  

![Henkilot-olio](/osa1/img/henkilot_olio.jpeg "Henkilot-olio")

Palauta tehtävästä `Puhelinmuistio`-funktion sisältävä tiedosto `puhelinmuistio.js`. Varmista ennen palauttamista, että tehtäväpohjan sisältämät testit menevät läpi ilman virheilmoituksia.

#### Vihjeitä ja lisätietoja

Oheismateriaalin [kohdassa 8.1](/weso/#8.1-Oliot) on tehtävään liittyvä esimerkki, jossa rakennetaa kirja-olioita muodostava `Kirja`-funktio. Olioiden rakenne esimerkissä on seuraavanlainen:

![Kirja-luokka](/osa1/img/kirja_olio.jpeg "Kirja-luokka")

JavaScriptissä ei ole olioden luokkia, mutta oliolla on tiedossa, sen luonut funktio. Jos esimerkin `Kirja`-funktiolla on luotu `kirja`-olio, tilannetta voidaan kuvata seuraavanlaisella oliokaaviolla:

![Kirja-rakenne](/osa1/img/kirja_rakenne.jpeg "Kirja-rakenne")

Tehtävän ratkaisussa esim. seuraavat apuveuvot saattavat olla hyödyllisiä:
[Array.prototype.includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes),
[Array.prototype.indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf),
[Array.prototype.push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push),
[Array.prototype.slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice),
[Array.prototype.splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice),
[Object.keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys),
[delete operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete).

