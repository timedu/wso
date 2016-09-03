---
layout: sivu
title: Tehtävä 1.4
exercise_template_name: W1E04.PuhelinmuistioD
exercise_upload_id: 278936
---

## Puhelinmuistio

Laadi funktio `Puhelinmuistio`, jonka avulla voidaan muodostaa aiemmista tehtävistä tuttuja puhelinmuistio-olioita kuitenkin siten, että muistiot sisältävät valmiina joukon hätänumeroita. Tehtäväpohjassa on seuraava hatanumerot -olio:

{% highlight javascript %}

var hatanumerot = {
    poliisi: [112],
    sos: [112, 911]
};

{% endhighlight %}


Puhelinmuistio-funktiota käytetään olioita luotaessa seuraavasti:


{% highlight javascript %}

var puhelinmuistio = new Puhelinmuistio();

{% endhighlight %}


Oliota voi käyttää heti luonnin jälkeen esim. seuraavasti:


{% highlight javascript %}

puhelinmuistio.annaNumerot('sos'); // palauttaa taulukon [112, 911]
puhelinmuistio.lisaaNumero('poliisi', '03-311511') // ei tee mitään
puhelinmuistio.poistaNumero('sos', '112') // ei tee mitään

{% endhighlight %}

Toteutuksen tulee olla sellainen, että puhelinmuistio-olion metodit eivät viittaa globaaliin `hatanumerot`-olioon. `Puhelinmuistio`-funktiolla luotavia olioita voidaan esittää seuraavalla kaaviolla:


![Puhelinmuistio-olio](../img/puhelinmuistio_olio_14.png "Puhelinmuistio-olio")

**Palauta** tehtävästä tiedosto `puhelinmuistio.js`, joka määrittelee edellä kuvatun funktion `Puhelinmuistio`. Varmista ennen palauttamista, että tehtäväpohjan sisältämät [testit](../testit11/) menevät läpi ilman virheilmoituksia.

Tehtäväpohjassa on laadittavaa oliota käyttävä valmis käyttöliittymä (vrt. [Tehtävä 1.1](../tehtava11)).

#### Vihjeitä ja lisätietoja

Oheismateriaalin [kohdassa 8.4]({{site.baseurl}}/weso/#8.4-Moduulien-ja-olioiden-yhdistäminen) rakennetaan olioita luova `Ostoskori` -funktio siten, että muodostuvien olioiden käytössä on `hinnasto`.

Tehtävän ratkaisussa myös seuraavat apuveuvot saattavat olla hyödyllisiä:
[Array.prototype.includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes),
[Array.prototype.indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf),
[Array.prototype.push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push),
[Array.prototype.slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice),
[Array.prototype.splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice),
[Object.keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys),
[delete operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete)
(so. tarvittava koodi on likimain sama kuin edellisissä tehtävissä - ainoastaan jäsennys on hieman toisenlainen).

