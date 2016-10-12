---
layout: sivu
title: Tehtävä 4.3
exercise_upload_id: 289239
exercise_template_name: W4E03.ElokuvaHaku
---

## Elokuvahaku

> Muokkaa tehtäväpohjassa olevaa templatea siten, että templaten muodostamaa elokuvien listaa pystyy filtteröimään nimen, julkaisuvuoden ja ohjaajan perusteella käyttämällä sivulla olevia kenttiä. Jos siis käyttäjä syöttää esimerkiksi "nimi"-kenttään arvon "The Lord" ja "ohjaaja"-kenttään arvon "Peter", tulee näkymässä listata vain elokuvat, joiden nimestä löytyy sana "The Lord" ja ohjaajan nimestä löytyy sana "Peter". 

Palauta tehtävästä tiedosto `template.html`, jonka runko löytyy `todo`-hakemistosta. Varmista, että tehtäväpohjassa olevat testit menevät läpi ennen palautusta.  


#### Lisätietoja

Tämä on tehtävä on lähes sama kuin [kurssimateriaalin]({{site.baseurl}}/weso/)
[Tehtävä 29]({{site.baseurl}}/weso/#vk-4-t29), jonka edellä materiaalissa käsitellään tehtävän ratkaisua tukevia asioita. Filtteröinnistä löytyy tietoja *AngularJS* -käsikirjan [ao. sivulta](https://docs.angularjs.org/api/ng/filter/filter). 

Elokuvataulukko (`$scope.movies`) löytyy kontrollerista `MovieController` (`js/controller.js`). *Kontrolleriin* ei tarvitse tehdä mitään muutoksia.




