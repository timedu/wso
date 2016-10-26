---
layout: sivu
title: Tehtävä 5.4
exercise_upload_id: 
exercise_template_name: 
---

## Puhelinmuistio: Routing 

Kehitä puhelinmuistio-sovellusta edelleen siten, että se muodostuu käyttäjän näkökulmasta kolmesta erillisestä sivusta (Kuvat 1-3).


![ui-1](../img/w5e04-1.png "ui-1")

<small>Kuva 1. Numeroiden haku.</small>

*Hae numeroita* -sivu on sovelluksen oletusnäkymä, joka tulee näkyviin tentäessä (kehitysympäristössä) pyyntö osoitteeseen `http://localhost:8383/W5E04/`[^1]. Sivulle päädytään myös esim. pyynnöllä `http://localhost:8383/W5E04/#/bart`, jolloin `Nimi`-kenttään on valmiiksi täytetty henkilö `bart` ja sivulla on esillä kaikki em. henkilölle talletetut puhelinnumerot (vrt. Kuva 1). Sivulla olevien `uusi numero`- ja `poista` -linkkien avulla voidaan siirtyä sovelluksen muille sivuille. *Lisää numero* -sivulle voidaan siirtyä vain, jos `Nimi`-kenttään on syötetty jokin teksti.

[^1]: Tässä oletetaan, että käytetään oletusarvoin NetBeansin sulautettua web-palvelinta.

![ui-2](../img/w5e04-2.png "ui-2")

<small>Kuva 2. Numeron lisäys.</small>

*Lisää numero* -sivulle päästään klikkaamalla *Hae numeroita* -sivulla olevaa ao. linkkiä tai tekemällä pyyntö suoraan esim. osoitteeseen `http://localhost:8383/W5E04/#/bart/add` (Kuva 2). Sivulla on `Nimi`-kenttä on valmiiksi täytetty ao. henkilöllä, mutta kentän sisältöä voi muuttaa. Klikkaamalla `Lisää` -painiketta `Numero`-kenttään kirjattu puhelinnumero tallentuu henkilölle ja *Hae numeroita* -sivu palaa selaimen ikkunaan siten, että esillä on juuri *Lisää numero* -sivulla käsitellyn henkilön tiedot. `Peruuta` -painikkeen klikkaus tuo esiin *Hae numeroita* -sivun tallentamatta uutta numeroa muistioon.

![ui-3](../img/w5e04-3.png "ui-3")

<small>Kuva 3. Numeron poisto.</small>

*Poistetaanko numero?* -sivulle päästään klikkaamalla *Hae numeroita* -sivulla olevaa ao. linkkiä tai tekemällä pyyntö suoraan esim. osoitteeseen `http://localhost:8383/W5E04/#/bart/remove/222` (Kuva 3). Sivulla on `Nimi`-kenttä on valmiiksi täytetty ao. henkilöllä ja `Numero` -kenttässä on henkilöltä poistettava puhelinnumero. Kenttien sisältöä ei voi muuttaa. Klikkaamalla `Poista` -painiketta `Numero`-kenttään kirjattu puhelinnumero poistuu henkilöltä ja *Hae numeroita* -sivu palaa selaimen ikkunaan siten, että esillä on juuri *Poistetaanko numero?* -sivulla käsitellyn henkilön tiedot. `Peruuta` -painikkeen klikkaus tuo esiin *Hae numeroita* -sivun poistamatta numeroa muistiosta.


{% highlight html %}

    <body ng-app="PuhApp">

        <h1>Puhelinmuistio</h1>

        <div ng-view></div>

        <script src="js/app.js"></script>
        <script src="js/service.js"></script>
        <script src="js/directive.js"></script>

        <script src="todo/controller.js"></script>
        <script src="todo/config.js"></script>

    </body>

{% endhighlight %}

<small>Listaus 1. *index.html*-tiedoston *body*.</small>

Sovelluksen `index`-tiedoston (Listaus 1) viittaamista tiedostoista `app.js` on valmiina sisältäen angular-moduulin luonnin, direktiivin[^2] (`directive.js`) käyttämän vakion määrittelyn sekä alustusdatan palvelua[^3] (`service.js`) varten. Tiedostot `directive.js` ja `service.js` voi kopioida sellaisenaan [Tehtävän 5.3](../tehtava53) ratkaisusta. Halutessaan voi injektoida henkilöitä ja numeroita sisältävän alustusdatan[^4] palveluun.

Tiedostot `controller.js` ja `config.js` tulee laatia pohjassa oleviin runkoihin. `config.js` määrittelee sovelluksen reitityksen ja tiedostossa `controller.js` on kontrolleri kullekin sovelluksen näkymälle. Näkymät (`search.html`, `add.html` ja `remove.html`) ovat pohjassa valmiina projektin `view`-kansiossa.

[^2]: `wso-btn` -direktiivi (ks.[Tehtävän 5.3](../tehtava53)) 
[^3]: `Muistio` -palvelu (ks.[Tehtävän 5.2](../tehtava52))
[^4]: Tiedostossa `app.js` määritelty `init_data`.

**Palauta** tehtävästä tiedostot `controller.js` ja `config.js`. Varmista ennen palautusta, että sovellus toimii odotetusti. Jos pohjakoodi sisältää testejä, varmista myös niiden läpimeno ilman virheilmoituksia.

### Lisätietoja

AngularJS -direktiivejä käsitellään lyhyesti kurssilukemiston [luvuss 15][weso-15]. 

[weso-15]: {{site.baseurl}}/weso/#15-Reititys-Angularissa



#### Alaviitteet
