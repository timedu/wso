---
layout: sivu
title: Web-selainohjelmointi
---

Opintojakson toteutuksen runko on [TTY:n Moodlessa](https://moodle2.tut.fi/course/view.php?id=9776). Tämä sivusto sisältää opintojakson tehtävien kuvaukset ja tehtäviin liittyviä opastuksia.

Opintojakson lähtökohtana on [Helsingin yliopiston Tietojenkäsitelytieteen laitoksella](https://www.cs.helsinki.fi/) järjestettävä [samanniminen kurssi](https://www.cs.helsinki.fi/courses/582354/2015/s/k/1), jonka [materiaali ](http://web-selainohjelmointi.github.io) toimii tämän opintojakson tukena. Materiaalista on käytössä [kopio](weso/), joka ei alkuperäisestä poiketen kysy TMC-tunnusta[^1] sivun latauksen yhteydessä.

[^1]: TMC (Test My Code) - Helsingin yliopiston ohjelmointikursseilla käytössä oleva testauspalvelin.


{% comment %}


<div class="home">

  <h1 class="page-heading">Posts</h1>

  <ul class="post-list">
    {% for post in site.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
      </li>
    {% endfor %}
  </ul>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>

</div>

{% endcomment %}
