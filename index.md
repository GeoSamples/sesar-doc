---
name: index
title: Documentation Overview
date: 01/12/2020
layout: default
order: 1
---


SESAR, the System for Earth Sample Registration, operates a global digital index of samples, specimens, and related sampling features from our natural environment.  SESAR provides services to support the management and sharing of these materials which includes metadata registration and issuing IGSNs (globally unique identifiers for samples and specimens).  

Our application was built in 2005. After two major re-implementation with architecture improvements, it is now implemented by PHP and Javascript programming languages. We offer a set of web services to allow the client programs to interact with SESAR systems. SESAR uses GeoPass as its single-sign-on for secure login. We will soon support ORCID as a second authentication method. GeoPass single-sign-on service is maintained by EarthChem organization.  
SESAR implemented and released a Beta version of our web service REST API in 2020. In addition to our web services, SESAR also provides WMS and WFS for external application integration.   

SESAR is part of the [iSamples project](http://isamples.org/). iSamples a multi-disciplinary and multi-institutional project funded by NSF to expand and integrate discipline-specific infrastructure for material samples and sample metadata (like SESAR).  Changes and advances in our application as we integrate with the iSamples system will be documented on this site Please contact us with any questions or suggestions: [info@geosamples.org](info@geosamples.org)  

### System Requirements:
#### Database Server:  
OS Version: Red Hat Enterprise Linux Server release 6.10 (Santiago)  
PostgreSQL: version 9.0.3  
PostGIS: version 1.5.1  

#### Application Server:  
PHP: version 5.4.45(cli) (built: Mar 1 2018)  
OS Version: Red Hat Enterprise Linux Server release 7.4 (Maipo)  
Apache: version 2.4.6  
