---
title: Execution commands
layout: training
permalink: documentation/Functional Testing/Native Android/JAVASCRIPT/Training Guide/Tests Framework/Execution commands
level1: Functional Testing
level2: Native Android
level3: JAVASCRIPT
level4: Training Guide
course: Tests Framework
---
<div class="sidebar">
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-pending" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Execution commands">Execution commands</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/unread.png" srcset="/images/training/unread%402x.png 2x, /images/training/unread%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-pending" href="./Tests framework structure">Tests framework structure</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
</div>
<div class="training-content markdown">
<h2>Execution commands</h2>
<p>After getting your tests up and running, you probably have tons of questions regarding how this work, let’s start with the command that we are using to get the tests running in local, which is:</p>
<pre><code class="language-bash">./node_modules/.bin/magellan --config magellan.json --local_browser appiumandroidapp --test tests/app.test.js --serial 
</code></pre>
<ul>
<li>Commands parameters <strong><em>--test</em></strong> , <strong><em>--serial</em></strong>, <strong><em>--config</em></strong>, etc are all magellan arguments. To find all magellan command line arguments and the usages:</li>
</ul>
<pre><code class="language-bash">./node_modules/.bin/magellan --help
</code></pre>
<ul>
<li><p>Magellan is part of the functional JS TDK, and it is designed for running tests in massive scale.</p>
<p>Following is an example that telling magellan to run tests with 30 workers, 5 retry attempts per failed test</p></li>
</ul>
<pre><code class="language-bash">./node_modules/.bin/magellan --max_workers 30 --max_test_attempts 5
</code></pre>
<ul>
<li><p><strong>--local_browser appiumandroidapp</strong> tells tests to use <a href="https://github.com/TestArmada/magellan-local-executor">testarmada-magellan-local-executor</a> . It loads Desired Capabilities from nightwatch.json.</p>
<p>For our sample here, it will load <strong><em>appiumandroidapp</em></strong> desired capability from nightwatch.json file:</p>
<p>To know more about Desired Capability, please read the next training section - Android Automation.</p></li>
<li><p><strong>Executor</strong>  - acts as a middle layer between magellan and test framework to drive test run (via framework) based on a specific need (differentiated by executing environments).</p>
<p>For local emulator test, you need to enable <strong><em>testarmada-magellan-local-executor</em></strong> in the magellan.json file.</p>
<p>For remote emulator test, e.g. on SauceLabs, need to enable <strong><em>testarmada-magellan-saucelabs-executor</em></strong> in the magellan.json file.</p></li>
</ul>
</div>
<div class="training-doc-nav-btn">
<a href="./Tests framework structure"><img src="/images/training/btn-right.png" srcset="/images/training/btn-right%402x.png 2x, /images/training/btn-right%403x.png 3x" /></a>
</div>
