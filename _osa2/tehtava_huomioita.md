---
layout: sivu
title: Huomioita osan 2 tehtävistä
---


#### \# 001


Kontrolleri voisi toimia niin, että se ei kutsu mallin `annaNumerot`-metodia, jos hakuehtona oleva nimi on tyhjä merkkijono.Testi odottaa, että koodi olisi laadittu tällä tavalla. 

{% highlight javascript %}

    // ...
    var nimi = inputNimi.value.trim();
    if (nimi.length) {
      model.annaNumerot(nimi);
    }
    // ...

{% endhighlight %}

#### \# 002


*Poisto* -nappin `click`-tapahtuman käsittelijässä tulisi viitata tapahtuman aiheuttaneeseen elementtiin `target`-attribuutilla `srcElement`-attribuutin sijaan. Esim. *Firefox* ei tunnista jäkimmäistä. `srcElement`-ominaisuus on tiettävästi peräisin *IE*-selaimesta. Elementin sovelluskohtaista dataa voidaan käyttää `dataset`-ominaisuuden kautta. Testi odottaa vielä, että elementin datasta poimitut tiedot "trimmattaisiin" ennen niiden käyttöä `poistaNumero`-metodin parametrina.

Edellinen huomioiden koodin  

{% highlight javascript %}

    // ...
    var numero = e.srcElement.getAttribute("data-numero");
    var nimi = e.srcElement.getAttribute("data-nimi");
    // ...

{% endhighlight %}

voisi korvata koodilla

{% highlight javascript %}

    // ...
    var numero = e.target.dataset.numero.trim();
    var nimi = e.target.dataset.nimi.trim();
    // ...

{% endhighlight %}




