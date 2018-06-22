---
title: Setup iOS app test on local machine
layout: training
permalink: documentation/Functional Testing/Native iOS/JAVASCRIPT/Training Guide/Setup/Setup iOS app test on local machine
level1: Functional Testing
level2: Native iOS
level3: JAVASCRIPT
level4: Training Guide
course: Setup
---
<div class="sidebar">
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-pending" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Setup iOS app test on local machine">Setup iOS app test on local machine</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/unread.png" srcset="/images/training/unread%402x.png 2x, /images/training/unread%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-pending" href="./Setup iOS app test on Sauce Labs">Setup iOS app test on Sauce Labs</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
</div>
<div class="training-content markdown">
<p>New to native iOS app testing? No worry, you don’t need to know much to set it up. Let's get your first native iOS app test up and running in a couple of minutes.</p>
<h3>Setup iOS app test on local machine</h3>
<h4>Prerequisites:</h4>
<ul>
<li>Install <a href="https://developer.apple.com/download/">Xcode 9.2</a></li>
<li>Install Node.js &gt;= v4.x.x</li>
<li>Install <a href="http://nodejs.org/">npm</a>. Check that you have at least <strong>npm</strong> version 3 or above (required by <em>appium@1.7.x</em>):</li>
</ul>
<pre><code class="language-bash">$ npm --version
# If not, install npm3
$ npm install -g npm@3
</code></pre>
<ul>
<li>Please map <strong>dev.walmart.com</strong> to <strong>127.0.0.1</strong> in your host file</li>
</ul>
<h4>Setup Steps:</h4>
<ul>
<li>Get the sample code and install the node package dependencies:</li>
</ul>
<pre><code class="language-bash"># Create a workspace and get the smaple code
$ git clone git@github.com:TestArmada/boilerplate-nightwatch.git
$ cd boilerplate-nightwatch
$ npm install
$ npm install appium@1.7.2
$ npm install wd
</code></pre>
<ul>
<li>Verify all the required items are setup properly by running appium-doctor:</li>
</ul>
<pre><code class="language-bash"># install appium-doctor (may require sudo)
$ npm install appium-doctor -g
# check that all iOS dependencies are set up correctly
$ appium-doctor --ios
</code></pre>
<ul>
<li>Get a developer build of the application you want to test, put it under <code>./app</code> folder, for example rename .app and put it as <code>./app/AUT.app</code>.</li>
<li>Please make sure you have iPhone 8, iOS 11.2 simulator before execute the sample test.</li>
<li>Put following entry in your <code>nightwatch.json</code></li>
</ul>
<pre><code class="language-javascript">&quot;appiumiosapp&quot;: {
    &quot;skip_testcases_on_fail&quot;: true,
    &quot;desiredCapabilities&quot;: {
      &quot;app&quot;: &quot;./app/AUT.app&quot;,
      &quot;appiumVersion&quot;: &quot;1.7.2&quot;,
      &quot;automationName&quot;: &quot;XCUITest&quot;,
      &quot;platformName&quot;: &quot;iOS&quot;,
      &quot;platformVersion&quot;: &quot;11.2&quot;,
      &quot;deviceName&quot;: &quot;iPhone 8&quot;,
      &quot;waitForAppScript&quot;: &quot;true&quot;,
      &quot;browserName&quot;: &quot;&quot;
    },
    &quot;selenium&quot;: {
      &quot;start_process&quot;: false
    },
    &quot;appium&quot;: {
      &quot;start_process&quot;: true,
      &quot;fullReset&quot;: true
    }
  }
</code></pre>
<ul>
<li>If you would like to try out some different simulators, please modify the <strong><em>appiumiosapp</em></strong> part in <strong>.conf/nightwatch.json</strong> file.</li>
<li>Add a test <code>app.test.js</code> under <code>./tests</code> folder, it can be as simple as following</li>
</ul>
<pre><code class="language-javascript">var Test = require(&quot;testarmada-nightwatch-extra/lib/base-test-class&quot;);

module.exports = new Test({
  
  &quot;Load demo page&quot;: function (client) {
    console.log('yeah');
  }
});
</code></pre>
<ul>
<li>Try the sample test:</li>
</ul>
<pre><code class="language-bash">./node_modules/.bin/magellan --config magellan.json --local_browser appiumiosapp  --test tests/app.test.js --serial --max_test_attempts 1
</code></pre>
<p>You should see iOS simulator open, your app open, close and simulator close.</p>
<ul>
<li>If you don't have Saucelabs credential , please remove this line in <strong><em>./magellan.json</em></strong> file for now. We'll get back to Saucelabs setup in next section.</li>
</ul>
<pre><code class="language-bash">&quot;testarmada-magellan-saucelabs-executor&quot;
</code></pre>
</div>
<div class="training-doc-nav-btn">
<a href="./Setup iOS app test on Sauce Labs"><img src="/images/training/btn-right.png" srcset="/images/training/btn-right%402x.png 2x, /images/training/btn-right%403x.png 3x" /></a>
</div>
