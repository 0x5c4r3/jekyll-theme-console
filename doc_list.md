---
title: /docs
layout: default
permalink: "/docs/"
---
<style>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 100%;
}
</style>

<p style="display:inline;">The <div style="color:red;display:inline;">DOCS</div> are a list of notes, researches and relevant knowledge that I personally worked on that might help with engagements of various types.</p>
&nbsp;
<!-- Html Elements for Search -->
<div id="search-container">
<input type="text" id="search-input" placeholder="search...">
<ul id="results-container"></ul>
</div>

<!-- Script pointing to search-script.js -->
<script src="/js/search-script.js" type="text/javascript"></script>

<!-- Configuration -->
<div class="center">
  <script>
SimpleJekyllSearch({
  searchInput: document.getElementById('search-input'),
  resultsContainer: document.getElementById('results-container'),
  json: '/search.json'
})
  </script>
</div>
&nbsp;
