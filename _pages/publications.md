---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

<!-- ###### *(\* indicates equal contribution)* -->

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

<br>

# Projects

<!-- ###### *(\* indicates equal contribution)* -->

{% for post in site.projects reversed %}
  {% include archive-single.html %}
{% endfor %}
