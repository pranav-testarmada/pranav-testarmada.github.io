---
title: Prerequisites
layout: training
permalink: documentation/Functional Testing/Native Android/JAVASCRIPT/Training Guide/Setup/Prerequisites
level1: Functional Testing
level2: Native Android
level3: JAVASCRIPT
level4: Training Guide
course: Setup
---
<div class="sidebar">
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/actived.png" srcset="/images/training/actived%402x.png 2x, /images/training/actived%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-pending" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-current" href="./Prerequisites">Prerequisites</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/unread.png" srcset="/images/training/unread%402x.png 2x, /images/training/unread%403x.png 3x" /><hr class="training-doc-link-left__hr training-doc-link-left__hr-pending" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-pending" href="./Setup Android app test on local machine">Setup Android app test on local machine</a></p>
</div>
<div class="training-doc-link">
<div class ="training-doc-link-left">
<img class="training-doc-link-left__img" src="/images/training/unread.png" srcset="/images/training/unread%402x.png 2x, /images/training/unread%403x.png 3x" /></div>
<p class="training-doc-link__text">
<a class="training-doc-link__text-pending" href="./Setup Android app test on SauceLabs">Setup Android app test on SauceLabs</a></p>
</div>
</div>
<div class="training-doc-nav-btn">
</div>
<div class="training-content markdown">
<p>New to Android app automation testing? No worry, you don’t need to know much to set it up. Let's get your first Android app test up and running in a couple of minutes.</p>
<h3>Prerequisites:</h3>
<ul>
<li><p>Install latest <a href="https://developer.android.com/studio/index.html#downloads">Android Studio</a></p>
<ul>
<li>Update the following through Tools &gt; SDK Manager:</li>
<li><strong>SDK Platforms</strong>: Download <strong><em>Android 7.1.1 (Nougat)</em></strong>
<ul>
<li>Expand package details and include Google APIs Intel x86 Atom_64 System Image</li>
</ul></li>
<li><strong>SDK Tools</strong>: Update Android SDK Build-Tools, Android Emulator, Android SDK Platform-Tools, Android SDK Tools, Intel x86 Emulator Accelerator</li>
</ul></li>
<li><p>Create this Android Virtual Device (AVD):</p>
<ul>
<li>Download <a href="../../../images/a71_device.xml">a71_device.xml</a></li>
<li>Go to Tools &gt; <strong>AVD Manager</strong> in Android Studio</li>
<li>Click on <strong>Create Virtual Device</strong></li>
<li>Click on <strong>Import Hardware Profiles</strong></li>
<li>Select the <strong>a71_device.xml</strong> file</li>
<li>Refresh page, select <strong>a71</strong> device profile, and click Next</li>
<li>Click on <strong>x86 Images</strong> tab</li>
<li>Select Nougat x86_64 Android 7.1.1 (Google APIs) (download may be required), and click Next</li>
<li>Set AVD Name as <strong>a71_API_25</strong>, and click Finish</li>
</ul></li>
<li><p>Install Node.js &gt;= v4.x.x</p></li>
<li><p>Install <a href="http://nodejs.org/">npm</a>. Check that you have at least <strong>npm</strong> version 3 or above (required by <em>appium@1.7.x</em>):</p></li>
</ul>
<pre><code class="language-bash">$ npm --version
# If not, install npm3
$ npm install -g npm@3
</code></pre>
</div>
<div class="training-doc-nav-btn">
<a href="./Setup Android app test on local machine"><img src="/images/training/btn-right.png" srcset="/images/training/btn-right%402x.png 2x, /images/training/btn-right%403x.png 3x" /></a>
</div>
