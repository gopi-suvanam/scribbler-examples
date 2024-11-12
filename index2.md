---
layout: default
title: Sample Scribbler Notebooks in JavaScript
description: 
---
# List of Sample Scribbler Notebooks in JavaScript


## Explore the Power of Scribbler Notebooks in JavaScript

Welcome to our collection of sample Scribbler Notebooks in JavaScript! These interactive notebooks showcase the capabilities of Scribbler, a powerful tool for creating and sharing interactive stories, tutorials, and presentations.

## Discover the Possibilities

From beginner-friendly tutorials to advanced projects, our sample notebooks demonstrate the versatility of Scribbler in JavaScript. Learn how to create engaging interactive experiences, visualize data, and build dynamic simulations using Scribbler's intuitive interface and JavaScript code.

## Get Inspired

Browse through our list of sample notebooks and get inspired by the creative possibilities of Scribbler. Whether you're a student, teacher, or developer, our notebooks are designed to help you learn, create, and innovate.

## Start Exploring Today!

Click on any of the notebooks below to open it in Scribbler and start exploring. You can also modify and remix the code to create your own unique projects. Happy scribbling!


<ul class="row">
  {% for file in site.static_files %}
    {% if file.path contains '.jsnb' %}
      <li class="col-md-3 col-sm-4 mb-4 card">
        <a href="https://app.scribbler.live/?jsnb=https://examples.scribbler.live{{ file.path }}">{{ file.name | replace: '-', ' ' | replace: '_', ' ' | remove: '.jsnb' }}</a>
      </li>
    {% endif %}
  {% endfor %}
</ul>