---
name: sample_registration
title: Sample Registration
date: 01/12/2020
layout: default
order: 2
---

#### Sample Registration
- The web service ``` https://app.geosamples.org/webservices/upload.php ``` allows the client program to register a single sample or multiple samples.This service will automatically create an IGSN or accept user specified IGSN. It will store sample metadata in the system.
- It only accepts POST requests from the client program. GET, PUT and DELETE are not supported.
- <ins>Notes</ins>
  - The older version (v1) [uploadservice.php](https://app.geosamples.org/webservices/uploadservice.php) is deprecated and its bugs will not be fixed. The v1 only supports the [schema v1.0](https://app.geosamples.org/sample.xsd). It does not support later version of the schema ([schema v2.0](https://app.geosamples.org/samplev2.xsd), [schema 3.0](https://app.geosamples.org/3.0/sample.xsd), or [schema 4.0](https://app.geosamples.org/4.0/sample.xsd)). It will not be supported in the future release.
  - **<ins>The current</ins>** [upload web service](https://app.geosamples.org/webservices/upload.php) **<ins>(upload.php) only supports</ins>** [schema 3.0](https://app.geosamples.org/3.0/sample.xsd) **<ins>and</ins>** [schema 4.0](https://app.geosamples.org/4.0/sample.xsd). **<ins>Please update your sample registration XML accordingly.</ins>**
  - <ins>The user should use the following test URI during client program testing, so that the production server will not be populated with test samples:</ins>
     - ``` https://sesardev.geosamples.org/webservices/upload.php ```  
    
##### POST API
**URI** ``` https://app.geosamples.org/webservices/upload.php ```

**TEST URI** ``` https://sesardev.geosamples.org/webservices/upload.php ```

**GeoPass Account:**
- Before you use this web service, you need to create a free GeoPass account. Here is the link to register for a GeoPass account: [https://geopass.iedadata.org/josso/](https://geopass.iedadata.org/josso/).
- After the GeoPass account is created, you need to log in to the SESAR system at least once to create your namespace (user code). Here is the link to log in to SESAR: [https://app.geosamples.org/](https://app.geosamples.org).
- Or the user can request permissions from other user by providing the geopass login to the granter. The granter can set up his or her user code permission on the user profile page.
- The user can only register samples with user codes or namespaces that they own or have write permission to.

##### Request Headers
- Requires HTTP Basic Authentication header. [http://en.wikipedia.org/wiki/Basic_access_authentication](http://en.wikipedia.org/wiki/Basic_access_authentication)
- Accept: text/xml, application/xml, application/json

##### Request Body

```
username={yourusername} password={yourpassword} content={sampleinformation}
```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;where {sample information} is the XML text about sample metadata.

- The XML text should use the following schema. [http://app.geosamples.org/4.0/sample.xsd](http://app.geosamples.org/4.0/sample.xsd).

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Example XML format for registering one sample:**

```
<?xml version="1.0" encoding="UTF-8"?> 
<samples xmlns="http://app.geosamples.org" 
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://app.geosamples.org/4.0/sample.xsd "> 
  <sample>
    <user_code>ABC</user_code> <!-- required --> 
    <sample_type>Individual Sample</sample_type> <!-- required --> 
    <sample_subtype>Thin Section</sample_subtype>
    <name>TestSample123</name> <!-- Required --> 
    <material>Rock</material><!-- required, -->
    <igsn>ABC123456</igsn> <!-- Not Required, If it is not specified, the system will create it automatically. --> 
    <!-- If no classification.xsd is specified, the older format for classification is still supported e.g., Igneous>Plutonic>Felsic --> 
    <classification xmlns="http://app.geosamples.org" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://app.geosamples.org/classifications.xsd"> 
      <Rock>
        <Igneous>
          <Plutonic> 
           <PlutonicType>Felsic</PlutonicType>
          </Plutonic>
        </Igneous>
      </Rock> 
    </classification> <description>arkose</description> 
    <age_min>6.5</age_min> 
    <age_max>13</age_max> 
    <age_unit>years</age_unit> 
    <collection_method>Grab</collection_method> 
    <latitude>35.5134</latitude>
    <longitude>-117.3463</longitude>
    <elevation>781.4</elevation> 
    <primary_location_name>Lava Mountains, Mojave Desert, California </primary_location_name> 
    <country>United States</country> 
    <province>California</province> 
    <county>San Bernardino</county>
    <collector>J. E. Andrew</collector> 
    <collection_start_date>2002-05-30T09:30:10Z </collection_start_date> 
    <collection_date_precision>time</collection_date_precision>
    <original_archive>University of Kansas</original_archive> 
  </sample>
</samples>
```

- You can upload multiple samples by adding the <sample></sample> block nested within the <samples></samples> tag. You can find the XML sample template at this [link](https://app.geosamples.org/4.0/sample.xml).

##### Response Body  
**HTTP status codes:**  
- **200** Sample registered successfully. The response text is like the following.

```
<results> 
  <sample> 
    <status>Sample [Lulin Upload Status Sample test] was saved successfully with IGSN [LLS00009I].</status> 
    <name>Lulin Upload Status Sample test</name> 
    <igsn>LLS00009I</igsn> 
  </sample> 
</results>
```

- **400** Bad Request - Request body either has syntax errors or xml content has errors. Error messages will look like the following.
  - <ins>*XML Syntax error:*</ins>
  
  ```
  <results>
    <valid code="InvalidXML">no</valid> 
    <error>Element '{http://app.geosamples.org}publish_date':[facet'pattern'] The value '2016-03-0' is not accepted by the patter '([0-9]{4}-[0-9]{2})(.........)'
    </error>
  </results>
  ```
  
  - <ins>*XML Content error:*</ins>
  
  ``` 
  <results>
    <sample name="your sample name">
    <valid code="InvalidSample">no</valid>
    <status>Not Saved</status>
    <error>The User Code ABC in your IGSN ABC123456 does not belong to you.</error>
    </sample>
  </results>
  ```
  
- **401** Unauthorized - A login failure will return error message as following:

```
<results>
  <valid code="InvalidAuth">no</valid>
  <error>Invalid login, username not known or password not matched</error>
</results>
```

  
