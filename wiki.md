---
layout: page
title: Wiki Home
permalink: /wiki/
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
    <h1>Wiki Home</h1>
    
    <div class="wiki-welcome">
      <p>Welcome to our project wiki. Here you'll find documentation, guides, and information about our project.</p>
    </div>
    
    <div class="wiki-featured">
      <h2>Featured Articles</h2>
      <div class="featured-grid">
        {% assign featured_pages = site.wiki | where: "featured", true | sort: 'title' %}
        {% if featured_pages.size > 0 %}
          {% for page in featured_pages limit:3 %}
            <div class="featured-item">
              <h3><a href="{{ page.url | relative_url }}">{{ page.title }}</a></h3>
              {% if page.excerpt %}
                <p>{{ page.excerpt }}</p>
              {% endif %}
            </div>
          {% endfor %}
        {% else %}
          <div class="featured-item">
            <h3><a href="{{ site.wiki.first.url | relative_url }}">{{ site.wiki.first.title }}</a></h3>
            <p>Check out our first wiki page to get started.</p>
          </div>
        {% endif %}
      </div>
    </div>
    
    <h2>Recent Updates</h2>
    <ul class="wiki-list">
      {% assign recent_pages = site.wiki | sort: 'date' | reverse %}
      {% for page in recent_pages limit:5 %}
        <li>
          <a href="{{ page.url | relative_url }}">{{ page.title }}</a>
          <span class="date">- {{ page.date | date: "%B %d, %Y" }}</span>
        </li>
      {% endfor %}
    </ul>
    
    <h2>Categories</h2>
    <div class="wiki-categories-list">
      {% assign all_categories = "" | split: "" %}
      {% for page in site.wiki %}
        {% if page.categories %}
          {% assign all_categories = all_categories | concat: page.categories %}
        {% endif %}
      {% endfor %}
      
      {% assign unique_categories = all_categories | uniq | sort %}
      {% for category in unique_categories %}
        <a href="{{ '/wiki/category/' | append: category | relative_url }}" class="category-tag">{{ category }}</a>
      {% endfor %}
    </div>
  </main>
</div>

<style>
.wiki-welcome {
  background-color: #f8f9fa;
  border: 1px solid #a2a9b1;
  border-radius: 3px;
  padding: 1rem;
  margin-bottom: 1.5rem;
}

.featured-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1rem;
  margin: 1rem 0;
}

.featured-item {
  background-color: #f8f9fa;
  border: 1px solid #a2a9b1;
  border-radius: 3px;
  padding: 1rem;
}

.featured-item h3 {
  margin-top: 0;
  border-bottom: none;
}

.wiki-categories-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin: 1rem 0;
}

.category-tag {
  background-color: #f8f9fa;
  border: 1px solid #a2a9b1;
  border-radius: 3px;
  padding: 0.3rem 0.6rem;
  text-decoration: none;
  color: #0645ad;
}

.category-tag:hover {
  background-color: #eaecf0;
}
</style>