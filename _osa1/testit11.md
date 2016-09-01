---
layout: sivu
title: Tehtävien testeistä
---

Tehtäväpohjat sisältävät tyypillisesti joukon testitapauksia, joita ajetaan selaimessa avaamalla pohjassa oleva dokumentti `SpecRunner.html`.  Dokumentin viittaamat testitapaukset ovat hakemistossa `spec` sijaitsevissa JavaScript -tiedostoissa. Testit on toteutettu [Jasmine](http://jasmine.github.io/) -kirjastolla, joka otetaan käyttöön verkon yli[^1].

Jos SpecRunner tuo esiin sävyltään vihreän sivun, ovat testit menneet läpi. Sivulla on tällöin testitapausten luettelo, jonka otsikossa näkyy ajettujen testien kokonaismäärä ja epäonnistuneiden testien määränä on 0. 

Jos ilmestyvällä sivulla on punaista, kaikki testit eivät ole onnistuneet. Sivu esittää nyt epäonnistuneet testit ja epäonnistumisten syyt[^2]. Testi epäonnistuu, jos testattava koodi aiheutaa poikkeustilanteen tai se antaan virheellisen tuloksen.

Esim. testi `Puhelinmuistion käyttö: ei alusta muistiota numeroilla`[^3] edellyttää, että metodi `annaNumerot` palauttaa tyhjän taulukon, kun kutsun parametrina annetaan nimi, jolle ei ole talletettu numeroja. Testin epäonnistuminen voi johtua esim. siitä, että koodista ei löydy ko. metodia, metodi palauttaa taulukon sijaan arvon null tai metodin palauttaman taulukon alkioiden lukumäärä on yksi. Näihin epäonnistumisiin liittyy seuraavanlaiset ilmoitukset:

* `TypeError: muistio.annaNumerot is not a function ...`
* `TypeError: muistio.annaNumerot(...) is null ...`
* `Expected 1 to equal 0.`


[^1]: Testien ajaminen edellyttää verkkoyhteyttä.
[^2]: Epäonnistumisen jälkeen on vielä epämääräisen näköistä tekstiä, joka esittää epäonnistuneen testin sijainnin ao. JavaScript-tiedostossa sekä testauskirjaston funktioiden kutsupolun.
[^3]: Voi olla, että joitakin testeita ei ole nimetty kovin osuvasti.
