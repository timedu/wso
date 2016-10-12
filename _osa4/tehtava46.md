---
layout: sivu
title: Tehtävä 4.6
exercise_upload_id: 289242
exercise_template_name: W4E06.Pikakirjoitus
---

## Pikakirjoitus

~~~
// sivu edellyttää päivitystä
~~~

> Muokkaa tehtäväpohjassa olevaa dokumenttia siten, että käyttäjä voi testata pikakirjoitustaitojaan. Pikakirjoituspelin tulee toimia niin, että käyttäjä näkee sivulla pitkän "Lorem ipsum dolor sit amet..."-tekstin, jonka sisältö löytyy muuttujasta text. Kun käyttäjä painaa "Aloita!"-painiketta, hänen täytyy alkaa kirjoittamaan näkeemäänsä tekstiä tekstikenttään niin nopeasti kuin mahdollista. Käyttäjällä on aikaa kirjoittaa tekstiä 15 sekuntia. Varmista, ettei käyttäjä tee kirjoitusvirhettä niin, ettet hyväksy tekstikenttään virheellisiä merkkejä. Samaan aikaan, kun käyttäjä kirjoittaa, sivulla näkyvän laskurin arvo vähenee joka sekunti. Kun laskurin arvo on 0, tulee käyttäjälle ilmoittaa alert-ikkunan kautta, kuinka monta merkkiä hän onnistui kirjoittamaan. Pelin uudelleen aloittamiseksi riittää, että käyttäjä päivittää sivun, mutta voit halutessasi alustaa pelin uudelleen, kun laskurin arvo on 0.
> 
> Toteuta pikakirjoituspeli käyttämällä $watch-funktiota tarkkailemaan esimerkiksi timeLeft (kuinka paljon laskurissa on aikaa) ja userText nimisten muuttujien (käyttäjän kirjoittama teksti) arvoja. Kun timeLeft muuttujan arvo on 0, ilmoita käyttäjälle, kuinka monta merkkiä hän onnistui kirjoittamaan oikein (esim. "Onnistuit kirjoittamaan 30 merkkiä!"). Tarkkaile userText-muuttujaa kirjoitusvirheiden varalta esimerkiksi seuraavasti:

~~~
   var lastChar = newVal.charAt(newVal.length - 1);
   if(lastChar != $scope.text.charAt(newVal.length - 1)){
      $scope.userText = $scope.userText.slice(0,-1);
   }
~~~ 
 
> Pelin aloittaa "Aloita!"-painikkeen klikkaaminen. Aloita siis laskurin vähentäminen siitä hetkestä käyttämällä $interval-funktiota. TypeController-kontrollerin pohja löytyy tiedostosta app/app.js ja näkymä tiedostosta index.html. 

Palauta tehtävästä tiedosto `controller.js`, jonka runko löytyy `todo`-hakemistosta. Varmista, että tehtäväpohjassa olevat testit menevät läpi ennen palautusta.

### Lisätietoja

Tehtävä on poimittu lähes sellaisenaan [kurssimateriaalista]({{site.baseurl}}/weso/),
[Tehtävä 32]({{site.baseurl}}/weso/#vk-4-t32), jonka edellä materiaalissa käsitellään tehtävän ratkaisua tukevia asioita.

