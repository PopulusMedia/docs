# Populus Media - Media Integration Guide

## Integrating Web Applications

Partner that have a web-application based platform can integrate via a Populus Media Tag (PMT).  A Populus Media Tag is an HTML &lt;ins&gt; tag with a set of data-attributes used for either configuring the user epxerience or for passing any additional data from the partner to Populus.

To use the PMT, all that is needs to is to insert the tag in the patient environment like the waiting room or a async chat window or possibly at other locations during the user journey.  

There are two distinct types of tags available, 

* [Campaign Tag](#campaign-tag)  

* [Inventory Tag](#inventory-tag)


### Campaign Tag

A campaign tag is specific to a campaign. They are used when the partner is able to preselect and target sessions for a given campaign based on contextual relevance of the session.  A campaign typically consists of edutional content plus some sponsorship content.

*A sample campaign tag*

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
* data-pop-visit-id is an anonymous session identifier associated with the visit used to tie back partner data with Populus data
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


### Inventory Tag

An inventory tag is used by partner to call out an opportunity to engage with a user by passing contextual information like keywords or ICD codes associated with the session.  This allows Populus to select the best possible content for the opportunity.


*A sample inventory tag*

~~~~~
	<ins class="popcorn" 
	  	data-pop-width="640px"
	  	data-pop-height="360px"
		data-pop-partner="<partner-code>"
		data-pop-visit-id="1234-5678-9abc-def0"
		data-pop-inventory-class="video"
		data-pop-keywords="asthma">
        	<script src="https://cdn.populus-media.net/popcorn/v1.js" async></script>    
	</ins>
~~~~~

Where,

* data-pop-partner is the partner-code (provided by Populus Media)
* data-pop-visit-id is an anonymous session identifier associated with the visit used to tie back partner data with Populus data
* data-pop-inventory-class is class of inventory, possible values are
	* video - video engagement is possible
	* display - display banners are possible
	* any - both video and display are possible
* data-pop-keywords is the list of comman separate keywords for the session. This will be used by Populus to select the best content for the session
* data-pop-icdx is the ICD10 code associated with the session, this could be used instead of keywords
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
