---
layout: page
title: Tags
---
Jump to a tag:
{% assign tags = site.tags | sort %}
{% for tag in tags %}
 <span class="site-tag">
    <a href="{{ site.baseurl }}tags.html#{{ tag[0] }}">
            {{ tag[0] | replace:'-', ' ' }} <span class="tag-number">{{ tag | last | size }}</span>
    </a>
</span>
{%- endfor -%}
<br><br>
## Tag list

<!-- Loop over all tags -->
{% for tag in site.tags %}
  <h5 id="{{ tag[0] }}" class="h5 bold text-accent">{{ tag[0] }}</h5>
    {% for post in tag[1] %}
    {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
<p class="post-meta"><small><i>{{ post.date | date: date_format }}</i></small>&nbsp;&nbsp;

<b><a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></b></p>

    {% endfor %}
<br>
{% endfor %}