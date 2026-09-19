---
layout: page
permalink: /publications/
title: Publications
description: Peer-reviewed papers and preprints in LLM security, organizational access control, adaptive multi-agent learning, and healthcare reasoning.
nav: true
nav_order: 1
---

<div class="publications">

  <!-- Editorial Hero Header -->
  <div class="header-bar pub-hero">
    <div class="pub-hero-badge">
      <i class="fa-solid fa-book-bookmark"></i> Peer-Reviewed & Preprints
    </div>
    <h1 class="pub-hero-title">Publications</h1>
    <p class="pub-hero-subtitle">
      Research contributions spanning enterprise LLM access control, adaptive pedagogical multi-agent systems, and clinical reasoning faithfulness.
    </p>

    <!-- Quick Highlights Pill Bar -->
    <div class="pub-highlights-bar">
      <span class="pub-metric-pill">
        <i class="fa-solid fa-award"></i> 2 Papers Accepted at EMNLP 2025
      </span>
      <span class="pub-metric-pill">
        <i class="fa-solid fa-file-medical"></i> 1 Clinical AI Study
      </span>
      <a href="https://scholar.google.com/citations?user=Gzr-FpUAAAAJ&hl" target="_blank" rel="noopener noreferrer" class="pub-metric-pill scholar-link">
        <i class="ai ai-google-scholar"></i> Google Scholar Profile <i class="fa-solid fa-arrow-up-right-from-square fa-xs ml-1"></i>
      </a>
    </div>

  </div>

  <!-- Search & Filter Toolbar -->
  <div class="pub-toolbar">
    <div class="pub-search-wrap">
      <i class="fa-solid fa-magnifying-glass pub-search-icon"></i>
      <input type="text" id="pub-search-input" placeholder="Search publications by title, co-author, conference, or keyword..." autocomplete="off">
    </div>

    <div class="pub-filter-pills" id="pub-filter-pills">
      <button class="pub-filter-btn active" data-filter="all">All Papers</button>
      <button class="pub-filter-btn" data-filter="emnlp">EMNLP 2025</button>
      <button class="pub-filter-btn" data-filter="preprint">Preprints</button>
      <button class="pub-filter-btn" data-filter="access-control">Access Control / RBAC</button>
      <button class="pub-filter-btn" data-filter="pedagogical">Multi-Agent</button>
      <button class="pub-filter-btn" data-filter="medical">Healthcare</button>
    </div>

  </div>

  <!-- Publications Bibliography in Modern Card Layout -->
  <div class="publications-card" id="pub-cards-container">
    {% bibliography %}
  </div>

  <!-- Empty Search Result Notice -->
  <div id="pub-no-results" style="display: none;">
    <i class="fa-solid fa-magnifying-glass"></i>
    <p>No publications found matching your query.</p>
  </div>

</div>

<!-- Client-side Interactive Search & Venue Filtering -->
<script>
  document.addEventListener('DOMContentLoaded', function () {
    const searchInput = document.getElementById('pub-search-input');
    const filterBtns = document.querySelectorAll('.pub-filter-btn');
    const pubItems = document.querySelectorAll('#pub-cards-container ol.bibliography > li');
    const noResults = document.getElementById('pub-no-results');
    let activeFilter = 'all';

    function filterPubs() {
      const query = (searchInput ? searchInput.value.toLowerCase().trim() : '');
      let visibleCount = 0;

      pubItems.forEach(item => {
        const text = item.textContent.toLowerCase();
        const matchesQuery = !query || text.includes(query);
        const matchesFilter = (activeFilter === 'all') || text.includes(activeFilter);

        if (matchesQuery && matchesFilter) {
          item.style.display = '';
          visibleCount++;
        } else {
          item.style.display = 'none';
        }
      });

      // Hide/show year headings if all child items in that group are hidden
      document.querySelectorAll('#pub-cards-container h2.bibliography').forEach(h2 => {
        const nextOl = h2.nextElementSibling;
        if (nextOl && nextOl.tagName === 'OL') {
          const visibleChildren = Array.from(nextOl.children).filter(li => li.style.display !== 'none');
          h2.style.display = (visibleChildren.length === 0) ? 'none' : '';
        }
      });

      if (noResults) {
        noResults.style.display = (visibleCount === 0) ? 'block' : 'none';
      }
    }

    if (searchInput) {
      searchInput.addEventListener('input', filterPubs);
    }

    filterBtns.forEach(btn => {
      btn.addEventListener('click', function () {
        filterBtns.forEach(b => b.classList.remove('active'));
        this.classList.add('active');
        activeFilter = this.getAttribute('data-filter');
        filterPubs();
      });
    });
  });
</script>
