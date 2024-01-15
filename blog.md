---
title: /blog
layout: home
permalink: /blog
---


<p style="display:inline;">All the information provided on this blog is for <div style="color:red;display:inline;">educational purposes only</div>. The author is no way responsible for any misuse of the information.</p>

<!-- Html Elements for Search -->
<div id="search-container" style="display:block;margin-left:auto;margin-right:auto;color:red;">
<input type="text" id="search-input" placeholder="search..." style="color:red;">
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

