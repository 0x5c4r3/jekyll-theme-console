---
title: doc_list
layout: default
permalink: "/docs/"
---
{% assign posts = site.posts | where:"type", "docs" %}

<p style="display:inline;">Search the <div style="color:red;display:inline;">DOCS</div>...</p>
&nbsp;
<!-- Html Elements for Search -->
<div id="search-container">
<input type="text" id="search-input" placeholder="search...">
<ul id="results-container"></ul>
</div>

<!-- Script pointing to search-script.js -->
<script src="/js/search-script.js" type="text/javascript"></script>

<!-- Configuration -->
<script>
SimpleJekyllSearch({
  searchInput: document.getElementById('search-input'),
  resultsContainer: document.getElementById('results-container'),
  json: '/search.json'
})
</script>
&nbsp;
