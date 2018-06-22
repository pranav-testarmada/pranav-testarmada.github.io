---
title: Setup iOS app test on Sauce Labs
layout: training
permalink: documentation/Functional Testing/Native iOS/JAVASCRIPT/Training Guide/Setup/Setup iOS app test on Sauce Labs
level1: Functional Testing
level2: Native iOS
level3: JAVASCRIPT
level4: Training Guide
course: Setup
---
<div class="sidebar">
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/checked.png" srcset="/images/training/checked%402x.png 2x, /images/training/checked%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-completed" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-completed" href="./Setup iOS app test on local machine">Setup iOS app test on local machine</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Setup iOS app test on Sauce Labs">Setup iOS app test on Sauce Labs</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
<a href="./Setup iOS app test on local machine"><img src="/images/training/btn-left.png" srcset="/images/training/btn-left%402x.png 2x, /images/training/btn-left%403x.png 3x" /></a>
</div>
<div class="training-content markdown">
<h3>Setup iOS app sample test on Sauce Labs</h3>
<ul>
<li>Open terminal: (or add them into .bash_profile)</li>
</ul>
<pre><code class="language-bash">$ export SAUCE_USERNAME=${USERNAME}
$ export SAUCE_ACCESS_KEY=${ACCESSKEY}
</code></pre>
<ul>
<li><p>Zip <code>./app/AUT.app</code> to <code>./app/AUT.zip</code></p></li>
<li><p>Upload the testing iOS app to Sauce Labs</p></li>
</ul>
<pre><code class="language-bash"># Upload Walmart app to SauceLabs, and name it: Walmart_app.zip
$ curl -u ${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY} -X POST &quot;http://saucelabs.com/rest/v1/storage/${SAUCE_USERNAME}/AUT.zip?overwrite=true&quot; -H &quot;Content-Type: application/octet-stream&quot; --data-binary @./app/
AUT.zip
</code></pre>
<ul>
<li>Add following content under <code>profiles</code> in <code>magellan.json</code></li>
</ul>
<pre><code class="language-js">&quot;appium-ios-app&quot;: [
    {
      &quot;browser&quot;: &quot;iphone_10_3_iOS_iPhone_7_Simulator&quot;,
      &quot;orientation&quot;: &quot;portrait&quot;,
      &quot;appium&quot;: {
        &quot;app&quot;: &quot;sauce-storage:AUT.zip&quot;,
        &quot;appiumVersion&quot;: &quot;1.6.5&quot;,
        &quot;automationName&quot;: &quot;XCUITest&quot;,
        &quot;sendKeyStrategy&quot;: &quot;setValue&quot;,
        &quot;waitForAppScript&quot;: &quot;true&quot;,
        &quot;locationServicesAuthorized&quot;: &quot;false&quot;,
        &quot;locationServicesEnabled&quot;: &quot;true&quot;
      }
    }
  ]
</code></pre>
<ul>
<li>To run tests on Saucelabs, use command:</li>
</ul>
<pre><code class="language-bash">./node_modules/.bin/magellan --config magellan.json --profile appium-ios-app  --test tests/app.test.js --serial --max_test_attempts=1
</code></pre>
<ul>
<li>You can view your tests running at: https://saucelabs.com/beta/dashboard/tests. You should see an iOS simulator open, your app open, close and simulator close.</li>
</ul>
</div>
<div class="training-doc-nav-btn">
</div>
