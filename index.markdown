---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Populus Media Libary Version 4

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
| width | Maximum available width as a percentage (%) of the containing element or as an absolute value in pixels (px). | No | 100% |
| height | Maximum available height as a percentage (%) of the containing element or as an absolute value in pixels (px). | No | auto |
| aspect-ratio | Aspect ratio of the video player when a video is played on the parter site like ***4:3*** or ***16:9*** | No | 16:9 | 
| visit-stage | The stage of the journey the user is in within the telemedicine visit. Possible values are ***pre*** which represents the user in the intake process, ***during*** which represents the waiting room or a chat window or ***post***  which is any time after the consult has completed | No | during
| inventory-class | A value indicating what kind of content are acceptable for the opportunity. Possible values are ***video***, ***display*** or ***any*** | No | any
| reason | A user entered reason for the visit, this would be used to determine the best possible content for the opportunity | No | | 
| keywords | A list of comma separate keywords for the session to be used to determine the best content for the opportunity. When passed, this attribute takes priority over the attribute _reason_ | No | |
| icdx | The first three characters of the ICD-10 code representing the disease category associated with the session. When passed, this takes priority over attributes _keywords_ and _reason_ | No | |

For Populus Media to be able to show content one of the three attributes, ___reason___, ___keywords___ or ___icdx___ must be passed

