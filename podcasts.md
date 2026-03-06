---
layout: default
title: "Podcasts"
---
# AI Research Podcasts

*Daily conversations about AI research papers, generated with Gemini TTS.*

{% assign podcast_pages = site.pages | where_exp: "p", "p.path contains '/podcast.md'" | sort: "path" | reverse %}
{% if podcast_pages.size == 0 %}
<p>No podcast episodes yet.</p>
{% else %}
<ul>
{% for ep in podcast_pages %}
  {% assign ep_date = ep.path | remove: "/podcast.md" %}
  <li><a href="{{ site.baseurl }}/{{ ep_date }}/podcast">{{ ep_date }}</a></li>
{% endfor %}
</ul>
{% endif %}
