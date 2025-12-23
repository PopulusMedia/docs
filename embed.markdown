---
layout: page
title: Embedded
permalink: /embed
---

Embedding content through an iframe is straightforward. The iframe is served from a predefined URI, with parameters passed as request variables to that URI.

*Example Embedded URI*

~~~~~
https://cdn.populus-media.net/popcorn/v5/embed.html?partner=test&visit-id=1234-5678-9abc-def0&width=300&height=250&npi=9876543210&email=aaa@bbb.ccc

~~~~~

Where,

* partner is the partner-code (provided by Populus)
* visit-id is the visit-id associcated witht he visit
* width is the maximum width of external content from Populus
* height is the maximum height external content from Populus
* npi is the npi number associated with the HCP
* email is the email associated with the HCP

For a complete list of parameters that could be passed, please refer [here](index.html#parameters).