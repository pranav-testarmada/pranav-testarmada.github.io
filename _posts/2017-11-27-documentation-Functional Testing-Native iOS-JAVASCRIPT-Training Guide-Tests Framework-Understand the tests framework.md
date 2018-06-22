---
title: Understand the tests framework
layout: training
permalink: documentation/Functional Testing/Native iOS/JAVASCRIPT/Training Guide/Tests Framework/Understand the tests framework
level1: Functional Testing
level2: Native iOS
level3: JAVASCRIPT
level4: Training Guide
course: Tests Framework
---
<div class="sidebar">
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Understand the tests framework">Understand the tests framework</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
</div>
<div class="training-content markdown">
<h3>Tests framework structure</h3>
<h4>Where to find mobile commands</h4>
<ol>
<li>When look at commands in page files, e.g. <strong>setMobileElValue()</strong> may look new to you. Those mobile commands are defined in <strong><em>./node_modules/testarmada-nightwatch-extra/lib/commands/mobile</em></strong>.</li>
<li>Assertions, e.g. <strong>mobileElAttrContains()</strong>, are defined in <strong><em>./node_modules/testarmada-nightwatch-extra/lib/assertions/mobile</em></strong>.</li>
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
