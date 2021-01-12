---
name: rest_services_overview
title: REST Services Overview
date: 01/12/2020
layout: default
---

#### SESAR REST API (Beta v1)
SESAR is undergoing the architecture redesign. Currently it is a monolith application. It will transforme to web services oriented applications. 
The first step is to separate the interwinded web services and application features. The set of standalone REST APIs for interaction with SESAR database have been implemented. 

##### The following existing PHP web services are reimplemented.

* IGSN list for a specific user code
* IGSN list for a geospatial polygon
* IGSN list for a specific field program
* Sample profile for a specific IGSN
* Get IGSN(s) for a specific user code and a sample name (NEW)

##### The swagger documentation can be reached here. https://api.geosamples.org/swagger-ui.html#/ 

* It contains REST APIs which implement the various functions as below.
  * Classification
  * Country
  * GroupSample
  * LaunchType
  * NavType
  * Sample
  * SampleType
  * User counts.
