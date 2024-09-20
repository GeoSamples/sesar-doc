---
name: delete_a_related_url_for_a_specific_igsn
title: Delete a related URL for a specific IGSN (NEW)
date: 01/12/2020
layout: default
order: 12
---

# Delete a related URL for a specific IGSN (NEW)
- The web service ```https://app.geosamples.org/webservices/deletePubURL.php``` allows the client program to delete a URL that is associated with an IGSN.
- It only accepts POST requests from client programs. GET, PUT and DELETE are not supported.
- <ins>Notes:</ins>
  - <ins>The user should use the following test URI during client program testing, so production sample profiles are not accidentally edited.</ins>
  - ```http://app-sandbox.geosamples.org/webservices/deletePubURL.php```

##### POST API
**URI:** ```https://app.geosamples.org/webservices/deletePubURL.php```

**TEST URI:** ```https://app-sandbox.geosamples.org/webservices/deletePubURL.php```

## Usage

**JSON Web Token (preferred)**

##### Request Headers for JWT
- Requires a JWT access token in the authorization header of your request
- - Click here for more information: [How to use JWT with SESAR](https://geosamples.github.io/sesar-doc/web_services/how_to_use_jwts.html)


```
curl \
-X POST \
-H "Content-Type: application/xml" \
-H "Authorization: Bearer YOUR_JWT_ACCESS_TOKEN" \
-d "igsn=your_igsn&puburl=url_to_be_deleted" \
https://app.geosamples.org/webservices/credentials_service_v2.php
```

**Geopass (to be deprecated)**
##### Request Headers for Geopass
- Requires HTTP Basic Authentication header. [http://en.wikipedia.org/wiki/Basic_access_authentication](http://en.wikipedia.org/wiki/Basic_access_authentication)

```
curl \
-X POST \
-H "Content-Type: application/xml" \
-d "username=your_user_name&password=your_password&igsn=your_igsn&puburl=url_to_be_deleted" \
https://app.geosamples.org/webservices/credentials_service_v2.php
```

##### Response Body
**HTTP status codes:**
- **200** The URL is successfully deleted. The response text is as follows.

```
<results> 
  <sample> 
  <status>Publication URL(http://www.earthchem.org) is deleted successfully.</status>
  <igsn>SES000001</igsn> 
  </sample> 
</results>
```

**400** Bad Request - Request body contains invalid values. Error messages will look like the following.

```
<results> 
  <error> Error: Specified URL or IGSN not found. </error> 
</results>
```

**401** Unauthorized - A login failure will return text as follows.

```
<results> 
  <valid code="InvalidAuth">no</valid> <error>Invalid login, username not known or password not matched</error> 
</results>
```

**Example:**

```
curl -X POST -H "accept: application/xml" -d "username=yourusername&puburl=http://www.earthchem.org&password=yourpassword&igsn=SES000001";
```
