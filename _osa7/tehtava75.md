---
layout: sivu
title: Tehtävä 7.5
exercise_upload_id: 294732
exercise_template_name: W7E05.CalcGeolocation
---

## Laskin - Geolocation

~~~
// sivu työn alla
~~~

Tehtäväpohjassa on AngularJS -pohjainen laskin -sovellus (vrt. esim. [Tehtävä 7.1](../tehtava71)). Muokkaa sovellusta siten, että se esittää sijaintitiedot paikasta, jossa laskenta suoritetaan. Sivulla on myös linkki, jonka klikkaus tuo esiin laskentapaikan Google -kartalla.

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

Sijaintitietojen käsittely on itsenäinen osa sovellusta. *GeoController* (`geo_controller.js`) toimittaa sijaintitiedot käyttöliittymään hyödyntäen palvelua *GeoService* (`geo_service.js`).

### Palautettava aineisto

**Palauta** tehtävästä `todo` -hakemiston tiedostot `geo_service.js` ja `geo_controller.js`. 

### Lisätietoja

<http://diveintohtml5.info/geolocation.html>

<https://developer.mozilla.org/en-US/docs/Web/API/Geolocation>

<https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/Using_geolocation>

<http://html5doctor.com/finding-your-position-with-geolocation/>

