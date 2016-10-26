---
layout: sivu
title: Tehtävä 5.3
exercise_upload_id: 291566
exercise_template_name: W5E03.PuhDirective
---

## Puhelinmuistio: Directive 

Jatkokehitä *AngularJS*-pohjaista puhelinmuistio-sovellustasi siten, että painikkeiden omainaisuudet määrittelee erillinen *direktiivi*. Sovelluksen ulkoasu ja ulkoinen käyttäytyminen pysyy muuttumattomana.

Tehtävissä [5.1](../tehtava51) ja [5.2](../tehtava52) näkymän (`template.html`) merkkaus on seuraavanlainen:

{% highlight html %}
{% raw %}

  <div ng-controller="PuhController">

    <div id="lomake">
        ...
        <button id="lisaa" ng-click="add()">Lisää</button>
    </div>
    
    <div id="luettelo">                
        ...
            <li ng-repeat="numero in numerot">
                {{numero}}
                <button ng-click="remove(nimi, numero)">X</button>
            </li>
        </ul>                
    </div>

  </div>

{% endraw %}
{% endhighlight %}


Merkkaus sisältää kaksi painiketta (`button`). Molemmille painikkeille on `ng-click`-direktiivillä määritelty tapahtumakäsittelijä. `button`-elementtien sisältönä oleva teksti näkyy sivulla painikkeiden otsikkona.

Tämän tehtävän pohjakoodissa vastaava tiedosto on seuraavanlainen:

{% highlight html %}
{% raw %}

  <div ng-controller="PuhController">

    <div id="lomake">
        ...
        <button wso-btn="add"></button>
    </div>

    <div id="luettelo">  
        ...              
            <li ng-repeat="numero in numerot">
                {{numero}}
                <button wso-btn="remove" 
                        data-nimi="{{nimi}}" 
                        data-numero="{{numero}}">                            
                </button>
            </li>
        </ul>
    </div>

  </div>

{% endraw %}
{% endhighlight %}

Painikkeilla ei ole `ng-click`-direktiiviä eikä sisältöä. Näiden sijaan painikkeilla on tässä tehtävässä määriteltävä `wso-btn`-direktiivi. Poisto-painikkeella on myös attribuutit `data-nimi` ja `data-numero`, joiden arvona on numeron poistossa tarvittavat tiedot. Direktiivi laaditaan pohjassa olevaan runkoon, `directive.js`:

{% highlight javascript %}

PuhApp.directive('wsoBtn', function (WSO_BTN) {

    return {        
        // ...                
    };
});

{% endhighlight %}

Direktivi otsikoi painonapin sekä asettaa sille `click`-tapahtuman käsittelijän. 

Painikkeiden otsikot määrittelee `WSO_BTN`-olio, jolle `index.html` asettaa arvon. Esim. jos painikkeella on `wso-btn`-direktiivi ja sitä vastaavan attribuurin arvona on `add`, painikkeelle haetaan avaimella `add` otsikkoa oliosta `WSO_BTN`. Jos otsikkotekstiä ei löydy, otsikoksi asetetaan `add` so. `wso-btn`-attribuutin arvo.

Painikkeen `click`-tapahtuman käsittelijäksi asetetaan funktio, joka kutsuu ao. kontrollerin määrittelemää metodia. Jos `wso-btn`-attribuutin arvona on `add`, tapahtumakäsittelijä kutsuu metodia `add` so. attribuutin arvo määrää kutsuttavan metodin. Metodikutsun parametriksi annetaan ao. elementti. Direktiivi ei kuitenkaan aseta tapahtumakäsittelijää, jos ao. kontrollerilta ei löydy `wso-btn`-attribuutin arvoa vastaavaa metodia.

Sovelluksen pohjassa olevan pääsivun `index.html` merkkaus on seuraava:

{% highlight html %}

    <body ng-app="PuhApp">

        <h1>Puhelinmuistio</h1>

        <div ng-include=" 'view/template.html'"></div>

        <script>

            PuhApp = angular.module('PuhApp', []);

            PuhApp.constant('WSO_BTN', {
                add: 'Lisää',
                remove: 'X'
            });

        </script>

        <script src="js/service.js"></script>

        <script src="todo/controller.js"></script>
        <script src="todo/directive.js"></script>

    </body>

{% endhighlight %}

Pääsivun viittaamista tiedostoista `template.html` on pohjassa valmiina. Tiedoston `service.js` voi kopioida sellaisenaan edellisen tehtävän ratkaisusta. *Direktiivi* laaditaan tiedostoon `directive.js`. Kontrollerin `controller.js` lähtökohdaksi voi ottaa edellisen tehtävän ratkaisun, mutta se edellyttää pieniä muutoksia

**Palauta** tehtävästä tiedostot `controller.js` ja `directive.js`. Varmista ennen palautusta, että sovellus toimii odotetusti. Jos pohjakoodi sisältää testejä, varmista myös niiden läpimeno ilman virheilmoituksia.


### Lisätietoja

AngularJS -direktiivejä käsitellään lyhyesti kurssilukemiston [kohdassa 12.6][weso-12.6]. Laajempi esitys asiasta löytyy AngularJS:n [kehittäjän oppaasta][guide].

[weso-12.6]: {{site.baseurl}}/weso/#12.6-Direktiivit
[guide]: https://docs.angularjs.org/guide/directive

*AngularJS*:n elementti-objektit muistuttavat hieman *jQuery*-objekteja, mutta esim. läheskään kaikki *jQuery*:n metodit eivät ole käytettävissä, ks. [angular.element][angular.element]. 

[angular.element]: https://docs.angularjs.org/api/ng/function/angular.element


