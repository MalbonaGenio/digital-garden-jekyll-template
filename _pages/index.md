---
layout: page
title: Home
id: home
permalink: /
---

# Welcome! 🌱

<p style="padding: 3em 1em; background: #f5f7ff; border-radius: 4px;">
  To get started you can check <span style="font-weight: bold"><a class="internal-link" href="/notes">Notes</a></span> to find anything you want to read about.
</p>

This digital garden is my way to share notes and thoughts. 

[[Notes]] are mainly extracted from the books and articles I read while [[posts]] are my own. Usually based on the notes you will find here.

<div class="grid-element">
  <h2>Last notes</h2>
  {% assign notes_limit = 5 %}
  {% for notes in site.notes limit: notes_limit %}
  <div class="list-entry">
    <div>
      <a class="internal-link" href="{{ notes.url }}">
        {{ notes.title }}
      </a> 
      <span class="faded">({{ notes.date | date: "%Y-%m-%d" }})</span>
    </div>
    <div>{{ notes.excerpt | strip_html | truncatewords: 30 }}</div>
  </div>
  {% endfor %}
  <p>
    <a class="internal-link" href="/notes">I wrote {{ site.notes.size | minus: notes_limit }} more notes</a>.
  </p>
</div>


<style>
  .wrapper {
    max-width: 46em;
  }
</style>
