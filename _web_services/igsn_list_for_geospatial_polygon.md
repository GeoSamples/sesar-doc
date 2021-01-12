---
name: igsn_list_for_geospatial_polygon
title: IGSN list for a geospatial polygon
date: 01/12/2020
---

# IGSN list for a geospatial polygon
- The end point is https://app.geosamples.org/samples/polygon
- Usage: https://app.geosamples.org/samples/polygon/[lon1 lat1, lon2 lat2, lon3 lat3, lon4 lat4, lon1,lat1].
  - [lon1 lat1, lon2 lat2, lon3 lat3, lon4 lat4, lon1 lat1] are points of a concave polygon. Please note that the last point is the same as the first point.
- The service will retrieve all IGSNs whose geo-coordinates are located within the user defined polygon. It only accepts GET requests from the client program. It does not require login and password and supports pagination. If `hide_private` flag is set to 1, it will not return IGSNs whose sample metadata are not public accessible. It supports spatial reference systems transformation.

# GET API
### Request Headers
- Accept: application/xml, application/json, text/xml, text/json
### Request Body
<pre>
<b>lon1 lat1, lon2 lat2, lon3 lat3, lon4 lat4, lon1 lat1</b> = longitudes, latitudes for a polygon <b>limit={limit}</b> maximum IGSN
number for each page. If it is not specified, it will default to 100. <b>page_no={page_no}</b> page number. If it is not
specified, it will default to 1.
</pre>

<pre>
<b> hide_private={1 or 0 or none} default to 0</b>
</pre>

If 1, it will not return IGSNs whose sample metadata are not public accessible.
<pre>
<b>srs={SRID number}</b> Spatial Reference System Identifier (SRID). If it is not specified, it will default to EPSG:4326.
</pre>

### Response Body
**HTTP status codes:**
- **400** Bad Request - User specified polygon is not valid.
- **404** Not Found - No IGSNs associated with the given polygon
- **200** Successful. It will return a list of IGSN(s) as following.

**Output format when request is successful ( status code = 200 ) XML format:**
```
<samples><sample> <igsn>LCZ7700AN</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=LCZ7700AN</url>
</sample> <sample> <igsn>LCZ7700AM</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=LCZ7700AM</url>
</sample> <sample> <igsn>LCZ7700AL</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=LCZ7700AL</url>
</sample> <sample> <igsn>LCZ7700AK</igsn> <url>https://app.geosamples.org/webservices/display.php?igsn=LCZ7700AK</url>
</sample> <total_counts>1489</total_counts> <previous_list>https://app.geosamples.org/samples/polygon/-67.4156
18.6972,-67.4968 17.6568,-65.4526 17.6865,-65.5252 18.5649,-67.4156 18.6972?
limit=4&amp;page_no=1&amp;hide_private=1</previous_list> <next_list>https://app.geosamples.org/samples/polygon/-67.4156
18.6972,-67.4968 17.6568,-65.4526 17.6865,-65.5252 18.5649,-67.4156 18.6972?
limit=4&amp;page_no=3&amp;hide_private=1</next_list> </samples>
```

**JSON format:**
```
{ "igsn_list": [ "LCZ7700AN", "LCZ7700AM", "LCZ7700AL", "LCZ7700AK" ], "total_counts": 1489, "previous_list":
"https://app.geosamples.org/samples/polygon/-67.4156 18.6972,-67.4968 17.6568,-65.4526 17.6865,-65.5252
18.5649,-67.4156 18.6972?limit=4&page_no=1&hide_private=1", "next_list":
"https://app.geosamples.org/samples/polygon/-67.4156 18.6972,-67.4968 17.6568,-65.4526 17.6865,-65.5252
18.5649,-67.4156 18.6972?limit=4&page_no=3&hide_private=1" }
```

***Please note: Total count of IGSNs is tagged as "total_counts" in the returned content. If limits, page numbers, etc. are specified, the returned content will have <previous_list> and <next_list> tags when there are more than one page of IGSNs.***

```
curl -X GET -H "accept: application/xml" "https://app.geosamples.org/samples/
polygon/-67.4156%2018.6972,-67.4968%2017.6568, -65.4526%2017.6865,-65.5252%2018.5649, -67.4156%2018.6972&
hide_private=1&limit=4&page_no=2"
```
```
curl -X GET -H " accept: application/json" "https://app.geosamples.org/samples/
polygon/-67.4156%2018.6972,-67.4968%2017.6568, -65.4526%2017.6865,-65.5252%2018.5649, -67.4156%2018.6972&
hide_private=1&limit=4&page_no=2"
```
```
NEW curl -X GET -H " accept: application/json" "https://app.geosamples.org/samples/
polygon/-43096291.5430165%20223829530.742031, -53338557.3468762%20277024863.02079,
87260142.0817049%20268278668.61794,70504128. 9133862%20216762812.731158,-43096291.5430165%20223829530.742031
&srs=3031&hide_private=1& limit=4&page_no=2"
```
