---
name: index
title: Documentation Overview
date: 01/12/2020
layout: default
order: 1
---


SESAR, the System for Earth Sample Registration, operates a global digital index of samples, specimens, and related sampling features from our natural environment. SESAR provides services to support the management and sharing of these materials, which includes metadata registration and issuing IGSN IDs (globally unique identifiers for samples and specimens).  

Our application was built in 2005. After two major re-implementations with architecture improvements, SESAR is now implemented by PHP and Javascript programming languages. We offer a set of web services to allow client programs to interact with SESAR systems. SESAR uses GeoPass as its single-sign-on for a secure login. We will soon support ORCID as a second authentication method. GeoPass single-sign-on service is maintained by EarthChem organization.  
SESAR implemented and released a Beta version of our web service REST API in 2020. In addition to our web services, SESAR also provides WMS and WFS for external application integration.   

SESAR is part of the [iSamples project](http://isamples.org/). iSamples a multi-disciplinary and multi-institutional project funded by NSF to expand and integrate discipline-specific infrastructure for material samples and sample metadata.  Changes and advances in our application as we integrate with the iSamples system will be documented on this site. Please contact us with any questions or suggestions: [info@geosamples.org](info@geosamples.org)  

### System Requirements:
#### Database Server:   
PostgreSQL: version 12.11
PostGIS: version 2.5.5

#### Application Server:  
PHP: version 8.0.8(cli) (built: Mar 3 2022)  
OS Version: Ubuntu 21.10 (Impish Indri)
Apache: version 2.4.48
