---
layout: sivu
permalink: /osa7/index.html 
title: 7. Sovellusrajapintoja
---

Mozillan kehittäjäsivusto ([MDN][MDN]) esittää termistä *HTML5* seuraavaa: "HTML5 is the latest evolution of the standard that defines HTML. The term represents two different concepts:

[MDN]: https://developer.mozilla.org/fi/

* It is a new version of the language HTML, with new elements, attributes, and behaviors,
* and a larger set of technologies that allows more diverse and powerful Web sites and applications. This set is sometimes called HTML5 & friends and often shortened to just HTML5."

<small>*[HTML5][HTML5] by Mozilla Contributors is licensed under [CC-BY-SA 2.5][CC].*</small>

[HTML5]: https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5
[CC]: http://creativecommons.org/licenses/by-sa/2.5/

Kurssin tämä osa esittelee jälkimmäisen käsitteen alaan liittyviä teknologioita: [web-workerit][worker], [selaimen muisti][storage], [dokumenttien välinen kommunikointi][xdm], [web-soketit][ws] ja [paikkatieto][geo].

[worker]: https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers
[storage]: https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API
[xdm]: https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage
[ws]: https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API
[geo]: https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/Using_geolocation

MDN jakaa HTML5-teknologiat kahdeksaan ryhmään, joista kukin sisältää useita jäseninä, joten tämän osan tehtävissä on esillä vain hyvin pieni osa tarjolla olevasta teknologiakokonaisuudesa. Aiheesta on tarjolla runsaasti teknistä kirjallisuutta. Esim. yliopiston verkkokirjastosta löytyvä [Pro HTML5 Programming][lubbers-et-al-2011] käsittelee kaikkia tämän osan esittelemiä teknologioita.

[lubbers-et-al-2011]: http://link.springer.com.libproxy.tut.fi/book/10.1007%2F978-1-4302-3865-2

#### Tehtävät

Osa tehtävien pohjana on sama [AngularJS][AngularJS] -perustalle rakennettu laskinsovellus, jonka käyttöliittymää on ehostettu [jQuery UI][jQueryUI] -kirjastolla.

[AngularJS]: https://angularjs.org
[jQueryUI]: https://jqueryui.com

[Tehtävä 7.1 Laskin - Worker](tehtava71)   
[Tehtävä 7.2 Laskentaloki - Storage](tehtava72)  
[Tehtävä 7.3 Laskentaloki - XDM](tehtava73)  
[Tehtävä 7.4 Laskentaloki - WebSocket](tehtava74)  
[Tehtävä 7.5 Laskin - Geolocation](tehtava75)   

Tehtävässä [7.1](tehtava71) laskimen suorittama laskenta erotetaan erilliseen JavaScript -moduuliin, *Web Workeriin*, jonka kanssa muu sovellus kommunikoi viestien avulla. Tehtävistä kolme seuraavaa toteuttaa laskentalokin eri teknologioilla. Tehtävässä [7.2](tehtava72) laskimen suorittama laskutoimitus välitetään erilliselle lokidokumentille selaimen  muistin välityksellä. Tehtävässä [7.3](tehtava73) tieto välittyy suoraan dokumenttien välisen viestinnän keinoin. Tehtävässä [7.4](tehtava74) laskutoimitus kiertää verkon kautta matkalla laskimesta lokidokumentille. Osan viimeisessä tehtävässä [7.5](tehtava75) selaimen tarjoamasta rajapinnasta haetaan sijaintitiedot laskinsovelluksen jäädessä rekvisiitan rooliin. Sijaintitietojen avulla muodostetaan linkki, jonka klikkaus tuo esiin vastaavan Google -kartan.  


