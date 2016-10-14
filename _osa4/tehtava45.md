---
layout: sivu
title: Tehtävä 4.5
exercise_upload_id: 289241
exercise_template_name: W4E05.Laskin
---

## Laskin

> Muokkaa tehtäväpohjassa olevia tiedostoja[^1] siten, että käyttäjä voi laskea kokonaislukujen kerto-, plus-, erotus- ja jakolaskuja syöttämällä haluamansa luvut kahteen kenttään ja painamalla jotain neljästä painikkeesta, jolloin valittu laskuoperaatio suoritetaan luvuille ja tulos näytetään käyttäjälle kenttien alapuolella. Jos käyttäjä yrittää jakaa lukua nollalla, ota jakolaskupainike pois käytöstä ([ng-disabled][ng-disabled]). 

Laskimen kaikki painikkeet ovat pois käytöstä, jos ainakin toinen laskutoimituksen operandeista ei ole kelvollinen kokonaisluku.

[^1]: `todo/template.html` ja `todo/controller.js`

[ng-disabled]: https://docs.angularjs.org/api/ng/directive/ngDisabled

Palauta tehtävästä tiedostot `template.html` ja `controller.js`, joiden rungot löytyvät `todo`-hakemistosta. Varmista, että tehtäväpohjassa olevat testit menevät läpi ennen palautusta.

### Lisätietoja

Tehtävä on poimittu lähes sellaisenaan [kurssimateriaalista][weso],
[Tehtävä 31][tehtävä-31], jonka edellä materiaalissa käsitellään tehtävän ratkaisua tukevia asioita.

[weso]: {{site.baseurl}}/weso/
[tehtävä-31]: {{site.baseurl}}/weso/#vk-4-t31 

Tehtäväpohjassa on määritelty [säännölliset lausekkeet][Regular_Expressions], joita voi hyödyntää painikkeiden aktivoinnissa:

[Regular_Expressions]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions

{% highlight javascript %}

    var LUKU = /^\s*[0-9]{1,}\s*$/;
    var NOLLA = /^\s*0{1,}\s*$/;

{% endhighlight %}

Säännöllisen lausekkeen [test][test] -metodin avulla voidaan tutkia, sopiiko jokin merkkijono lausekkeen määrittelemään malliin, esim.

[test]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test

{% highlight javascript %}

    LUKU.test('123X');  // false
    LUKU.test('123');   // true
    NOLLA.test(' 00 '); // true

{% endhighlight %}



#### Alaviitteet
