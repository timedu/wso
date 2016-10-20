---
layout: sivu
title: Tehtävä 4.1
exercise_upload_id: 289237
exercise_template_name: W4E01.JamesBond
---

## James Bond 

> Muokkaa tehtäväpohjassa olevaa dokumenttia siten, että näkymän otsikon sisältö määräytyy "etunimi" ja "sukunimi" tekstikenttien perusteella. Jos siis "etunimi"-kentän arvo on "Kalle" ja "sukunimi"-kentän arvo on "Ilves", on otsikon sisältö "My names is Ilves, Kalle Ilves". Otsikon alkuarvon tulee olla "My name is Bond, James Bond".

Palauta tehtävästä tiedostot `template.html` ja `controller.js`. Varmista, että tehtäväpohjassa olevat testit[^2] menevät läpi ennen palautusta.

[^2]: Huom. Älä poista templatessa olevia `id`-attribuutteja - testit käyttävät näitä elementtien paikannuksessa.

### Lisätietoja

Tämä on tehtävä on lähes sama kuin [kurssimateriaalin]({{site.baseurl}}/weso/)
[Tehtävä 27]({{site.baseurl}}/weso/#vk-4-t27), jonka edellä käsitellään tehtävän ratkaisua tukevia asioita.


Tehtäväpohjan tietostot on jäsennetty NetBeans-projektissa seuraavasti:

~~~
index.html

todo -+-- template.html
      |
      +-- controller.js

test -+-- SpecRunner.html
      |
      +-- spec -+-- SpecApp.js
~~~

`index.html` integroi sovelluksen siten, että se sisällyttää osakseen täydentävää merkkausta (`template.html`) ja ohjelmakoodia (`controller.js`), jotka löytyvät projektin `todo`-hakemistosta[^1]. Testaukseen liittyvät tiedostot sijaitsevat `test`-hakemistossa.

[^1]: projektin `todo`-hakemisto sisältää tiedostorunkoja, jotka palautetaan täydennettynä tehtävän ratkaisuna. 

Tiedosto `index.html` on pohjassa valmiina. Merkkauksessa on viite
 [AngularJS](https://angularjs.org) -kirjastoon, joka otetaan käyttöön verkon yli. 

{% highlight html %}

<!DOCTYPE html>
<html>
    <head>
        <title>My name is Bond, James Bond</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.5.8/angular.min.js"></script>
    </head>
    <body ng-app='BondApp'>
        <div ng-include="'./todo/template.html'" /></div>        
        <script src='./todo/controller.js'></script>
    </body>
</html>

{% endhighlight %}

Merkkauksessa olevassa *template* otetaan tässä käyttöön AngularJS:n `ng-include` -direktiivillä. Viitatun tiedoston sisältö tulee `div` -elementin sisällöksi. *Kontrolleri* on rakennettu pohjassa hieman eri tavalla kuin mitä on esitetty kurssimateriaalin ao. luvun alkupuolella, mutta sen toiminnassa ei ole rakenteellisesta eroavaisuudesta huolimatta eroa. 


#### Päivityksiä

161020

* lisätty testeihin liittyvä alaviite


#### Alaviitteet

