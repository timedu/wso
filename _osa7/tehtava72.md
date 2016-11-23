---
layout: sivu
title: Tehtävä 7.2
exercise_upload_id: 294729
exercise_template_name: W7E02.CalcLogStorage
---

## Laskentaloki - Storage 

Tehtäväpohjassa on AngularJS -pohjainen laskin -sovellus (vrt. [Tehtävä 7.1](../tehtava71)). Täydennä sitä niin, että sovellus pitää kirjaa sillä suoritetuista laskutoimituksista. Kirjanpito tapahtuu selaimen paikallisen muistin (*Session Storage*) avulla. Luettelo laskutoimituksista on esillä  erillisessä *iframe* -elementin sisältönä olevassa dokumentissa.

Seuraavassa on ote projektin tiedostorakenteesta:

~~~
+ [css ]
- [js  ]
   - app.js
   - calc_service.js
   - controller.js
- [todo]
   - log_service.js
   - logframe.js
- index.html    
- logframe.html
~~~

Sovelluksessa *kontrolleriin* on injektoitu *laskentapalvelun* (`calc_service.js`) ohella *lokipalvelu* (`log_service.js`), jolle *kontrolleri* välittää *laskentapalvelulta* saamansa merkkijono-muotoisen laskutoimituksen.   

Laskimen käyttöliittymän merkkauksen lisäksi tiedostossa `index.html` on [iframe][iframe]-elementti, jonka sisältönä on lokin esittävä dokumentti `logframe.html`. Dokumenttiin liittyy tiedoston `logframe.js` sisältämä ohjelmakoodi.

Toteuta *lokipalvelun* `log`-metodi niin, että se tallettaa sille välitetyn laskutoimituksen selaimen istuntokohtaiseen muistiin[^1] (*Session Storage*).

[^1]: Muistipaikan avain injektoidaan palveluun vakiossa `STORAGE_KEY`, jolle asetetaan arvo tiedostossa `app.js`. 

Täydennä tiedoston `logframe.js` koodia niin, että se lukee selaimen istuntokohtaisesta muistista sinne talletetun laskutoimituksen ja esittää sen sivulla (`logframe.html`) hyödyntäen pohjassa olevaa funktiota `createLogElement` aina, kun ao. muistipaikan sisältö muuttuu.

[iframe]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe

### Palautettava aineisto

**Palauta** tehtävästä `todo` -hakemiston tiedostot `log_service.js` ja `logframe.js`. 

### Lisätietoja ja vihjeitä

Selaimen muistia esitellään esim. *Mark Pilgrimin* verkkokirjassa [Dive into HTML5][pilgrim]. Kirjan kohdassa [Using HTML5 Storage][pilgrim-storage] on esimerkkejä `localStorage` -oliosta mikä ei eroa käyttöperiaatteeltaan tässä sovellettavasta `sessionStorage` -oliosta[^2]. [Mozillan kehittäjäsivustolla][mdn] asiaa käsitellään kohdassa [Web Storage API][wsapi]. 

[pilgrim]: http://diveintohtml5.info/
[pilgrim-storage]: http://diveintohtml5.info/storage.html#methods
[mdn]: https://developer.mozilla.org/
[wsapi]: https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API

[^2]: *Local Storagen* sisältö säilyy vaikka selain suljetaan mutta *Session Storagen* ei.


#### Alaviitteet

