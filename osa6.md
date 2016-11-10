---
layout: sivu
permalink: /osa6/index.html 
title: 6. Käyttöliittymistä
---

Tässä osassa on esillä kolme selainsovellusten käyttöliittymiin liittyvää teemaa. Seuraavat lähes suorat lainaukset on poimittu [kurssilukemistostosta][weso]. 

[weso]: {{site.baseurl}}/weso/

> [Bootstrap][bootstrap] on Mark Otton and Jacob Thorntonin Twitterillä kehittämä front-end sovelluskehys, joka on yleistynyt viime vuosien aikana. Bootstrap tarjoaa laajan skaalan HTML- ja CSS-pohjaisia suunnittelupohjia selkeiden käyttöliittymien toteuttamiseen. 
> 
> Ns. "Responsive Design" -periaatteen perusteella jokaisen käyttöliittymän tulisi toimia laitteesta ja näytön koosta riippumatta. Verkkosovelluksia käytetään yhä useammin pieninäyttöisillä sovelluksilla, jolloin on välttämätöntä, että sovelluksen käyttöliittymä osaa mukautua pienempään näyttöön. Responsiivisuus voidaan toteuttaa CSS-kielessä [mediakyselyillä][media_queries], joiden avulla voidaan määrittää erilaisia tyylejä erilaisille ja eri kokoisille laitteille. Myös [Bootstarap][bootstrap]  -kirjastossa responsiivisuus on vahvasti esillä.
> 
> CSS-kielellä on keskeinen asema muodostettaessa selaissovellusten käyttöliittymiä. Kielessä on kuitenkin merkittäviä puutteita, jotka ilmenevät etenkin tyylien määrän kasvaessa. Ongelmaan on kehitetty viime vuosina monia laajennuksia, jotka lisäävät CSS-kieleen lukuisia toimintoja, kuten muuttujia, funktiota ja sisäkkäisiä valitsimia. Kielen laajennus käännetään omalla kääntäjällään CSS-kielelle. Suosituinpia CSS-kielen laajennuksia ovat [Less][less] ja [Sass][sass], joista tässä osassa käsitellään ensin mainittua.

[bootstrap]: http://getbootstrap.com/
[media_queries]: https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries
[less]: http://lesscss.org
[sass]: http://sass-lang.com

Käyttöliittymäteemoja käsitellään [kurssilukemiston][weso] luvuissa

[18. Twitter Bootstrap][luku-18]   
[19. Responsiivinen web-suunnittelu][luku-19]   
[20. Selkeyttä ja rakennetta tyylitiedostoihin: Less][luku-20]  

[luku-18]: {{site.baseurl}}/weso/#18-Twitter-Bootstrap
[luku-19]: {{site.baseurl}}/weso/#19-Responsiivinen-web-suunnittelu
[luku-20]: {{site.baseurl}}/weso/#20-Selkeyttä-ja-rakennetta-tyylitiedostoihin:-Less

#### Tehtävät

Kurssin tämä osa sisältää neljä tehtävää, joista ensimmäinen (5.6) kuuluu vielä aiheensa puolesta [edelliseen osaan](../osa5). Muut kolme tehtävää keskittyvät kukin yhteen tämä osan kolmesta teemasta.

[Tehtävä 5.6 Puhelinmuistio: Firebase](../osa5/tehtava56) (ks. [osa 5](../osa5))   
[Tehtävä 6.1 Bootstrap-elokuvat](tehtava61)   
[Tehtävä 6.2 Responsiivisuus](tehtava62)   
[Tehtävä 6.3 Less-navigaatio](tehtava63)   

[Tehtävän 6.1](tehtava61) lähtökohtana on elokuvatietojen hallintaa tukeva sovellus, jonka käyttöliittymän ulkoasua viimeistellään Bootstrap -tyylinen avulla. [Tehtävässä 6.2](tehtava62) muokataan web-sivu responsiiviseksi hyödyntäen CSS:n mediakyselyjä ja Bootstrapin tarjoamaa gridiä. [Tehtävässä 6.3](tehtava63) kehitetään tyylitiedoston ylläpidettävyyttä eliminoimalla tyylimäärittelyissä ilmenevää toisteisuutta Less -laajennuksen avulla. Nämä tehtävät perustuvat [kurssilukemiston][weso] tehtäviin [47][tehtava47], [48][tehtava48] ja [49][tehtava49].

[weso]: {{site.baseurl}}/weso/
[tehtava47]: {{site.baseurl}}/weso/#vk-6-t47
[tehtava48]: {{site.baseurl}}/weso/#vk-6-t48
[tehtava49]: {{site.baseurl}}/weso/#vk-6-t49
