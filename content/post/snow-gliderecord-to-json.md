---
title: "SNOW GlideRecord to JSON"
date: 2019-03-16T11:58:16+02:00
draft: false
description: Converting ServiceNow GlideRecords to JSON
images: [/images/snow.png]
tags: [snow, servicenow, gliderecord, json, stringify, automation, api, business-rule, integration]
keywords: [SNOW, Service Now, GlideRecord, JSON, stringify, Automation, API, Business Rule,
Integration]
---
This week I needed to implement an integration with [Service Now](https://www.servicenow.com/) (SNOW).    

The integration would fire an API request whenever a new record is inserted, or when an existing one is updated. The way to achieve this in SNOW is by creating a [Business Rule](https://docs.servicenow.com/bundle/london-application-development/page/script/business-rules/concept/c_BusinessRules.html), with custom script in the "Advanced" section.

To give a little more background, my goal was to send the entire record, [GlideRecord](https://docs.servicenow.com/bundle/jakarta-application-development/page/script/glide-server-apis/concept/c_GlideRecord.html) in SNOW, in the payload of the outbound request.

Finding [code examples](https://docs.servicenow.com/bundle/london-application-development/page/integrate/outbound-rest/concept/c_ScriptingOutboundREST.html) for the API request itself was pretty straightforward (with SNOW's [RESTMessageV2](https://docs.servicenow.com/bundle/geneva-servicenow-platform/page/app-store/dev_portal/API_reference/RESTMessageV2/concept/c_RESTMessageV2API.html)).

This is why I was surprised when the body I received in the inbound side included only the record's
keys, without their values.

The reason was - I used [`JSON.stringify()`]() to convert the GlideRecord to a JSON, which was sent as the payload.    
It turns out, some values in GlideRecords cannot be encoded by the JSON object.

## The Solution

After spending some time in SNOW developer docs and community forum, I decided to go with a naive approach.

Iterate over the GlideRecord props and add each prop with its' value, **using the [`getValue`](https://developer.servicenow.com/app.do#!/api_doc?v=jakarta&id=r_GlideRecord-getValue_String) method**, to a new JavaScript object.

```javascript
function glideRecordToJson(gr) {
  var obj = {};

  for (var prop in gr) {
    if (gr[prop]){
      obj[prop] = gr.getValue(prop);
    }
  }

  return obj;
};
```
