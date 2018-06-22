---
title: Tests framework structure
layout: training
permalink: documentation/Functional Testing/Native Android/JAVASCRIPT/Training Guide/Tests Framework/Tests framework structure
level1: Functional Testing
level2: Native Android
level3: JAVASCRIPT
level4: Training Guide
course: Tests Framework
---
<div class="sidebar">
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/checked.png" srcset="/images/training/checked%402x.png 2x, /images/training/checked%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-completed" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-completed" href="./Execution commands">Execution commands</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Tests framework structure">Tests framework structure</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
<a href="./Execution commands"><img src="/images/training/btn-left.png" srcset="/images/training/btn-left%402x.png 2x, /images/training/btn-left%403x.png 3x" /></a>
</div>
<div class="training-content markdown">
<h2>Tests framework structure</h2>
<h3>Where to find mobile commands and assertions</h3>
<ol>
<li>When look at commands in page files, e.g. <strong>clickMobileEl()</strong> may look new to you. Those mobile commands are defined in <strong><em>./node_modules/testarmada-nightwatch-extra/lib/commands/mobile</em></strong></li>
<li>Assertions, e.g. <strong>mobileElAttrContains()</strong>, are defined in <strong><em>./node_modules/testarmada-nightwatch-extra/lib/assertions/mobile</em></strong></li>
<li>To use those mobile commands and assertions, need to add the following lines in nightwatch.json file:</li>
</ol>
<pre><code class="language-bash">  &quot;custom_commands_path&quot;: [
    &quot;./node_modules/testarmada-nightwatch-extra/lib/commands/mobile&quot;
  ],
  &quot;custom_assertions_path&quot;: [
    &quot;./node_modules/testarmada-nightwatch-extra/lib/assertions/mobile&quot;
  ],
</code></pre>
<ol start="4">
<li>You can also add your customized commands into folder <strong>./lib/custom_commands</strong>, to increase code reusability. And please remember to add the path to nightwatch.json file, e.g.</li>
</ol>
<pre><code class="language-bash">  &quot;custom_commands_path&quot;: [
    &quot;./node_modules/testarmada-nightwatch-extra/lib/commands/mobile&quot;,
    &quot;./lib/custom_commands&quot;
  ],
</code></pre>
</div>
<div class="training-doc-nav-btn">
</div>
