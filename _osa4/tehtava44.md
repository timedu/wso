---
layout: sivu
title: Tehtävä 4.4
exercise_upload_id: 289240
exercise_template_name: W4E04.SyotteenValidointi
---

## Lomakkeen kelpoistaminen

> Muokkaa tehtäväpohjassa olevia tiedostoja siten, että pohjassa oleva lomake validoidaan. Lomake on validi, jos seuraavat ehdot ovat voimassa:
>
* Käyttäjätunnus on vähintään kolme merkkiä pitkä.
* Käyttäjän salasanan pituus on vähintään kahdeksan merkkiä ja sisältää vähintään yhden numeron ja ison kirjaimen.
* Käyttäjän antama salasana ja sen vahvistus vastaavat toisiaan[^1]. 
* Sekä etu-, että sukunimi on pituudeltaan vähintään kaksi merkkiä ja koostuvat pelkistä kirjaimista.
* Henkilötunnus on määritellynsä mukainen[^2].
* Käyttäjä on hyväksynyt käyttöehdot (checkboxi on valittu).
>
> Poista lomakkeen lähetyspainike käytöstä, kunnes lomake on validi 
([ng-disabled](https://docs.angularjs.org/api/ng/directive/ngDisabled)). Näytä lisäksi kenttiin kohdistuvat virheilmoitukset, jos niille on tarvetta, kunhan käyttäjä on ehtinyt syöttää kenttään arvon.  Jokainen kenttä tulee sitoa jonkin muuttujan arvoon [ng-model](https://docs.angularjs.org/api/ng/directive/ngModel) -attribuutin avulla, muuten validointi ei toimi. 

[^1]: Tähän käytetään Angulariin toteutettua [direktiiviä](https://github.com/TheSharpieOne/angular-validation-match#usage), joka on otettu osaksi sovellusta (JavaScript -tiedosto on projektin hakemistosta `js/libs`). 

[^2]: Henkilötunnuksen muodon määrittely löytyy [Wikipediasta](https://fi.wikipedia.org/wiki/Henkil%C3%B6tunnus#Tunnuksen_muoto). Tässä tehtävässä voi rajoittua 1900 -luvulla syntyneiden henkilöiden rekisteröintiin. Asia hoitunee joudevasti oman direktiivin määrittelyllä, mihin liittyviä ohjeita löytyy *AngularJS:n* kehittäjän oppaasta kohdasta [Custom validation][custom-validation]. Kohdassa voi silmällä vaikka esimerkkiä, jossa määritellään merkkauksessa viitattava `integer` -direktiivi. Tosin tässä tarvittava direktiivi ja siihen liittyvä apufunktio on pohjassa jo lähes valmiina (`todo/directive.js`).

[custom-validation]: https://docs.angularjs.org/guide/forms#custom-validation

Palauta tehtävästä tiedostot `template.html` ja `directive.js`, joiden rungot löytyvät `todo`-hakemistosta. Varmista, että tehtäväpohjassa olevat testit menevät läpi ennen palautusta.


### Lisätietoja

Tehtävä on poimittu lähes sellaisenaan [kurssimateriaalista]({{site.baseurl}}/weso/),
[Tehtävä 30]({{site.baseurl}}/weso/#vk-4-t30), jonka edellä materiaalissa käsitellään tehtävän ratkaisua tukevia asioita.

Erilaisten syötteiden tarkistuksia on usein luonteva tehdä ns. säännöllisillä lausekkeilla (regular expressions). Tähän liittyvä käyttökelpoinen työkalu löytyy osoitteesta <http://rubular.com/>.


#### Alaviitteet

