---
title: /
layout: home
permalink: /
---
<script>
  var TxtType = function(el, toRotate, period) {
        this.toRotate = toRotate;
        this.el = el;
        this.loopNum = 0;
        this.period = parseInt(period, 10) || 2000;
        this.txt = '';
        this.tick();
        this.isDeleting = false;
    };
</script>

<style>
  body {
  background-color:#ce3635;
  text-align: center;
  color:#fff;
  padding-top:10em;
}
</style>

<h1>
  <a href="" class="typewrite" data-period="2000" data-type='[ "Welcome to the shadow, darling...", "I am Scarecrow, pleasure..", "Wanna hack?", "Hey honey, read the posts below" ]'>
    <span class="wrap"></span>
  </a>
</h1>

