---
layout: page
title: talks & tutorial
permalink: /talks/
description: 
---
### tutorials

* Jan 15,2020, at ICPR; 2020 Multiple parametric model fitting.

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
    


