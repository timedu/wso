---
layout: sivu
permalink: /osa5/index.html 
title: 5. Kirjastoista - AngularJS (II)
---

~~~
// sivu työn alla
~~~

[AngularJS](https://angularjs.org)


#### Kurssilukemisto

[12. Sovelluksen rakenteen hallinta: AngularJS]({{site.baseurl}}/weso/#12-Sovelluksen-rakenteen-hallinta:-AngularJS)   
[13. Jatketaan keskustelua palvelimen kanssa: Firebase]({{site.baseurl}}/weso/#13-Jatketaan-keskustelua-palvelimen-kanssa:-Firebase)   
[15. Reititys Angularissa]({{site.baseurl}}/weso/#15-Reititys-Angularissa)   
[17. Suurempi Angular-sovellus: Elokuvakirjasto]({{site.baseurl}}/weso/#17-Suurempi-Angular-sovellus:-Elokuvakirjasto)   


#### Tehtävät

[Tehtävä 5.1 Puhelinmuistio: Angular](tehtava51)   
[Tehtävä 5.2 Puhelinmuistio: Service](tehtava52)   
[Tehtävä 5.3 Puhelinmuistio: Directive](tehtava53)   
[Tehtävä 5.4 Puhelinmuistio: Routing](tehtava54)   
[Tehtävä 5.5 Hello Firebase](tehtava55)   
[Tehtävä 5.6 Puhelinmuistio: Firebase](tehtava56)   

Tämän osan tehtävissä palataan jo edellisissä osissa esillä olleeseen puhelinmuistio -sovellukseen, jonka ominaisuuksia kehitetään nyt AngularJS:n avulla.

[Tehtävä 5.1](tehtava51) kertaa jo [kurssin edellisessä osassa](../osa4) esiin tulleita asioita. Testävässä muokataan aikaisemmin toteutettu sovellus siten, että sen näkymä ja kontrolleri toteutetaan Angularilla. [Tehtävässä 5.2](tehtava52) sovelluksen dataa ylläpitävästä Muistio-moduulista laaditaan erillinen palvelu, joka injektoidaan kontrollerin käyttöön. [Tehtävä 5.3](tehtava53) esittelee, miten direktiivin avulla voidaan määritellä käyttöliittymässä olevan elementin ominaisuuksia. Tehtävässä laadittava sovelluksen painikkeisiin liitettävä direktiivi määrää panikkeen otsikon ja samalla klikkaukseen liityvän käsittelijän.

[Tehtävässä 5.4](tehtava54) sovellus jaetaan kolmeen erilliseen näkymään ja määritellään erillisen reitityskonfiguraation avulla osoitteet, joissa kukin näkymä tulee esiin. [Tehtävässä 5.6](tehtava56) injektoidaan sovellukseen palvelu, jonka kautta voidaan käyttää verkossa toimivaa [Firebase][Firebase] -tietokantaa. Sovellusen data tallennataan tässä palvelun kautta tietokantaan. Sovellukseen liitetään samalla myös tunnistautuminen. [Tehtävä 5.5](tehtava55) on tehtävää 5.6 valmisteleva tehtävä. Tehtävässä 5.5 kytketään sovellus Firebase -tietokantaan ja haetaan sieltä näkymään tietoa.

[Firebase]: https://firebase.google.com


