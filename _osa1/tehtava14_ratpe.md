---
layout: sivu
title: Tehtävä 1.4
---

## Ratkaisuperiaate

Tämän tehtävän ratkaisussa tavoitellaan "kaksoiskapselirakennetta": muodostimella luodaan olioita, joilla on paikallinen data (nimet ja puhelinnumerot) mutta sen lisäksi vielä yhteistä dataa (hätänumerot), johon ei viitata globaalilla tunnisteella. Muodostimesta halutaan sellainen, että sitä kutsuttaessa olioiden yhteistä dataa ei tarvitse antaa parametriksi.

Tehtävän yhteydessä viitataan oheismateriaalin vastaavaa tilannetta kuvaavaan esimerkkiin:


{% highlight javascript %}

kauppa.hinnasto = ...

kauppa.Ostoskori = (function(hinnasto) {

    // hinnasto-parametri (ulomman funktion paikallinen muuttuja)
    // on samasilältöisenä kaikkien muodostimella luotavien
    // olioiden käytettävissä

    function Kori() {

        // oliokohtainen data
        var ostokset = [];

        this.lisaa = function(tuotteenNimi) {
            // ...
        }

        this.tuotteidenLukumaara = function() {
            // ...
        }

        this.yhteishinta = function() {
            // ...
        }
    }

    return Kori;
    
})(kauppa.hinnasto);

var kori1 = new kauppa.Ostoskori();
kori.lisaa("kekseja");

// ...

var kori2 = new kauppa.Ostoskori();


{% endhighlight %}

