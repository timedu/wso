---
layout: sivu
title: Tehtävä 5.6
exercise_upload_id: 291901
exercise_template_name: W5E06.PuhFirebase
---

## Puhelinmuistio: Firebase 

~~~
// sivu on työn alla
~~~

[Firebase][firebase]-tietokantaa käyttävä versio [tehtävästä 5.4](../tehtava54) ...

[firebase]: https://firebase.google.com/




{% highlight html %}

    <body ng-app="PuhApp">

        <h1>Puhelinmuistio</h1>

        <div ng-view></div>
        
        <script src="js/app.js"></script>
        
        <script src="js/firebase.auth.service.js"></script>
        <script src="js/button.directive.js"></script>             
        <script src="js/add.remove.controller.js"></script>
        
        <script src="todo/route.config.js"></script>
        <script src="todo/firebase.db.service.js"></script>
        <script src="todo/search.controller.js"></script>

    </body>

{% endhighlight %}


**Palauta** tehtävän ratkaisusta tiedostot `route.config.js`, `firebase.db.service.js`, `search.controller.js` sekä `search.view.html`, joiden rungot löytyvät tehtäväkohjan `todo`-kansiosta. Varmista ennen palautusta, että sovellus toimii odotetusti. Jos pohjakoodi sisältää testejä, varmista myös niiden läpimeno ilman virheilmoituksia.


### Lisätietoja
