---
layout: page
title: Tags
---
Jump to a tag:
{% assign tags = site.tags | sort %}
{% for tag in tags %}
 <span class="site-tag">
    <a href="{{ site.baseurl }}/tag/tags.html#{{ tag[0] }}"
        style="font-size: {{ tag | last | size  |  times: 10 | plus: 75  }}%">
            {{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
    </a>
</span>
{%- endfor -%}
<br><br>
Here is a list of tags with all their related posts:

<!-- Loop over all tags -->
{% for tag in site.tags %}
  <h2 id="{{ tag[0] }}" class="tag">{{ tag[0] }}</h2>
    {% for post in tag[1] %}
    {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
<p class="post-meta"><small><i>{{ post.date | date: date_format }}</i></small>&nbsp;&nbsp;

<b><a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></b></p>

    {% endfor %}
{% endfor %}