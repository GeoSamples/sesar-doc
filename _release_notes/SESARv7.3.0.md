# SESAR v.7.3.0 (July 16, 2019)
1. Bug Fix: Sample names containing only ‘space’ are no longer allowed. Related validations and error messages improved.
2. Bug Fix: Improved validation of release date in batch registration so that samples could not be registered with release dates more than two years in the future.
3. Bug Fix: Fixed a bug where the sub-object type was not written out to the downloaded batch registration template.
4. Bug Fix: Fixed a bug where batch update failed to update elevation start and end.
5. Bug Fix: Fixed a bug in total sample count for a group, which caused pagination to work improperly.
6. Bug Fix: Fixed a bug where the classification field was overwritten when users left the field blank during single sample edit.
7. Enhancement: Added email address validation for requests to contact sample owners.
8. Enhancement: Improved validation for classification and material fields during batch upload and update.
9. Enhancement: Elevation Start, Elevation End, Depth (min), and Depth (max) are now displayed for all object types.
10. Enhancement: Improved the sample search so that it is no longer case sensitive and to allow for searches by “contains”, “ends with”, and partial matching.
11. Enhancement: Improved database schema to remove legacy and obsolete columns, add primary id and keys to tables without them, and remove temporary tables and redundant foreign keys.
