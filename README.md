## NOTE: YOU SHOULD NOT USE THIS

I simply wanted to have a copy of Mark's classic flashblockplugin. There are better, more flexible detects available now ([modernizr](http://modernizr.com) beings my favorite).

---

<p>
  This is a pure-JavaScript library that detects whether Flash is blocked on the current page due to a Flash blocking extension. The current version can detect </p>
<ul>
  <li><a href="https://chrome.google.com/extensions/detail/cdngiadmnkhgemkimkhiilgffbjijcie" rel="nofollow">FlashBlock #1 for Chromium / Google Chrome</a> (Windows/Mac/Linux) </li>
  <li><a href="https://chrome.google.com/extensions/detail/gofhjkjmkpinhpoiabjplobcaignabnl" rel="nofollow">FlashBlock #2 for Chromium / Google Chrome</a> (Windows/Mac/Linux) </li>
  <li><a href="https://addons.mozilla.org/en-US/firefox/addon/433" rel="nofollow">FlashBlock for Firefox</a> (Windows/Mac/Linux) </li>
  <li><a href="http://rentzsch.github.com/clicktoflash/" rel="nofollow">ClickToFlash 1.5.x</a> (Mac/Safari only) </li>
</ul>

<p><a href="https://rawgit.com/patrickkettner/flashblockdetector/master/demo.html" rel="nofollow">See the live demo</a> </p>
<p>This library does not interfere with, or try to counteract, any Flash blocking extensions. It simply tells you whether a blocker is active on your page. Note: if the user has a Flash blocker but has whitelisted your site, the library will (correctly) say that Flash is not blocked. </p>
<p>Because some Flash blockers are not instantaneous, this library inserts some dummy Flash objects into the page and then waits for up to 5 seconds to see if they get blocked. To use the library, you must give it a callback function. If a Flash blocker is active, your callback function will be called almost immediately. If no Flash blocker is active, your callback function will be called after the 5 second timeout. Your callback function should take a single boolean parameter, which will be true if a Flash blocker is active, or false otherwise. </p>
<p>The library cleans up after itself, so there should be no remnants of its dummy Flash objects in the DOM by the time your callback function is called. </p>
<p>Example usage: </p><pre class="prettyprint"><span class="tag">&lt;script</span><span class="pln"> </span><span class="atn">src</span><span class="pun">=</span><span class="atv">"http://flashblockdetector.googlecode.com/hg/fbd.js"</span><span class="tag">&gt;&lt;/script&gt;</span><span class="pln"><br></span><span class="tag">&lt;script&gt;</span><span class="pln"><br>FBD</span><span class="pun">.</span><span class="pln">initialize</span><span class="pun">(</span><span class="pln">my_callback_function</span><span class="pun">);</span><span class="pln"><br><br></span><span class="kwd">function</span><span class="pln"> my_callback_function</span><span class="pun">(</span><span class="pln">flash_is_blocked</span><span class="pun">)</span><span class="pln"> </span><span class="pun">{</span><span class="pln"><br>&nbsp; </span><span class="kwd">if</span><span class="pln"> </span><span class="pun">(</span><span class="pln">flash_is_blocked</span><span class="pun">)</span><span class="pln"> </span><span class="pun">{</span><span class="pln"><br>&nbsp; &nbsp; </span><span class="com">/* ... do whatever you like ... */</span><span class="pln"><br>&nbsp; </span><span class="pun">}</span><span class="pln"> </span><span class="kwd">else</span><span class="pln"> </span><span class="pun">{</span><span class="pln"><br>&nbsp; &nbsp; </span><span class="com">/* ... do something else, or nothing ... */</span><span class="pln"><br>&nbsp; </span><span class="pun">}</span><span class="pln"><br></span><span class="pun">}</span><span class="pln"><br></span><span class="tag">&lt;/script&gt;</span></pre>
<p>For best performance, put this script at the bottom of your page, not at the top. </p>
<p><a href="https://rawgit.com/patrickkettner/flashblockdetector/master/demo.html" rel="nofollow">See the live demo</a> </p>
