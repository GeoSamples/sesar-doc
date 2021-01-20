---
name: igsn_list_for_specific_user_code
title: IGSN list for specific user code
date: 01/12/2020
layout: default
order:3
---

# IGSN list for specific user code
- The end point is [https://app.geosamples.org/samples/user_code](https://app.geosamples.org/samples/user_code).
  - E.G. [https://app.geosamples.org/samples/user_code/IEUHM](https://app.geosamples.org/samples/user_code/IEUHM)
    - User code examples: IEUHM or IELCZ, ODP, NHB or HRV
- The service will retrieve all IGSNs for a specific user code. It only accepts GET requests from client programs. It does not require login and password and supports pagination. If `hide_private` flag is set to 1, it will not return IGSNs whose sample metadata are not public accessible.

# GET API
### Request Headers
- Accept: application/xml, application/json, text/xml, text/json
### Request Body

<pre>
<b>limit={limit}</b> maximum IGSN number for each page. If it is not specified, it will default to 100. <b>page_no={page_no}</b> page
number. If it is not specified, it will default to 1.
</pre>

<pre>
<b>hide_private={1 or 0 or none} default to 0</b>
</pre>

If 1, it will not return IGSNs whose sample metadata are not public accessible.
### Response Body
**HTTP status codes:**
- **400** Bad Request - User Code is not valid.
- **404** Not Found - No IGSNs associated with the given user code.
- **200** Successful. It will return a list of IGSN(s) as following.

**Output format when request is successful ( status code = 200 ) XML format:**

```
<samples>
```

```
<sample> <igsn>LLS00000L</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=LLS00000L</url> </sample>
```

```
<sample> <igsn>LLS00000M</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=LLS00000M</url> </sample>
```

```
<sample> <igsn>LLS00000N</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=LLS00000N</url> </sample>
```

```
......
```

```
<total_counts>320</total_counts>
```

```
<previous_list>https://app.geosamples.org/samples/user_code/LLS?limit=20&page_no=1</previous_list>
<next_list>https://app.geosamples.org/samples/user_code/LLS?limit=20&page_no=3</next_list> </samples>
```

**JSON format**

```
{ "igsn_list": [ "MOB000001", "MOB000002", "MOB000003", "MOB000004", ...... ], "total_counts":450, "previous_list":
[ "http: //app.geosamples.org/samples/user_code/MOB?limit=100&page_no=1" ], "next_list":
[ "http: //app.geosamples.org/samples/user_code/MOB?limit=100&page_no=3" ] }
```

**Example:**

```
curl -X GET -H "accept: application/xml" "https://app.geosamples.org/samples/user_code/ARF?limit=20&page_no=2&hide_private=1"
```
