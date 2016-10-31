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

*Logout* -painikkeen klikkaus palauttaa näkymän Kuvassa 1 esitetyn kaltaiseksi.

![ui-2](../img/w5e06-2.png "ui-2")

<small>Kuva 2. Hae numeroita -sivu (kirjauduttu).</small>

Kun käyttäjä on kirjautunut, sovelluksen näkymiin voidaan siirtyä painikkeiden ja linkkien ohella myös suorilla osoitteilla (vrt. [Tehtävä 5.4](../tehtava54)). Jos kirjautumista ei ole tehty, on suoralla osoitteella pääsy ainoastaan sovelluksen juuriosoitteeseen (`/W5E06/#/` tai `/W5E06/`), joka tuo esiin *Hae numeroita* -näkymän. Yritys muuhun osoitteeseen (esim. `/W5E06/#/bart`, `/W5E06/#/bart/remove/111` tai `/W5E06/#/jotakin/muuta`) palauttaa käsittelyn juuriosoitteeseen.


### Tietokanta

[Firebase-tietokanta][firebase-db] on avain-arvo -tyyppinen, missä arvo voi muodostua  avain-arvo -pareista. Tietokantaan ei voi sellaisenaan tallettaa taulukko -tyyppistä tietoa eikä tietävästi ole [kovin suositeltavaa][array-practices] käyttää nollasta lähteviä juoksevia numeerisia avaimia.

[array-practices]: https://firebase.googleblog.com/2014/04/best-practices-arrays-in-firebase.html

Edellisissä puhelinmuistio-toteutuksissa tiedot on talletettu sovelluksessa seuraavanlaiseen rakenteeseen:

{% highlight json %}

{ "bart": ["111", "222", "333"],
  "ned":  ["444", "555"] }

{% endhighlight %}

<small>Listaus 1. Tietojen rakenne edellisissä puhelinmuistio-toteutuksissa.</small>

Tässä edellä esitetyt taulukot tulisi muuntaan toisenlaiseksi rakenteeksi, joka voisi olla esim. seuraava:

{% highlight json %}

{ "bart": {"_111": "111", "_222": "222", "_333": "333" },
  "ned":  {"_444": "444", "_555": "555" } }

{% endhighlight %}

<small>Listaus 2. Taulukot muunnettu avain-arvo -rakenteeksi.</small>

Tällaisessa tilanteessa avaimet ja arvot voisivat olla samoja, mutta esim. *Listauksen 2*  esittämää periaatetta noudattaen sovellusta kehitettäessä ilmenee, onko kulloinkin käsittelyssä arvo vai sen avain. 

Firebase-konsolissa *Listauksen 2* data näkyy seuraavasti:

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

<small>Kuva 3. Avain-arvo -rakenne Firebase -konsolissa.</small>

### Autentikointi

Firebase-projektin autentikonti-asetuksiin liittyvä sivu tulee esiin konsolin valikon *Authentication* -valinnalla. *SIGN-IN METHOD* -välilehdellä voi valita projektissa käytettävät tunnistusmenetelmät. Tässä käytetään *Email/Password* -tunnistusta.  Tunnistetiedot voi määritellä *USERS* -välilehdellä. *Email* -arvon ei tarvitse tässä olla oikea sähköpostiosoite.

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


### Ratkaisun laatimisen esimerkkivaiheistus

#### *Lähtökohta*

Kun tehtäväpohjan käynnistää, selaimen ikkunaan ilmestyy sivu, joka sisältää sovelluksen pääotsikon *Puhelinmuistio*. Selaimen konsolille tulee ilmoitus *Error: No Firebase App '[DEFAULT]' has been created - call Firebase App.initializeApp()*.

#### *Vaihe I*

Askelten 1-5 toteuttamisen jälkeen sovelluksen pitäisi toimia [tehtävän 5.4](../tehtava54) kuvauksen mukaisesti.

#### 1. Sovelluksen kytkentä Firebase -projektiin.

Kirjaa Firebase -projektisi tunnisteet ao. kohtaan tiedostossa `app.js`.
 
Tämän jälkeen em. virheilmoitusta ei enää pitäsi tulla selaimen konsolille. Tosin konsolille ilmestynee teksti *User signed out.*, jonka tuottaa pohjassa valmiina oleva autentikaatioon liittyvä koodi.

#### 2. Näkymien reititys

Kopio [tehtävän 5.4](../tehtava54) ratkaisusta tiedoston `config.js` sisältö tiedostoon `route.config.js` ja tee kopioimaasi koodiin seuraavat *Hae numeroita* -näkymää koskevat muutokset:

{% highlight javascript %}

// ...

    // controller: 'PuhController',
    // templateUrl: 'view/search.html'
    controller:  'SearchController',
    templateUrl: 'todo/search.view.html'

// ...

{% endhighlight %}

Sovelluksen käynnistyessä *Hae numeroita* -näkymän pitäisi tulla nyt esiin. *Lisää numero* -näkymään pääsee kirjaamalla jotakin sivulla olevaan *Nimi* -kenttään ja klikkaamalla sitten *uusi numero* -linkkiä. Näkymiin pääsee myös suorilla osoitteilla, esim.  `/W5E06/#/` , `/W5E06/#/joku`, `/W5E06/#/joku/add` ja `W5E06/#/joku/remove/123`. *Lisää numero*- ja *Poistetaanko numero?* -näkymät eivät sisällä painikkeita.

#### 3. Ylläpito -näkymien painikkeet

Kopio [tehtävän 5.4](../tehtava54) ratkaisusta tiedoston `directive.js` sisältö tiedostoon `button.directive.js`.

 *Lisää numero*- näkymä sisältää nyt *Lisää*- ja *Peruuta* -painikkeet ja *Poistetaanko numero?* -näkymä sisältää *Poista*- ja *Peruuta* -painikkeet. Näkymissä olevien painikkeiden klikkaukset eivät vaihda esillä olevaa näkymää.

#### 4. Ylläpito -näkymien painikkeiden aktivointi

Kopio [tehtävän 5.4](../tehtava54) ratkaisun tiedostosta `controller.js` kontrollerien  sisältö tiedostoihin `add.remove.controller.js` (`AddController` ja `RemoveController`) ja `search.controller.js` (`SearchController`[^puh-controller]).

[^puh-controller]: Tehtävässä 5.4 vastinkontrolleri on nimeltään `PuhController`.

 *Lisää numero*- ja *Poistetaanko numero?* -näkymissä olevien painikkeiden klikkauksen pitäisi nyt tuoda esiin *Hae numeroita*- näkymän.

#### 5. Datan talletus sovellukseen

Kopio [tehtävän 5.4](../tehtava54) ratkaisusta tiedoston `service.js` metodien sisältö tiedoston `firebase.db.service.js` vastimetodeihin.

Sovelluksen pitäisi nyt toimia [tehtävän 5.4](../tehtava54) kuvauksen mukaisesti.

#### *Vaihe II*

#### 6. Tunnistautuminen


ks. [Autentikointi](#autentikointi)

...

#### *Vaihe III*


#### 10. Palauta tehtävän ratkaisu

**Palauta** tehtävän ratkaisusta tiedostot `route.config.js`, `firebase.db.service.js`, `search.controller.js` sekä `search.view.html`, joiden rungot löytyvät tehtäväkohjan `todo`-kansiosta. Varmista ennen palautusta, että sovellus toimii odotetusti. Jos pohjakoodi sisältää testejä, varmista myös niiden läpimeno ilman virheilmoituksia.


### Lisätietoja

#### Alaviitteet



