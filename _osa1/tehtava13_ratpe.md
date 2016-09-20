---
layout: sivu
title: Tehtävä 1.3
---

## Ratkaisuperiaate



### Puhelinmuistio

Funktiota käytetään kuten Tehtävän 1.1 laadittavaa muodostinta. Ratkaisut poikkeavat kuitenkin niin, että tässä (a) data on muodostimen paikallinen muuttuja, ja (b) metodit ovat olion omia ominaisuuksia.

{% highlight javascript %}

function OlionMuodostin() {

  var data = {};
  
  this.metodi = function() {
    // käsittele dataa
  };

  // ei return-lausetta
}

// ...

var olio = new OlionMuodostin();

// ...

olio.metodi();

{% endhighlight %}



### UusiPuhelinmuistio

Tässä ratkaisu on sama kuin Tehtävässä 1.2 kuitenkin niin, että olion rakentavaa funktiota ei suoriteta heti sen määrittelyn yhteydessä.


{% highlight javascript %}

function OlioRakentaja() {

  var data = {};
  
  var o = {}; // funktion palauttama olio
  
  o.metodi = function() {
    // käsittele dataa
  };

  return o;
}

// ...

var olio = OlioRakentaja(); // ei new-operaattoria

// ...

olio.metodi();

{% endhighlight %}


