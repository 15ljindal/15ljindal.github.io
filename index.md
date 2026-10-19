---
layout: page
title: Lokesh Jindal
---
{% assign p = site.data.profile %}

{% for para in p.about %}
{% capture intro %}{% include hl.html text=para %}{% endcapture %}
<p class="intro">{{ intro | replace: 'LinkedIn', '<span class="hl-company">LinkedIn</span>' }}</p>
{% endfor %}

## Experience

{% for job in p.experience %}
### <span class="hl-company">{{ job.company }}</span>, {{ job.team }}

<p class="job-meta"><span class="hl-date">{{ job.dates }}</span>. <em>{{ job.title }}.</em></p>

<ul>
  {% for b in job.bullets %}<li>{% include hl.html text=b %}</li>
  {% endfor %}
</ul>
{% endfor %}

## Open source

{% for o in p.open_source %}
<p><span class="hl-company">{{ o.name }}</span>. {% include hl.html text=o.text %}</p>

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
