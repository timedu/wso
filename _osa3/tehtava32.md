---
layout: sivu
title: Tehtävä 3.2
---

## Puhelinmuistio 

Toteuta [Tehtävän 3.0](../tehtava30) kuvaama sovellus - kuitenkin niin, että *näkymä* (`View`) on laadittu hyödyntäen [jQuery](http://jquery.com)-kirjastoa. 

Ratkaisun *näkymä* ei käytä (suoraan) [document](https://developer.mozilla.org/en-US/docs/Web/API/Document) -olion eikä [HTMLElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)-tyyppisten olioiden ominaisuuksia (metodeja/attribuutteja). Niiden sijaan sovelletaan *jQuery*-funktiota (`$`), jonka palauttaman olion metodit 
[append](http://api.jquery.com/append/), 
[appendTo](http://api.jquery.com/appendto/), 
[click](http://api.jquery.com/click/), 
[data](http://api.jquery.com/data/), 
[html](http://api.jquery.com/html/) ja 
[text](http://api.jquery.com/text/) 
saattavat olla tässä hyödyllisiä. 

Mahdollisti tarvittavissa iteraatiossa ei käytetä JavaScriptin silmukkarakenteita eikä 
[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)-tyyppisen olion 
[forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)-metodia. Niiden sijaan voi soveltaa *jQueryn* tarjoamia 
[apufunktiota](http://api.jquery.com/category/utilities/), 
joista esim.
[each](http://api.jquery.com/jQuery.each/) 
saattaa antaa tukea iteraatioiden toteutukseen.


**Palauta tehtävästä** `View`- ja `initView`[^1] -funktiot sisältämä tiedosto `view.js`. Varmista ennen palautusta, että tehtäväpohjassa olevat testit onnistuvat.

[^1]: `initView` on pohjassa valmiina.
