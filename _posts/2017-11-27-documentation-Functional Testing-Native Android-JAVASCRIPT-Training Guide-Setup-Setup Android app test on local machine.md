---
title: Setup Android app test on local machine
layout: training
permalink: documentation/Functional Testing/Native Android/JAVASCRIPT/Training Guide/Setup/Setup Android app test on local machine
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
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-pending" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Setup Android app test on local machine">Setup Android app test on local machine</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/unread.png" srcset="/images/training/unread%402x.png 2x, /images/training/unread%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-pending" href="./Setup Android app test on SauceLabs">Setup Android app test on SauceLabs</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
<a href="./Prerequisites"><img src="/images/training/btn-left.png" srcset="/images/training/btn-left%402x.png 2x, /images/training/btn-left%403x.png 3x" /></a>
</div>
<div class="training-content markdown">
<h3>Run Android app test in local emulator</h3>
<ul>
<li>Get the sample code and install the node package dependencies:</li>
</ul>
<pre><code class="language-bash"># Create a workspace and get the smaple code
$ git clone git@github.com:TestArmada/boilerplate-nightwatch.git
$ cd boilerplate-nightwatch
$ npm install
$ npm install appium@1.7.2
</code></pre>
<ul>
<li>Verify all the required items are setup properly by running appium-doctor (only needed for the first time using):</li>
</ul>
<pre><code class="language-bash"># install appium-doctor (may require sudo)
$ npm install appium-doctor -g
# check that all Android dependencies are set up correctly
$ appium-doctor --android
</code></pre>
<ul>
<li>Get a developer build of the application you want to test, put it under <code>./app</code> folder, for example, rename .apk and put it as <code>./app/AUT.apk</code></li>
<li>Launch the <strong>a71_API_25</strong> AVD in the emulator</li>
<li>Put following entry in your <code>nightwatch.json</code></li>
</ul>
<pre><code class="language-js">&quot;appiumandroidapp&quot;: {
  &quot;skip_testcases_on_fail&quot;: true,
  &quot;desiredCapabilities&quot;: {
    &quot;app&quot;: &quot;./app/AUT.apk&quot;,
    &quot;appiumVersion&quot;: &quot;1.7.2&quot;,
    &quot;platformName&quot;: &quot;Android&quot;,
    &quot;platformVersion&quot;: &quot;7.1.1&quot;,
    &quot;deviceName&quot;: &quot;a71_API_25&quot;
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
<pre><code class="language-bash">./node_modules/.bin/magellan --config magellan.json --local_browser appiumandroidapp --test tests/app.test.js --serial --max_test_attempts 1
</code></pre>
<p>You should see Android emulator open, your app open, close and simulator close.</p>
<ul>
<li>If you don't have Saucelabs credential , please remove following line in <strong><em>./magellan.json</em></strong> file for now. We'll get back to Saucelabs setup in next section.</li>
</ul>
<pre><code class="language-bash">&quot;testarmada-magellan-saucelabs-executor&quot;
</code></pre>
<p>Please note: the AVD_NAME may different from the AVD manager you see from Android Studio, you can find the right name from the following command:</p>
<pre><code class="language-bash">${ANDROID_HOME}/platform-tools/emulator -list-avds
</code></pre>
<p>To know more about emulator commands, please read <a href="https://developer.android.com/studio/run/emulator-commandline.html">this</a>.</p>
</div>
<div class="training-doc-nav-btn">
<a href="./Setup Android app test on SauceLabs"><img src="/images/training/btn-right.png" srcset="/images/training/btn-right%402x.png 2x, /images/training/btn-right%403x.png 3x" /></a>
</div>
