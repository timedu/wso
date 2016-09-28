---
layout: sivu
title: Tehtävä 3.0
exercise_template_name: W3E00.PuhelinmuistioH1
---

## Puhelinmuistio

Tämän osan tehtävien lähtökohtana on [Tehtävän 2.4](../../osa2/tehtava24) ratkaisuksi laadittu puhelinmuistio. Sovelluksen osia kuitenkin toteutetaan perus-JavaScriptin sijaan tukeutumalla *jQuery*- ja *Mustache*-kirjastoihin. [Tehtävässä 3.1](../tehtava31) kontrollerin toteutuksessa sovelletaan *jQueryä*. [Tehtävän 3.2](../tehtava32) näkymä rakennetaan *jQueryllä*. [Tehtävässä 3.3](../tehtava33) käytetään *Mustachea* näkymän toteutuksessa. [Tehtävän 3.4](../tehtava34) käyttämä data talletetaan palvelimelle. Mallin palvelimelle tekemät pyynnöt rakennetaan *jQueryllä*.

Sovellus rakentuu [Tehtävään 2.4](../../osa2/tehtava24) verrattuna jonkin verran eri tavalla. Halutessasi voit muodostaa ensin tässä kuvatun perus-JavaScript -perustaisen ratkaisun jäsentäen Tehtävän 2.4 tuotoksesi hivenen toisella tavalla. Projektipohjan testeineen voi ladata tältä sivulta.

`muistio`-olioon on paketoituna *mallin* ja *näkymän*  muodostinfunktiot sekä funktiot *näkymän* ja *kontrollerin* alustamiseksi:

![Puhelinmuistio-olio](../img/olio30.png "Puhelinmuistio-olio")

Funktiot sijaitsevat tiedostoissa `model.js` (*Model*), `view.js` (*initView*, *View*) ja `controller.js` (*initController*).  Koko sovelluksen alustus on tiedostossa `app.js`:

{% highlight javascript %}

window.onload = function() {
  
    var model = new muistio.Model();   
    var view = new muistio.View();

    muistio.initView(model, view);
    muistio.initController(model, view);        
};

{% endhighlight %}

Alustuksen jälkeen muistio toimii seuraavan kaavion mukaan: 

![Puhelinmuistio-oliokaavio](../img/kaavio30.png "Puhelinmuistio-oliokaavio")


Kontrollerin roolin hoitavat *Html-dokumentissa* olevien panonappien (etsi, lisää, poista) click-tapahtumien käsittelijät, jotka kutsuvat *mallin* (`annaNumerot`, `lisaaNumero`, `poistaNumero`) ja *näkymän*  (`hahmonna`) metodeja halutun toiminnan aikaansaamiseksi. UML-luokkaesityksenan malli[^1] ja näkymä ovat seuraavanlaisia: 

[^1]: Huom. mallin metodit `lisaaNumero` ja `poistaNumero` eivät palauta mitään arvoa.

![Puhelinmuistio-luokat](../img/luokat30.png "Puhelinmuistio-luokat")

Näkymän alustaja (`initView`) määrittelee dokumentin paikan (`asetaPaikka`), johon näkymä rakentaa käyttöliittymän. Kontrollerin alustaja (`initController`) kytkee dokumentin *Etsi*- ja *Lisää* -nappien *click*-tapahtumille käsittelijät sekä välittää näkymälle (`asetaPoista`) funktion, jonka se kytkee rakentamiensa *Poista* -nappien käsittelijäksi.

Koodipohjassa on seuraava merkkaus:

{% highlight html %}

    <body>

        <h1>Puhelinmuistio</h1>

        <div id="lomake">
            <label>Nimi: <input id="nimi"/></label>
            <br/>
            <label>Puhelinnumero: <input id="numero"/></label>
            <br/>
            <button id="etsi">Etsi</button>
            <button id="lisaa">Lisää</button>
        </div>

        <div id="luettelo"></div>

        <script src="js/app.js"></script>        
        <script src="js/model.js"></script>
        <script src="js/view.js"></script>
        <script src="js/controller.js"></script>

    </body>
{% endhighlight %}

*Näkymä* rakentaa ("hahmontaa") käyttöliittymän `div`-elementin (`id="luettelo"`) sisällöksi seuraavaan tapaan:

{% highlight html %}

  <div id="luettelo">
  
    <h2>Henkilön Bart numerot</h2>
    
    <ul>
    
      <li>111-222<button 
        data-nimi="Bart" 
        data-numero="111-222">X</button>
      </li>
      
      <li>333-444<button 
        data-nimi="Bart" 
        data-numero="333-444">X</button>
      </li>
      
    </ul>
    
  </div>
{% endhighlight %}


Tehtäväpohjassa on kolme testijoukkoa. `SpecMuistioModel.js` testaa *mallia*, `SpecMuistioView.js` *näkymää* ja `SpecMuistio.js` koko sovellusta käyttöliittymän kautta.

Tämän tehtävän ratkaisua **ei palauteta**, mutta se lienee luonteva lähtökohta tämän osan (3) muille tehtäville.


