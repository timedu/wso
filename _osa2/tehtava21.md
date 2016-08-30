---
layout: sivu
title: Tehtävä 2.1
---

## Puhelinmuistio

Laadi puhelinmuistiosta MVC-sunnittelumallia mukaileva toteutus. Ratkaisussa on `muistio`-olioon paketoituna kullekin MVC-mallin elementille oma muodostinfunktionsa sekä funktio sovelluksen alustamista varten:

![Puhelinmuistio-olio](../img/muistio_olio_21.png "Puhelinmuistio-olio")

Malliin (`Model`) tallennetaan puhelinmuistion data. Näkymä (`View`) rakentaa käyttöliittymän mallin datalle. Kontrolleri (`Controller`) vastaanottaa käyttöliitymästä mallin dataan liittyviä pyyntöjä. Sovelluksen alustuksen (`init`) jälkeen muistio toimii seuraavan kaavion mukaan: 

![Puhelinmuistio-oliokaavio](../img/olio_kaavio_21.png "Puhelinmuistio-oliokaavio")

Kontrollerin metodit (`etsiNumerot`, `lisaaNumero`, `poistaNumero`) on kytketty html-dokumentissa olevien panonappien click-tapahtumien käsittelijöiksi. Ne kutsuvat mallin vastaavia metodeja (`annaNumerot`, `lisaaNumero`, `poistaNumero`) parametreilla, jotka on poimittu dokumentista  (`inputNimi`, `inputNumero`) tai tapahtumaobjektista (`e`). Malli suorittaa metodikutsujen edellyttämät datan päivitysoperaatiot ja pyytää näkymää muodostamaan (`paivita`) tilannetta vastaavan käyttöliittymän. Näkymä rakentaa käyttöliittymän määrättyyn paikkaan (`spanNimi`, `ulNumerot`) html-dokumentissa. Seuraavassa MVC-olioden rakenne on esitetty UML-luokkina:

![Puhelinmuistio-luokat](../img/muistio_luokat_21.png "Puhelinmuistio-luokat")

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

Esimerkissä on tähän tehtävään verrattuna yksi rakenteellinen taso enemmän. Kukin muodostinfunktio on paketoitu omaan olioonsa (`view`, `domain`, `controller`) ja muodostimille on annettu niiden tehtävää kuvaavat nimet. Tämä ratkaisu on luonteva erityisesti silloin, kun sovelluksessa on useita malleja, näkymiä ja/tai kontrollereita. Esimerkissä näkymän käsittelemä html-dokumentin kohta välitetään näkymälle muodostimen parametrina. Tehtävän ratkaisussa on tätä tarkoitusta varten omat näkymän metodinsa.


