---
layout: page
title: JavaScript
permalink: /javascript
---

Integrationg through a JavaScript API is a two-step process

### Step 1 - Including the JavaScript Library in your Web App or Page

The JavaScript library must be loaded with the request variable of ***mode=api***.

~~~~~
<script src="https://cdn.populus-media.net/popcorn/v3/index.js?mode=api">
</script>    
~~~~~

Once the library loads, the API is exposed through a window object called ***$pop***


### Step 2 - Calling the JavaScript API

Create and record the element-id associated with the container where extenal content from Populus Media would render.  In the example below, the parent container identifier is *custom-content*. Please note that the container element can also be generated dynamically.

Example:

~~~~~
<div id="custom-content">

</div>
~~~~~

Call the render() method on the API.  The render method takes the parent container as the first argument and a list of attributes are passed as properties of an object as the second.

~~~~~
let external = $pop.render(document.getElementById('custom-content'), {
	"partner": "test",
	"visit-id": "1234-5678-9abc-def0",
	"width": "640px"
	"height":"360px"
	"icdx": "G20"
})
~~~~~


Where,

* partner is the partner-code (provided by Populus Media)
* visit-id is the visit-id associcated witht he visit
* width is the maximum width of external content from Populus Media
* height is the maximum height external content from Populus Media 
* icdx is the ICD10 code associated with the session / visit

For a complete list of attributes that could be passed, please refer the [home page](index.html).

