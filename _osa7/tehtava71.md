---
layout: sivu
title: Tehtävä 7.1
exercise_upload_id: 294726
exercise_template_name: W7E01.CalcWorker
---

## Laskin - Worker 

Tehtäväpohjassa on toimiva AngularJS -pohjainen laskin -sovellus. Muokkaa sovellusta siten, että laskenta suoritetaan esillisessä *Web Worker* -säikeessä.

Seuraavassa on ote laskin-projektin tiedostorakenteesta:

~~~
+ [css ]
- [js  ]
   - app.js
   - controller.js
- [todo]
   - service.js
   - worker.js
- index.html    
~~~


Tiedostossa `index.html` on käyttöliittymän merkkaus. `app.js` muodostaa angular -moduulin. `controller.js` toteuttaa  käyttöliittymän painikkeisiin liittyvän käsittelyn välittäen laskentapyynnöt palvelulle `service.js`. Käyttöliittymää on tässä ehostettu [jQuery UI][jQueryUI] -kirjastolla, johon liityvää koodia on tiedoston `app.js` lopussa.

[jQueryUI]: http://jqueryui.com

Tehtävässä *palvelun* `service.js` sisältämä laskentalogiikka siirretään *workerin* perustana olevaan tiedostoon `worker.js`. Ratkaisussa *palvelu*[^1] muodostaa *workerin*, jolle se välittää saamansa laskentapyynnöt. Laskennan suoritettuaan *worker* palauttaa laskennan tuloksen *palvelulle*, joka välittää tuloksen edelleen *kontrollerille*.

[^1]: Tehtäväpohjan koodissa palvelulle injektoidaan vakio `CalcWorker`, joka sisältönä on *workerin* koodin tiedostonimi. Vakio on asetettu tehtäväpohjan tiedostossa `app.js`.

*Kontrolleriin* on tehtävä pieni muutos, kun laskenta siirretään *palvelusta* *workeriin*. Tarvittava muutos koodeineen on kommentoituna tiedostossa `controller.js`.

### Palautettava aineisto

**Palauta** tehtävästä `todo` -hakemiston tiedostot `service.js` ja `worker.js`. 

### Lisätietoja ja vihjeitä

Tehtävän ratkaisun keskeisiä ongelmia ovat, miten *Worker* muodostetaan ja, miten *Worker* kommunikoi muun sovelluksen kanssa. Näihin kysymyksiin antaa vastauksia esim.  *Eric Bidelmanin* kirjoitus [The Basics of Web Workers][Bidelman2010]. Kirjoituksesta kannattanee silmäillä erityisesti sen alkupuolella olevia kohtia *Getting Started* ja *Communicating with a Worker via Message Passing*. [Mozillan kehittäjäsivustolla][mdn] asiaa käsitellään kohdassa [Web Workers API][wwapi]. 


[Bidelman2010]: https://www.html5rocks.com/en/tutorials/workers/basics/
[mdn]: https://developer.mozilla.org/
[wwapi]: https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API



#### Alaviitteet
