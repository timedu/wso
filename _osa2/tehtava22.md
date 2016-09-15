---
layout: sivu
title: Tehtävä 2.2
exercise_upload_id: 284936
exercise_template_name: W2E02.PuhelinmuistioF
---

## Puhelinmuistio

Laadi puhelinmuistiosta MVC-sunnittelumallia mukaileva toteutus, jossa ei ole eksplisiittistä *kontrolleria*. Ratkaisussa `muistio`-olioon on paketoituna *mallin* ja *näkymän*  muodostinfunktiot sekä funktio sovelluksen alustamista varten:

![Puhelinmuistio-olio](../img/muistio_olio_22.png "Puhelinmuistio-olio")

*Malliin* (`Model`) tallennetaan puhelinmuistion data. *Näkymä* (`View`) rakentaa käyttöliittymän *mallin* datalle. Käyttöliittymän painonappeihin kytketyt tapahtumakäsittelijät esittävät *mallin* dataan liittyviä pyyntöjä. Sovelluksen alustuksen (`init`) jälkeen muistio toimii seuraavan kaavion mukaan: 

![Puhelinmuistio-oliokaavio](../img/olio_kaavio_22.png "Puhelinmuistio-oliokaavio")

*Html-dokumentissa* olevien panonappien click-tapahtumien käsittelijät kutsuvat *mallin* metodeja (`annaNumerot`, `lisaaNumero`, `poistaNumero`) parametreilla, jotka on poimittu dokumentin tekstikentistä  tai tapahtumaobjektista. *Malli* suorittaa metodikutsujen edellyttämät datan päivitysoperaatiot ja pyytää *näkymää* muodostamaan (`paivita`) tilannetta vastaavan käyttöliittymän. *Näkymä* rakentaa käyttöliittymän määrättyyn paikkaan (`spanNimi`, `ulNumerot`) *html-dokumentissa*. 

Seuraavassa *mallin* ja *näkymän* rakenteet on esitetty UML-luokkina:

![Puhelinmuistio-luokat](../img/muistio_luokat_22.png "Puhelinmuistio-luokat")

*Mallin* ja *näkymän* muodostimet ovat täysin samoja kuin [Tehtävän 2.1](../tehtava21) ratkaisussa. *Kontrollerin* roolin toteuttaa käyttöliittymän painonappien tapahtumakäsittelijäfunktiot, jotka asetetaan sovelluksen alustuksen yhteydessä (`muistio.init`).

**Palauta** tehtävästä tiedosto `app.js`, joka sisältää sovelluksen alustuksen suorittavan funktion `muistio.init`. 

Tehtäväpohjassa ei ole mukana testikoodia. Varmista kuitenkin, että sovellus toimii sitä ajamalla, kun ratkaisussa on mukana edellisen tehtävän yhteydessä laaditut ja testatut *mallin* ja *näkymän* muodostimet.

Edellisten puhelinmuistio-tehtävävien tapaan pohjakoodi sisältää puhelinmuistion  käyttöliittymän merkkauksen (vrt. [Tehtävä 1.1](../../osa1/tehtava11)). Pohjassa on mukana myös `app.js`, jossa on sovelluksen alustamisen suorittavan funktion runko, sekä tiedosto `puhelinmuistio.js`, joka sisältää *mallin* ja *näkymän* muodostinfunktioiden rungot.

#### Vihjeitä ja lisätietoja

Tämän tehtävän voi ratkaista siten, että a) kopioi suoraan edellisen tehtävän ratkaisusta *mallin* ja *näkymän* muodostimet, ja b) kopioi edellisen tehtävän pohjasta `init`-funktion ja muokkaa sitä hyödyntäen koodia, joka löytyy edelisen tehtävän ratkaisun *kontrollerin* muodostimesta.


Oheismateriaalin [kohdassa 9.1]({{site.baseurl}}/weso/#9.1-Esimerkki:-Muistuttaja) esitellään MVC-mallin mukainen Muistuttaja-esimerkki, joka sisältää eksplisiittisen kontrollerin. [Kohdassa 9.2]({{site.baseurl}}/weso//#9.2-Kontrollerin-rooli-selainohjelmistoissa) esitetään, miten ratkaisu voidaan toteuttaan ilman *kontrollerin* muodostinta.

