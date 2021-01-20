---
name: sample_profile_for_specific_IGSN
title: Sample Profile for specific IGSN
date: 01/12/2020
layout: default
order: 7
---

# Sample Profile for specific IGSN
- The end point is [https://app.geosamples.org/sample/igsn](https://app.geosamples.org/sample/igsn) or The old end point is [https://app.geosamples.org/webservices/display.php](https://app.geosamples.org/webservices/display.php)
- Usage: https://app.geosamples.org/sample/igsn/XXXXXXXXX
  - https://app.geosamples.org/webservices/display.php?igsn=XXXXXXXXX
  - XXXXXXXX is the IGSN of a sample. e.g., GEE0000O4, ODP000002
- The service will retrieve most metadata of the sample. It only accepts GET requests from the client program. User name and password are not required. If they are provided, none public accessible sample metadata will be returned also.

# GET API
### Request Headers
- Accept: text/xml, application/xml, application/json, text/json
### Request Body

```
igsn={igsn} username={yourusername} (optional) password={yourpassword} (optional)
```

### Response Body
**HTTP status codes:**
- **400** Bad Request -  IGSN is not valid.
- **403** Forbidden - IGSN is either deactived or has no public metadata.
- **404** Not Found - IGSN not found.
- **200** Successful. It will return metadata related to the IGSN.

**Output format when request is successful ( status code = 200 )**
- **XML Format:**

<pre>
<b>(NEW)</b> The returned xml file uses the following xml schema. https://app.geosamples.org/4.0/downloadSample.xsd
</pre>

<pre>
<b>Notes:</b> To be backward compatible, the old end point (https://app.geosamples.org/webservices/display.php?igsn=XXXXXXXXX)
will return the old XML format if the user executes from the browser or sends ACCEPT header with 'text/html'. The old
format is as follows. <results> <user_code>XXX</user_code><igsn>XXXXXXXXX</igsn><name>myname</name> .... </results> The
old end point was REST-Type so it did not follow HTTP protocol standards. If your client program used any HTTP
standards such as relying on HTTP status code, you need to adjust them according to the current documentation.
</pre>

- **JSON Format:**

```
{ "sample": { "qrcode_img_src": "app.geosamples.org/barcode/image.php?igsn=ODP000002&sample_id=Core 1-1*-1M",
"user_code": "ODP", "igsn": "ODP000002", "name": "Core 1-1*-1M", "sample_type": "Core", "sample_subtype": "Thin
Section", "parent_igsn": "ODP000001", "collection_method": "Coring", "collection_method_description": "M: This
represents material that could not be labeled with a standard core type.  This category includes limited numbers of
cores which are recovered using experimental drilling methods which, once they are established, are assigned their own
core type.", "latitude": "25.8583", "longitude": "-92.1833", "elevation": "-2827", "cruise_field_prgrm": "DSDP Leg 1",
"platform_type": "Ship", "platform_name": "Glomar Challenger", "collector": "Curator", "collector_detail": "Texas A&M
University, Integrated Ocean Drilling Program, College Station, TX, 77845, USA", "current_archive": "Texas A&M
University, Integrated Ocean Drilling Program, College Station, TX, 77845, USA", "current_archive_contact": "Curator",
"original_archive": "Texas A&M University, Integrated Ocean Drilling Program, College Station, TX, 77845, USA",
"original_archive_contact": "Texas A&M University, Integrated Ocean Drilling Program, College Station, TX, 77845, USA",
"parents": { "samples": { "sample": { "igsn": "ODP000001", "name": "Hole 1-1*" } } }, "siblings": { "samples": {
"sample": [ { "igsn": "ODP000003", "name": "Core 1-1*-1R" }, { "igsn": "ODP000004", "name": "Core 1-1*-2R" }, { "igsn":
"ODP000005", "name": "Core 1-1*-3R" }, { "igsn": "ODP000006", "name": "Core 1-1*-40" }, { "igsn": "ODP000007", "name":
"Core 1-1*-5R" }, { "igsn": "ODP000008", "name": "Core 1-1*-6R" }, { "igsn": "ODP000009", "name": "Core 1-1*-7R" }, {
"igsn": "ODP000010", "name": "Core 1-1*-8R" }, { "igsn": "ODP000011", "name": "Core 1-1*-9R" } ] } }, "children": {
"samples": { "sample": [ { "igsn": "ODP01133U", "name": "Section 1-1*-1M-1" }, { "igsn": "ODP01133Y", "name": "Section
1-1*-1M-2" }, { "igsn": "ODP011342", "name": "Section 1-1*-1M-3" }, { "igsn": "ODP011346", "name": "Section 1-1*-1M-4"
}, { "igsn": "ODP01134A", "name": "Section 1-1*-1M-5" }, { "igsn": "ODP01134E", "name": "Section 1-1*-1M-6" }, {
"igsn": "ODP01134I", "name": "Section 1-1*-1M-7" } ] } } } }
```

**Example**

```
curl -X GET -H "accept: application/xml" "https://app.geosamples.org/webservices/display.php?igsn=ODP000002"
```

```
curl -X GET -H "accept: application/xml" "https://app.geosamples.org/sample/igsn/ODP000002" -L
```

```
curl -X GET -H "accept: application/xml" "https://app.geosamples.org/sample/igsn/ODP000002" -L -u yourusername
```
