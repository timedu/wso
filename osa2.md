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

[Tehtävä 2.1](tehtava21)  
[Tehtävä 2.2](tehtava22)  
[Tehtävä 2.3](tehtava23)  
[Tehtävä 2.4](tehtava24)  




