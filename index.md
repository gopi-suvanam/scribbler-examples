---
layout: default
title: Sample Scribbler Notebooks in JavaScript
description: 
---
Welcome to our collection of sample Scribbler Notebooks in JavaScript! These interactive notebooks showcase the capabilities of Scribbler, a powerful tool for creating and sharing interactive stories, tutorials, and presentations. From beginner-friendly tutorials to advanced projects, our sample notebooks demonstrate the versatility of Scribbler in JavaScript. Learn how to create engaging interactive experiences, visualize data, and build dynamic simulations using Scribbler's intuitive interface and JavaScript code.

Browse through our list of sample notebooks and get inspired by the creative possibilities of Scribbler. Whether you're a student, teacher, or developer, our notebooks are designed to help you learn, create, and innovate.

Click on any of the notebooks below to open it in Scribbler and start exploring. You can also modify and remix the code to create your own unique projects. Happy scribbling!
<hr>

{{ site.static_files | inspect }}
{% for file in site.static_files %}
  {{ file.path | inspect }}
{% endfor %}


{% assign files_by_subdirectory = {} %}
{% for file in site.static_files %}
  {% if file.path contains '.jsnb' %}
    {% assign files_by_subdirectory[file.path] = file.path %}
  {% endif %}
{% endfor %}
Testing {{ files_by_subdirectory | inspect }}


{% assign files_by_subdirectory = {} %}
{% for file in site.static_files %}
  {% if file.path contains '.jsnb' %}
    {% assign path_parts = file.path | split: '/' %}
    {% if path_parts.size == 1 or path_parts[0] == "" %}
      {% assign subdirectory = 'Miscellaneous' %}
    {% else %}
      {% assign subdirectory = path_parts[0] %}
    {% endif %}
    {% if files_by_subdirectory[subdirectory] %}
      {% assign files_by_subdirectory[subdirectory] = file %}
    {% else %}
      {% assign files_by_subdirectory[subdirectory] = file %}
    {% endif %}
  {% endif %}
{% endfor %}

assigned without appending {{files_by_subdirectory | inspect }}

{% for subdirectory in files_by_subdirectory %}
  <h2>{{ subdirectory }}</h2>
  <ul class="row">
    {% for file in files_by_subdirectory[subdirectory] %}
      <li class="col-md-3 col-sm-6 col-xs-12 mb-4 sampleCard">
        <a href="https://app.scribbler.live/?jsnb=https://examples.scribbler.live{{ file.path }}">{{ file.name | replace: '-', ' ' | replace: '_', ' ' | remove: '.jsnb' }}</a>
     
      </li>
    {% endfor %}
  </ul>
{% endfor %}

<hr>

<ul class="row">
  {% for file in site.static_files %}
    {% if file.path contains '.jsnb' %}
      <li class="col-md-3 col-sm-6 col-xs-12 mb-4 sampleCard">
        <a href="https://app.scribbler.live/?jsnb=https://examples.scribbler.live{{ file.path }}">{{ file.name | replace: '-', ' ' | replace: '_', ' ' | remove: '.jsnb' }}</a>
     
      </li>
    {% endif %}
  {% endfor %}
</ul>
