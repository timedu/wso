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

*Html-dokumentissa* olevien painonappien click-tapahtumien käsittelijät kutsuvat *mallin* (`annaNumerot`, `lisaaNumero`, `poistaNumero`) ja *näkymän*  (`paivita`) metodeja. 

*Näkymän* muodostin pysyy tässä edelleen samana (vrt. tehtävät [2.1](../tehtava21),  [2.2](../tehtava22) ja [2.3](../tehtava23)). *Malli* pelkistyy seuraavanlaiseksi:

![Puhelinmuistio-luokat](../img/muistio_luokat_24.png "Puhelinmuistio-luokat")

Sovelluksen alustuksen suorittavan `init`-funktion rakentaa seuraavaan tyyliin:

{% highlight javascript %}


muistio.init = function () {

    /*
     * Malli
     * ----------------------------------------------------------------
     */

    var model = new muistio.Model();

    /*
     * Näkymä
     * ----------------------------------------------------------------
     */

    var view = new muistio.View();

    // näkymän käsittelemät elementissä html-dokumentissa
    
    view.asetaSpanNimi(...);
    view.asetaUlNumerot(...);
    
    /*
     * Tapahtumakäsittelijät ("kontrolleri")
     * ----------------------------------------------------------------
     */

    // syötekentät, joista "kontrolleri" poimii tiedot

    ...

    // numeroiden haku 
    
    var buttonEtsi = document.getElementById('etsi');
    buttonEtsi.onclick = function () {
    
        // haetaan mallista (model) annaNumerot-metodilla ao. tietokenttään
        // annetun henkilön numerot
        
        // päivitetään käyttöliittymä kutsumalla näkymän (view)
        // paivita-metodia        
    };
        
    // numeron lisäys

    var buttonLisaa = document.getElementById('lisaa');
    buttonLisaa.onclick = function () {

        // lisätää malliin (model) lisaaNumero -metodilla sivun tietokenttiin
        // annetut tiedot ("trimmattuna")

        // haetaan mallista (model) annaNumerot-metodilla numerot koskien 
        // henkilöä, jolle lisättiin uusi numero
        
        // päivitetään käyttöliittymä kutsumalla näkymän (view)
        // paivita-metodia                
    };

    // numeron poisto

    // - näkymä rakentaa ajon aikana poisto-nappeja ja määrittelee
    //   niiden click-tapahtumien käsittelijäksi tässä parametrina 
    //   annetun funktion
    
    view.asetaPoistonKasittelija(function (e) {
    
        // poistetaan mallista (model) poistaNumero -metodilla ao. painonapin
        // oheen (dataset) talletetut tiedot, jotka annetaan ko. funktiolle 
        // parametreina "trimmattuna"

        // haetaan mallista (model) annaNumerot-metodilla numerot koskien 
        // henkilöä, jolta poistettiin numero
        
        // päivitetään käyttöliittymä kutsumalla näkymän (view)
        // paivita-metodia                        
    });
        
};

{% endhighlight %}


**Palauta** tehtävästä tiedosto `app.js`, joka sisältää sovelluksen *alustajan* ja *mallin* muodostinfunktion. Varmista ennen palauttamista, että tehtäväpohjan sisältämät testit menevät läpi ilman virheilmoituksia.

Edellisten tehtävävien tapaan pohjakoodi sisältää puhelinmuistion  käyttöliittymän merkkauksen (vrt. [Tehtävä 1.1](../../osa1/tehtava11)). Tiedostot `app.js` ja `view.js` sisältävät ao. funktioiden rungot. 

#### Vihjeitä ja lisätietoja

Tämän tehtävän voi ratkaista siten, että kopioi ensin edellisen tehtävän ratkaisusta  *mallin* ja *näkymän* muodostimet sekä alustusfunktion. *Näkymä* on valmis sellaisenaan, mutta *malli* ja *alustaja* edellyttävät pieniä muutoksia. Aiemmista tehtävistä poiketen, tässä sovelluksen alustajan (`muistio.init`) kutsu on tiedostossa `index.html`[^2]. 

[^2]: Aiemmissa tehtävissä sovelluksen alustajan kutsu on tiedostossa `app.js`.

Oheismateriaalin [kohdassa 9.4]({{site.baseurl}}/weso/#9.4-MVC,-MVP,-MVVM,-...) esitellään tässä sovellettavan MVP-mallin periaate.

#### Päivityksiä

161003

* lisätty `init`-funktion runko

#### Alaviitteet


