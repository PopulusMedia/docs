# Populus Media - Media Integration Guide

## Integration Method for Web Applications

Partners that are web-application based can integrate via Populus Media Tag (PMT).  A Populus Media Tag is an HTML <ins> tag with a bunch of data-attributes used for either configuring the user epxerience or for passing any other data from the partner to Populus Media.

All the partner application needs to is to insert the tag in the patient environment like the waiting room or a async chat window or possibly at other locations during the user journey. 

There are two types of tags availble, 

* Campaign Tags  

* Inventory Tags (Beta)


### Campaign Tags

Campaign Tags are typically specific to a campaign. They are used when the partner is able to selectively target sessions based on diagnostic data of the user 

Here's an sample tag

~~~~~
	<ins class="popcorn" 
	  	data-pop-width="640px"
	  	data-pop-height="360px"
		data-pop-partner="<partner-code>"
		data-pop-visit-id="1234-5678-9abc-def0"
		data-pop-campaign="test">
        	<script src="https://cdn.populus-media.net/popcorn/v1.js" async></script>    
	</ins>
~~~~~

Where,

* data-pop-partner is the partner-code (provided by Populus Media)
* data-pop-visit-id is a anonymous session ID associated with the visit, this can be used to tie back partner data with Populus Media data
* data-pop-campaign is the name of the campaign (provided by Populus Media)
* data-pop-width is the width in either pixels or as a percentage, examples below
	* "90%" - set the width to 90% of the containing element width
	* "640px" - set the width to a fixed value of 640 pixels
	* "auto" - auto-compute width based given height and aspect ratio
* data-pop-height is the height in either pixels or as a percentage, examples below
	* "100%" - set the height to 100% of the containing element width
	* "360px" - set the height to a fixed value of 360 pixels
	* "auto" - auto-compute height based given width and aspect ratio
* data-pop-aspect-ratio is the user defined aspect ratio, some values are
	* 16:9 (default)
	* 4:3 


### Inventory Tags

Inventory Tags are more generic 
