---
layout: page
permalink: /skills/

title: skills
nav: true
nav_order: 4
---

{% assign skills = site.skills | sort: "order" %}

{% for skill in skills %}

<h2>{{ skill.title }}</h2>

{% if skill.items %}
<ul>
{% for item in skill.items %}
<li>{{ item }}</li>
{% endfor %}
</ul>
{% endif %}

{% if skill.text %}
{{ skill.text }}
{% endif %}

---

{% endfor %}