---
title: "People"
layout: collection
permalink: /people/
collection: people
entries_layout: grid
classes: wide
---



{% assign categories = "Faculty,Postdoc,PhD Student" | split: "," %}
{% for category in categories %}
  <h2>{{ category }}</h2>
  <div class="people-grid">
    {% assign grouped_people = site.people | where: "title", category | sort: "last_name" %}
    {% for person in grouped_people %}
      <div class="person-card">
        <img src="{{ person.header.teaser }}" alt="{{ person.name }}">
        <h3>{{ person.name }}</h3>
        <p>{{ person.position }}</p>
      </div>
    {% endfor %}
  </div>
{% endfor %}