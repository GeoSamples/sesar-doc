---
name: update_sample_metadata
title: Update Sample Metadata
date: 01/12/2020
layout: default
---

# Update Sample Metadata
- The web service [https://app.geosamples.org/webservices/update.php](https://app.geosamples.org/webservices/update.php) allows the client program to update registered sample(s) metadata profile(s).
- It only accepts POST requests from client programs. GET, PUT and DELETE are not supported.
- <ins>Notes</ins>
  - <ins>The user should use the following test URI during client program testing, so production sample profiles are not accidentally edited.</ins>
    - [https://sesardev.geosamples.org/webservices/update.php](https://sesardev.geosamples.org/webservices/update.php)
  - <ins> New:</ins> The user can replace an existing URL using 'old_url' element. See document in updateSample.xsd schema file
  
  ``` 
  E.G. <external_urls><external_url><old_url>http://oneurl.tobereplaced.org </old_url><url>http://oneurl.new.org</url>
  </external_url></external_urls>
  ```
  
# POST API
**URI:** [https://app.geosamples.org/webservices/update.php](https://app.geosamples.org/webservices/update.php)  
**TEST URI:** [https://sesardev.geosamples.org/webservices/update.php](https://sesardev.geosamples.org/webservices/update.php)  

### Request Headers
- Requires HTTP Basic Authentication header. http://en.wikipedia.org/wiki/Basic_access_authentication
- Accept: text/xml, application/xml
### Request Body

```
username={yourusername} password={yourpassword} content={sampleinformation} 
```

where {sampleinformation} is the xml text.
- The text should use the following schema. [https://app.geosamples.org/4.0/updateSample.xsd](https://app.geosamples.org/4.0/updateSample.xsd).

**Example XML format for updating one sample profile:**

```
<?xml version="1.0" encoding="UTF-8"?> <samples xmlns="http://app.geosamples.org"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://app.geosamples.org/4.0/updateSample.xsd "> <sample> <sample_type>Individual
Sample</sample_type> <sample_subtype>Thin Section</sample_subtype> <name>TestSample123</name> <material>Rock</material>
<igsn>ABC123456</igsn> <!-- Required. --> <!-- If no classification.xsd is specified, the older format for
classification is still supported e.g., Igneous>Plutonic>Felsic --> <classification xmlns="http://app.geosamples.org"
xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://app.geosamples.org/classifications.xsd"> <Rock><Igneous> <Plutonic>
<PlutonicType>Felsic</PlutonicType> </Plutonic> </Igneous></Rock> </classification> <description>arkose</description>
<age_min>6.5</age_min> <age_max>13</age_max> <age_unit>years</age_unit> <collection_method>Grab</collection_method>
<latitude>35.5134</latitude> <longitude>-117.3463</longitude> <elevation>781.4</elevation> <primary_location_name>Lava
Mountains, Mojave Desert, California </primary_location_name> <country>United States</country>
<province>California</province> <county>San Bernardino</county> <collector>J. E. Andrew</collector>
<collection_start_date>2002-05-30T09:30:10Z </collection_start_date>
<collection_date_precision>time</collection_date_precision> <original_archive>University of Kansas</original_archive> 
</sample> </samples>
```

- You can update multiple samples by adding the <sample></sample> block nested into the <samples></samples> tag.

### Response Body
**HTTP status codes:**
- **200** Sample registered successfully. The response text is as follows:

```
<results> <sample> <status>Sample [Lulin Update Status Sample test] was updated successfully with IGSN [LLS00009I].
</status> <name>Lulin Update Status Sample test</name> <igsn>LLS00009I</igsn> </sample> </results>
```

- **400** Bad Request - Request body either has syntax errors or xml content has errors. Error messages will look like the following.
  - <ins>*XML Syntax error:*</ins>
  
  ```
  <results> <valid code="InvalidXML">no</valid> <error>Element '{http://app.geosamples.org}user_code':......</error> 
  </results>
  ```
  
  - <ins>*XML Content error:*</ins>
  
  ``` <results> <sample name="your sample name"> <valid code="InvalidSample">no</valid><status>Not Saved</status> <error>You 
  do not have permission to edit the sample metadata.</error> ...... </sample> </results>
  ```
  
- **401** Unauthorized - A login failure will return text as follows.

```
<results> <valid code="InvalidAuth">no</valid> <error>Invalid login, username not known or password not matched</error> 
</results>
```

***
For more information, please visit the [IEDA web services page](https://www.iedadata.org/help/web-services/#rest) or its [technical API documentation](https://www.iedadata.org/help/web-services/).

Currently, web services are used for sample registration or update by the GEOCHRON data system, Smithsonian Institution, etc.

If you are interested in establishing interoperability with SESAR, please contact info@geosamples.org.
