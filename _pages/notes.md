---
layout: page
title: Notes archives
permalink: /notes
---

<div class="post-heading">
  <h1 class="post-title">All notes 📘</h1>
</div>

{% include notes_graph.html %}

<br>

<div>
  {% assign notes = site.notes | where_exp: "item", "item.path contains 'notes'" | sort: "last_modified_at" | reverse %}
  {% for entry in notes %}
  {% unless entry.path contains "index.md" or entry.path contains "index.html" %}
  <div class="list-entry">
    <div>
        <a class="internal-link" href="{{ entry.url }}">
            {{ entry.title }}
        </a> 
        <span class="faded">({{ entry.last_modified_at | date: "%Y-%m-%d" }})</span>
    </div>
    <div>{{ entry.excerpt | strip_html | truncatewords: 30 }}</div>

  </div>
  {% endunless %}
  {% endfor %}
</div>