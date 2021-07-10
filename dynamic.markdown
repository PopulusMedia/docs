---
layout: page
title: JavaScript
permalink: /javascript
---

Integrationg through a JavaScript API is a two-step process.  An optional third step allows developers to obtain status of the ad rendering process through an event handler.

### Step 1 - Including the JavaScript Library in your Web App or Page

The JavaScript library must be loaded with the request variable of ***mode=api***.

~~~~~
<script src="https://cdn.populus-media.net/popcorn/v4/index.js?mode=api">
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

Call the _render()_ method on the API.  The render method takes the parent container as the first argument and a list of attributes are passed as properties of an object as the second.

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


### Step 3 - Obtaining rendering status 

Call to the _render()_ method on the API returns an object which can provide useful information about the the work that library is doing.  A _null_ response from render() would meant that there was a problem early in the lifecycle of ad rendering.    For problems that occur late stage which is by nature asynchronous, an event listener can be added on the returned object to check if there were problems during rendering. The exact event to lookout for is called _noAds_ which is fired when the render() method could not show an ad.  Here's an illustration of the correct way to use output from the library

Illustration:

~~~~~
let external = $pop.render(...)

// If render returns an object, add an event listener
if (external) {
  external.addEventListener('noAds', () => {
    // No ad could be shown - late stage - during rendering
    ...
  })
}
else {
  // No ad could be shown - early stage - during initialization
  ...
}
~~~~~


#### List of other events fired (v4 only)

| Event Name | Description |
|------------|-------------|
| done       | When a video ad has finished running |
| error      | An error occurred while rendering a video ad |



