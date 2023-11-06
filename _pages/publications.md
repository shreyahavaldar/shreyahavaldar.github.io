---
layout: archive
title: "Publications <sub><sup><sub>*(\*indicates equal contribution)*</sup></sub></sub>"
permalink: /publications/
author_profile: true
---

###### (* indicates equal contribution)

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

<br>

# Projects <sub><sup><sub>*(\*indicates equal contribution)*</sup></sub></sub>


{% for post in site.projects reversed %}
  {% include archive-single.html %}
{% endfor %}
