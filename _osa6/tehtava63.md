---
layout: sivu
title: Tehtävä 6.3
exercise_upload_id: 293166
exercise_template_name: W6E03.LessNavigaatio
---

## Less-navigaatio 

Tämä tehtävä on poimittu lähes sellaisenaan kurssilukemistosta: [Tehtävä 49][tehtava49].

[tehtava49]: {{site.baseurl}}/weso/#vk-6-t49

Tehtäväpohjassa on tyylitiedosto `css/site.css` ja sitä käyttävä esimerkkisivu `index.html` sekä näiden vastintiedostot `todo/site.less` ja `indexless.html`. `less`- ja `css` -tiedostojen sisällöt ovat aktiivisen koodin osalta samoja[^less-vs-css]. Muokkaa tiedostoa `site.less` seuraavassa kohdassa kuvattujen vaiheiden mukaan. 
 
 [^less-vs-css]: *css* -koodi on samalla myös kelvollista *less* -koodia
 
### Ratkaisun vaiheistus 

Vaikka jokin tehtäväpohjassa oleva tai aikaisemmassa vaiheessa kirjoittamasi koodi käy uuden vaiheen myötä tarpeettomaksi, älä poista sitä vaan jätä se poiskommentoituna ( `/* ... */` ) tiedostoon. 

Kehitystyön ajan (*Vaiheet 1-3, 5*) tiedostot `index.html` ja `indexless.html` näkyvät selaimessa samanlaisina lukuunottamatta *Vaihetta 4*, jonka toteuttamisen myötä `less`-version painikkeisiin pitäisi ilmestyä liukuvärjäys.
 
#### Vaihe 1

Toteuta kaikki valitsimet sisäkkäisinä niin, ettei `site.less` -tiedosta löydy yhtään monen peräkkäisen valitsimen ryhmää.

#### Vaihe 2

Määrittele väri `#5BB12F` muuttujassa `@green`, väri `#008BBA` muuttujassa `@blue` ja väri `#DC403B` muuttujassa `@red`. Korvaa sen jälkeen värien esiintymät muuttujilla niin, ettei tyylitiedostossa enää löydy värien heksadesimaaliesityksiä.

#### Vaihe 3

Toteuta funktio `.btn(@color)`, joka määrittää painikkeen annetulla värillä. Käytä funktion pohjana valitsimissa `.btn-blue`, `.btn-green` ja `.btn-red` toistuvia ominaisuuksia ja aseta sen taustaväri parametrin `@color` mukaan. 

Lisää funktioon `:hover` -pseudovalitsin, jossa painikkeen taustaväri muuttuu 20% alkuperäistä taustaväriä (parametrin `@color` arvoa) tummemmaksi (vinkki: `darken` -funktio). 

Käytä toutettamaasi funktiota valitsimissa `.btn-red`, `.btn-blue` ja `.btn-green`, joissa kutsut `.btn` -funktiota edellisessä kohdassa määrittämilläsi muuttujien `@red`, `@blue` ja `@green` arvoilla.

#### Vaihe 4

Toteuta funktio `.gradient(@start, @end)`, joka lisää elementtiin gradientin taustan. Gradientti tausta määritellään eri selainten ominaisuuksilla seuraavasti:

{% highlight css %}

  background: -webkit-linear-gradient(red, blue); /* Safarille */
  background: -o-linear-gradient(red, blue); /* Operalle */
  background: -moz-linear-gradient(red, blue); /* Firefoxille */
  background: linear-gradient(red, blue); /* Standardi */

{% endhighlight %}

Tämä esimerkki luo gradientin, joka alkaa sinisenä ja päättyy punaiseen. Käytä omassa funktiossasi alkuvärinä parametrin `@start` -arvoa ja loppuvärinä parametrin `@end` arvoa.

Kun funktio on toteutettu, kutsu sitä `.btn` -funktiossa niin, että tausvärin asettamisen sijaan painikkeeseen liitetään gradientti-tausta, joka alkaa `@color` -parametrina annetusta väristä ja päättyy siitä 15% vaaleampaan väriin (vinkki: `lighten`). 

Vaihda myös `:hover` -pseudovalitsinta niin, että se käyttää `.gradient` -funktiota `@color` -parametria 20% tummemmalle värillä (vinkki: alkuväri on `darken(@color, 20%)` ja loppuväri 15% vaaleampi, eli `darken(@color, 5%)`).

#### Vaihe 5

Määrittele taulukko `xs`, `sm`, `md`, `lg`, `xl` muuttujaan `@sizes` ja poista tiedostosta valitsimet `.btn-xs`, `.btn-sm`, `.btn-md`, `.btn-lg` ja `.btn-xl`. 

Tutustu sen jälkeen [toistorakenteisiin][loops] ja toteuta funktio `.btn-sizes(@counter: 1, @fontSize: 0.6em)`, joka generoi valitsimet eri kokoisille painikkeille niin, että `.btn-xs` -painikkeen fontin koko on `0.6em` ja fontin koko kasvaa aina 0.2em painikkeen kasvaessa, kunnes `.btn-xl` -painikkeen fontin koko on `1.4em`. 

[loops]: http://lesscss.org/features/#loops-feature

Käytä funktion `@counter` -parametria pitämään kirjaa siitä, kuinka mones kierros rekursiossa on käynnissä ja lopeta rekursio, kun `@counter` -parametrin arvo saavuttaa arvon `length(@sizes)`, eli taulukon `@sizes` pituuden. 

Kasvata rekursiossa `@fontSize` -parametrin arvoa aina 0.2em:llä. Muista, että saat alkion taulukon indeksissä käyttämällä `extract` -funktiota, mistä on hyötyä generoidessa valitsimien nimiä. Valmiin funktion kutsuminen generoi seuraavat valitsimet:


{% highlight css %}

.btn-xs{
  font-size: 0.6em;
}
.btn-sm{
  font-size: 0.8em;
}
.btn-md{
  font-size: 1em;
}
.btn-lg{
  font-size: 1.2em;
}
.btn-xl{
  font-size: 1.4em;
}

{% endhighlight %}

### Palautettava aineisto

**Palauta** tehtävästä `todo` -hakemiston tiedostot `site.less` ja `suoritusyhteenveto.txt`. Kirjaa ennen palautusta pyydetyt tiedot jäkimmäiseen.

### Lisätietoja

less -kieltä käsitellään lyhyesti kurssilukemiston [luvussa 20][weso-20]. Kattava esitys kielestä löytyy sen [omalta sivustolta][less].

[weso-20]: {{site.baseurl}}/weso/#20-Selkeyttä-ja-rakennetta-tyylitiedostoihin:-Less
[less]: http://lesscss.org

Kurssilukemistossa ohjataan asentamaan less -kääntäjä NetBeansiin. Tässä kuitenkin käytetään `less.js` -kirjastoa less -koodin kääntämiseen. Kirjasto otetaan käyttöön verkon yli (ks. `indexless.html`). Käännös tapahtuu sovelluksen ajon yhteydessä. Tieto käänöksestä ilmestyy selaimen konsolille. Käännösvirheet tulostuvat sivulle selaimen ikkunaan. 

Osoitteesta <http://winless.org/online-less-compiler> löyttyy työkalu, jolla voi tutkia, minkälainen *css* -koodi vastaa annettua *less* -koodia.

Saattaa olla, että Netbeansin less -editori, ei hyväksy jotakin syntaksia, jonka  `less.js` kääntää onnistuneesi. Liittyen tämän tehtävän *Vaiheeseen 5*, esimerkki tällaisesta tilanteesta on valitsin `.btn-@{size}` (a), jossa muuttuja `@size` sisältää esim. arvon `xs`. NetBeans hyväksyy valitsimelle esim. muodon `.@{class}` (b). Jos (a) on tavoiteltava valitsin, tarvitaa sijoituslause `@class: ~'btn-@{size}'`, jotta valitsin saadaan lausekkeella (b).   


#### Alaviitteet


