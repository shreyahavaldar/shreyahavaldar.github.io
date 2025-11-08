---
layout: archive
title: "Selected Publications"
permalink: /publications/
author_profile: true
---

🌸<em> Please see my Google Scholar for a complete list </em>🌸
<!-- ###### *(\* indicates equal contribution)* -->

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

<br>

# Preprints

<!-- ###### *(\* indicates equal contribution)* -->

{% for post in site.projects reversed %}
  {% include archive-single.html %}
{% endfor %}
