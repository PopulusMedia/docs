---
layout: page
title: JavaScript
permalink: /javascript
---

Integrating through a JavaScript API is a two-step process.  An optional third step allows developers to obtain status of the ad rendering process through an event handler.

### Step 1 - Including the JavaScript Library in your Web App or Page

The JavaScript library must be loaded with the request variable of ***mode=api***.

~~~~~
<script src="https://cdn.populus-media.net/popcorn/v5/index.js?mode=api">
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
let adObject = $pop.render(document.getElementById('custom-content'), {
	"partner": "test",
	"visit-id": "1234-5678-9abc-def0",
	"width": "640px",
	"height":"360px",
	"keywords": "plaque psoriasis,L40"
})
~~~~~


Where,

* partner is the partner-code (provided by Populus Media)
* visit-id is the visit-id associcated witht he visit
* width is the width of the display container
* height is the height of the display container
* keywords are the keywords associated with the session / visit

For a complete list of attributes that could be passed, please refer the [home page](index.html).


### Step 3 - Obtaining rendering status 

Call to the _render()_ method on the API returns an object, called the ***ad-object***, which can provide useful information about the the work that library is doing.  A _null_ response from render() would meant that there was a problem early in the lifecycle of ad rendering.    For problems that occur late stage which is by nature asynchronous, an event listener can be added on the returned object to check if there were problems during rendering. The exact event to lookout for is called _noAds_ which is fired when the render() method could not show an ad.  Here's an illustration of the correct way to use output from the library

Illustration:

~~~~~
let adObject = $pop.render(...)

// If render returns an object, add an event listener
if (adObject && adObject.status != '' ) {
  adObject .addEventListener('noAds', () => {
    // No ad could be shown - late stage - during rendering
    ...
  })
}
else {
  // No ad could be shown - early stage - during initialization
  ...
}
~~~~~


#### List of all events fired

Plaese note that all events other than error* are in the order in which they occur.  Some events like *done* may only occur for video.

| Event Name | Description |
|------------|-------------|
| init | A campaign has been selected; this does not eliminate the possibility of an *noAds* event from firing later in the lifecycle|
| noAds | No matching ad was found |
| rendered | Fired when an ad has rendered. A new property called *creativeType* which has a value of either _banner_ or _video_ is added to the ***ad-object*** |
| viewed     | Occurs when the video has been played for the minimum duration stipulated by either IAB or the brand |
| done       | When a video ad has finished playing |
| error      | An error occurred while plyaing a video ad |


#### Ad Object Attributes

In addition to events that gets fired, the Ad Object also contains attributes that contain useful information.  The attributes *status* and *reason* will be non-blank in case an ad cannot be show due to reasons like *frequency capping* within a visit, which could happen early in the lifecycle ad-rendering and making it unfeasible to be caught through an event listener.

These attributes *campaignCode* is available after the *init* event has been fired.

All other attributes become available only after the *rendered* event

| Attribute Name | Description |
|----------------|-------------|
| status | When non-blank indicates a condition that can cause an ad not to be rendered. Possible values are **noAds** or **error** |
| reason | Supplements the status field by indicating reason why the ad could not be rendered | 
| campaignCode | An abbreviated campaign code associated with the campaign |
| creativeType | Contains a value of either **banner** or **video** depending on creative selected | 
| rxname | The name or brand of the drug being advertised |
| landingPage | The landing page associated with the brand |
