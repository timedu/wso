---
layout: sivu
title: Tehtävä 4.7
exercise_upload_id: 289243
exercise_template_name: W4E07.Muistilista
---

## Muistilista

~~~
// sivu edellyttää päivitystä
~~~

> Seuraavaksi pääset toteuttamaan hieman suurempaa sovellusta, muistilistaa. Muistilistan avulla käyttäjä voi lisätä itselleen tehtäviä, jotka hän itse priorisoi. Lisätyn tehtävän voi merkata tehdyiksi, poistaa ja sen prioriteettia voi muuttaa. Tehtävät tulee järjestää muistilistaan niiden prioriteetin mukaan. Lopullinen muistilista muistuttaa tätä (pelkkä käyttöliittymä, toiminallisuus puuttuu):
>
> Toteuta valmiiseen käyttöliittymään seuraavat toiminnot:
>
* Käyttäjä voi lisätä tehtävän listaan "Uusi tehtävä"-tekstikentän nimen perusteella. Älä anna käyttäjän lisätä tehtävää tyhjällä nimellä.
* Käyttäjä voi merkata merkata tehtävän tehdyksi klikkaamalla checkboxia. Tehdyn tehtävän nimi vedetään yli (voit lisätä tehtävän nimeen tällöin luokan todo-done (vinkki: ng-class).
* Käyttäjä voi merkata kaikki tehtävät tehdyksi klikkaamalla "Merkkaa kaikki tehdyiksi"-painiketta.
* Käyttäjä voi poistaa tehtävän listasta painamalla oikeasta laidasta "Poista"-painiketta.
* Käyttäjä voi poistaa kaikki tehtävät klikkaamalla "Poista kaikki"-painiketta. Varmista painikkeen klikkaamisen jälkeen, että käyttäjä haluaa varmasti poistaa kaikki tehtävät (vinkki: confirm).
* Tehtävään liittyy prioriteetti. Jokaiselle tehtävälle lisätään sen lisäämisen yhteydessä prioriteetti 1. Mitä pienempi prioriteetti on, sitä tärkeämpi tehtävä on. Käyttäjä voi muokata tehtävän prioriteettia vaihtamalla sen vieressä olevan tekstikentän arvoa. Järjestä tehtävät prioriteetin mukaan niin, että tärkeimmät tehtävät ovat listan yläpäässä (vinkki: liitä prioriteetin sisältävään tekstikenttään ng-blur-kuuntelija ja järjestä tehtävien taulukko prioriteetin mukaan, kun kenttä menettää fokuksen käyttämällä sort-funktiota).
* Käyttäjä voi nähdä muistilistan alalaidasta, kuinka monta tehtävää hän on tehnyt ja kuinka monta on vielä tekemättä. Käytä selkeää suomen kieltä, jolloin "1 tehtävä tehty" on oikein ja "1 tehtävää tehty" on väärin (vinkki: ng-pluralize). Voit toteuttaa toiminnon käyttämällä $watch-funktiota niin, että seuraat tehtävät sisältävää taulukkoa ja päivittää esimerkiksi muuttujien todosDone ja todosRemaining arvot aina, kun taulukossa tapahtuu muutoksia. Muista lisätä $watch-funktiokutsun viimeiseksi parametriksi true, niin Angular tarkastaa onko taulukossa tapahtunut muutoksia sen sisällön, eikä pelkän viitteen perusteella.
> 
> TodoController-kontrollerin valmis pohja löytyy tiedostosta app/controllers/todo_controller.js ja näkymä tiedostosta index.html. 

Palauta tehtävästä tiedostot `template.html` ja `controller.js`, joiden rungot löytyvät `todo`-hakemistosta. Varmista, että tehtäväpohjassa olevat testit menevät läpi ennen palautusta.


### Lisätietoja

Tehtävä on poimittu lähes sellaisenaan [kurssimateriaalista]({{site.baseurl}}/weso/),
[Tehtävä 33]({{site.baseurl}}/weso/#vk-4-t33), jonka edellä materiaalissa käsitellään tehtävän ratkaisua tukevia asioita.

