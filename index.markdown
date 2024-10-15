---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Populus Health Tech - Media Library Version 5

## Integrating Web Applications

Partner that have a web-application based platform can integrate via either HTML tag or a JavaScript based API. Data can be passed to the HTML tag through standard data attributes and the JavaScript API through a JSON object.  A call needs to be made out for every opportunity tthat exists on the partner's app by either through one of the methods described here.  

To see how attributes can be passed, please check out the sections on [HTML](html) and [JavaScript](javascript) for examples.  The following set of attributes can be passed 

| Attribute Name | Description | Required | Default |
| ----- | -------- |----- | ----- |
| network | An alphanumeric code provided by Populus | Yes | |
| partner | An alphanumeric code assigned to the partner | Yes | |
| partner-subacct | An alphanumeric code that represents a sub-account on a partner to facilitate reporting | No | none |
| visit-id | A unique session identifier associated with the visit used to tie back partner data with Populus data | Yes | |
| anon-id | An anonymized but uniquely identifiable user id on the partner network. While normally optional, this value must be passed to be considered for campaigns that require user opt-outs | No 
| suppress | A comma separate list of HTML element id's that must be hidden in case there's no content to show for the opportunity.  Alternatively you could use the utility class ***pop-suppress*** on those elements.  This is useful for hiding companian notices. | No | none |
| width | Available width as a percentage (%) of the containing element or as an absolute value in pixels (px). | No | 100% |
| height | Available height as a percentage (%) of the containing element or as an absolute value in pixels (px). | No | auto |
| max-height | Maximum height in pixels which the the container can accomodate, only used when height=auto | No | 600px |
| aspect-ratio | Aspect ratio of the video player when a video is played on the parter site like ***4:3*** or ***16:9*** | No | 16:9 | 
| visit-stage | The stage of the journey the user is in within the telemedicine visit. Possible values are ***pre*** which represents the user in the intake process, ***during*** which represents the waiting room or a chat window or ***post***  which is any time after the consult has completed | No | during
| inventory-class | A value indicating the kind of content that is acceptable for the opportunity. Possible values are ***video***, ***display*** or ***any*** | No | any
| reason | A user entered reason for the visit, this would be used to determine the best possible content for the opportunity | No | | 
| keywords | A list of comma separated keywords for the user or session to be used to determine the best content for the opportunity. It may contain the specialty or therapeutic categories associated with the question or the visit.   May also contain other attributes associated with the user like comorbodities, ICD10 codes or diagnosis made in previous visits. | No | |
| gender | Gender the patient was born or identify: <br/> ***m*** &rarr; Male, ***f*** &rarr; Female, ***o*** &rarr; Other or ***x*** &rarr; Unknown | Yes | x |
| age-range | User age range with the following bands:<br/>&emsp; 2 &rarr; 18-24<br/>&emsp; 3 &rarr; 25-34<br/>&emsp; 4 &rarr; 35-44<br/>&emsp; 5 &rarr; 45-54<br/>&emsp; 6 &rarr; 55-64 <br/>&emsp; 7 &rarr; 65+<br/>&emsp; 0 &rarr; Unknown| Yes | 0 | 
| age | User age, may be used if age ranges aren't readily available.  Will be used only if age-range isn't passed| Yes | none |
| race | Race associated with the where, <br/>&emsp; 1 &rarr; White, not hispanic<br/>&emsp; 2 &rarr; Black, not hispanic<br/>&emsp; 3 &rarr; Hispanic<br/>&emsp; 4 &rarr; American Indian or Alaska Native<br/>&emsp; 5 &rarr; Asian or Pacific Islander<br/>&nbsp;&ensp; -1 &rarr; Missing or Unknown | No | -1 |
| pld | Physician Level Data in the form ***"npi=9876543210;email=aaa@bbb.ccc"*** where 9876543210 is the NPI of the consulting healthcare provider and aaa@bbb.ccc is the email address  <br/><br/>Example: <br/>&emsp; pld="npi=9876543210" | Yes | none |

