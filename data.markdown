---
layout: page
title: Data Synch
permalink: /data
---

There are scenarios under which all data, like Phsycian Level Data, is not available during the primary workflow.  In those cases, data can be sent after the fact via a server to server (S2S) API call using the visit-id that was used for the original visit.   

*This can be done by issuing a POST call to our API endpoint*

~~~~~
https://<api-endpoint>/event/data/<visit-id>
Content-Type: application/json

POST
{
   "partner": "<partner-code>",
   "secret": "<partner-secret>",
   "npi": "987654321"
}
~~~~~

Where,

* visit-id is the visit-id associcated with the original visit
* partner is the partner-code (provided by Populus Media)
* secret is a partner specific hash (provided by Populus Media)
* npi is the NPI number associated with the consulting povider