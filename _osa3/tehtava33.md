---
layout: sivu
title: Tehtävä 3.3
exercise_upload_id: 286903
---

## Puhelinmuistio 

Toteuta [Tehtävän 3.0](../tehtava30) kuvaama sovellus - kuitenkin niin, että *näkymä* (`View`) on laadittu hyödyntäen 
[Mustache](https://github.com/janl/mustache.js)- ja 
[jQuery](http://jquery.com)-kirjastoja.

*Mustachea* hyödyntävä toteutus täydentää sovelluksen `muistio`-oliota `template`-attribuutilla, jonka näkymän alustus, `initView`, välittää näkymälle kutsumalla sen `asetaTemplate`-metodia. 

![Mustache-ekstrat](../img/mustache_ext_33.png "Mustache-ekstrat")

Kutsuttaessa *näkymän* `hahmonna`-metodia, *Mustache* muodostaa *templaten* perusteella käyttöliittymän, joka asetetaan *jQueryn* avulla sivulla oleva `div`-elementin (`id='luettelo'`) sisällöksi. *jQueryn* avulla myös asetetaan käyttöliittymän sisältämien Poisto-nappien click-tapahtumille käsittelijät.

**Palauta** tehtävästä tiedosto `view.js`, joka sisältää `View`- ja `initView`[^1] -funktiot sekä `template`-merkkijonon. Varmista ennen palautusta, että tehtäväpohjassa olevat testit onnistuvat.

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

Oheismateriaalin [kohdassa 10.2]({{site.baseurl}}/weso/#10.2-N%C3%A4kym%C3%A4templatet-ja-Mustache.js) käsitellään  *Mustache*-kirjastoa, josta löytyy tarkempi kuvaus pakettiin liittyvässä [README](https://github.com/janl/mustache.js/blob/master/README.md)-tiedostossa.




[^1]: `initView` on pohjassa valmiina.


