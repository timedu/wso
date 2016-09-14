---
layout: sivu
title: Tehtävä 2.4
exercise_upload_id: 285026
exercise_template_name: W2E04.PuhelinmuistioH
---

## Puhelinmuistio

Laadi puhelinmuistiosta MVC-sunnittelumallia mukaileva toteutus[^1], jossa *malli* toimii  siten, että se ei tiedota ulospäin datansa muutoksista. Tässä *kontrolleri* välittää  *mallista* datan *näkymälle*. *Kontrollerin* roolin hoitaa käyttöliittymän painonappien tapahtumakäsittelijät, jotka määrittelee sovelluksen *alustaja*.

Ratkaisussa `muistio`-olioon on paketoituna *mallin* ja *näkymän*  muodostinfunktiot sekä funktio sovelluksen alustamista varten:

[^1]: Oheismateriaalissa tästä toteutusmallista käytetään nimitystä *Model-View-Presenter (MVP)* 

![Puhelinmuistio-olio](../img/muistio_olio_22.png "Puhelinmuistio-olio")

Sovellukseen liittyy kaksi JavaScript -tiedostoa. *Alustuksen* toteuttava koodi ja *mallin* muodostin sijaitsevat (palautettavassa) tiedostossa `app.js`, ja *näkymän* muodostin tiedostossa `view.js`.

 Sovelluksen alustuksen (`init`) jälkeen muistio toimii seuraavan kaavion mukaan: 

![Puhelinmuistio-oliokaavio](../img/olio_kaavio_24.png "Puhelinmuistio-oliokaavio")

*Html-dokumentissa* olevien panonappien click-tapahtumien käsittelijät kutsuvat *mallin* (`annaNumerot`, `lisaaNumero`, `poistaNumero`) ja *näkymän*  (`paivita`) metodeja. 

*Näkymän* muodostin pysyy tässä edelleen samana (vrt. tehtävät [2.1](../tehtava21),  [2.2](../tehtava22) ja [2.3](../tehtava23)). *Malli* pelkistyy seuraavanlaiseksi:

![Puhelinmuistio-luokat](../img/muistio_luokat_24.png "Puhelinmuistio-luokat")

**Palauta** tehtävästä tiedosto `app.js`, joka sisältää sovelluksen *alustajan* ja *mallin* muodostinfunktion. Varmista ennen palauttamista, että tehtäväpohjan sisältämät testit menevät läpi ilman virheilmoituksia.

Edellisten tehtävävien tapaan pohjakoodi sisältää puhelinmuistion  käyttöliittymän merkkauksen (vrt. [Tehtävä 1.1](../../osa1/tehtava11)). Tiedostot `app.js` ja `view.js` sisältävät ao. funktioiden rungot. 

#### Vihjeitä ja lisätietoja

Tämän tehtävän voi ratkaista siten, että kopioi ensin edellisen tehtävän ratkaisusta  *mallin* ja *näkymän* muodostimet sekä alustusfunktion. *Näkymä* on valmis sellaisenaa, mutta *malli* ja *alustaja* edellyttävät pieniä muutoksia. 


Oheismateriaalin [kohdassa 9.4]({{site.baseurl}}/weso/#9.4-MVC,-MVP,-MVVM,-...) esitellään tässä sovellettavan MVP-mallin periaate.

