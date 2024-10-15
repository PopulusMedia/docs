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
   "net": "<network-code>",
   "partner": "<partner-code>",
   "token": "<partner-token>",
   "npi": "9876543210"
}
~~~~~

Where,

* visit-id is the visit-id associcated with the original visit
* net is a constant (provided by Populus)
* partner is the partner-code (provided by Populus)
* token is a partner specific hash (provided by Populus)
* npi is the NPI number associated with the health care provider