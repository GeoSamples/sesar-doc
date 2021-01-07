#### Open Geospatial Consortium (OGC) WxS Services
WxS services provides a live access to SESAR sample location map, sample heat map and sample core profile

* WFS provides the access to the top level samples core metadata in SESAR system.
  * WFS: http://prod-app.earthchem.org:8989/geoserver/SESAR/ows?service=WFS&request=GetCapabilities
  
* WMS provides the distribution map of the top level samples in SESAR system.
  * WMS: http://prod-app.earthchem.org:8989/geoserver/SESAR/wms?service=WMS&request=GetCapabilities
  * Demo: http://prod-app.earthchem.org:8989/geoserver/gwc/demo/SESAR:wfs_samples?gridSet=EPSG:4326&format=image/jpeg
