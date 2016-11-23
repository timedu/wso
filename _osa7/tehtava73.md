---
layout: sivu
title: Tehtävä 7.3
exercise_upload_id: 294730
exercise_template_name: W7E03.CalcLogXDM
---

## Laskentaloki - XDM 

Tehtäväpohjassa on AngularJS -pohjainen laskin -sovellus. Täydennä sitä niin, että sovellus pitää kirjaa sillä suoritetuista laskutoimituksista (vrt. [Tehtävä 7.2](../tehtava72)). Luettelo laskutoimituksista on esillä  edellisen tehtävän tapaan erillisessä *iframe* -elementin sisältönä olevassa dokumentissa (loki). Tieto suoritetusta laskutoimituksesta välitetään *lokille* suoraan dokumentien välisen viestinnän (*cross-document messaging, XDM*) avulla.

Projektin tiedostorakenne vastaa [edellisen tehtävän](../tehtava72) tiedostorakennetta. 

Ratkaisussa *lokipalvelu* (`log_service.js`) lähettää `iframe` -elementissä olevalle loki-dokumentille[^1] (`logframe.html`) laskutomituksen sisältävän viestin[^2].  Dokumentiin liittyvä ohjelmakoodi (`logframe.js`) reagoi viestiin esitämällä sen sisällön sivulla hyödyntäen pohjassa olevaa funktiota `createLogElement`.

[^1]: Dokumentin sisätämä ikkuna-olio injektoidaan palvelulle vakiossa `LOG_WINDON`, jolle asetetaan arvo tiedostossa `app.js`.
[^2]: Tässä viestin lähetykseen liittyvän metodikutsun toiseksi parametriksi voi antaa arvon `'*'`.

### Palautettava aineisto

**Palauta** tehtävästä `todo` -hakemiston tiedostot `log_service.js` ja `logframe.js`. 

### Lisätietoja ja vihjeitä

[Mozillan kehittäjäsivustolla][mdn] oleva [postMessage][postMessage] -metodin kuvaus sisältää asiaan liittyviä esimerkkejä. 

[mdn]: https://developer.mozilla.org/
[postMessage]: https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage

#### Alaviitteet
