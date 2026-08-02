---
layout: page
permalink: /education/

title: education
description: My academic background
nav: true
nav_order: 5
---

{% assign educations = site.education | sort: "order" %}

{% for edu in educations %}
<div class="education-entry">
  <h2>{{ edu.title | markdownify | remove: '<p>' | remove: '</p>' }}</h2>

  <p>
    <strong>{{ edu.school }}{% if edu.location %} - {{ edu.location }}{% endif %}</strong><br>
    {{ edu.start }} - {{ edu.end }}
  </p>

{% if edu.graduation %}
  <p>{{ edu.graduation }}</p>
  {% endif %}

{% if edu.description %}
  <p>{{ edu.description }}</p>
  {% endif %}

{% if edu.courses %}
  <h3>Courses</h3>
  <ul>
    {% for c in edu.courses %}<li>{{ c }}</li>{% endfor %}
  </ul>
  {% endif %}

{% if edu.minor %}
  <p>Minor: {{ edu.minor }}</p>
  {% endif %}

{% if edu.projects %}
  <h3>Activities</h3>
  <ul>
    {% for p in edu.projects %}<li>{{ p }}</li>{% endfor %}
  </ul>
  {% endif %}
</div>

{% unless forloop.last %}<hr>{% endunless %}
{% endfor %}
