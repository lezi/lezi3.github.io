---
layout: page
class: category
description: Software Development.
---
# Software Development


<ul id="posts">
  {% for post in site.categories.dev %}
  {% unless post.draft %}
    <li class="post">
    {% if post.link %}
    <h2 class="linktitle"><a href="{{ post.link }}">{{ post.title }}</a>&nbsp;<a href="{{ post.url }}" class="infin">&infin;</a></h2>
    {% else %}
    <h2 class="posttitle"><a href="{{ post.url }}" class="articletitle">{{ post.title }}</a></h2>
  <p class="date articledate">{{ post.date | date:"%d/%m/%Y" }}</p>
    {% endif %}

    {% if post.excerpt %}
    {{ post.excerpt | markdownify }}
      {% if post.nomore != true %}
      <p><a href="{{ post.url }}">
        {% if post.language == "en" %}
        <strong>Continue reading&#8230;</strong>
        {% else %}
        <strong>Continue lendo&#8230;</strong>
        {% endif %}
      </a></p>
      {% endif %}
    {% else %}
    {{ post.content }}
    {% endif %}
    </li>
  {% endunless %}
  {% endfor %}
</ul>



