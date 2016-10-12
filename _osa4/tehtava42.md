---
layout: sivu
title: Tehtävä 4.2
exercise_upload_id: 289238
exercise_template_name: W4E02.Elokuvat
---

## Elokuvat

> Laadi tehtäväpohjaan template siten, että se listaa 
( [ng-repeat](https://docs.angularjs.org/api/ng/directive/ngRepeat) ) 
osana dokumentia  `MovieController` -kontrollerissa[^2] määritellyn taulukon[^3]  elokuvat siten, että lista vastaa pohjassa olevaa  vakiomerkkausta[^1].

[^1]: Merkkaus on poiskommentoituna tiedostossa `index.html`.

[^2]: `MovieController` löytyy tiedostosta `js\controller.js`.

[^3]: `$scope.movies`

> Elokuvan otsikko sisältää sen nimen ja julkaisuvuoden. Elokuvan nimen tulee olla linkki sen sivulle 
[IMDb](http://www.imdb.com/):ssä 
( [ng-href](https://docs.angularjs.org/api/ng/directive/ngHref) ). 
Oscar-palkinnot tulee näyttää vain, jos elokuvalla niitä on 
( [ng-if](https://docs.angularjs.org/api/ng/directive/ngIf) ). 
"Oscar awards" otsikon vieressä suluissa on Oscar-palkintojen lukumäärä. Elokuvan näyttelijät tulee listata 
( [ng-repeat](https://docs.angularjs.org/api/ng/directive/ngRepeat) ) 
niin, että näyttelijän nimi on ensin ja sen jälkeen suluissa näyttelijän roolinimi elokuvassa. Järjestä elokuvien lista julkaisuvuoden perusteella 
( [orderBy](https://docs.angularjs.org/api/ng/filter/orderBy) ), 
niin että uusin elokuva on listan kärjessä. 

Palauta tehtävästä tiedosto `template.html`, jonka runko löytyy `todo`-hakemistosta. Varmista, että tehtäväpohjassa olevat testit menevät läpi ennen palautusta.


#### Lisätietoja

Tämä on tehtävä on lähes sama kuin [kurssimateriaalin]({{site.baseurl}}/weso/)
[Tehtävä 28]({{site.baseurl}}/weso/#vk-4-t28), jonka edellä materiaalissa käsitellään tehtävän ratkaisua tukevia asioita.


#### Alaviitteet
