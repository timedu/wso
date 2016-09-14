---
layout: sivu
permalink: /osa2/index.html 
title: 2. Arkkitehtuurimalleja
---

> Termi MVC (Model, View, Controller) esiintyy lähes kaikkialla ohjelmistotekniikassa. MVC on suunnittelumalli, joka pilkkoo sovelluksen kolmeen osaan: dataan (model), näkymään (view), ja käyttäjän interaktioita hallinnoivaan sovelluslogiikkaan eli kontrolleriin (controller). MVC-mallia on käytetty alunperin työpöytäsovelluksissa, mutta se on otettu käyttöön myös palvelin- ja selainpuolen ohjelmistoihin niiden kehittyessä.
>
> Perusideat ovat säilyneet samoina. Käyttäjän tehdessä jotain, esimerkiksi painaessa sivulla olevaa nappia, toimintoon liittyvä tieto välittyy kontrollerille, joka päättää mitä seuraavaksi tehdään. Yleisin toiminto on mallin muokkaaminen tai korvaaminen palvelimelta haetulla datalla, ja uuden näkymän näyttäminen muokattuun malliin perustuen. Palvelinohjelmistoja rakennettaessa tämä tapahtuu esimerkiksi lähettämällä web-sivulla olevan lomakkeen data tiettyyn osoitteeseen, jossa kontrolleri odottaa pyyntöä. Kontrollerin vastaanottaessa pyynnön, pyyntöön liittyvä mahdollinen data tallennetaan. Tämän jälkeen luodaan uusi model, johon haetaan tietoa esimerkiksi tietokantapalvelusta. Model ohjataan näkymän luovalle komponentille, joka lopulta palauttaa uuden näkymän käyttäjälle.
>
> Dynaamista toiminnallisuutta sisältävissä selainohjelmistoissa erityisesti vastaukset voivat sisältää paljon vähemmän dataa. Koko näkymää ei tarvitse hakea uudestaan jokaisen kyselyn yhteydessä.
>
> Käytännössä kaikissa MV* -suunnittelumalleissa ajatuksena on näkymän ja sovelluslogiikan erottaminen toisistaan.

Edelliset lainaukset on poimittu [oheislukemiston]({{site.baseurl}}/weso/) luvusta 
[9. MV* ja Web-sovelluksen rakenne]({{site.baseurl}}/weso/#9-MV*-ja-Web-sovelluksen-rakenne), joka esittelee erilaisten MVC -mallien JavaScript-toteutuksia. 

#### Tehtävät

Tämä osa sisältää neljä tehtävää, joiden kaikkien ratkaisuna on ulospäin samalla tavalla toimiva puhelinmuistio-sovellus. Tehtäväpohjat sisältävät käyttöliittymän merkkauksen. Tarvittava ohjelmakoodi on sama kuin kurssin [edellisen osan](../osa1) tehtävissä, mutta nyt sovellus jäsentyy hieman toisella tavalla.

[Tehtävän 2.1](tehtava21) ratkaisussa  jokaisellen MVC-mallin elementtille (Model, View, Controller) on oma muodostinfunktionsa. 
[Tehtävässä 2.2](tehtava22) ei ole eksplisiittistä *kontrolleria* vaan sen roolin hoitaa käyttöliittymän painonappeihin sidotut tapahtumakäsittelijät. Tehtävissä 2.1 ja 2.2 *malli* (Model) pyytää *näkymää* (View) rakentamaan käyttöliittymän *mallin* datalle.
[Tehtävässä 2.3](tehtava23) *malli* ei viittaa *näkymään* vaan *mallille* asetetaan ns. tarkkailija, joka tiedottaa *mallissa* tapahtuvista datan muutoksista. 
[Tehtävän 2.4](tehtava24) *malli* ei kommunikoi *näkymän* kanssa suoraan eikä tarkkailijan kautta. Ratkaisussa kontrolleri toimittaa *mallin* datan *näkymälle*.




