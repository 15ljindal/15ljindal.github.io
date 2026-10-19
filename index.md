---
layout: page
title: Lokesh Jindal
---
{% assign p = site.data.profile %}

{% for para in p.about %}
<p>{{ para | escape }}</p>
{% endfor %}

## Experience

{% for job in p.experience %}
### {{ job.company }}, {{ job.team }}

*{{ job.dates }}. {{ job.title }}.*

<ul>
  {% for b in job.bullets %}<li>{{ b | escape }}</li>
  {% endfor %}
</ul>
{% endfor %}

## Open source

{% for o in p.open_source %}
**{{ o.name }}.** {{ o.text | escape }}

{% endfor %}

## Skills

<dl>
  {% for s in p.skills %}
  <dt>{{ s.label }}</dt>
  <dd>{{ s.items | escape }}</dd>
  {% endfor %}
</dl>

## Publication

{{ p.publication | markdownify }}

## Education

<ul>
  {% for e in p.education %}<li>{{ e | escape }}</li>
  {% endfor %}
</ul>

*Last updated {{ p.updated }}.*
