---
name: ogc_wxs
title: Open Geospatial Consortium (OGC) Overview
date: 01/12/2020
layout: default
---

#### Open Geospatial Consortium (OGC) WxS Services
WxS services provides a live access to SESAR sample location map, sample heat map and sample core profile

* WFS provides the access to the top level samples core metadata in SESAR system.
  * WFS: https://prod-app.earthchem.org/geoserver/SESAR/ows?service=WFS&request=GetCapabilities
  
* WMS provides the distribution map of the top level samples in SESAR system.
  * WMS: https://prod-app.earthchem.org/geoserver/SESAR/wms?service=WMS&request=GetCapabilities
  * Demo: https://prod-app.earthchem.org/geoserver/gwc/demo/SESAR:wfs_samples?gridSet=EPSG:4326&format=image/jpeg
