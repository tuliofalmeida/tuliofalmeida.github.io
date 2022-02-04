---
layout: single
title: "Publications"
header:
  overlay_image: mineirao.png
  overlay_filter: 0.3
excerpt: |
  <br>

permalink: /publications/
author_profile: true
redirect_from:
  - /resume
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
