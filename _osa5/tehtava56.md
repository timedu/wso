---
layout: sivu
title: Tehtävä 5.6
exercise_upload_id: 291901
exercise_template_name: W5E06.PuhFirebase
---

## Puhelinmuistio: Firebase 

~~~
// sivu on työn alla
~~~

Laadi puhelinmuistiosovellus, joka on ulkoiselta käyttäytymiseltään pääosin [tehtävän 5.4](../tehtava54) ratkaisun kaltainen. Laadittava sovellus kuitenkin tukeutuu tietojen talletuksen osalta [Firebase-tietokantaan][firebase-db]. Sovelluksen käyttö myös edellyttää käyttäjältään tunnistautumista, mikä toteteutetaan [Firebasen autentikointipalvelulla][firebase-auth].

[firebase-db]: https://firebase.google.com/docs/database/
[firebase-auth]: https://firebase.google.com/docs/auth/

### Käyttöliittymä

Sovelluksen ulkoasu ja reititys on pääosin kuten [tehtävässä 5.4](../tehtava54). Tunnistautumisvaatimus kuitenkin tuo näihin pieniä muutoksia. 

![ui-1](../img/w5e06-1.png "ui-1")

<small>Kuva 1. Hae numeroita -sivu (ei kirjauduttu).</small>

Jos käyttäjä ei ole tunnistautunut, *Hae numeroita* -sivulla on *Login* -painike. Tällöin *Nimi* -kenttään ei voi kirjoittaa ja *uusi numero* -linkki ei ole näkyvissä (Kuva 1).

Käyttäjä tunnistautuu klikkaamalla *Login* -painiketta. Jos tunnistautuminen onnistuu, näkymään ilmestyy *Login* -painikkeen tilalle *Logout* -painike, *Nimi* -kenttä aktivoituu ja *uusi numero* -linkki tulee näkyviin (Kuva 2).

![ui-2](../img/w5e06-2.png "ui-2")

<small>Kuva 2. Hae numeroita -sivu (kirjauduttu).</small>

Kun käyttäjä on kirjautunut, sovelluksen näkymiin voidaan siirtyä painikkeiden ja linkkien ohella myös suorilla osoitteilla (vrt. [Tehtävä 5.4](../tehtava54)). Jos kirjautumista ei ole tehty, on suoralla osoitteella pääsy ainoastaan sovelluksen juuriosoitteeseen (`/W5E06/#/` tai `/W5E06/`), joka tuo esiin *Hae numeroita* -näkymän. Yritys muuhun osoitteeseen (esim. `/W5E06/#/bart`, `/W5E06/#/bart/remove/111` tai `/W5E06/#/jotakin/muuta`) palauttaa käsittelyn juuriosoitteeseen.


### Tietokanta

Tietokanna Firebase-konsolissa (esim.):

~~~
puhelinmuistio-5e3d9
  |
  +-bart
  |   |
  |   +-_111: "111"
  |   |
  |   +-_222: "222"
  |   |     
  |   +-_333: "333"  
  |
  +-ned
      |
      +-_444: "444" 
      |
      +-_555: "555"
~~~

Vastaava JavaScript-objekti sovelluksessa:

{% highlight json %}

{ "bart": {"_111": "111", "_222": "222", "_333": "333" },
  "ned":  {"_444": "444", "_555": "555" } }

{% endhighlight %}


### Sovelluksen rakenne

Pääsivun (`index.html`) `body`-elementin merkkaus:


{% highlight html %}

    <body ng-app="PuhApp">

        <h1>Puhelinmuistio</h1>

        <div ng-view></div>
        
        <script src="js/app.js"></script>
        
        <script src="js/firebase.auth.service.js"></script>
        <script src="js/button.directive.js"></script>             
        <script src="js/add.remove.controller.js"></script>
        
        <script src="todo/route.config.js"></script>
        <script src="todo/firebase.db.service.js"></script>
        <script src="todo/search.controller.js"></script>

    </body>

{% endhighlight %}


**Palauta** tehtävän ratkaisusta tiedostot `route.config.js`, `firebase.db.service.js`, `search.controller.js` sekä `search.view.html`, joiden rungot löytyvät tehtäväkohjan `todo`-kansiosta. Varmista ennen palautusta, että sovellus toimii odotetusti. Jos pohjakoodi sisältää testejä, varmista myös niiden läpimeno ilman virheilmoituksia.


### Lisätietoja
