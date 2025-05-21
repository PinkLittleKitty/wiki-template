---
layout: page
title: All Wiki Pages
permalink: /wiki/all/
---

<div class="wiki-container">
  <aside class="wiki-sidebar">
    {% include wiki/search.html %}
    
    <div class="sidebar-nav">
      <h3>Wiki Navigation</h3>
      <ul>
        <li><a href="{{ '/wiki/' | relative_url }}">Wiki Home</a></li>
        <li><a href="{{ '/wiki/all/' | relative_url }}">All Pages</a></li>
      </ul>
      
      <h3>Wiki Pages</h3>
      <ul>
        {% assign wiki_pages = site.wiki | sort: 'title' %}
        {% for page in wiki_pages %}
          <li>
            <a href="{{ page.url | relative_url }}">{{ page.title }}</a>
          </li>
        {% endfor %}
      </ul>
    </div>
  </aside>

  <main class="wiki-content">
    <h1>All Wiki Pages</h1>
    
    <div class="wiki-alphabet-nav">
      <span>Jump to:</span>
      {% assign letters = "A,B,C,D,E,F,G,H,I,J,K,L,M,N,O,P,Q,R,S,T,U,V,W,X,Y,Z" | split: "," %}
      {% for letter in letters %}
        <a href="#{{ letter }}">{{ letter }}</a>
      {% endfor %}
    </div>
    
    {% assign wiki_pages = site.wiki | sort: 'title' %}
    {% assign grouped_pages = wiki_pages | group_by_exp: "page", "page.title | slice: 0 | upcase" %}
    {% assign sorted_groups = grouped_pages | sort: "name" %}
    
    {% for group in sorted_groups %}
      <h2 id="{{ group.name }}">{{ group.name }}</h2>
      <ul class="wiki-list">
        {% for page in group.items %}
          <li>
            <a href="{{ page.url | relative_url }}">{{ page.title }}</a>
            {% if page.date %}
              <span class="date">- {{ page.date | date: "%B %d, %Y" }}</span>
            {% endif %}
          </li>
        {% endfor %}
      </ul>
    {% endfor %}
  </main>
</div>

<style>
.wiki-alphabet-nav {
  margin: 1rem 0;
  padding: 0.5rem;
  background-color: #f8f9fa;
  border: 1px solid #a2a9b1;
  border-radius: 3px;
}

.wiki-alphabet-nav a {
  display: inline-block;
  padding: 0.2rem 0.4rem;
  margin: 0.1rem;
  text-decoration: none;
}

.wiki-alphabet-nav a:hover {
  background-color: #eaecf0;
  border-radius: 3px;
}
</style>