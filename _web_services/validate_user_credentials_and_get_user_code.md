---
name: validate_user_credentials_and_get_user_code
title: Validate user credentials and get user code
date: 01/12/2020
layout: default
order: 3
---

# Validate user credentials and get user code
- The web service is at: [https://app.geosamples.org/webservices/credentials_service_v2.php](https://app.geosamples.org/webservices/credentials_service_v2.php).
- It will check the user's credentials. If valid, it will return user code(s). If not valid, it will return error messages. It only accepts POST requests from the client program. GET, PUT and DELETE are not supported.
- <ins>Notes</ins>
  - (Deprecated) The older version v1 end point is [https://app.geosamples.org/webservices/credentials_service.php](https://app.geosamples.org/webservices/credentials_service.php)
  - Starting from version 2, the user is allowed to access other user's user code with different permissions. In v1 the user has to create a user code for his/her samples .
  
**Before you use this web service, you need to do the following two steps:**
- Create a free GeoPass account. Follow this [link](https://geopass.iedadata.org/josso/).
- Log in to the SESAR system to create your namespace or user code. If you would like to use other user's user code, you can login to the system and make a request. Follow this [link](https://geopass.iedadata.org/josso/).

# POST API
**URI:** [https://app.geosamples.org/webservices/credentials_service_v2.php](https://app.geosamples.org/webservices/credentials_service_v2.php)

### Request Headers
- Requires HTTP Basic Authentication header. [http://en.wikipedia.org/wiki/Basic_access_authentication](http://en.wikipedia.org/wiki/Basic_access_authentication)
- Accept: text/xml, application/xml

### Request Body

```
username={yourusername} password={yourpassword}
```

### Response Body
- **200** Successful. User name and password are valid. It will return user code(s) as following.

```
<results> <valid>yes</valid> <user_codes> <user_code>MOB</user_code> </user_codes> </results> 
```

- **401** Unauthorized - A login failure will return text as following.

```
<results> <valid>no</valid> <error>Invalid login, username not known or password not matched</error> </results>
```

**Usage Examples:**

**Example 1:**

```
command line example curl --data " username=your_user_name& password=your_password"  
https://app.geosamples.org/ webservices/credentials_service_v2.php
```

**Example 2**

```
<?php  function curl_http_post_request($requestdata) {     $ch = curl_init();   curl_setopt($ch,CURLOPT_SSL_VERIFYPEER,
false); curl_setopt($ch, CURLOPT_URL, $requestdata["url"]);   curl_setopt($ch,CURLOPT_POST,true); 
curl_setopt($ch,CURLOPT_POSTFIELDS, $requestdata["data"]);      curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);  
$result["content"]= curl_exec($ch);  $result["errno"]= curl_errno($ch); $result["errmsg"] = curl_error($ch) ;  
$result["header"] = curl_getinfo($ch);  curl_close($ch);      return $result; }    
$baseurl=" https://app.geosamples.org/ webservices/credentials_service_v2.php";  $username="your_user_name"; 
$password="your_password";  $requestinfo["url"]=$baseurl;  requestinfo["data"]=array ("username"=>$username, 
"password"=>$password);   $result=curl_http_post_request($requestinfo);   
echo $result["content"].PHP_EOL;  echo $result["header"]["http_code"].PHP_EOL;  echo $result["errno"].PHP_EOL;  
echo $result["errmsg"].PHP_EOL;  ?> 
```
