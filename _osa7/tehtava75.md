---
layout: sivu
title: Tehtävä 7.5
exercise_upload_id: 294732
exercise_template_name: W7E05.CalcGeolocation
---

## Laskin - Geolocation

Tehtäväpohjassa on AngularJS -pohjainen laskinsovellus (vrt. esim. [Tehtävä 7.1](../tehtava71)). Muokkaa sovellusta siten, että se esittää sijaintitiedot paikasta, jossa laskenta suoritetaan. Sivulla on myös linkki, jonka klikkaus tuo esiin laskentapaikan Google -kartalla.

Seuraavassa on ote projektin tiedostorakenteesta:

~~~
+ [css ]
- [js  ]
   - app.js
   - calc_controller.js
   - calc_service.js
- [todo]
   - geo_controller.js
   - geo_service.js
- index.html    
~~~

Sijaintitietojen käsittely on itsenäinen osa sovellusta[^1]. *GeoController* (`geo_controller.js`) toimittaa sijaintitiedot käyttöliittymään hyödyntäen palvelua *GeoService* (`geo_service.js`). Toteuta tehtävän ratkaisu seuraavassa kuvattavalla tavalla:

[^1]: Laskin on tehtävässä lähinnä rekvisiitan asemassa.


{% highlight javascript %}

CalcApp.service('GeoService', function ($window, GEO_TIMEOUT) {
    this.getPosition = function (done) {
        // ...
    };
});

{% endhighlight %}

`GeoService`-palvelun `getPosition`-metodi palauttaa sijaintitiedot kutsumalla parametrina saamaansa `done`-funktiota. Palveluun injektoidaan `$window` -olio, jonka kautta päästään käsiksi *geolocation*-rajapintaan, sekä vakio `GEO_TIMEOUT`[^2], joka määrittelee, kuinka kauan sijaintitietoja enimmillään odotetaan. 

[^2]: Vakiolle asetetaan arvo tiedostossa `app.js`.

{% highlight javascript %}

CalcApp.controller('GeoController', function ($scope, GeoService) {    
    GeoService.getPosition(function (reply) {        
        // ...
    });
});

{% endhighlight %}

`GeoService`-palvelu injektoidaan kontrolleriin, joka kutsuu palvelun metodia `getPosition`. Metodille parametrina annettu funktio[^3] sisältää koodin, jolla sijaintitiedot ilmestyvät käyttöliittymään. Jos sijaintitietoja ei saada, tulostuu selaimen konsolille tilanteeseen liittyvä virhekoodi ja -ilmoitus.

[^3]: Funktiossa koodi tulee suorittaa `$scope`-olion `$apply`-metodilla.  

Funktion saama `reply`-parametri on olio, jonka rakenne on odotetussa tilanteessa seuraavanlainen:

{% highlight javascript %}
{
  latitude:   // leveysasteet kolmen desimaalin tarkkuudella
  longitude:  // pituusasteet kolmen desimaalin tarkkuudella
  accuracy:   // arvio sijainnin tarkuudesta metreinä
}
{% endhighlight %}

Jos sijaintia ei pystytä määrittämään `reply`-olio on seuraavanlainen:

{% highlight javascript %}
{
  errorCode:    // virhetilanteen koodi
  errorMessage: // virhetilanteeseen liittyvä sanoma
}
{% endhighlight %}


### Palautettava aineisto

**Palauta** tehtävästä `todo` -hakemiston tiedostot `geo_service.js` ja `geo_controller.js`. 

### Lisätietoja

*Geolocation* -rajapintaa käsitellään esim. *Pro HTML5 Programming* -kirjan luvussa [Using the Geolocation API][lubbers-chp5] ja *Dive Into HTML5* -kirjan luvussa [You are here
(and so is everybody else)][pilgrim-chp6]. *MDN* -aineistossa asia on esillä sivuilla [Geolocation][mdn-geo] ja [Using geolocation][mdn-using-geo].

[lubbers-chp5]: http://rd.springer.com/chapter/10.1007/978-1-4302-3865-2_5
[pilgrim-chp6]: http://diveintohtml5.info/geolocation.html
[mdn-geo]: https://developer.mozilla.org/en-US/docs/Web/API/Geolocation
[mdn-using-geo]: https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/Using_geolocation

#### Alaviitteet

