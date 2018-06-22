---
title: Built-in browser testing
layout: training
permalink: documentation/Functional Testing/rWeb/JAVASCRIPT/Training Guide/rWeb Testing/Built-in browser testing
level1: Functional Testing
level2: rWeb
level3: JAVASCRIPT
level4: Training Guide
course: rWeb Testing
---
<div class="sidebar">
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/checked.png" srcset="/images/training/checked%402x.png 2x, /images/training/checked%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-completed" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-completed" href="./Prerequisites">Prerequisites</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-pending" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Built-in browser testing">Built-in browser testing</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/unread.png" srcset="/images/training/unread%402x.png 2x, /images/training/unread%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-pending" href="./Remote browser testing">Remote browser testing</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
<a href="./Prerequisites"><img src="/images/training/btn-left.png" srcset="/images/training/btn-left%402x.png 2x, /images/training/btn-left%403x.png 3x" /></a>
</div>
<div class="training-content markdown">
<h3>Built-in browser testing</h3>
<ul>
<li>The sample project has some pre-configured browsers that you can use via <code>--local_browser</code> command.</li>
<li>For example, the following command triggers your test in the local Chrome.</li>
</ul>
<pre><code class="language-bash">DPRO=local ./node_modules/.bin/magellan  --local_browser chrome  --test tests/demo-simple.js --serial --max_test_attempts 1
</code></pre>
<ul>
<li>Full list of built in browser can be found at <strong><em>test_settings</em></strong> part in <strong>conf/nightwatch.json</strong> file</li>
<li>To run test with a <strong>new browser</strong>, you can just create a new entry in <strong>test_settings</strong> part</li>
</ul>
</div>
<div class="training-doc-nav-btn">
<a href="./Remote browser testing"><img src="/images/training/btn-right.png" srcset="/images/training/btn-right%402x.png 2x, /images/training/btn-right%403x.png 3x" /></a>
</div>
