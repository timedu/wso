---
layout: sivu
title: Tehtävä 4.7
exercise_upload_id: 289243
exercise_template_name: W4E07.Muistilista
---

## Muistilista

> Toteuta edellisiä tehtäviä hieman laajempi sovellus, *muistilista*. Muistilistan avulla käyttäjä voi lisätä itselleen tehtäviä, jotka hän itse priorisoi. Lisätyn tehtävän voi merkata tehdyiksi, poistaa ja sen prioriteettia voi muuttaa. Tehtävät tulee järjestää muistilistaan niiden prioriteetin mukaan. Muistilistan ulkoasu[^1] on seuraavanlainen: 

[^1]: käyttöliittymän perusmerkkaus ja tyylit ovat pohjassa valmiina (`todo/template.html`, `css/todo.css`)

![Muistilista](../img/muistilista.png "Muistilista")

> Toteuta sovellukseen seuraavat toiminnot:
>
* Käyttäjä voi lisätä tehtävän listaan "Uusi tehtävä"-tekstikentän nimen perusteella. Älä anna käyttäjän lisätä tehtävää tyhjällä nimellä.
* Käyttäjä voi merkata merkata tehtävän tehdyksi klikkaamalla checkboxia. Tehdyn tehtävän nimi vedetään yli (voit lisätä tehtävän nimeen tällöin luokan `todo-done` (vihje: [ng-class][ng-class]).
* Käyttäjä voi merkata kaikki tehtävät tehdyksi klikkaamalla "Merkkaa kaikki tehdyiksi" -painiketta.
* Käyttäjä voi poistaa tehtävän listasta painamalla oikeasta laidasta "Poista"-painiketta.
* Käyttäjä voi poistaa kaikki tehtävät klikkaamalla "Poista kaikki"-painiketta. Varmista painikkeen klikkaamisen jälkeen, että käyttäjä haluaa varmasti poistaa kaikki tehtävät (vihje: [confirm][confirm]).
* Tehtävään liittyy prioriteetti. Jokaiselle tehtävälle lisätään sen lisäämisen yhteydessä prioriteetti 1. Mitä pienempi prioriteetti on, sitä tärkeämpi tehtävä on. Käyttäjä voi muokata tehtävän prioriteettia vaihtamalla sen vieressä olevan tekstikentän arvoa. Järjestä tehtävät prioriteetin mukaan niin, että tärkeimmät tehtävät ovat listan yläpäässä (vihje: liitä prioriteetin sisältävään tekstikenttään [ng-blur][ng-blur] -kuuntelija ja järjestä tehtävien taulukko prioriteetin mukaan, kun kenttä menettää fokuksen käyttämällä [sort][sort] -funktiota).
* Käyttäjä voi nähdä muistilistan alalaidasta, kuinka monta tehtävää hän on tehnyt ja kuinka monta on vielä tekemättä. Käytä selkeää suomen kieltä, jolloin `1 tehtävä tehty` on oikein ja `1 tehtävää tehty` on väärin (vihje: [ng-pluralize][ng-pluralize]). Voit toteuttaa toiminnon käyttämällä [$watch][watch] -funktiota niin, että seuraat tehtävät sisältävää taulukkoa ja päivittää esimerkiksi muuttujien `todosDone` ja `todosRemaining` arvot aina, kun taulukossa tapahtuu muutoksia. Muista lisätä `$watch` -funktiokutsun viimeiseksi parametriksi `true`, niin Angular tarkastaa onko taulukossa tapahtunut muutoksia sen sisällön, eikä pelkän viitteen perusteella.

[ng-class]: https://docs.angularjs.org/api/ng/directive/ngClass
[confirm]: https://developer.mozilla.org/en-US/docs/Web/API/Window/confirm
[ng-blur]: https://docs.angularjs.org/api/ng/directive/ngBlur
[sort]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort
[ng-pluralize]: https://docs.angularjs.org/api/ng/directive/ngPluralize
[watch]: https://docs.angularjs.org/api/ng/type/$rootScope.Scope#$watch

Palauta tehtävästä tiedostot `template.html` ja `controller.js`, joiden rungot löytyvät `todo`-hakemistosta. Varmista, että tehtäväpohjassa olevat testit menevät läpi ennen palautusta.

### Lisätietoja

Tehtävä on poimittu lähes sellaisenaan [kurssimateriaalista][weso],
[Tehtävä 33][tehtäva-33]. Tehtävässä on sovellettava suhteellisen paljon materiaalin [luvun 12][luku-12] asioista.

[weso]: {{site.baseurl}}/weso/
[tehtäva-33]: {{site.baseurl}}/weso/#vk-4-t33
[luku-12]: {{site.baseurl}}/weso/#12-Sovelluksen-rakenteen-hallinta:-AngularJS

#### Alaviitteet


