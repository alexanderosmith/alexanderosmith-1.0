---
layout: page
title: "Michael Standen - Curriculum Vitae"
description: "Software Engineer for fun and profit"
permalink: /cv.html
image: "images/sai-kiran-anagani-61187.jpg"
imageattribution: "Sai Kiran Anagani"
imageattributionlink: https://unsplash.com/@iamkiran
block_share_bottom: true
---

<button class="btn align-right print-content-button">Print</button>

<div class="print-content">

{% capture pageContent %}
{% assign cv = site.data.cv %}
# {{ cv.details.name }}
{% if cv.details.blurb %}
### {{ cv.details.blurb }}
{% endif %}

{% if cv.details.email %}Email: **<a href="mailto:{{ cv.details.email }}">{{ cv.details.email }}</a>**<br />{% endif %}
{% if cv.details.phone %}Phone: **{{ cv.details.phone }}**<br />{% endif %}
{% if cv.details.location %}Location: **{{ cv.details.location }}**<br />{% endif %}

{% for section in cv.sections %}
## {{ section.title }}
{% if section.request %}
### {{section.title}} available on request
{% else %}
{% for item in section.content %}
{% if item.title %}
### {{ item.title }}
{% endif %}
{% if item.date and item.blurb %}
#### ({{ item.date }}) {{ item.blurb }}
{% elsif item.date %}
#### {{ item.date }}
{% elsif item.blurb %}
#### {{ item.blurb }}
{% endif %}
{% for content in item.content %}
{{ content }}
{% endfor %}
{% endfor %}
{% endif %}
{% unless forloop.last %}
---
{% endunless %}
{% endfor %}
{% endcapture %}

{{ pageContent | markdownify }}

</div>

