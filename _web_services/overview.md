---
name: web_services_overview
title: Overview on Web Services
date: 01/12/2020
layout: default
order: 1
---

<!---
<style>
.alert{
    background: #ddab5f;
    color: #fff;
    box-shadow: 0 2px 4px -2px rgb(0 0 0 / 50%);
    padding: 10px;
    margin: 20px auto;
}
</style>

<div class="alert">
    <h2> Attention: </h2>
    <p>SESAR will be undergoing a server maintenance on Thursday August 26th 2021 from 10:00am ET to 1:00pm ET. This will cause interruptions in our web services. Please refrain from uploading new samples or conducting updates using web services during this time. We apologize for any inconvenience this may cause. Thanks, SESAR Team.</p>
</div>
-->


### Accessing SESAR's PHP web services
SESAR's web services will have restricted access after release v8.0 (22 July 2021). SESAR's web services provides a possible pathway where individuls can register samples directly through web services without undergoing curatorial review. Therefore, access to SESAR's web services will be restricted to ensure quality of registered sample metedata. If you had a MySESAR account prior to the release of v8.0, you will be grandfathered into accessing SESAR's web services. New user of SESAR's web services must fill out [this request form](https://app.geosamples.org/views/webservice_request.php). SESAR curators will work with you to ensure that your use of SESAR's web services results in the registration of good, quality metadata. If you want to test usecases of SESAR's web services you can do so with the test endpoint ``` https://sesardev.geosamples.org/webservices ```

### SESAR provides following PHP web services
1. [Sample registration](https://geosamples.github.io/sesar-doc/web_services/sample_registration.html)
2. [Validate user credentials and get user codes](https://geosamples.github.io/sesar-doc/web_services/validate_user_credentials_and_get_user_code.html)
3. [IGSN list for a specific user code](https://geosamples.github.io/sesar-doc/web_services/igsn_list_for_specific_user_code.html)
4. [IGSN list for a geospatial polygon](https://geosamples.github.io/sesar-doc/web_services/igsn_list_for_geospatial_polygon.html)
5. [IGSN list for a specific field program](https://geosamples.github.io/sesar-doc/web_services/igsn_for_specific_field_program.html)
6. [Sample profile for a specific IGSN](https://geosamples.github.io/sesar-doc/web_services/sample_profile_for_specific_IGSN.html)
7. [Update sample metadata for a specific IGSN](https://geosamples.github.io/sesar-doc/web_services/update_sample_metadata.html)
8. [Get IGSN(s) for a specific user code and a sample name (NEW)](https://geosamples.github.io/sesar-doc/web_services/get_igsns_for_a_specific_user_code_and_a_sample_name.html)
9. [Delete a related URL for a specific IGSN (NEW)](https://geosamples.github.io/sesar-doc/web_services/delete_a_related_url_for_a_specific_igsn.html)  

The production end point is ```https://app.geosamples.org/webservices/```. The test end point is ```https://sesardev.geosamples.org/webservices/```. Before you start to use web services 1, 2, 7, you need to do the following three steps.
  
1. Create a free GeoPass account. Follow [this link](https://geopass.iedadata.org/josso/).
2. Create your namespace(s) or user code(s). Or gain access to other user's namespace(s). Follow [this link](https://app.geosamples.org/index.php).
3. Fill out [this request form](https://app.geosamples.org/views/webservice_request.php)
