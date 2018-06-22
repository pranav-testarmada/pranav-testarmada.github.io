---
title: Setup Android app test on SauceLabs
layout: training
permalink: documentation/Functional Testing/Native Android/JAVASCRIPT/Training Guide/Setup/Setup Android app test on SauceLabs
level1: Functional Testing
level2: Native Android
level3: JAVASCRIPT
level4: Training Guide
course: Setup
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
<img class="training-doc-link-left__img" src="/images/training/checked.png" srcset="/images/training/checked%402x.png 2x, /images/training/checked%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-completed" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-completed" href="./Setup Android app test on local machine">Setup Android app test on local machine</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Setup Android app test on SauceLabs">Setup Android app test on SauceLabs</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
<a href="./Setup Android app test on local machine"><img src="/images/training/btn-left.png" srcset="/images/training/btn-left%402x.png 2x, /images/training/btn-left%403x.png 3x" /></a>
</div>
<div class="training-content markdown">
<h3>Run Android app test on SauceLabs</h3>
<ul>
<li>Open terminal: (or add them into .bash_profile)</li>
</ul>
<pre><code class="language-bash">$ export SAUCE_USERNAME=${USERNAME}
$ export SAUCE_ACCESS_KEY=${ACCESSKEY}
</code></pre>
<ul>
<li>Upload ./app/AUT.apk to SauceLabs via following curl</li>
</ul>
<pre><code class="language-bash">$ curl -u ${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY} -X POST &quot;http://saucelabs.com/rest/v1/storage/${SAUCE_USERNAME}/AUT.apk?overwrite=true&quot; -H &quot;Content-Type: application/octet-stream&quot; --data-binary @./app/AUT.apk
</code></pre>
<ul>
<li>Add following content under <code>profiles</code> in <code>magellan.json</code></li>
</ul>
<pre><code class="language-js">&quot;appium-android-app&quot;: [{
    &quot;browser&quot;: &quot;Android_GoogleAPI_Emulator_Android_7_1_Android&quot;,
    &quot;orientation&quot;: &quot;portrait&quot;,
    &quot;appium&quot;: {
      &quot;app&quot;: &quot;sauce-storage:AUT.apk&quot;,
      &quot;platformName&quot;: &quot;Android&quot;,
      &quot;appiumVersion&quot;: &quot;1.7.2&quot;,
      &quot;fullReset&quot;: &quot;true&quot;,
      &quot;noReset&quot;: &quot;false&quot;
    }
  }
</code></pre>
<ul>
<li>Run the Android sample app test on SauceLabs</li>
</ul>
<pre><code class="language-bash">./node_modules/.bin/magellan --nightwatch_config conf/nightwatch.json --profile appium-android-app --test tests/app.test.js --max_test_attempts=1
</code></pre>
<ul>
<li>You can view your tests running at: https://saucelabs.com/beta/dashboard/tests. You should see an Android emulator open, your app open, close and simulator</li>
</ul>
</div>
<div class="training-doc-nav-btn">
</div>
