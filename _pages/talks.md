---
layout: page
title: talks & tutorial
permalink: /talks/
description: 
---
### tutorials

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
    


[mmf]:https://www.micc.unifi.it/icpr2020/index.php/tutorial6/
