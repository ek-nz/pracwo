---
layout: page
title: Browse
permalink: /browse/
nav: true
---

Have a look around the blog by using the category links below:

<uL>
{% for c in site.categories %}
    <li><a href="/{{ c[0] }}">{{ c[0] }}</a></li>
{% endfor %}
</ul>

Or browse by tag:

{% assign tags = site.tags | sort %}
{% for tag in tags %}
 <span class="site-tag">
    <a href="{{ site.baseurl }}/tags.html#{{ tag[0] }}"
        style="font-size: {{ tag | last | size  |  times: 10 | plus: 75  }}%">
            {{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
    </a>
</span>
{%- endfor -%}
<br><br>