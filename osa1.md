---
layout: sivu
permalink: /osa1/index.html 
title: 1.  Oliot ja moduulit
---

JavaScript-ohjelmissa käsitellään oliota, vaikka kieli ei sisällä esim. Java-kielen kaltaisia luokkia. Olioita voidaan luoda sijoittamalla tyhjä olio `{}` muuttujan arvoksi. Toinen tapa aikaansaada olio on kutsua jotakin funktioa `new`-operaattorilla. Olioon tallentuu tieto sen luoneesta funktiosta, joka tyhjän olion sijoituksen tapauksessa on `Object`. Olion voidaan sanoa olevat tätä tyyppiä.

Oliolle syntyy ominaisuuksia (attribuutteja ja metodeja) sijoituslauseiden myötä (`olio.ominaisuus =  ...`). Jos olio luodaan funktiolla, se voi viitata muodostuvaan uuteen olioon tunnisteella `this`. Olion kaikki ominaisuudet näkyvät olion ulkopuolelle. Esim. attribuutteja ei voi määritellä esim. Javan attribuuttien kaltaisella `private`-määreellä.

Olion `o` luoneen funktion `F` sisältämän `prototype`-olion ominaisuuksiin voidaan viitata olio `o` kautta. Usein olioon liittyvät metodit määritellään juuri `prototype`-olion ominaisuuksiksi. Esim. jos on määritelty metodi `F.prototype.m`, se voidaan suorittaa kutsulla `o.m()`. 

Oliot eivät kapseloi ominaisuuksiaan, mutta modulointiin on käytettävissä kielessä muita mekanismeja. Muuttujat voidaan piilottaa ns. sulkeumaan, joka voidaan muodostaa funktion avulla: Funktio luo olion, jonka metodit käsittelevät funktion paikallisia muuttujia. Muuttujat ovat nyt kapselissa, johon on pääsy ainoastaan funktion  palauttaman olion metodien kautta.

JavaScriptissa funktio voidaan suorittaa määrittelyn yhteydessä ilman erillistä kutsua. Käytäntö on luonteva olioita muodostaessa silloin, kun tietyn rakenteisia oliota tarvitaan ainoastaan yksi.

JavaScriptin olioita ja moduuleja käsitellään
[oheislukemiston]({{site.baseurl}}/weso/) 
luvuissa 
[6. Lisää JavaScriptistä]({{site.baseurl}}/weso/#6-Lisää-JavaScriptistä) 
ja 
[8. Oliot ja Moduulit]({{site.baseurl}}/weso/#8-Oliot-ja-Moduulit).

#### Tehtävät

Tämä osa sisältää neljä tehtävää, joiden kaikkien ratkaisuna on ulospäin samalla tavalla toimiva puhelinmuistio-sovellus. Tehtävien pohjakoodissa käyttöliittymän merkkaus ja käyttöliittymää käsittelevä ohjelmakoodi on valmiina. Laadittavana on puhelinmuistion dataa ylläpitävä olio eri periaatteilla toteutettuna.

[Tehtävässä 1.1](tehtava11) laaditaan muodostinfunktio, jolla luodut oliot eivät kapseloi dataa. Metodit sijoitetaan muodostimen `prototype` -olion ominaisuuksiksi. [Tehtävässä 1.2](tehtava12) rakennetaan määrittelyn yhteydessä suoritettava funktio, joka luo kapseloitua muistio-dataa käsittelevän olion. [Tehtävän 1.3](tehtava13) funktiolla voidaan muodostaa useita samarakenteisia datan kapseloivia puhelinmuistio-olioita. Funktiosta laaditaan kaksi versiota, joista toista kutsutaan `new`-operaattorilla ja toista ilman sitä. [Tehtävässä 1.4](tehtava14) laaditaan määrittelyn yhteydessä suoritettava funktio, joka palauttaa muodostinfunktion. Muodostinta käytetään `new`-operaattorilla ja sen avulla luodaan datan kapseloivia olioita.  

Tehtävät ovat modifikaatioita 
[oheislukemiston]({{site.baseurl}}/weso/) 
[tehtävästä 17]({{site.baseurl}}/weso/#vk-2-t17). 


