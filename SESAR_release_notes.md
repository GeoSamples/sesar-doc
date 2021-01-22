# SESAR - Release Notes

Version | Release Date | Summary 
------- | ------------ | ------- 
[v 7.4.2](#version-742) | November 2020 | Update of security features, Bug fixes 
[v 7.4.1](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-741) | July 2020 | Implementation of JSON-D, Bug fixes 
[v 7.4.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-740) | February 2020 | New features including file upload, export to ECL templates, Bug fixes 
[v 7.3.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-730) | July 2019 | Improved validations in batch upload process, Bug fixes
[v 7.2.2](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-722) | November 2018 | New version of web service schema, Bug fixes
[v 7.2.1](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-721) | October 2018 | Minor bug fixes  
[v 7.2.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-720) | October 2018 | New object type, Bug fixes  
[v 7.1.2](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-712) | September 2018 | Improved web services, Bug fixes 
[v 7.1.1](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-711) | April 2018 | New feature to view sample locations during upload  
[v 7.1.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-710) | January 2018 | Sample release date implementation 
[v 7.0.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#sesar-version-700) | July 2017 | Sample metadata batch update implementation, Bug fixes  
[v 6.4.3](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-643) | September 2016 | Batch upload speed improvement, New IGSN searching feature 
[v 6.4.2](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-642) | June 2016 | Improvements downloading files 
[v 6.4.1](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-641) | April 2016 | Ability to view user permissions, Error message standardization 
[v 6.4.0 (beta)](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#640-beta) | March 2016 | New sample registration features, Various MySESAR improvements 
[v 6.3.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-630) | July 2015 | New web service features, Improvements to batch registration fields 
[v 6.2.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-620) | March 2015 | New web service features, Bug fixes 
[v 6.1.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-610) | February 2015 | Improvements to metadata display, Bug fixes 
[v 6.0.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-600) | November 2014 | Improved security, Bug fixes 
[v 5.1.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-510) | October 2014 | Improved web services, Bug fixes 
[v 5.0.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-500) | July 2014 | New user code syntax, New web service 
[v 4.6.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-460) | May 2014 | New sub-object types available, Bug fixes 
[v 4.5.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-450) | February 2014 | IGSN deactiviation, Improvements to supplemental file uploads 
[v 4.4.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-440) | October 2013 | MySESAR updates, Custom label printing 
[v 4.3.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-430) | July 2013 | Sample Grouping, Batch upload improvements 
[v 4.2.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-420) | March 2013 | Batch Registration Updates, Enhanced Classification 
[v 4.1.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-410) | January 2013 | Time zone in UTC, Label Printing 
[v 3.8.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-380) | February 2012 | Improved Search Interface, QR code introduction, Help with sample registration 
[v 3.0.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-300) | 2010 | Customizable submission templates, Supplemental files for samples, GeoPass introduction 

### Version 7.4.2 
- November 24, 2020
```
1. Enhancement: Clarified instructions for transfer of sample 
ownership.
2. Enhancement: Added validations for ‘Relation to Parent’ 
fields
3. Enhancement: Updated security features to support https 
instead of http (including a SSL certificate) for pages which 
display maps.
4. Enhancement: Updated validations in administrative tools.
5. Bug Fix: Web services credentials now support LATIN1 encoding.
6. Bug Fix: Edit page now allows users to remove parent IGSN 
from record.
7. Bug Fix: Corrected error which allowed users to set release 
date more than 2 years in the future.
8. Bug Fix: Removed outdated syntax information from error message 
when resolving an invalid IGSN.
9. Bug Fix: Removed limitation which prevented acceptance of large 
scale transfer of samples.
10. Bug Fix: Resolved issue where resetting password in GeoPass 
was not propagating to web services.
```

### Version 7.4.1 
- July 27, 2020
```
1. New Feature: Added JSON-LD (a format for machine to machine 
communication) into the HTML header for SESAR sample profile 
pages. You can read about the role of JSON-LD in the IGSN ecosystem 
here.
2. New Feature: Created sitemaps for SESAR’s top level IGSNs. To be
used in conjunction with the JSON-LD.
3. New Feature: A REST API endpoint has been deployed to support the 
registration of IGSNs in SESAR. Documentation can be found here.
4. Enhancement: A latitude and longitude display has been added to 
our map search feature. As your mouse moves over the map, the 
latitude and longitude of the location you hover above is displayed 
at the bottom of the map.
5. Enhancement: The confirmation message displayed to users after 
submitting a batch registration has been updated.
6. Bug Fix: Fixed a bug in the batch registration process which caused 
a failure based on the cell formatting of the date fields in EXCEL.
7. Bug Fix: Fixed a bug in the map projection.
8. Bug Fix: Fixed a bug in the web services. The URL validation was 
failing if there were multiple redirects for a DOI.
9. Bug Fix: Fixed a bug in the image upload tool that allowed 
uploads of files which exceed our storage limits. Clarifications were 
made to the text associated with the tool.
10. Database Improvements: the SESAR database was migrated to a 
new server.
```


### Version 7.4.0 
- February 6, 2020
```
1. New Feature: File upload feature implemented. Users may now 
upload files at one click. Files are limited to the size of 
4Mbs. Only three files per IGSN are allowed. Each user code is 
limited to 1000 files. The feature supports uploading: one file 
associated with multiple IGSNs; multiple files associated with 
one IGSN; and multiple files associated with multiple IGSNs
2. New Feature: Users may now export SESAR sample data for the 
EarthChem Library templates using the ‘My Sample Group’ feature. 
Users can export four different groups of sample data: a combined 
export for Bulk Elemental Analyses/In Situ Mineral or Glass 
Analyses (EMP)/Bulk Isotope Analyses/In Situ Melt Inclusion Analyses, 
and individual files for Soil Analyses, Vent Fluids, and 
Volcanic Gases.
3. New Feature: Users may now update which image is the primary 
image from the associated files for an IGSN.
4. New Feature: Metadata completeness indicators have been added
to the sample profile page and the search results page. Icons 
include Geolocation, Geological Age, Collection Method, Classification, 
and an indicator for primary image. Icons will be visible 
when associated metadata fields have been completed.
5. New Feature: Web services now support publication URL deletion
and retrieving an IGSN by sample name for a specific user code.
6. New Feature: Added a ‘View on Map’ feature which allows users 
to view catalog search results on a map.
7. Enhancement: ‘My Sample Group’ page now generates a URL for 
sharing groups. Users may export sample data for IGSNs in a group 
to ECL templates.
8. Enhancement: Extended downloads of large files from the 
My Samples/Shared Samples pages will now be broken up into 
multiple 
CSV files with 5000 samples per file which are then downloaded 
as a zip 
file.
9. Enhancement: Provide recommended archive organization names 
in search, individual sample registration, and on sample edit page. 
Search for archive 
name now case insensitive.
10. Enhancement: The SESAR Quick Guide has been updated (SESAR 
Quick Guide v7).
11. Enhancement: Standardized IGSN landing page URLs in exports, 
display, printable labels, and in QR Code image.
12. Enhancement: Added a validation which prevents users from 
registering a sample name as only a space.
13. Enhancement: Allow users to edit sample metadata on the 
same day as the publish date.
14. Enhancement: Allow users to enter collection dates formatted 
as YYYY or YYYY-MM in addition to YYYY-MM-DD.
15. Enhancement: Search queries now ignore space, /, >, -, _ in 
the ‘Field Program / Cruise’ field.
16. Bug Fix: Fixed bugs in the primary image thumbnail and URL.
17. Bug Fix: Fixed a bug where the user requested deletion of a 
file associated with an IGSN but the file was not removed from 
the server.
18. Bug Fix: Fixed a bug in the Search download, My Group export, 
and My Samples download where downloaded files did not reflect 
precision information in collection start/end.
19. Bug Fix: Fixed a bug that when a user changed their password 
on the GeoPass server, the credential check for the Web Services 
failed.
20. Bug Fix: Fixed a bug in the release date validation during 
the batch upload process.
```

### Version 7.3.0 
- July 16, 2019
```
1. Bug Fix: Sample names containing only ‘space’ are no longer 
allowed. Related validations and error messages improved.
2. Bug Fix: Improved validation of release date in batch 
registration so that samples could not be registered with release 
dates more than two years in the future.
3. Bug Fix: Fixed a bug where the sub-object type was not written 
out to the downloaded batch registration template.
4. Bug Fix: Fixed a bug where batch update failed to update 
elevation start and end.
5. Bug Fix: Fixed a bug in total sample count for a group, which 
caused pagination to work improperly.
6. Bug Fix: Fixed a bug where the classification field was overwritten
when users left the field blank during single sample edit.
7. Enhancement: Added email address validation for requests to 
contact sample owners.
8. Enhancement: Improved validation for classification and material 
fields during batch upload and update.
9. Enhancement: Elevation Start, Elevation End, Depth (min), and 
Depth (max) are now displayed for all object types.
10. Enhancement: Improved the sample search so that it is no longer 
case sensitive and to allow for searches by “contains”, 
“ends with”, and partial matching.
11. Enhancement: Improved database schema to remove legacy and 
obsolete columns, add primary id and keys to tables without them, 
and remove temporary tables and redundant foreign keys.
```


### Version 7.2.2 
- November 16, 2018
```
1. Enhancement: Improved validations and error messages related to 
the fields of Sub-Object Type and Classification. 
2. Enhancement: Sub-Object Type is now displayed alongside Object 
Type on all lists, pages, and search results.
3. Enhancement: Implemeneted a new version (4.0) of web service 
schema. All related web services such as sample upload, update, 
and profile retrieve are updated to support the new schema.
4. Bug Fix: Fixed a bug that caused "Material" or "Classification" 
fields to be overwritten when not specified in a batch update 
template or update web service XML file, and backfilled missing 
values. 
5. Bug Fix: Fixed a bug that displayed incorrect sample numbers 
when using the polygon search. 
6. Bug Fix: Updated JQuery library to use https to avoid sometimes 
occuring blank pages. 
```


### Version 7.2.1 
- October 18, 2018
```
1. Bug Fix: Minor bug fix.
```

### Version 7.2.0 
- October 16, 2018
```
1. Enhancement: Added Deleted Sample(s) to the My Samples block on 
the home page.
2. New Feature: "Experimental Specimen" is now an accepted object 
type with the sub-sample types of "Thin Section" or "Other". 
This change is reflected in the template generator as well as the 
drop down and pick lists. This new type is currently supported 
on batch upload, batch update, single sample registration and sample 
profile edit page.
3. Bug Fix: Fixed a bug which occasionally caused the home page 
to go blank.
4. Bug Fix: Fixed a bug so that the database records the user who 
updates sample metadata.
```

### Version 7.1.2 
- September 7, 2018
```
1. Enhancement: Improved the clarity of error messages returned 
when using web services.
2. Bug Fix: Fixed a bug which returned an error when templates 
containing reserved symbols were uploaded.
3. Bug Fix: Fixed a bug which caused an offset in the display of 
sample locations in the SESAR batch upload map preview.
```

### Version 7.1.1 
- April 25, 2018
```
1. New Feature: An option to preview sample locations on a map is 
now provided when you upload a SESAR batch registration or batch 
upload template. You can access the map by clicking "View Locations 
on Map." Locations are only shown if you have entered values for 
Latitude and Longitude (not UTM). You can see if samples plot in 
expected locations and, if not, you can adjust coordinates in your 
batch template and re-upload it, eliminating the need to edit 
sample metadata at a later time or involve the SESAR curator.
2. Enhancement: Additional text was added to clarify changes made 
in the batch template in SESAR v.7.1.0. Changes were made to the 
template in order to enable easier assignment of sample metadata 
release dates.
3. Enhancement: Sequence requirement for external URLs in sample 
registration web service was removed.
4. Bug Fix: Sub-object type is now correctly retained or updated 
using SESAR batch update.
```


### Version 7.1.0 
- January 18, 2018
```
1. New Feature: Users may now set release dates for samples through 
individual sample registration, batch registration, and through 
the registration web service.
2. New Feature: Users may now update release dates for samples by 
editing individual sample profiles in MySESAR, using the MySESAR 
batch update functionality, or using the update web service.
3. New Feature: A new batch registration template can now be 
downloaded from MySESAR. This new template allows users to specify
different 
release dates for each sample in the template, rather than setting 
a single release date for all samples in the template. If no 
release dates are specified, sample metadata will be publicly 
accessible immediately (recommended).
4. New Feature: An email notification will now be sent to SESAR 
users one month before their sample metadata release dates. This 
email will notify users of the upcoming release dates and 
recommend steps for editing release dates if desired.
5. Improvement: The is_private field was deprecated. Previously, 
metadata accessibility was controlled by both is_private flag 
and the release date (called publish_date). Now, metadata 
accessibility is controlled solely by release date.
6. Improvement: Formatting for dates (e.g., collection date) in 
batch registration templates has been relaxed. Acceptable date 
formats now include YYYY-MM-DD and MM/DD/YYYY. Date cells no 
longer have to be formatted as text.
7. Improvement: Added documentation to each PHP script.
8. Bug Fix: Added validation to ensure that collection end date 
is after collection start date.
```


### SESAR Version 7.0.0 
- July 26, 2017
```
1. New Feature: Users may now update sample metadata for existing
samples in bulk by uploading a batch template, a method that is 
very similar to the initial batch registration mechanism. Check 
out this tutorial about the new functionality.
2. New Feature: Users can now assign IGSNs of up to 32 characters 
in length (A-Z, 0-9, '-', '.'). The new syntax follows 
recommendations of the IGSN e.V. at http://igsn.github.io/syntax/. 
The extended syntax is primarily intended for use by large 
repositories, where it may be necessary to use hierarchical syntax 
conventions. However, in consideration of human readability as 
well as the fact that the IGSN will appear on-line and in print, 
the IGSN e.V. recommends that the IGSN should be as concise as 
possible. If you are considering assigning IGSNs to your samples 
that are longer than 9 characters, please contact info@geosamples.org 
to discuss.
3. New Feature: Users can now specify Elevation Unit when 
registering samples (must be either feet, meters, miles, 
or kilometers).
4. New Feature: A Help button has been added to the top row of 
tabs in MySESAR.
5. Improvement: A 'Go Back' button has been added to each sample
profile page.
6. Improvement: The initial page users see when they log into 
MySESAR for the first time was restructured and enhanced with 
additional help text.
7. Improvement: On the batch template creator page in MySESAR, 
selecting either Northing, Easting, or Zone will automatically 
select the other two choices for inclusion in the downloaded 
template.
8. Improvement: The My Account tab in MySESAR has been enhanced 
to include additional help text and functionalities for user 
code management.
9. Bug fix: Parent IGSN validation bug fixed for individual sample
registration.
10. Bug fix: Sample XML schema bug fixed for material validation.
11. Bug fix: Sample ownership transfer bug fixed for when Geopass 
ID does not match with the email address specified by the user in 
the My Account tab of MySESAR.
```

### Version 6.4.3 
- September 1, 2016
```
1. New Feature: If others have shared permissions with you to view,
edit, and/or register sample metadata on their behalf in SESAR, you 
can now view what permissions you have on the My Account tab in 
MySESAR.
2. Improvement: batch upload speed was significantly reduced, 
particularly for large batches of samples.
3. New Feature: users can now search by multiple IGSNs in the SESAR 
catalog.
4. Improvement: error messages for batch and individual sample 
registration in MySESAR were clarified and standardized.
```

### Version 6.4.2 
- June 23, 2016
```
1. Improvement: Large files with metadata for a large number of 
samples can now more easily be downloaded from the SESAR search 
catalog.
2. Improvement: downloaded files of sample metadata from SESAR now 
contain a clickable hyperlink to the sample metadata profiles of 
each sample.
```

### Version 6.4.1 
- April 28, 2016
```
1. New Feature: If others have shared permissions with you to view,
edit, and/or register sample metadata on their behalf in SESAR, you 
can now view what permissions you have on the My Account tab in 
MySESAR.
2. Improvement: error messages for all SESAR web services were 
clarified and standardized.
```

### 6.4.0 (beta) 
- March 11, 2016
```
1. New Feature: If they own more than one namespace, SESAR users 
can now choose which namespace to use as prefix for IGSNs when they 
upload a batch registration template.
2. New Feature: a new field for users to specify sample other names 
has been added.
3. New Feature: users may now specify ORCID numbers in their 
account profile.
4. New Feature: there is now the option to contact the owner of a 
sample at the bottom of each public sample metadata profile.
5. New Feature: users can now filter samples by user code in 
MySESAR.
6. New Feature: SESAR users can now assign permissions to others 
to view, edit, and/or register sample metadata on their behalf. This 
substantial new functionality is described in more detail here.
7. New feature: a new sample metadata update web service now exists 
for updating sample metadata in bulk programmatically.
8. New Feature: a new web feature service provides access to the 
core metadata for top level samples.
9. New Feature: a new web map service provides the distribution map 
of top level samples in SESAR.
10. Improvement: error messages in single sample registration are 
now more clear and specific.
11. Improvement: the performance of the sample upload web service 
has been improved, greatly reducing the time necessary to register 
samples.
12. Improvement: the date string on printed labels and in sample 
profiles now reflects precision as indicated in the collection date 
precision field.
13. Improvement: the speed of page loading in MySESAR has been 
improved.
14. Improvement: downloading large amounts of sample metadata has 
now been streamlined. Metadata are now written out into CSV files 
with metadata for 5000 samples each.
15. Improvement: SESAR users can now run multiple searches of the 
SESAR catalog concurrently in multiple tabs.
16. Improvement: SESAR samples can now be discovered through the 
IEDA Data Browser. Once a user selects samples of interest, he/she 
can click "Explore", which will take the user to the SESAR catalog 
to further define search criteria.
17. Bug Fix: pagination for samples from a particular cruise has 
been improved. By default, 25 samples will be shown per page, with 
the option to show less or all per page.
```

### Version 6.3.0
- July 30, 2015
```
1. New feature: User can set sample metadata to public or private 
from their MySESAR sample list.
2. New feature improvement: UTM Zone has been updated to a more 
popular user syntax - using the zones A-Z instead of N or S.
3. New feature: The sample profile page is now a RESTful webservice, 
returning xml or json.
4. New feature: There is now a webservice to return IGSNs given a 
latitude-longitude defined polygon.
5. New feature: There is now a webservice to return IGSNs according 
to Field Program (e.g., Susquehanna Shale Hills Critical Zone 
Observatory (CZO))
6. Improvement: Batch registration template headers are now case 
insensitive. Although we recommend using the provided template and 
not editing the column headers, templates that differ only in header 
capitalization will work.
7. Improvement: Web service for a given sample now returns a tree 
structure for parents, siblings, or children samples.
9. Improvement: Increased the efficiency of IGSN registrations 
with the GFZ handle registration service. This improves the 
efficiency of IGSNs being resolvable by URI.
10. Improvement: Missing metadata about cruise and ship filled in 
for many ODP samples. 
11. Bug fix: Printable labels now update fields correctly, 0 depths 
show up, and blank fields are blank instead of "Not Provided"
```

### Version 6.2.0 
- March 31, 2015
```
1. New feature: additional metadata fields in response to feedback 
from the Critical Zone Observatory community. New object type "site", 
fields for UTM coordinates: Easting, Northing, Zone. Vertical datum.
2. New feature: created classification XML schema file.
3. New feature: XML Sample Upload Web Service
4. Improvement: rewrote the xml sample upload service, the new URL 
is http://app.geosamples.org/webservices/upload.php. New service 
includes robust validation, definitions, improved error messages, and 
ISO 8601 date time format.
5. Improvements: sample edit page URL uses the IGSN instead of 
internal sample id, improved error messages, robust validation.
6. Bug fix: individual registration material pull-down menu now 
properly refreshes upon a change in material to Biology.
7. Bug fix: several places where "help text" in the entry form 
would be read in as typed characters has been fixed.
8. Bug fix: bug related to navigation type and launch platform 
name not being saved is fixed.
9. Bug fix: sample edit page, sample subtypes now can be chosen 
from a pickable list in a popup.
10. Bug fix: fixed bug when updating classification
```

### Version 6.1.0 
- February 20, 2015
```
1. Added option for users to toggle samples as public or private 
from the Sample Edit page.
2. Improved the SESAR upload XML schema file to have more 
comments.
3. Improved the map projection for better display in the polar 
regions.
4. Improved the collection date precision validation.
5. Improved the notification of data managers when new namespaces 
are used for the first time.
6. Improved the label generation: blank spaces allowed on the 
labels for writing in information instead of "Not Provided"
7. Improved the SESAR API search to handle 5-digit namespaces.
8. Improved the display of cruise information for linked cruises.
9. Improved instructions for deleting multiple samples.
10. Improved downloaded spreadsheets to all have URL links to 
the sample profiles.
11. Standardized the IGSN sample link URLs within SESAR.
12. Added new materials - Ice and Synthetic.
13. Added new classification: Macrobiology>Coral.
14. Bug fix: Web Services, fixed bug where whitespace before 
IGSN would create error. 
15. Bug fix: Web Services, fixed bug of incorrect error 
message when IGSN already exists.
16. Bug fix: Web Services, improved the error message when no 
login or password was entered.
17. Bug fix: Web Services, improvement so that the "less than" 
symbol no longer causes an XML Parsing Error.
18. Bug fix: validation of data in batch registrations now 
checks the entire batch.
19. Bug fix: reimplemented the generation of PostGIS location 
information upon batch registration.
```


### Version 6.0.0 
- November 25, 2014 
```
1. Improvement of system for added protection against SQL 
injection attacks.
2. Improved database to separate uploads from the source tree.
3. Improved security through added accounts for separate database 
access.
4. Improved display of image paths.
5. Improved admin site messages when registering IGSNs with IGSN 
handle service.
6. Bug fix: fixed incorrect display of information in printable 
label update options and print all labels.
7. Bug fix: fixed geographic region search failure.
8. Bug fix: fixed bug in MySESAR search by registration date 
filter.
9. Bug fix: fixed missing QR code images in printable labels.
10. Created scripts for exporting certain information (e.g., in 
the Person table) to graph databases.
```

### Version 5.1.0 
- October 9, 2014
```
1. Improved credentials web service. Improved documentation for 
the service, including examples.
2. Improved search by registrant.
3. Bug fix: fixed empty return result for advanced search by 
registrant.
4. Bug fix: fixed display of special symbols in the description 
field.
```


### Version 5.0.0 
- July 18, 2014
```
1. New namespace syntax with 5 characters (beginning with IE), 
instead of 3 characters. This change will not affect existing 
IGSNs or namespaces.
2. New web service for retrieving IGSNs for a specific namespace, 
documented on the SESAR API page.
```

### Version 4.6.0
- May 27, 2014
```
1. New sub-object types available nested under Individual Sample 
including bead, chemical fraction, cube, culture, cylinder, 
mechanical fraction, powder, slab, smear, specimen, squeeze cake, 
thin section, toothpick, U-channel and wedge.
2. Support for a new printable label format, (Cryotags from 
Electron Microscopy Sciences, 77565-W).
3. In batch registration, users may assign IGSNs with any of their
namespaces (previously, only the primary namespace was allowed).
4. Bug fix: Latitude end and longitude end now show up on the 
Edit page for dredge samples.
5. Bug fix: Special symbols for Sample Type and Classification 
validation fixed, now allowing "Liquid>aqueous" in batch registration.
6. Batch registration upload and preview functions have improved 
performance.
7. Improvement: Data model now allows different URL link types 
including DOI.
8. Transition to new IGSN architecture: new checking procedures 
ensure that user codes and IGSNs are not duplicated in the growing 
number of IGSN allocating agents.
```

### Version 4.5.0
- February 10, 2014
```
1. IGSN deactivation: An IGSN can be deactivated (a.k.a. deleted) 
by request to the SESAR Admin, when approved, the IGSN no longer 
shows up in the public search or in the user's MySESAR environment.
2. Improvements to related file upload: More formats are allowed 
to upload and be attached to sample profiles: .xls, xlsx, .doc, 
.docx, .txt, .rtf, .pdf, .ps, .zip, .gz.
3. Improvement to batch registration template: the template now 
has alternately colored lines to aid data entry.
4. Individual Sample Registration form improvement: better 
validation on latitude/longitude/elevation.
5. Special characters such as åäö displaying correctly on the Sample 
profiles now.
6. Batch registration validation: A recent bug caused by javascript 
functions or package failure on the Mac Chrome or Safari has been 
fixed. 
IGSNs that are not 9 digits are no longer allowed to be uploaded via 
batch uploader.
7. Sample deletion request bug fixed and the feature is functional 
again.
```

### Version 4.4.0
- October 15, 2013
```
1. Filter by IGSN in MySESAR for better sample management.
2. Customize columns displayed in the MySESAR list view: In MySESAR, 
a new link for "Add Column(s)" allows users to display additional 
fields for better sample management.
3. Customized Label printing: The label printing has been customized so 
that you can choose which fields to display on the label, including 
Sample Other Name, Depth (min) and Depth (max), and Collection Date.
4. Direct links to Sample profile pages in the Downloaded file: Metadata 
downloads from SESAR now include a hyperlink that leads directly 
to the sample profile.
5. Batch Registration improvements: Several improvements include: 
reformatting of the batch registration template for better readability, 
improved error checking upon Batch Registration, improved instructions 
for fixing batch registration template errors, and case insensitivity 
of controlled vocabularies.
6. New Developer's Document posted: SESAR webservices API documentation 
is posted on the IEDA webservices page.
7. Fixed a bug that did not display or allow editing of Depth (min) and 
Depth (max) for certain object types.
```

### Version 4.3.0
- July 22, 2013
```
1. Sample Grouping: Create, edit, and view customized groups of SESAR 
samples. There is a new tab in MySESAR called My Groups. Create groups 
for projects, loan groups, field programs, or funding awards. You can 
add samples both from your own namespace or from other namespaces. 
These groups will be saved in your SESAR workspace. To help us guide 
future development, use the orange feedback tab on the right side of 
this page to let us know how you intend to use SESAR groups.
2. Automatic notification of new batch registrations: When you 
successfully submit a new batch registration template, our data 
managers are 
notified immediately. This has improved response time for registration
of SESAR batches.
3. A fix for the Chrome browser now allows negative numbers to be
entered into the latitude, longitude, and elevation fields during 
Individual 
sample registration.
4. When entering Geologic Age and Geologic Unit in individual sample
registration, non-numeric entries are now allowed.
5. Sample profiles with release dates in the future can no longer 
be accessed by the Search IGSN box on the front web page or by direct URL 
query. A message is displayed that indicates the information is 
not yet public. Previously, these samples were only excluded from the catalog 
search.
6. Batch registrations will not be be uploaded if error messages 
still exist. The errors must be corrected before the batch can be uploaded.
```

### Version 4.2.0 
- March 26, 2013
```
1. Collection Time is read in from the batch registration sheet in 
the format HH:MM:SS UTC. See the SESAR Quick Guide for more information.
2. Classification search is enhanced to now return all hierarchically-lower 
categories in addition to the category itself. e.g. A search for 
"Igneous>Volcanic" will return "Igneous>Volcanic>Mafic", 
"Igneous>Volcanic>Intermediate" and "Igneous>Volcanic>Felsic" as well.
3. More information (Material and Classification) is shown in the list 
view of MySESAR and search results.
4. The Map Search has been updated to correctly return results by both 
map polygon and user-entered N-S-E-W bounding values.
5. Private samples are now linked correctly to the detailed sample 
profile from MySESAR.
6. Individual batch registration hover-over definitions are 
properly aligned.
7. Individual batch registration "Ready?" button at the bottom of 
the webform directs to the correct sample profile display instead 
of a blank 
page.
8. The primary image thumbnail of a sample correctly displays at 
the top of the sample profile.
9. IGSN case insensitivity is correctly deployed to more features 
in SESAR. (If you previously had any lowercase IGSNs, please contact 
info@geosamples.org if you have questions.)
```

### Version 4.1.0
- January 14, 2013
```
1. Time zone display is now in UTC (Universal Time Coordinated). 
The display on sample profile pages follows ISO-8601.
2. Label printing is implemented in MySESAR. Users have the option 
to select certain samples and print labels for them. More 
information here.
3. Batch registration template Quick Guide instructions are now 
included with each new download of a Batch Registration Template.
4. The sample delete button at the bottom of a user's sample 
profiles now leads to the correct page for requesting sample delete.
```

### Version 3.8.0 
- February 2012
```
1. Improved Search Interface: The Advanced Settings panel now 
auto-completes searches for Registrant, Collector, Archive, 
Field Program/Cruise, 
Platform Name, and Collection Method. In addition, by clicking 
View list, the user can view all possible entries that exist 
in SESAR. There is a new option to search by registration date 
of the sample.
2. QR code has replaced the barcode: On the sample profile, 
the barcode has been replaced with a 2-D QR (quick response) 
code. This QR code, 
if snapped with a QR reader (for example, on smartphones), 
will resolve to the URL of the sample profile.
3. New metadata fields: New metadata fields, have been added 
to the Sample Profile: Launch, Launch Type, Launch ID, Navigation 
Type, Purpose. 
See their definitions on the vocabulary page.
4. Download complete metadata option: You can now download the 
complete metadata list from MySESAR and search results. 
Just click “Download extended list”
5. More help with sample registration: More information has 
been added to help you to register samples, suggested and controlled 
vocabulary lists are posted on the help page. Please visit: 
http://www.geosamples.org/help.
6. The IGSN Search box on the upper-right hand corner of the SESAR 
home page returns existing samples only, not empty profiles.
7. The Download Sample List option in MySESAR and on search result 
pages can now download more than 100 samples.
```

### Version 3.0.0
- 2010
```
1. Create customized templates for submitting metadata of multiple 
samples.
2. Register multiple samples online by uploading templates.
3. Add up to 5 images and other documents to a sample profile.
4. Add publications to a sample profile.
5. Control public access to sample metadata (set a 'release' date 
for samples to become public in the SESAR Sample Catalog).
6. Transfer samples to a different SESAR user.
7. Use of GeoPass, a single sign-on authentication system that 
gives account holders access to multiple data systems (e.g. the 
Geochemical Resource Library).
```

