---
name: igsn_for_specific_field_program
title: IGSN list for a specific field program
date: 01/12/2020
layout: default
order: 6
---


#### IGSN list for a specific field program
- The end point is [https://app.geosamples.org/samples/field_program](https://app.geosamples.org/samples/field_program)
  - Usage: https://app.geosamples.org/samples/field_program/[field program name].
- The service will retrieve all IGSNs for a user defined field program. It only accepts GET requests from client programs. It does not require login and password and supports pagination. If `hide_private` flag is set to 1, it will not return IGSNs whose sample metadata are not public accessible.

##### GET API
##### Request Headers
- Accept: application/xml, application/json, text/xml, text/json
##### Request Body

<pre>
<b>field program name</b> = exact name of the field program (case sensitive) <b>limit={limit}</b> maximum number of IGSNs for each
page. If it is not specified, it will default to 100. page_no={page_no} page number. If it is not specified, it will
default to 1.
</pre>

<pre>
<b>hide_private={1 or 0 or none} default to 0</b>
</pre>

If 1, it will not return IGSNs whose sample metadata are not public accessible.

##### Response Body
**HTTP status codes:**
- **400** Bad Request - Field program name is not valid.
- **404** Not Found - No IGSNs associated with the given field program name.
- **200** Successful. It will return user IGSN(s) as follows.

**Output format when request is successful ( status code = 200 ) XML format:**

```
<samples><sample> <igsn>SSH0002V6</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=SSH0002V6</url>
</sample> <sample> <igsn>SSH0002V5</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=SSH0002V5</url>
</sample> <sample> <igsn>SSH0002V4</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=SSH0002V4</url>
</sample> <sample> <igsn>SSH0002V3</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=SSH0002V3</url>
</sample> <total_counts>4339</total_counts> <previous_list>https://app.geosamples.org/samples/field_program/Susquehanna
Shale Hills Critical Zone Observatory (CZO)?limit=4&amp;page_no=99&amp;hide_private=0</previous_list>
<next_list>https://app.geosamples.org/samples/field_program/Susquehanna Shale Hills Critical Zone Observatory (CZO)?
limit=4&amp;page_no=101&amp;hide_private=0</next_list> </samples>
```

**JSON format:**

```
{ "igsn_list": [ "SSH0002V6", "SSH0002V5", "SSH0002V4", "SSH0002V3" ], "total_counts": 4339, "previous_list":
"https://app.geosamples.org/samples/field_program/Susquehanna Shale Hills Critical Zone Observatory (CZO)?
limit=4&page_no=99&hide_private=0", "next_list": "https://app.geosamples.org/samples/field_program/Susquehanna Shale
Hills Critical Zone Observatory (CZO)?limit=4&page_no=101&hide_private=0" }
```

***Please note: Total count of IGSNs is tagged as "total_counts" in the returned content. If limits, page numbers, etc. are specified, the returned content will have <previous_list> and <next_list> tags when there are more than one page of IGSNs.***
**Example:**

```
curl -X GET -H "accept: application/xml" "https://app.geosamples.org/samples/field_program
/Susquehanna%20Shale%20Hills%20Critical %20Zone%20Observatory%20(CZO)& limit=4&page_no=100";
```
