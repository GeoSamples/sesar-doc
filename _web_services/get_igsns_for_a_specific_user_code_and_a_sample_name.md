---
name: get_igsns_for_a_specific_user_code_and_a_sample_name
title: Get IGSN(s) for a specific user code and a sample name (NEW)
date: 01/12/2020
layout: default
order: 9
---

##### Get IGSN(s) for a specific user code and a sample name (NEW)
- The endpoint is [https://app.geosamples.org/samples/user_code](https://app.geosamples.org/samples/user_code).
- E.G. [https://app.geosamples.org/samples/user_code/ODP?sample_name=test](https://app.geosamples.org/samples/user_code/ODP?sample_name=test)
  - User code examples: IEUHM or IELCZ, ODP, NHB or HRV
  - Sample name examples: Section 90-588C-14R-3 or NMNH 125980-00 (MIN)
- The service will retrieve all IGSNs matching with a specific user code and a sample name. It only accepts GET requests from client programs. The login is optional. If 'hide_private' flag is set to 1, it will not return IGSNs whose sample metadata are not publicly accessible.

##### GET API
##### Request Headers
- Accept: application/xml, application/json, text/xml, text/json
##### Request Headers 
```
limit={limit}: maximum IGSN number for each page. If it is not specified, it will default to 100.
page_no={page_no}: page number. If it is not specified, it will default to 1.
hide_private={1 or 0 or none}: default to 0. If 1, it will not return IGSNs whose sample metadata are not publicly accessible.
```
##### Response Body
**HTTP status codes:**
- **400** Bad Request - User Code is not valid.
- **404** Not Found - No IGSNs associated with the given user code.
- **200** Successful. It will return a list of IGSN(s) as follows.

**Output format when the request is successful ( status code = 200 ) XML format:**

```
<samples>
  <sample> 
    <igsn>NHB001B2E</igsn> 
    <url>http://igsn.org/NHB001B2E</url> 
  </sample>
</samples>
```

```
<total_countst>1</total_counts>
```

**Example**

```
curl -v -X GET -H "accept:application/xml" "https://app.geosamples.org/samples/user_code/NHB?sample_name=NMNH+148841-
00+(MIN)";
```

**JSON format:**

```
{ "igsn_list": [ "NHB001B2E"], "total_counts":1 }
```

**Example:**

```
curl -v -X GET -H "accept:application/json" "https://app.geosamples.org/samples/user_code/NHB?sample_name=NMNH+148841-
00+(MIN)";
```


