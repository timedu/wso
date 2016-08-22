---
layout: sivu
title: Tehtävä 1.3
---

## Puhelinmuistio

[Tehtävässä 1.1](../tehtava11) 
laadittiin funktio, joka luo new -operaattorin tuella puhelinmuistio-olioita. Muodostuvien ongelmaksi jäi se, että niiden sisältämää dataa ei kapseloitu so. dataan pääsi käsiksi metodien ulkopuolelta. [Tehtävässä 1.2](../tehtava12) ratkaisiin kapselointiin liittyvä ongelma, mutta esitetyllä tavalla voidaan tuottaa ainoastaa yksi olio.  

Tässä tehtävässä laaditaan funktio, jolla voidaan tuottaa useita olioita siten, että niiden dataa ei voi käsitellä metodien ulkopuolellta. Funktiosta laaditaan kaksi erilaista versiota, josta toista kutsutaan `new` -operaattorilla ja toista ilman sitä. Molemmissa tapauksissa muodostuvien olioiden rakennetta voidaan kuvata seuraavalla luokkaesityksellä:

![Puhelinmuistio-luokka](../img/puhelinmuistio_luokka_13.png "Puhelinmuistio-luokka")

Funktioiden kutsun jälkeistä tilannetta esittävät oliokaaviot kuitenkin poikkeavat hivenen toisistaan:

{% highlight javascript %}

var puhelinmuistio = new Puhelinmuistio();

{% endhighlight %}

![Puhelinmuistio-olio](../img/puhelinmuistio_olio_13a.png "Puhelinmuistio-olio")

{% highlight javascript %}

var puhelinmuistio = UusiPuhelinmuistio();

{% endhighlight %}

![Puhelinmuistio-olio](../img/puhelinmuistio_olio_13b.png "Puhelinmuistio-olio")

Ensimmäinen olioista on `Puhelinmuistio` mutta jäkimmäinen `Object`. 

**Palauta** tehtävästä tiedosto `puhelinmuistio.js`, joka määrittelee edellä kuvatut funktiot `Puhelinmuistio` ja `UusiPuhelinmuistio`. Varmista ennen palauttamista, että tehtäväpohjan sisältämät testit menevät läpi ilman virheilmoituksia.

Tehtäväpohjassa on laadittavaa oliota käyttävä valmis käyttöliittymä (vrt. [Tehtävä 1.1](../tehtava11)).

#### Vihjeitä ja lisätietoja

Oheismateriaalin [kohdassa 8.3]({{site.baseurl}}/weso/#8.3-Olioiden-tila-ja-new) on tehtävään liittyviä esimerkkejä, joissa määritellään hivenen toisistaan poikkeavia  `Laskuri` -funktioita.

Tehtävän ratkaisussa myös seuraavat apuveuvot saattavat olla hyödyllisiä:
[Array.prototype.includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes),
[Array.prototype.indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf),
[Array.prototype.push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push),
[Array.prototype.slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice),
[Array.prototype.splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice),
[Object.keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys),
[delete operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete)
(so. tarvittava koodi on likimain sama kuin edellisissä tehtävissä - ainoastaan jäsennys on hieman toisenlainen).

