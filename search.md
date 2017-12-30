---
layout: default
title: "Search"
---

<div class="post">
  <!-- Html Elements for Search -->
  <div id="search-container">
    <h2 class="pageTitle">Search</h2>
    <input
      type="text"
      id="search-input"
      class="full-width"
      placeholder="Type the article title ..."
    >
    <div class="search-result">
      <ul id="results-container"></ul>
    </div>
  </div>
</div>

<!-- Script pointing to search-script.js -->
<script src="/assets/js/search-script.min.js" type="text/javascript"></script>

<!-- Configuration -->
<script>
  SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    json: '/search.json'
  })
</script>
