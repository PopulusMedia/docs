---
layout: page
title: Tracking Pixels
permalink: /pixels
---

Transparent or 1x1 pixels can be used to send back additional event data to the platform.  Here's an example of an event called "open" that corresponds to an email being opened 


~~~~~
<img height="1" width="1" src="<server-url>/open?partner=test&campaign=newsletter&email=xxxx@yyyy.com" />
~~~~~

Where,

* server-url is the URL associated with the pixel (provided by Populus Media) 
* partner is the partner-code (provided by Populus Media)
* campaign is a the name of the campaign (provided by Populus Media)
* email is the email address of the recipient
* npi is the npi-number associated with the HCP opening the email