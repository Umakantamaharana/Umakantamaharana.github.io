---
layout: default
permalink: /blog/
title: Blog
nav: true
nav_order: 4
pagination:
  enabled: true
  collection: posts
  permalink: /page/:num/
  per_page: 10
  sort_field: date
  sort_reverse: true
  trail:
    before: 1
    after: 3
---

<div class="post">

  <!-- Editorial Blog Hero Header -->
  <div class="header-bar blog-hero">
    <div class="blog-hero-badge">
      <i class="fa-solid fa-feather-pointed"></i> Research Notes & Insights
    </div>
    <h1 class="blog-hero-title">Writings & Explorations</h1>
    <p class="blog-hero-subtitle">
      Deep-dives into AI access control, adaptive multi-agent learning, and healthcare reasoning. Breaking down complex research into accessible ideas.
    </p>
  </div>

  <!-- Search & Topic Filter Toolbar -->
  <div class="blog-toolbar">
    <div class="blog-search-wrap">
      <i class="fa-solid fa-magnifying-glass blog-search-icon"></i>
      <input type="text" id="blog-search-input" placeholder="Search articles by title, topic, or keyword..." autocomplete="off">
    </div>

    <div class="blog-topic-tags" id="blog-topic-tags">
      <button class="topic-filter-btn active" data-topic="all">All Topics</button>
      {% for tag in site.display_tags %}
        <button class="topic-filter-btn" data-topic="{{ tag | slugify }}">#{{ tag }}</button>
      {% endfor %}
    </div>

  </div>

  <!-- Featured Research Section -->
{% assign featured_posts = site.posts | where: "featured", true %}
{% if featured_posts.size > 0 %}
    {% for post in featured_posts limit: 1 %}
      {% if post.external_source == blank %}
        {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
      {% else %}
        {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %}
      {% endif %}
      {% assign year = post.date | date: "%Y" %}

      <div class="blog-featured-card">
        <div class="featured-badge-pill">
          <i class="fa-solid fa-star"></i> Featured Research
        </div>
        <h2 class="featured-title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h2>
        <p class="featured-desc">{{ post.description }}</p>
        <div class="featured-footer">
          <div class="featured-meta">
            <span><i class="fa-regular fa-calendar"></i> {{ post.date | date: '%B %d, %Y' }}</span>
            <span>&bull;</span>
            <span><i class="fa-regular fa-clock"></i> {{ read_time }} min read</span>
          </div>
          <a class="featured-cta" href="{{ post.url | relative_url }}">
            Read Featured Story <i class="fa-solid fa-arrow-right"></i>
          </a>
        </div>
      </div>
    {% endfor %}
{% endif %}

  <!-- All Articles Cards Grid -->
{% if page.pagination.enabled %}
    {% assign postlist = paginator.posts %}
{% else %}
    {% assign postlist = site.posts %}
{% endif %}

  <div class="blog-cards-grid" id="blog-cards-grid">
    {% for post in postlist %}
      {% if post.external_source == blank %}
        {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
      {% else %}
        {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %}
      {% endif %}
      {% assign year = post.date | date: "%Y" %}

      <article class="blog-card" data-tags="{{ post.tags | join: ' ' | downcase }}" data-search="{{ post.title | downcase }} {{ post.description | downcase }} {{ post.tags | join: ' ' | downcase }}">
        <div class="blog-card-meta">
          <span><i class="fa-regular fa-calendar"></i> {{ post.date | date: '%B %d, %Y' }}</span>
          <span class="meta-dot">&bull;</span>
          <span><i class="fa-regular fa-clock"></i> {{ read_time }} min read</span>
        </div>

        <h3 class="blog-card-title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h3>

        <p class="blog-card-desc">{{ post.description }}</p>

        <div class="blog-card-footer">
          <div class="blog-card-tags">
            {% for tag in post.tags limit: 4 %}
              <a href="{{ tag | slugify | prepend: '/blog/tag/' | prepend: site.baseurl }}" class="blog-tag-chip">#{{ tag }}</a>
            {% endfor %}
          </div>
          <a class="blog-read-link" href="{{ post.url | relative_url }}">
            Read Article <i class="fa-solid fa-arrow-right"></i>
          </a>
        </div>
      </article>
    {% endfor %}

  </div>

  <!-- Empty Search Result Notice -->
  <div id="blog-no-results" style="display: none;">
    <i class="fa-solid fa-magnifying-glass"></i>
    <p>No articles found matching your query.</p>
  </div>

{% if page.pagination.enabled %}
    {% include pagination.liquid %}
{% endif %}

</div>

<!-- Client-side Interactive Search & Tag Filtering -->
<script>
  document.addEventListener('DOMContentLoaded', function () {
    const searchInput = document.getElementById('blog-search-input');
    const topicBtns = document.querySelectorAll('.topic-filter-btn');
    const cards = document.querySelectorAll('.blog-card');
    const noResults = document.getElementById('blog-no-results');
    let activeTopic = 'all';

    function filterPosts() {
      const query = (searchInput ? searchInput.value.toLowerCase().trim() : '');
      let visibleCount = 0;

      cards.forEach(card => {
        const cardSearch = card.getAttribute('data-search') || '';
        const cardTags = card.getAttribute('data-tags') || '';

        const matchesQuery = !query || cardSearch.includes(query);
        const matchesTopic = (activeTopic === 'all') || cardTags.includes(activeTopic);

        if (matchesQuery && matchesTopic) {
          card.style.display = 'flex';
          visibleCount++;
        } else {
          card.style.display = 'none';
        }
      });

      if (noResults) {
        noResults.style.display = (visibleCount === 0) ? 'block' : 'none';
      }
    }

    if (searchInput) {
      searchInput.addEventListener('input', filterPosts);
    }

    topicBtns.forEach(btn => {
      btn.addEventListener('click', function () {
        topicBtns.forEach(b => b.classList.remove('active'));
        this.classList.add('active');
        activeTopic = this.getAttribute('data-topic');
        filterPosts();
      });
    });
  });
</script>
