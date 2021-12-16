---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

Welcome to the Climate Compatible Growth Guidelines.
On this site, you can browse guidelines on practices that support
open science.

# u4RIA

The u4RIA [goals]({% post_url 2021-12-16-u4ria %}),
provide a set of high-level goals relating to conducting
open and accessible energy system analyses in countries.

{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

<h2>{{ t | downcase }}</h2>
<ul>
{% for post in posts %}
  {% if post.tags contains t %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
  {% endif %}
{% endfor %}
</ul>
{% endfor %}

# Categories

Alternatively, you can browse our guidelines by category:

{%- if site.posts.size > 0 -%}
{% assign mydocs = site.posts | group_by: 'category' %}
{% for cat in mydocs %}
  {%- if cat.size > 0 -%}
  <h2>{{ cat.name | capitalize }}</h2>
  <ul>
    {% assign items = cat.items | sort: 'order' %}
    {% for item in items %}
      <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a></li>
    {% endfor %}
  </ul>
  {%- endif -%}
{% endfor %}
{%- endif -%}
