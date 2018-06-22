---
title: Desired Capabilities
layout: training
permalink: documentation/Functional Testing/Native Android/JAVASCRIPT/Training Guide/Android Automation/Desired Capabilities
level1: Functional Testing
level2: Native Android
level3: JAVASCRIPT
level4: Training Guide
course: Android Automation
---
<div class="sidebar">
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-pending" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Desired Capabilities">Desired Capabilities</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/unread.png" srcset="/images/training/unread%402x.png 2x, /images/training/unread%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-pending" href="./Native Android locators">Native Android locators</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
</div>
<div class="training-content markdown">
<h2>Desired Capabilities</h2>
<h4>After we understand the tests framework, we can start to take a closer look on how Android app automation works</h4>
<h3>Underlying we are using <a href="http://appium.io"><strong>Appium</strong></a> to drive native Android app automation</h3>
<ul>
<li>Most concepts are similar for web and app automations, a few things maybe new to people who come from web automation world:</li>
</ul>
<p><strong>Desired Capabilities</strong></p>
<ul>
<li>Desired capabilities are a set of keys and values (i.e., a map or hash) sent to the Appium server to tell the server what kind of automation session we're interested in starting up.</li>
<li>There are various capabilities which can modify the behavior of the server during automation.</li>
<li>For example, we could set the <strong>platformName</strong> capability to <strong>Android</strong> to tell Appium that we want an Android session, rather than an iOS one. See the <a href="http://appium.io/docs/en/writing-running-appium/caps/index.html">capabilities doc</a> for the complete list of capabilities available for Appium.</li>
<li>For our sample repo, Desired Capabilities are defined either in profiles in <strong>magellan.json</strong> file or in <strong><em>./conf/nightwatch.json</em></strong> file. You can specify to use which one in your command line.</li>
<li>For example, in your command, you can specify it via <code>--profile appium-ios-app</code>, which means look up desired capability defined in <em>profile</em> style in <strong>magellan.json</strong> file.</li>
<li>It is highly recommended to set the  <code>appPackage</code>  and  <code>appActivity</code>  capabilities in order to let Appium know exactly which package and activity should be launched for your application. Otherwise, Appium will try to determine these automatically from your app manifest. E.g.</li>
</ul>
<pre><code class="language-bash">    &quot;appium-android-app&quot;: [
      {
        &quot;browser&quot;: &quot;Android_GoogleAPI_Emulator_Android_7_1_Android&quot;,
        &quot;orientation&quot;: &quot;portrait&quot;,
        &quot;appium&quot;: {
          &quot;app&quot;: &quot;sauce-storage:AUT.apk&quot;,
          &quot;platformName&quot;: &quot;Android&quot;,
          &quot;appiumVersion&quot;: &quot;1.7.2&quot;,
          &quot;fullReset&quot;: &quot;true&quot;,
          &quot;noReset&quot;: &quot;false&quot;,
          &quot;appActivity&quot;: &quot;com.yourcompany.android.main.MainActivity&quot;,
          &quot;appWaitActivity&quot;: &quot;com.yourcompany.android.main.AnotherActivity&quot;
        }
      }
    ],
</code></pre>
</div>
<div class="training-doc-nav-btn">
<a href="./Native Android locators"><img src="/images/training/btn-right.png" srcset="/images/training/btn-right%402x.png 2x, /images/training/btn-right%403x.png 3x" /></a>
</div>
