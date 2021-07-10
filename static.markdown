---
layout: page
title: HTML
permalink: /html
---

Integrating through HTML is fairly straightforward.   A standard HTML &lt;ins&gt; tag can be placed inline where the partner wishes to show content provided by Populus Media.  Attributes must be passed as data attributes with the prefix "data-pop-".   

*Sample HTML tag*

~~~~~
<ins class="popcorn" 
	data-pop-partner="test"
	data-pop-visit-id="1234-5678-9abc-def0"
	data-pop-anon-id="u9875643210"
	data-pop-width="640px"
  	data-pop-height="360px"
	data-pop-icdx="G40">
  <script src="https://cdn.populus-media.net/popcorn/v4/index.js" async></script>    
</ins>
~~~~~

Where,

* data-pop-partner is the partner-code (provided by Populus Media)
* data-pop-visit-id is the visit-id associcated witht he visit
* data-anon-id is an anonymized user identifier on the partner app 
* data-pop-width is the maximum width of external content from Populus Media
* data-pop-height is the maximum height external content from Populus Media 
* data-pop-icdx is the ICD10 code associated with the session / visit

The inline &lt;script&gt; tag is required to fetch the appropriate content from Populus Media based on the attributes passed in the tag and to render it within the &lt;ins&gt; element. For a complete list of attributes that could be passed, please refer the [home page](index.html).