---
layout: sivu
title: Tehtävä 3.1
---

## Puhelinmuistio 

Toteuta [Tehtävän 3.0](../tehtava30) kuvaama sovellus kuitenkin niin, että *kontrolleri* (`initController`) on laadittu hyödyntäen [jQuery](http://jquery.com)-kirjastoa. 

Ratkaisussa *kontrolleri* ei käytä (suoraan) [document](https://developer.mozilla.org/en-US/docs/Web/API/Document) -olion eikä [HTMLElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)-tyyppisten olioiden ominaisuuksia (metodeja/attribuutteja). Niiden sijaan sovelletaan *jQuery*-funktiota (`$`), jonka palauttaman olion metodit [click](http://api.jquery.com/click/), [val](http://api.jquery.com/val/) ja [data](http://api.jquery.com/data/) saattavat olla tässä hyödyllisiä. 

Palauta tehtävästä `initController`-funktion sisältämä tiedosto `controller.js`.

### Lisätietoja

Sovelluspohjan merkkauksessa (`index.htm`) on määritelty *jQuery*-kirjaston käyttöönotto:

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

        <script src="https://code.jquery.com/jquery-2.2.4.min.js"></script>

        <script src="js/app.js"></script>        
        <script src="js/model.js"></script>
        <script src="js/view.js"></script>
        <script src="js/controller.js"></script>

    </body>

{% endhighlight %}

Kirjasto otetaan käyttöön tässä verkon yli, mutta sen voi myös [ladata](http://jquery.com/download/) osaksi projektin tiedostokokonaisuutta. Luonteva paikka kirjastolle on tällöin esim. projektin hakemisto `js/vendor`. 

Pohjassa sovelluksen alustus on toteutettu jQuery-funktion (alias `$`) tuella:

{% highlight javascript %}

$(function () {
    
    var model = new muistio.Model();   
    var view = new muistio.View();

    muistio.initView(model, view);
    muistio.initController(model, view);  
});

{% endhighlight %}

`$`-funktiolle parametrina annettu funktio suoritetaan dokumentin latauduttua selaimen ikkunaan (vrt. `window.onload`).



