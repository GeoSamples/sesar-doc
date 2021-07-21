---
name: web_services_overview
title: Overview on Web Services
date: 01/12/2020
layout: default
order: 1
---

### Accessing SESAR's REST web services
SESAR's web services will have restricted access after release v8.0 (July 2021). SESAR's web services provides a possible pathway where individuls can register samples through web services without checks on the quality of the metadata or the mapping of metadata fields. Therefore, access to SESAR's web services will be restricted to ensure quality of registered sample metedata. If you used web services before the release of v8.0, you will be grandfathered into accessing SESAR's web services. If you wish to be a new user of SESAR's web services you must fill out [this request form](https://test-sesar.geosamples.org/views/webservice_request.php). SESAR curators will work with you to ensure that your use of SESAR's web services results in the registration of good, quality metadata. If you want to test usecases of SESAR's web services you can do so with the test endpoint https://sesardev.geosamples.org/webservices 

### SESAR provides following REST web services
1. [Sample registration](https://geosamples.github.io/sesar-doc/web_services/sample_registration.html)
2. [Validate user credentials and get user codes](https://geosamples.github.io/sesar-doc/web_services/validate_user_credentials_and_get_user_code.html)
3. [IGSN list for a specific user code](https://geosamples.github.io/sesar-doc/web_services/igsn_list_for_specific_user_code.html)
4. [IGSN list for a geospatial polygon](https://geosamples.github.io/sesar-doc/web_services/igsn_list_for_geospatial_polygon.html)
5. [IGSN list for a specific field program](https://geosamples.github.io/sesar-doc/web_services/igsn_for_specific_field_program.html)
6. [Sample profile for a specific IGSN](https://geosamples.github.io/sesar-doc/web_services/sample_profile_for_specific_IGSN.html)
7. [Update sample metadata for a specific IGSN](https://geosamples.github.io/sesar-doc/web_services/update_sample_metadata.html)
8. [Get IGSN(s) for a specific user code and a sample name (NEW)](https://geosamples.github.io/sesar-doc/web_services/get_igsns_for_a_specific_user_code_and_a_sample_name.html)
9. [Delete a related URL for a specific IGSN (NEW)](https://geosamples.github.io/sesar-doc/web_services/delete_a_related_url_for_a_specific_igsn.html)  

The end point is [https://app.geosamples.org/webservices/](https://app.geosamples.org/webservices/). The test end point is [https://sesardev.geosamples.org/webservices/](https://sesardev.geosamples.org/webservices/). Before you start to use web services 1, 2, 7, you need to do the following two steps.
  
1. Create a free GeoPass account. Follow [this link](https://geopass.iedadata.org/josso/).
2. Create your namespace(s) or user code(s). Or gain access to other user's namespace(s). Follow [this link](https://geopass.iedadata.org/josso/).
3. Fill out [this request form](https://test-sesar.geosamples.org/views/webservice_request.php)
