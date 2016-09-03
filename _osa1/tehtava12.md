---
layout: sivu
title: Tehtävä 1.2
exercise_template_name: W1E02.PuhelinmuistioB
exercise_upload_id: 278934
---

## Puhelinmuistio (moduuli)

Toteuta tehtäväpohjaan koodi, joka muodostaa olion `puhelinmuistio` siten, että puhelinmuistioon liittyvää dataa (nimiä ja numeroita) ei voi käsitellä olion metodien ulkopuolelta. UML-luokkana esitettynä olion rakenne on seuraavanlainen: 

![Puhelinmuistio-luokka](../img/puhelinmuistio_moduuli.jpeg "Puhelinmuistio-luokka")

Olioon laadittava `_reset`-metodi on tarkoitettu testausta varten. Se asettaa puhelinmuistion datan alkuarvoonsa (tyhjä olio). Oliokaaviona puhelinmuistio näyttää seuraavalta: 

![Puhelinmuistio-olio](../img/puhelinmuistio_sulkeuma.png "Puhelinmuistio-olio")

**Palauta** tehtävästä `puhelinmuistio`-olion muodostava tiedosto `puhelinmuistio.js`. Varmista ennen palauttamista, että tehtäväpohjan sisältämät [testit](../testit11/) menevät läpi ilman virheilmoituksia.

Tehtäväpohjassa on laadittavaa oliota käyttävä valmis käyttöliittymä (vrt. [Tehtävä 1.1](../tehtava11)).

#### Vihjeitä ja lisätietoja

Oheismateriaalin [kohdassa 8.2]({{site.baseurl}}/weso/#8.2-Moduulit) on tehtävään liittyvä esimerkki, jossa rakennetaa ostoskori-olion muodostava koodi. Olion rakenne esimerkissä on seuraavanlainen:

![Ostoskori-luokka](../img/ostoskori_moduuli.jpeg "Ostoskori-luokka")

Koodissa on ilman erillistä kutsua suoritettava anonyymifunktio, jonka paluuarvona on muodostettava olio. `ostokset` on funktion sisällä esitelty muuttuja, ja `lisaaOstos` ja `tuotteitaYhteensa` ovat funktion sisällä määriteltyjä toisia funktioita. `lisaa` ja `tuotteidenLukumaara` ovat funktion palauttaman olion metodeja. 

Funktio on anonyymi, jos sille ei määrittelyn yhteydessä anneta nimeä:

{% highlight javascript %}

    function() {
      // ...
    }

{% endhighlight %}

Funktio suoritetaan määrittelyn yhteydessä ilman erillistä kutsua, jos se on asetettu sulkumerkkien sisään:

{% highlight javascript %}

    (function() {
      // ...
    })();

{% endhighlight %}

Ostoskorin koodi rakentuu esimerkissä seuraavasti:

{% highlight javascript %}

  var ostoskori = (function() {
  
    // sisäiset muuttujat
  
    var ostokset = [];

    // sisäiset funktiot

    function lisaaOstos(tuotteenNimi) {
      // ...
    }

    function tuotteitaYhteensa() {
      // ...
    }

    // rajapinta
    
    return {
        lisaa: lisaaOstos,
        tuotteidenLukumaara: tuotteitaYhteensa
    };
    
  })();

{% endhighlight %}


Edellä palautettavan olion metodit (`lisaa`, `tuotteidenLukumaara`) ovat viitteitä funktion sisäisiin funktioihin (`lisaaOstos`, `tuotteitaYhteensa`), jotka käsittelevät funktion sisällä esiteltyä muuttujaa `ostokset`. Metodien ja metodien viittaamien sisäfunktioden nimet voivat olla samoja (, mikä lienee usein luontevaa):

{% highlight javascript %}

  var ostoskori = (function() {

    // ...  

    function lisaa(tuotteenNimi) {
      // ...
    }

    function tuotteidenLukumaara() {
      // ...
    }
    
    return {
        lisaa: lisaa,
        tuotteidenLukumaara: tuotteidenLukumaara
    };
    
  })();

{% endhighlight %}

Palautettavan olion metodit voidaan myös määritelä anonyymifunktiona palautettavan olion määrittelyn osana:

{% highlight javascript %}

  var ostoskori = (function() {
    
    var ostokset = [];
    
    return {
        lisaa: function(){
          // ...
        },
        tuotteidenLukumaara: function(){
          // ...
        }
    };
    
  })();

{% endhighlight %}

Edellä olevan koodin suorituksen jälkeinen tilanne voidaan esittää oliokaaviona  seuraavasti:

![Ostoskori-olio](../img/ostoskori_sulkeuma.png "Ostoskori-olio")


Tehtävän ratkaisussa myös seuraavat apuveuvot saattavat olla hyödyllisiä:
[Array.prototype.includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes),
[Array.prototype.indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf),
[Array.prototype.push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push),
[Array.prototype.slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice),
[Array.prototype.splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice),
[Object.keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys),
[delete operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete)
(so. tarvittava koodi on likimain sama kuin [edellisessä tehtävässä](../tehtava11) - ainoastaan jäsennys on hieman toisenlainen).

