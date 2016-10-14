---
layout: sivu
title: Tehtävä 4.6
exercise_upload_id: 289242
exercise_template_name: W4E06.Pikakirjoitus
---

## Pikakirjoitus

> Muokkaa tehtäväpohjassa olevaa kontrolleria[^1] siten, että käyttäjä voi testata pikakirjoitustaitojaan. Pikakirjoituspelin tulee toimia niin, että käyttäjä näkee sivulla pitkän `Lorem ipsum dolor sit amet...` -tekstin[^2]. Kun käyttäjä painaa `Aloita!` -painiketta, hänen täytyy alkaa kirjoittamaan näkeemäänsä tekstiä tekstikenttään niin nopeasti kuin mahdollista. Käyttäjällä on aikaa kirjoittaa tekstiä 15 sekuntia[^3]. Sovelluksen tulee toimia niin, ettei se hyväksy tekstikenttään virheellisiä merkkejä. Samaan aikaan, kun käyttäjä kirjoittaa, sivulla näkyvän laskurin arvo vähenee joka sekunti. Kun laskurin arvo on 0, sovellus ilmoittaa käyttäjälle, kuinka monta merkkiä hän onnistui kirjoittamaan[^4]. Peli voidaan aloittaa uudelleen `Aloita!` -painiketta klikkaamalla .
> 
> Toteuta pikakirjoituspeli käyttämällä [$watch][watch] -funktiota tarkkailemaan `timeLeft` (kuinka paljon laskurissa on aikaa) ja `userText` (käyttäjän kirjoittama teksti) muuttujien  arvoja. Kun `timeLeft` muuttujan arvo on 0, ilmoita käyttäjälle, kuinka monta merkkiä hän onnistui kirjoittamaan oikein[^4]. Tarkkaile `userText` -muuttujaa kirjoitusvirheiden varalta esimerkiksi seuraavasti:

[^1]: `todo/controller.js`
[^2]: teksti löytyy tiedoston `index.html` asettamasta globaalista muuttujasta `TEXT`
[^3]: tiedoston `index.html` asettaa globaalin muuttujan `TIME` arvoon `15`
[^4]: ilmoitus tulee  laskurin arvon viereen, esim. `Aikaa jäljellä: 0 => Onnistuit kirjoittamaan 99 merkkiä.` (pelin päättyessä ilmoitus voidaan konkatenoida laskurin arvon perään)

[watch]: https://docs.angularjs.org/api/ng/type/$rootScope.Scope#$watch

{% highlight javascript %}

   var lastChar = newVal.charAt(newVal.length - 1);
   if(lastChar != $scope.text.charAt(newVal.length - 1)){
      $scope.userText = $scope.userText.slice(0,-1);
   }

{% endhighlight %}

 
> Pelin aloittaa `Aloita!` -painikkeen klikkaaminen. Aloita laskurin vähentäminen siitä hetkestä käyttämällä [$interval][interval] -funktiota.  

[interval]: https://docs.angularjs.org/api/ng/service/$interval

Palauta tehtävästä tiedosto `controller.js`, jonka runko löytyy `todo`-hakemistosta. Varmista, että tehtäväpohjassa olevat testit menevät läpi ennen palautusta. Sovelluksen template on valmiina tiedostossa `tmpl/template.html`.

### Lisätietoja

Tehtävä on poimittu lähes sellaisenaan [kurssimateriaalista][weso],
[Tehtävä 32][tehtävä-32], jonka edellä materiaalissa käsitellään tehtävän ratkaisua tukevia asioita.

[weso]: {{site.baseurl}}/weso/
[tehtävä-32]: {{site.baseurl}}/weso/#vk-4-t32 

#### Alaviitteet






