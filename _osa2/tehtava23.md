---
layout: sivu
title: Tehtävä 2.3
exercise_upload_id: 285025
exercise_template_name: W2E03.PuhelinmuistioG
---

## Puhelinmuistio

Laadi puhelinmuistiosta MVC-sunnittelumallia mukaileva toteutus, jossa *mallin* käytössä ei ole viitettä *näkymään*. Ratkaisussa *mallille* asetetaan tarkkailija (funktio), jota *malli* kutsuu, kun sen sisältämä data muuttuu. [Edellisen tehtävän](../tehtava22) tapaan 
 sovellus ei sisällä eksplisiittistä *kontrolleria*. Ratkaisussa `muistio`-olioon on paketoituna *mallin* ja *näkymän*  muodostinfunktiot sekä funktio sovelluksen alustamista varten:

![Puhelinmuistio-olio](../img/muistio_olio_22.png "Puhelinmuistio-olio")

Sovellukseen liittyy kolme JavaScript -tiedostoa. *Alustuksen* toteuttava koodi on tiedostossa `app.js`, *mallin* muodostin tiedostossa `model.js` ja *näkymän* muodostin tiedostossa `view.js`.

*Malliin* (`Model`) tallennetaan puhelinmuistion data. *Näkymä* (`View`) rakentaa käyttöliittymän *mallin* datalle. Käyttöliittymän painonappeihin kytketyt tapahtumakäsittelijät esittävät *mallin* dataan liittyviä pyyntöjä. Sovelluksen alustuksen (`init`) jälkeen muistio toimii seuraavan kaavion mukaan: 

![Puhelinmuistio-oliokaavio](../img/olio_kaavio_23.png "Puhelinmuistio-oliokaavio")

*Html-dokumentissa* olevien painonappien click-tapahtumien käsittelijät kutsuvat *mallin* metodeja (`annaNumerot`, `lisaaNumero`, `poistaNumero`), ja myös *näkymän* `paivita`-metodia silloin, kun käyttöliittymä pyytää tietyn henkilön puhelinnumeroita. Jos kysymyksessä on *mallin* dataa päivittävä pyyntö, *malli* ilmoittaa datan päivittymisestä kutsumalla sille asetettua `tarkkailija`-funktiota. Tarkkailijaa ei kuitenkaan kutsuta, jos päivityspyynnön (esim. `lisaaNumero`) seurauksena data ei muutu (esim. yritettäessä lisätä henkilölle jo muistiossa olevaa numeroa).

Tarkkailija määritellään niin, että se kutsuu *näkymän* `paivita`-metodia. 

*Mallin* `annaNumerot` -metodi ei kutsu tarkkailijaa vaan `annaNumerot` palauttaa pyydetyn henkilön numerotaulukon. *Mallin* metodien suoritus ei saa aiheutaa virhetilannetta, vaikka mallille ei ole asetettu tarkkailijaa.  

Seuraavassa *mallin* ja *näkymän* rakenteet on esitetty UML-luokkina:

![Puhelinmuistio-luokat](../img/muistio_luokat_23.png "Puhelinmuistio-luokat")

<sup>Luokkaesityksessä olevia metodeja `suoritaTarkkailija` ja `esitaNumero` ei välttämättä tarvita. `Model`-luokan `tarkkailija`-ominaisuuden alkuarvona voisi olla `function(){}` (tyhjä funktio) `null`-arvon sijaan, jolloin asettamattoman tarkkailijan kutsu ei aiheuta virhettä.</sup>

*Näkymän* muodostin on täysin sama kuin tehtävin [2.1](../tehtava21) ja [2.2](../tehtava22) ratkaisussa. *Malliin* ei talleteta edellisten tehtävien tapaan viitettä *näkymään*. Sen sijaan sovelluksen alustaja (`muistio.init`) asettaa *mallille* `tarkkailija`-funktion `asetaTarkkailija`-metodilla.

**Palauta** tehtävästä tiedosto `model.js`, joka sisältää sovelluksen *mallin* muodostinfunktion. Varmista ennen palauttamista, että tehtäväpohjan sisältämät malliin liittyvät testit menevät läpi ilman virheilmoituksia.

Edellisten puhelinmuistio-tehtävävien tapaan pohjakoodi sisältää puhelinmuistion  käyttöliittymän merkkauksen (vrt. [Tehtävä 1.1](../../osa1/tehtava11)). Pohjassa on mukana myös `app.js` sekä `view.js`, jotka sisältää ao. funktioiden rungot.

#### Vihjeitä ja lisätietoja

Tämän tehtävän voi ratkaista siten, että kopioi ensin edellisen tehtävän ratkaisusta  *mallin* ja *näkymän* muodostimet sekä alustusfunktion. *Näkymä* on valmis sellaisenaa, mutta *malli* ja *alustaja* edellyttävät pieniä muutoksia. 


Oheismateriaalin [kohdassa 9.3]({{site.baseurl}}/weso/#9.3-Esimerkki:-Spoilaaja) on esimerkki, jossa mallille asetetaan datan muutoksista ilmoittava tarkkailija (esimerkissä: `listener`).

#### Päivityksiä

161002

* lisätty tarkkailijan toimintaan liittyviä täsmennyksiä

161001

* lisätty luokkaesityksen täsmennyksiä



