---
layout: sivu
title: Tehtävä 6.2
exercise_upload_id: 293162
exercise_template_name: W6E02.Responsiivisuus
---

## Responsiivisuus 

Tämä tehtävä on poimittu lähes sellaisenaan kurssilukemistosta: [Tehtävä 48][tehtava48].

[tehtava48]: {{site.baseurl}}/weso/#vk-6-t48

Tehtäväpohjassa on tiedosto `index.html` ja sen viittaamat tyylitiedostot `css/site.css` ja `todo/responsive.css`. Lähtötilanteessa tyylitiedostoista jälkimmäinen on vailla aktiivista sisältöä.

Pohjassa on mukana myös toinen edellä mainitun kanssa samasisältöinen html-tiedosto, `todo/indexgrid.html` kuitenkin niin, että se viittaa em. css-tiedostojen lisaksi verkon yli Bootstrap -tyyleihin.

Lähtötilanteessa html-tiedostot eivät käyttäydy selaimessa responsiivisesti. Kehitä ratkaisu seuraavien vaiheiden kautta responsiiviseksi muokkaamalla tiedostoja `todo/responsive.css` ja `todo/indexgrid.html`.

### Vaihe 1

Aloitetaan lisäämällä tyyleihin media-kyselyita, jonka avulla voimme mukauttaa ulkoasua kapenevaan näyttöön. Toteuta `todo/responsive.css` -tiedostoon media-kyselyt ja tyyleihin kohdistuvat muutokset, jotka tekevät seuraavat asiat:

1. Muuta id:llä `main-container` varustettua section-elementtiä niin, että sen leveys ei ole kiinteät 1300 pikseliä, vaan sen leveys on maksimissaan 1300 pikseliä ja kapeammilla näytöillä se on koko näytön leveyinen (vinkki: et välttämättä tarvitse media-kyselyä, jos käytät `max-width` -ominaisuutta; `width` kannattaa palauttaa oletusarvoonsa: `auto`).

2. Kun näytön leveys on alle 1000 pikseliä, piilota hakulomake navigaatiopalkista (vinkki: `display` -ominaisuus). Hakulomake sijaitsee section-elementissä, jonka id on `search-form`.

3. Kun näytön leveys on alle 800 pikseliä, muuta lilan laatikon fontin kooksi 1em. Lila laatikko muodostuu section-elementistä, jonka id on `jumbo-container`.

4. Kun näytön leveys on alle 800 pikseliä, piilota navigaatiopalkki, joka muodostuu ul-elementistä, jonka id on `navigation` ja näytä pudotusvalikko, joka muodostuu div-elementistä, jonka id on `dropdown-navigation` (vinkki: `display` -ominaisuus)

### Vaihe 2

Laitetaan seuraavaksi sisältö gridiin käyttämällä Bootstrapin tarjoamaa grid-järjestelmää. Toteuta tiedostoon `todo/indexgrid.html` grid seuraavanlaiseksi:

1. Vasemmanpuoleinen ja oikeanpuoleinen sisältö muodostavat rivin, jossa on kaksi saraketta. Vasemmanpuoleisen sarakkeen leveys on kahdeksan saraketta ja oikeanpuoleisen sarakkeen leveys on neljä saraketta.

2. Vasemmanpuoleisen sarakkeen sisällä on rivi, jossa on kolme saraketta. Kaikkien sarakkeiden leveys on neljä saraketta.

Palauta oletusarvoonsa tyylit koskien elementtejä, jotka asetit gridiin. Tämän voi tehdä poistamalla kommenttimerkit tiedoston `todo/indexgrid.html` `style` -elementin sisällöstä.

### Palautettava aineisto

**Palauta** tehtävästä `todo` -hakemiston tiedostot `responsive.css`, `indexgrid.html` sekä `suoritusyhteenveto.txt`. Kirjaa ennen palautusta pyydetyt tiedot txt-tiedostoon.

### Lisätietoja

Responsiivisuus on esillä kurssilukemiston [luvussa 19][weso-19]. Esim. Firefox-selaimessa on mukana [responsiivisen suunnittelun apuväline][responsive].

[weso-19]: {{site.baseurl}}/weso/#19-Responsiivinen-web-suunnittelu
[responsive]: https://developer.mozilla.org/en-US/docs/Tools/Responsive_Design_Mode



