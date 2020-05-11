---
layout: default
title: Populus Media - Partner Integration Guide
---

# About

Popcorn is a JavaScript library that Populus Media uses to control delivery of the right content in a virtual waiting room environment.  

## Integration Methods


### Campaign Specific Tags


<code>
    <pre class="pop-suppress">This is an ad </pre>
    <ins class="popcorn" 
		  data-pop-type="11"
		  data-pop-width="640px"
      data-pop-partner="test"
      data-pop-visit-id="1234-5678-9abc-def0"
      data-pop-campaign="ajovy"
      data-pop-debug="1"
      >
      <script src="index.js" async></script>    
	  </ins>
</code>




### Inventory Tags

Populus Media Tags (PMT) is the most direct way to use the library.  This is how a typical populus media tag looks like


1> Campaign Tags

Campaign Tags are typicall 



2> Inventory Tags


### Config : <code>object</code>
**Kind**: global namespace  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| AD_ID | <code>string</code> | Element Id of the container in which video ad should play |
| VIDEO_ID | <code>string</code> | Element Id of the <video> element that would play backup media |
| FULLSCREEN | <code>boolean</code> | Indicates if the Ad Pod should cover the whole viewport |
| [PADDING] | <code>number</code> | Padding (in pixels) on each side when the Ad Pod when in fullscreen, default to zero |
| [WIDTH] | <code>number</code> | Width of the Ad Pod (in pixels), used when FULLSCREEN is false, defaults to 640 |
| [HEIGHT] | <code>number</code> | Height of the Ad Pod (in pixels), used when FULLSCREEN is false, defaults to 480 |
| MIN_DURATION | <code>number</code> | Minumum duration the Ad Pod runs.  The Ad Pod would stay live for atleast the minimum duration regardless of if ads are available or not, playing backup media instead |
| MAX_DURATION | <code>number</code> | Maximum duration the Ad Pod runs - upon reaching this duration, the Ad Pod considers itself complete and invokes the callback function specified with CALLBACKFN |
| MAX_ADS | <code>number</code> | Maximum number of Ads to show, the Ad Pod would consider itself complete when if it has played MAX_ADS eve if it has not reached the MAX_DURATION |
| [DEBUG] | <code>boolean</code> | Indicates if severe messages should be shown on screen, default to false |
| BACKUP_MEDIA | <code>array</code> | An array containing a list of paths to local media files to be played when no ad is available to be played |
| CALLBACKFN | <code>function</code> | A callback function called by the Ad Pod upon completion, make change here to notify your player |


### Installation 

Install by moving the customized HTML file and related assets (like JavaScript) to a suitable location on the player from where it could be triggered by the CMS on the video player

### Scheduling

The Ad Pod HTML content is meant to be scheduled just like any other static or dynamic HTML on existing Content Management Systems (CMS).  A key element of scheduling is to understanding how to obtain control back iahead of the scheduled end time of the Ad Pod.   Control can be passed from the Ad Pod back to the main video player by writing custom code in JavaScript in the property called CALLBACKFN and it generally varies by the CMS used.

