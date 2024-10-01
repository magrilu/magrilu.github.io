---
layout: page
title: talks & tutorial
permalink: /talks/
description: 
nav: true
nav_order: 3
---
### tutorials

* <i>September 30,2024, at ECCV 2024</i>: [Inside Plato's door: a tour in multi-view geometry][plato24].

* <i>June 20,2022, at CVPR 2022</i>: [Inside Plato's door: a tour in multi-view geometry][plato].

* <i>Jan 15,2020, at ICPR 2020</i>: [Multiple parametric model fitting][mmf].

### talks
 {% if site.talks  %}
  {% assign talks = site.talks | reverse %}
{% for talk in talks %}
{% if talk.inline %}
 * <i>{{ talk.date | date: "%b %-d, %Y" }}, at {{ talk.place }}</i>:   {{ talk.content | remove: '<p>' | remove: '</p>' }}
 {% else %}

 {% endif %}
{% endfor %}
{% endif %}
    

[plato]:https://sites.google.com/view/platomultiview/
[plato24]:https://sites.google.com/view/platomultiview24/home-page
[mmf]:https://www.micc.unifi.it/icpr2020/index.php/tutorial6/
