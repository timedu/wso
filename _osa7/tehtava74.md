---
layout: sivu
title: Tehtävä 7.4
exercise_upload_id: 294731
exercise_template_name: W7E04.CalcLogWS
---

## Laskentaloki - WebSocket

Tehtäväpohjassa on AngularJS -pohjainen laskin -sovellus. Täydennä sitä niin, että sovellus pitää kirjaa sillä suoritetuista laskutoimituksista (vrt. esim. [Tehtävä 7.2](../tehtava72)). Luettelo laskutoimituksista on esillä  edellisten tehtävien tapaan erillisessä *iframe* -elementin sisältönä olevassa dokumentissa (loki). Tieto suoritetusta laskutoimituksesta välitetään *lokille* tässä kuitenkin *WebSocket* -pohjaisen kaiutuspalvelun kautta.

Projektin tiedostorakenne vastaa [edellisten tehtävien](../tehtava72) tiedostorakennetta. 

Ratkaisussa *lokipalvelu* (`log_service.js`) muodostaa *WebSocket* -olion, joka ottaa yhteyden verkossa toimivaan kaiutuspalveluun[^1]. *Lokipalvelun* `log`-metodi lähettää parametrina saamansa datan (merkkijonomuotoisen laskutoimituksen) *WebSocket* -olion avulla kaiutuspalveluun.

[^1]: Kaiutuspalvelun osoite injektoidaan palvelulle vakiossa `WEBSOCKET_URI`, jolle on asetettu arvo tiedostossa `app.js`. Palvelu toimii niin, että se lähettää välittömästi takaisin sinne lähetetyn datan.

Loki-dokumentiin (`logframe.html`) liittyvä koodi (`logframe.js`) kuuntelee kaiutuspalvelun lähettämiä viestejä *WebSocket* -olion avulla. Koodi reagoi viestiin esitämällä sen sisällön sivulla hyödyntäen pohjassa olevaa funktiota `createLogElement`.

Viite käytettävään *WebSocket* -olioon välitetään loki-dokumentille "päädokumentin" muuttujassa `CalcApp.websocket`, joka näkyy loki-dokumentissa `parent`-olion ominaisuutena.

### Palautettava aineisto

**Palauta** tehtävästä `todo` -hakemiston tiedostot `log_service.js` ja `logframe.js`. 

### Lisätietoja ja vihjeitä

Osoitteessa <http://www.websocket.org/echo.html> on kaiutuspalvelua hyödyntävä demo. Sivulla on esillä myös demoon liittyvä ohjelmakoodi. [Mozillan kehittäjäsivustolla][mdn] asiaa käsitellään kohdassa [WebSockets][ws]. 

[mdn]: https://developer.mozilla.org/
[ws]: https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API


#### Alaviitteet

