---
layout: sivu
title: Tehtävä 3.3
exercise_upload_id: 286903
exercise_template_name: W3E03.PuhelinmuistioK
---

## Puhelinmuistio 

Toteuta [Tehtävän 3.0](../tehtava30) kuvaama sovellus - kuitenkin niin, että *näkymä* (`View`) on laadittu hyödyntäen 
[Mustache](https://github.com/janl/mustache.js)- ja 
[jQuery](http://jquery.com)-kirjastoja.

*Mustachea* hyödyntävä toteutus täydentää sovelluksen `muistio`-oliota `template`-attribuutilla, jonka näkymän alustus, `initView`, välittää näkymälle kutsumalla sen `asetaTemplate`-metodia. 

![Mustache-ekstrat](../img/mustache_ext_33.png "Mustache-ekstrat")

Kutsuttaessa *näkymän* `hahmonna`-metodia, *Mustache* muodostaa *templaten* perusteella käyttöliittymän, joka asetetaan *jQueryn* avulla sivulla oleva `div`-elementin (`id='luettelo'`) sisällöksi. *jQueryn* avulla myös asetetaan käyttöliittymän sisältämien Poisto-nappien click-tapahtumille käsittelijät.

**Palauta** tehtävästä tiedosto `view.js`, joka sisältää `View`- ja `initView`[^1] -funktiot sekä `template`-merkkijonon. Varmista ennen palautusta, että tehtäväpohjassa olevat testit onnistuvat.

[^1]: `initView` on pohjassa valmiina.


### Lisätietoja

*Mustache* otetaan sovelluksessa käyttöön *jQueryn* tavoin (`index.html`):

{% highlight html %}

<body>
  
  ...
              
  <div id="luettelo"></div>
        
  <script src="https://code.jquery.com/jquery-2.2.4.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/mustache.js/2.2.1/mustache.min.js">
  </script>

  <script src="js/app.js"></script>  
  
  ...      

</body>

{% endhighlight %}

Kurssilukemiston [kohdassa 10.2][kohta-10.2] käsitellään  *Mustache* -kirjastoa, josta löytyy tarkempi kuvaus pakettiin liittyvässä [README][mustache] -tiedostossa.

[kohta-10.2]: {{site.baseurl}}/weso/#10.2-N%C3%A4kym%C3%A4templatet-ja-Mustache.js
[mustache]: https://github.com/janl/mustache.js/blob/master/README.md

#### Esimerkki

Templatet ovat html-muotoisia merkkijonoja, johon on merkitty paikat datalle. Kurssilukemiston esimerkeissä template-merkkijonot on laadittu `script` -elementin sisällöksi. Tässä tehtävässä template laaditaan merkkijono-tyyppisen muuttujan `muistio.template` arvoksi. 

Templaten hahmonnus ("rendedointi") tarkoittaa sitä, että templateen merkityt datan paikat korvataan todellisella datalla. Tulokseksi saadaan html-merkkausta.

{% highlight javascript %}

var template = '...';
var data = '...';

var renderedTemplate = Mustache.render(template, data);

{% endhighlight %}

Seuraavassa on yksinkertainen template ja sen hahmonnus:

{% highlight javascript %}
{% raw %}

var template = "<h2>{{otsikko}}</h2><p>{{kappale}}</p>";

var renderedTemplate = Mustache.render(template, {
  otsikko: "Tervehdys",
  teksti: "Hello, World!"
});

// muuttujan renderedTemplate sisältönä on nyt
// <h2>Tervehdys</h2><p>Hello, World!</p>

{% endraw %}
{% endhighlight %}

Hahmonnettu template voidaan asettaa elementin sisällöksi *jQuery* -objektin `html` -metodilla, esim.

{% highlight javascript %}

  $('#paikka').html(renderedTemplate);

{% endhighlight %}
 

#### Päivityksiä

161014

* Lisätietoja -kohtaan lisätty yksikertainen template -esimerkki


#### Alaviitteet

