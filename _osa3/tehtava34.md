---
layout: sivu
title: Tehtävä 3.4
exercise_upload_id: 286904
---

## Puhelinmuistio 

Toteuta [Tehtävän 3.0](../tehtava30) kuvaama sovellus - kuitenkin niin, että *malli* (`Model`) on laadittu hyödyntäen [jQuery](http://jquery.com)-kirjastoja. Tässä data on talletettuna palvelimelle ja siten *mallin* tehtävänä on toimia tietojen välittäjänä palvelimen ja muun sovelluksen vällillä.

Tehtäväpohjassa *mallin* kommunikointi palvelimen kanssa on toteutettu [XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)-tyypin oliolla. Korvaa tämä kommunikointi *jQueryllä* siten, että numerojen *haussa* käytetään [getJSON](http://api.jquery.com/jQuery.getJSON/)-funktiota, *lisäyksessä* 
[post](http://api.jquery.com/jQuery.post/)-funktiota ja *poistossa* 
[ajax](http://api.jquery.com/jQuery.ajax/)-funktiota. Toteuta myös mallin alustuksen suorittava funktio `initModel`.

**Palauta** tehtävästä tiedosto `model.js`, joka sisältää funktiot `Model`- ja `initModel`. Varmista ennen palautusta, että tehtäväpohjassa olevat testit onnistuvat.


### Lisätietoja

Muistion dataa ei tallenneta itse *malliin*, joten sen käytössä ei ole (esim.) tehtävien 3.0 - 3.3 tapaan `henkilöt`-muuttujaa (ks. alla oleva kuva). 

Kommunikointi palvelimen kanssa tapahtuu asynkonisesti, jolloin mallin muistio-datan käsittelyyn liittyvät metodit (`annaNumerot`, `lisaaNumero` ja `poistaNumero`) tulevat suoritetuksi loppuun ennen kuin mallin tekemä pyyntö palvelimella on toteutettu. Tällöin esim. `annaNumerot` ei voi palauttaa dataa, koska sitä ei ole vielä saatu palvelimelta. 

Tässä malli informoi pyynnön valmistumisesta sille asetetun *kuuntelijan* avulla, kun se on saanut tiedon ao. pyynnön suorittamisesta palvelimelta:

![Async-ekstrat](../img/async_ext_34.png "Async-ekstrat")
 
Mallin alustaja `initModel` asettaa mallille kuhunkin tapahtumaan (`anna`, `lisaa`, `poista`) liittyvän kuuntelijan kutsumalla mallin `asetaKuuntelija`-metodia. (vrt.  [addEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)). 

Tehtäväpohja on NetBeansin *php*-tyypin projekti, jossa palvelinpään osuuden toteutus löytyy tiedostosta `php/muistio.php`.  Skripti tallettaa muistio-datan istuntoon. Muistion koko sisällön voi tulostaa pyynnöllä `./php/muistio.php?dump` ja datan voi poistaa pyynnöllä `./php/muistio.php?reset`. Em. pyynnöt toteuttavat linkit löytyvät pohjassa olevasta tiedostosta `utils.html`.





