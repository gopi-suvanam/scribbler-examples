---
layout: default
title: List of Sample Scribbler Notebooks in JavaScript
---
<h1>List of Sample Scribbler Notebooks in JavaScript</h1>
<h2> site.documments </h2>
liquid
{{ site.pages | inspect }}
liquid
{{ site.static_files | inspect }}

liquid
{{ site.documents | inspect }}


liquid
{{ site.pages| inspect }}



<ul class="row">
  {% for file in site.documents %}
    {% if file.path contains '.jsnb' %}
      <li class="col-md-3 col-sm-4 mb-4 card">
        <a href="https://app.scribbler.live/?jsnb={{ file.path }}">{{ file.name | replace: '-', ' ' | replace: '_', ' ' | remove: '.jsnb' }}</a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
