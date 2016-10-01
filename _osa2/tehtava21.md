---
layout: sivu
title: Tehtävä 2.1
exercise_upload_id: 284793
exercise_template_name: W2E01.PuhelinmuistioE
---

## Puhelinmuistio

Laadi puhelinmuistiosta MVC-sunnittelumallia mukaileva toteutus. Ratkaisussa `muistio`-olioon on paketoituna kullekin MVC-mallin elementille oma muodostinfunktionsa sekä funktio sovelluksen alustamista varten:

![Puhelinmuistio-olio](../img/muistio_olio_21.png "Puhelinmuistio-olio")

*Malliin* (`Model`) tallennetaan puhelinmuistion data. *Näkymä* (`View`) rakentaa käyttöliittymän mallin datalle. *Kontrolleri* (`Controller`) vastaanottaa käyttöliitymästä mallin dataan liittyviä pyyntöjä. Sovelluksen alustuksen (`init`) jälkeen muistio toimii seuraavan kaavion mukaan: 

<!--
[^1]: Pohjakoodissa on kommenttimerkkien sisällä `View`-funktion edellä esitetty ko. funktiolla luotavien olioiden luokkaesityksessä myös metodi `poistaNumero(event)`. Tämän voi jättää huomioimatta. Näkymälle välitettävä viite numeron poistavaan funktioon talletetaan olion attribuuttiin `functionPoista`. Luokkaesityksessä on myös ehdotus funktiosta `esitäNumero(nimi, numero)`. Funktiota ei välttämättä tarvita (esim. testit eivät tutki funktion olemassaoloa). `Controller`-olion luokkaesityksessä on metodi `etsiNumerot()`. Sen tulisi olla `haeNumerot()`.
-->

![Puhelinmuistio-oliokaavio](https://www.lucidchart.com/publicSegments/view/c98a82cf-a76f-422d-a450-9a066ac7c278/image.png  "Puhelinmuistio-oliokaavio") 

<!--
![Puhelinmuistio-oliokaavio](../img/olio_kaavio_21.png "Puhelinmuistio-oliokaavio")
-->

*Kontrollerin* metodit (`haeNumerot`, `lisaaNumero`, `poistaNumero`) on kytketty html-dokumentissa olevien painonappien click-tapahtumien käsittelijöiksi. Ne kutsuvat *mallin* vastaavia metodeja (`annaNumerot`, `lisaaNumero`, `poistaNumero`) parametreilla, jotka on poimittu dokumentista  (`inputNimi`, `inputNumero`) tai tapahtumaobjektista (`e`). *Malli* suorittaa metodikutsujen edellyttämät datan päivitysoperaatiot ja pyytää *näkymää* muodostamaan (`paivita`) tilannetta vastaavan käyttöliittymän. *Näkymä* rakentaa käyttöliittymän määrättyyn paikkaan (`spanNimi`, `ulNumerot`) html-dokumentissa. 

Seuraavassa MVC-olioden rakenne on esitetty UML-luokkina:

![Puhelinmuistio-luokat](https://www.lucidchart.com/publicSegments/view/adacaed3-2055-47f7-8f7b-a924c5bf69c6/image.png "Puhelinmuistio-luokat")

<!--
![Puhelinmuistio-luokat](../img/muistio_luokat_21.png "Puhelinmuistio-luokat")
-->

<sup>**Huom.** Tehtävän pohjakoodin kommenttien luokkaesitys saattaa poiketa edellä esitetystä. Ratkaisussa on kuitenkin tarkoitus noudattaa näiltä osin tätä tehtäväkuvausta.</sup>

Seuraavassa on edellistä luokkaesitystä vastaavat tehtävässä laadittavien muodostinfunktioiden rungot;

{% highlight javascript %}

muistio.Model = function (view) {

    var henkilot = {};

    this.annaNumerot = function (nimi) {

    };
    this.lisaaNumero = function (nimi, numero) {

    };
    this.poistaNumero = function (nimi, numero) {

    };
};

{% endhighlight %}



{% highlight javascript %}

muistio.View = function () {

    var spanNimi = null;
    var ulNumerot = null;
    var functionPoistaNumero = null;

    this.asetaSpanNimi = function(elementti) {

    };
    this.asetaUlNumerot = function(elementti) {

    };
    this.asetaPoistonKasittelija = function (f) {

    };
    this.paivita = function (nimi, numerot) {

    };
};

{% endhighlight %}



{% highlight javascript %}

muistio.Controller = function (model) {

    var inputNimi;
    var inputNumero;

    this.asetaNimiInput = function (elementti) {

    };
    this.asetaNumeroInput = function (elementti) {

    };
    this.haeNumerot = function () {

    };
    this.lisaaNumero = function () {

    };
    this.poistaNumero = function (e) {

    };
};

{% endhighlight %}



Sovelluksen alustamisen suorittava funktio `muistio.init` löytyy tehtävän pohjakoodista tiedostosta `app.js`:

{% highlight javascript %}

muistio.init = function () {

    // muodostetaan model, view ja controller

    var view = new muistio.View();
    var model = new muistio.Model(view);
    var controller = new muistio.Controller(model);

    // näkymän käsittelemät kohdat html-dokumentissa

    var spanNimi = document.querySelector('#luettelo h2 span');
    var ulNumerot = document.querySelector('#luettelo ul');

    view.asetaSpanNimi(spanNimi);
    view.asetaUlNumerot(ulNumerot);

    // syötekentät, joista kontrolleri poimii tiedot

    var inputNimi = document.getElementById('nimi');
    var inputNumero = document.getElementById('numero');

    controller.asetaNimiInput(inputNimi);
    controller.asetaNumeroInput(inputNumero);

    // dokumentin nappien click tapahtumien käsitelijät

    var buttonEtsi = document.getElementById('etsi');
    var buttonLisaa = document.getElementById('lisaa');

    buttonEtsi.onclick = controller.haeNumerot;
    buttonLisaa.onclick = controller.lisaaNumero;

    // näkymä rakentaa ajon aikana poisto-nappeja ja määrittelee
    // niiden click-tapahtumien käsittelijäksi tässä parametrina 
    // annetun funktion

    view.asetaPoistonKasittelija(controller.poistaNumero);
};

{% endhighlight %}

**Palauta** tehtävästä tiedosto `puhelinmuistio.js`, joka määrittelee edellä kuvatun kaltaiset muodostinfunktiot `muistio.Model`, `muistio.View` ja `muistio.Controller`. Varmista ennen palauttamista, että tehtäväpohjan sisältämät testit menevät läpi ilman virheilmoituksia.

Edellisten puhelinmuistio-tehtävävien tapaan  pohjakoodi sisältää puhelinmuistion  käyttöliittymän merkkauksen (vrt. [Tehtävä 1.1](../../osa1/tehtava11)). Tässä kuitenkin käyttöliittymää käsittelevä ja sieltä pyyntöjä vastaanottava koodi tulee jäsentää laadittaviin muodostinfunktioihin.

#### Vihjeitä ja lisätietoja

Tässä tehtävässä laadittava `muistio.Model` voi olla likimain sama kuin 
[Tehtävän 1.3](../../osa1/tehtava13) ratkaisuna oleva `Puhelinmuistio`-funktio. Tilanne poikkeaa tässä kuitenkin niin, että mallin metodit kutsuvat näkymän `paivita`-metodia. Funktioihin `muistio.View` ja `muistio.Controller` tulevan koodin voi muodostaa melko pitkälle aikaisempien tehtävien (1.1...1.4) sovellusrungoissa olevan `init`-funktion pohjalta.

Tehtävän ratkaisu on periatteeltaan samankaltainen kuin oheismateriaalin [kohdassa 9.1]({{site.baseurl}}/weso/#9.1-Esimerkki:-Muistuttaja) oleva Muistuttaja-esimerkki:

![Muistutus-olio](../img/muistutus_olio_21.png "Muistutus-olio")

Esimerkissä on tähän tehtävään verrattuna yksi rakenteellinen taso enemmän. Kukin muodostinfunktio on paketoitu omaan olioonsa (`view`, `domain`, `controller`) ja muodostimille on annettu niiden tehtävää kuvaavat nimet. Tämä ratkaisu on luonteva erityisesti silloin, kun sovelluksessa on useita *malleja*, *näkymiä* ja/tai *kontrollereita*. Esimerkissä *näkymän* käsittelemä html-dokumentin kohta välitetään *näkymälle* muodostimen parametrina. Tämän tehtävän ratkaisussa on tätä tarkoitusta varten omat näkymän metodinsa.

#### Päivityksiä

161001:

* korjaus: oliokaaviossa kontrolleriin tehtävä metodikutsu `etsiNumerot` vaihdettu kutsuksi `haeNumerot`; muutos huomioitu myös kaavioon viittaavassa tekstissä 
* korjaus: edellistä vastaava muutos tehty myös olioiden luokka-esitykseen, josta on samalla poistettu `View`-luokassa ollut `esitaNumero` -metodi (esim. testit eivät edellyttä ratkaisun jäsentämistä tällä tavalla)
* lisätty huomautus, joka koskee tehtäväkuvauksen ja tehtäväpohjassa olevien kommenttien epäyhtenäisyyttä
* poistettu "painovirheitä" koskeva alaviite (ks. muutokset *160930*)
* kuvaukseen lisätty laadittavien muodostinfunktioiden rungot

160930: 

* lisätty olioiden luokka -esitysten "painovirheitä" koskeva alaviite 

