---
layout: sivu
title: Web-selainohjelmointi
---

Web-selainohjelmointi on nimensä mukaisesti web-sovellusten selainpäähän keskittyvä ohjelmointikurssi. Opintojakson 
[toteutusperiaatteena](toteutus/) 
on **ongelmakeskeinen itseopiskelu ohjatusti** (OIO). Kurssi on jaettu seitsemään osaan, joista kunkin ytimen muodostaa tiettyyn teemaan keskittyvä tehtäväsarja. 

*Web-sovellus*

Web-sovellusta voidaan kuvata aihepiirin johdantokurssilta tutulta kaaviolla. [Web-sovellusten][web_sovellus] käyttöliittymänä toimii [selain][selain], joka tekee [HTTP][http] – muotoisia pyyntöjä [web-palvelimelle][palvelin] joko käyttäjän tai selaimen tulkitseman koodin ohjaamana. Tyypillinen vaste pyyntöön on HTML – dokumentti, joka voi sisältää myös CSS – määreitä ja JavaScript – koodia, joko suoraan tai viitteinä ulkopuolisiin tiedostoihin.

![Web-sovellus]({{site.baseurl}}/img/web_kaavio.png "Web-sovellus")

[HTML][html] määrittelee dokumentin sisällön ja rakenteen [CSS][css] :n viimeistellessä dokumentin layoutin ja ulkoasun. [JavaScript][js] on selaimen tulkitsemaan ohjelmakoodia, joka voi muokata selaimen esittämää dokumenttia erityisen [DOM][dom] – rajapinnan kautta. JavaScript osaa myös tehdä palvelimelle, tyypillisesti asynkronisia, HTTP – pyyntöjä, mihin viitataan usein lyhenteellä [Ajax][ajax].

Selain voi pyynnössään viitata staattisen HTML – dokumentin sijaan myös palvelimella sijaitsevaan, esim. [PHP][php]-kielellä laadittuun, ohjelmaan, joka suoritetaan pyynnön seurauksena. Sovellukseen voi liittyä myös tietokanta – esim. pyynnön vaste muodostetaan tietokannassa olevan tiedon perusteella. Usein käytössä on relaatiotietokanta, jota käsitellään [SQL][sql]:n avulla.

[web_sovellus]: https://en.wikipedia.org/wiki/Web_application "Web-sovellus"
[selain]: https://en.wikipedia.org/wiki/Web_browser "Web-selain"
[http]: https://fi.wikipedia.org/wiki/HTTP  "Hypertext Transfer Protocol"
[palvelin]: https://fi.wikipedia.org/wiki/WWW-palvelin "Web-palvelin"
[html]: https://fi.wikipedia.org/wiki/HTML "Hypertext Markup Language"
[css]: https://fi.wikipedia.org/wiki/CSS "Cascading Style Sheets"
[js]: https://fi.wikipedia.org/wiki/JavaScript "JavaScript"
[dom]: https://fi.wikipedia.org/wiki/Document_Object_Model "Document Object Model"
[ajax]: https://fi.wikipedia.org/wiki/Ajax_%28ohjelmointi%29 "Asynchronous JavaScript And XML"
[php]: https://fi.wikipedia.org/wiki/PHP "PHP: Hypertext Preprocessor"
[sql]: https://fi.wikipedia.org/wiki/SQL "Structured Query Language"

*Kurssin sisältö*

Tämä kurssi keskittyy selainpään ohjelmointiongelmiin. Tavoitteena on, että kurssin suoritettuaan opiskelija kykenee jäsentämään web-selaimessa toimivan sovelluksen **hallittavaksi olioista ja moduuleista** (osat 1-2) muodostuvaksi kokonaisuudeksi, osaa soveltaa selainohjelmoinnissa yleisesti käytettyjä **ohjelmakirjastoja** (osat 3-6) sekä tuntee web-selainten tarjoamia **ohjelmointirajapintoja** (osa 7). Osallistujalta odotetaan ennalta ohjelmoinnin ja selainpään tekniikoiden (HTML, CSS, JavaScript) perusteiden tuntemusta. Kurssi on jäsennetty seisemään osaan seuraavasti:

1. [Oliot ja moduulit](osa1/)
2. [Arkkitehtuurimallit (MVC)](osa2/)
3. [Kirjastoista: jQuery, Mustache](osa3/)
4. [Kirjastoista: AngularJS (I)](osa4/)
5. [Kirjastoista: AngularJS (II)](osa5/)
6. [Käyttöliittymistä: Bootstrap, Less](osa6/)
7. [Sovellusrajapinnat](osa7/)

Opintojakson osat 1-6 perustuvat [Helsingin yliopiston Tietojenkäsitelytieteen laitoksella](https://www.cs.helsinki.fi/) järjestettävän [samannimisen kurssin](https://www.cs.helsinki.fi/courses/582354/2015/s/k/1) [materiaalin](http://web-selainohjelmointi.github.io) jälkiosaan (lähinnä luvut 8-20).

~~~
// sivusto täydentyy ja päivittyy kurssitoteutuksen edetessä
~~~
