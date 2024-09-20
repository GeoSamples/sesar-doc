---
name: validate_user_credentials_and_get_user_code
title: Validate user credentials and get user code
date: 01/12/2020
layout: default
order: 5
---

# Validate user credentials and get user code
Checks that the user credentials or jwt access token are valid. If valid, it will return user code(s). If invalid, it will return error messages. Only POST requests are supported.
  

##### POST API
**URI:** ``` https://app.geosamples.org/webservices/credentials_service_v2.php ```

**Test URI:** ``` https://app-sandbox.geosamples.org/webservices/credentials_service_v2.php ```
## Usage

**JSON Web Token (preferred)**

##### Request Headers for JWT
- Requires a JWT access token in the authorization header of your request
- - Click here for more information: [How to use JWT with SESAR](https://geosamples.github.io/sesar-doc/web_services/how_to_use_jwts.html)


```
curl -H "Authorization: Bearer YOUR_JWT_ACCESS_TOKEN" \
https://app.geosamples.org/webservices/credentials_service_v2.php
```

**Geopass (to be deprecated)**
##### Request Headers for Geopass
- Requires HTTP Basic Authentication header. [http://en.wikipedia.org/wiki/Basic_access_authentication](http://en.wikipedia.org/wiki/Basic_access_authentication)

```
curl -d "username=your_user_name&password=your_password" \
https://app.geosamples.org/webservices/credentials_service_v2.php
```

## Responses
##### Response Body
- **200** Successful. User name and password are valid. It will return user code(s) as following.

```
<results> 
  <valid>yes</valid> 
  <user_codes> <user_code>MOB</user_code> </user_codes> 
</results> 
```

- **401** Unauthorized - A login failure will return text as following.

```
<results> 
  <valid>no</valid> 
  <error>Invalid login, username not known or password not matched</error> 
</results>
```
**Example: PHP script**

```
<?php  

//initialize the parameters
$baseurl="https://app.geosamples.org/webservices/credentials_service_v2.php";

# For Geopass authentication
$username="your_user_name"; 
$password="your_password";
$post_data=array("username"=>$username, "password"=>$password);

$ch = curl_init();   
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_URL, $baseurl);
curl_setopt($ch, CURLOPT_POST, true); 
curl_setopt($ch, CURLOPT_POSTFIELDS, $post_data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);  

# For JWT authentication
$authorization = "Authorization: Bearer YOUR_JWT_ACCESS_TOKEN";
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Content-Type: application/xml' , $authorization));

$response["content"]= curl_exec($ch);
$response["errno"]= curl_errno($ch);
$response["errmsg"] = curl_error($ch);  
$response["header"] = curl_getinfo($ch);

curl_close($ch);
      
return $response;
?> 
```