# SESAR - Release Notes
Version | Release Date | Summary
--------|--------------|--------
[v 3.0.0](https://github.com/earthchem/sesar-doc/blob/gh-pages/release_notes/SESAR_release_notes.md#version-300) | 2010 | Customizable submission templates, Supplemental files for samples, GeoPass introduction |
[v 3.8.0](https://github.com/earthchem/sesar-doc/edit/gh-pages/release_notes/SESAR_release_notes.md#version-380) | February 2012 | Improved Search Interface, QR code introduction, Help with sample registration
[v 4.1.0](https://github.com/earthchem/sesar-doc/edit/gh-pages/release_notes/SESAR_release_notes.md#version-410) | January 2013 | Time zone in UTC, Label Printing |
[v 4.2.0](https://github.com/earthchem/sesar-doc/edit/gh-pages/release_notes/SESAR_release_notes.md#version-420) | March 2013 | Batch Registration Updates, Enhanced Classification |
[v 4.3.0](https://github.com/earthchem/sesar-doc/edit/gh-pages/release_notes/SESAR_release_notes.md#version-430) | July 2013 | Sample Grouping, Batch upload improvements | 
[v 4.4.0](https://github.com/earthchem/sesar-doc/edit/gh-pages/release_notes/SESAR_release_notes.md#version-440) | October 2013 | MySESAR updates, Custom label printing |
[v 4.5.0](https://github.com/earthchem/sesar-doc/edit/gh-pages/release_notes/SESAR_release_notes.md#version-450) | February 2014 | IGSN deactiviation, Improvements to supplemental file uploads |
[v 4.6.0](https://github.com/earthchem/sesar-doc/edit/gh-pages/release_notes/SESAR_release_notes.md#version-460) | May 2014 | New sub-object types available, Bug fixes | 


### Version 4.6.0
- May 27, 2014
```
1. New sub-object types available nested under Individual Sample including bead, chemical fraction, cube, culture, cylinder, mechanical fraction, powder, slab, smear, specimen, squeeze cake, thin section, toothpick, U-channel and wedge.
2. Support for a new printable label format, (Cryotags from Electron Microscopy Sciences, 77565-W).
3. In batch registration, users may assign IGSNs with any of their namespaces (previously, only the primary namespace was allowed).
4. Bug fix: Latitude end and longitude end now show up on the Edit page for dredge samples.
5. Bug fix: Special symbols for Sample Type and Classification validation fixed, now allowing "Liquid>aqueous" in batch registration.
6. Batch registration upload and preview functions have improved performance.
7. Improvement: Data model now allows different URL link types including DOI.
8. Transition to new IGSN architecture: new checking procedures ensure that user codes and IGSNs are not duplicated in the growing number of IGSN allocating agents.
```

### Version 4.5.0
- February 10, 2014
```
1. IGSN deactivation: An IGSN can be deactivated (a.k.a. deleted) by request to the SESAR Admin, when approved, the IGSN no longer shows up in the public search or in the user's MySESAR environment.
2. Improvements to related file upload: More formats are allowed to upload and be attached to sample profiles: .xls, xlsx, .doc, .docx, .txt, .rtf, .pdf, .ps, .zip, .gz.
3. Improvement to batch registration template: the template now has alternately colored lines to aid data entry.
4. Individual Sample Registration form improvement: better validation on latitude/longitude/elevation.
5. Special characters such as åäö displaying correctly on the Sample profiles now.
6. Batch registration validation: A recent bug caused by javascript functions or package failure on the Mac Chrome or Safari has been fixed. IGSNs that are not 9 digits are no longer allowed to be uploaded via batch uploader.
7. Sample deletion request bug fixed and the feature is functional again.
```

### Version 4.4.0
- October 15, 2013
```
1. Filter by IGSN in MySESAR for better sample management.
2. Customize columns displayed in the MySESAR list view: In MySESAR, a new link for "Add Column(s)" allows users to display additional fields for better sample management.
3. Customized Label printing: The label printing has been customized so that you can choose which fields to display on the label, including Sample Other Name, Depth (min) and Depth (max), and Collection Date.
4. Direct links to Sample profile pages in the Downloaded file: Metadata downloads from SESAR now include a hyperlink that leads directly to the sample profile.
5. Batch Registration improvements: Several improvements include: reformatting of the batch registration template for better readability, improved error checking upon Batch Registration, improved instructions for fixing batch registration template errors, and case insensitivity of controlled vocabularies.
6. New Developer's Document posted: SESAR webservices API documentation is posted on the IEDA webservices page.
7. Fixed a bug that did not display or allow editing of Depth (min) and Depth (max) for certain object types.
```

### Version 4.3.0
- July 22, 2013
```
1. Sample Grouping: Create, edit, and view customized groups of SESAR samples. There is a new tab in MySESAR called My Groups. Create groups for projects, loan groups, field programs, or funding awards. You can add samples both from your own namespace or from other namespaces. These groups will be saved in your SESAR workspace. To help us guide future development, use the orange feedback tab on the right side of this page to let us know how you intend to use SESAR groups.
2. Automatic notification of new batch registrations: When you successfully submit a new batch registration template, our data managers are notified immediately. This has improved response time for registration of SESAR batches.
3. A fix for the Chrome browser now allows negative numbers to be entered into the latitude, longitude, and elevation fields during Individual sample registration.
4. When entering Geologic Age and Geologic Unit in individual sample registration, non-numeric entries are now allowed.
5. Sample profiles with release dates in the future can no longer be accessed by the Search IGSN box on the front web page or by direct URL query. A message is displayed that indicates the information is not yet public. Previously, these samples were only excluded from the catalog search.
6. Batch registrations will not be be uploaded if error messages still exist. The errors must be corrected before the batch can be uploaded.
```

### Version 4.2.0 
- March 26, 2013
```
1. Collection Time is read in from the batch registration sheet in the format HH:MM:SS UTC. See the SESAR Quick Guide for more information.
2. Classification search is enhanced to now return all hierarchically-lower categories in addition to the category itself. e.g. A search for "Igneous>Volcanic" will return "Igneous>Volcanic>Mafic", "Igneous>Volcanic>Intermediate" and "Igneous>Volcanic>Felsic" as well.
3. More information (Material and Classification) is shown in the list view of MySESAR and search results.
4. The Map Search has been updated to correctly return results by both map polygon and user-entered N-S-E-W bounding values.
5. Private samples are now linked correctly to the detailed sample profile from MySESAR.
6. Individual batch registration hover-over definitions are properly aligned.
7. Individual batch registration "Ready?" button at the bottom of the webform directs to the correct sample profile display instead of a blank page.
8. The primary image thumbnail of a sample correctly displays at the top of the sample profile.
9. IGSN case insensitivity is correctly deployed to more features in SESAR. (If you previously had any lowercase IGSNs, please contact info@geosamples.org if you have questions.)
```

### Version 4.1.0
- January 14, 2013
```
1. Time zone display is now in UTC (Universal Time Coordinated). The display on sample profile pages follows ISO-8601.
2. Label printing is implemented in MySESAR. Users have the option to select certain samples and print labels for them. More information here.
3. Batch registration template Quick Guide instructions are now included with each new download of a Batch Registration Template.
4. The sample delete button at the bottom of a user's sample profiles now leads to the correct page for requesting sample delete.
```

### Version 3.8.0 
- February 2012
```
1. Improved Search Interface: The Advanced Settings panel now auto-completes searches for Registrant, Collector, Archive, Field Program/Cruise, Platform Name, and Collection Method. In addition, by clicking View list, the user can view all possible entries that exist in SESAR. There is a new option to search by registration date of the sample.
2. QR code has replaced the barcode: On the sample profile, the barcode has been replaced with a 2-D QR (quick response) code. This QR code, if snapped with a QR reader (for example, on smartphones), will resolve to the URL of the sample profile.
3. New metadata fields: New metadata fields, have been added to the Sample Profile: Launch, Launch Type, Launch ID, Navigation Type, Purpose. See their definitions on the vocabulary page.
4. Download complete metadata option: You can now download the complete metadata list from MySESAR and search results. Just click “Download extended list”
5. More help with sample registration: More information has been added to help you to register samples, suggested and controlled vocabulary lists are posted on the help page. Please visit: http://www.geosamples.org/help.
6. The IGSN Search box on the upper-right hand corner of the SESAR home page returns existing samples only, not empty profiles.
7. The Download Sample List option in MySESAR and on search result pages can now download more than 100 samples.
```

### Version 3.0.0
- 2010
```
1. Create customized templates for submitting metadata of multiple samples.
2. Register multiple samples online by uploading templates.
3. Add up to 5 images and other documents to a sample profile.
4. Add publications to a sample profile.
5. Control public access to sample metadata (set a 'release' date for samples to become public in the SESAR Sample Catalog).
6. Transfer samples to a different SESAR user.
7. Use of GeoPass, a single sign-on authentication system that gives account holders access to multiple data systems (e.g. the Geochemical Resource Library).
```

