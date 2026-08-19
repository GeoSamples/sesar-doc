---

## description: How SESAR 1.0 sample fields map to the current schema.
icon: table

# Field crosswalk (old → new)

This is the sample-field mapping used when SESAR 1.0 records were loaded into the current registry. Vocabulary **list** names (sample type → object type, and so on) are on [Renamed vocabularies](renamed-vocabularies.md).

Unlisted fields kept the same name: **IGSN**, **sample name**, **latitude** and **longitude** (including end coordinates), **country**, **province / state**, **county**, **city**, **locality**, **location description**, **size**, **purpose**, **elevation**, **depth in core**, **vertical datum**, **cruise / field program**, **publish date**, and archive contacts.

## Renamed fields


| SESAR 1.0                                   | Now                                                 | Notes                                                                                                                   |
| ------------------------------------------- | --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| User code                                   | SESAR code (`sesar_code`)                           |                                                                                                                         |
| Sample type (and subtype)                   | Object type                                         | Mapped through the object-type list. The original type is kept as **legacy sample type**                                |
| Field name                                  | Material name (verbatim) (`material_name_verbatim`) | Informal taxonomy / field name                                                                                          |
| Description                                 | Sample description                                  | See [Combined text](#combined-text)                                                                                     |
| Age min / max / unit                        | Numeric age min / max / unit                        | Units were normalized (for example `Ma` → `million years (Ma)`). Unrecognized units were appended to sample description |
| Geological age                              | Geological age (`geologic_age_verbatim`)            | Same content; the field name spelling changed                                                                           |
| Geological unit                             | Geological unit (`geologic_unit`)                   | Same content, spelling of the field name changed                                                                        |
| Collection method                           | Sampling method                                     |                                                                                                                         |
| Collection method description               | Sampling method description                         |                                                                                                                         |
| Collection start / end date, date precision | Sampling start / end date, sampling date precision  |                                                                                                                         |
| Navigation type                             | Location method                                     | Form still says **Navigation type / Location method**                                                                   |
| Material (top-level classification)         | General material type                               | Original value kept as **legacy top-level classification**                                                              |
| Classification                              | Material types                                      | Original value kept as **legacy classification**. A sample can have more than one material type now                     |
| Parent sample (`origin_sample_id`)          | Parent sample                                       | Set from the parent’s sample ID; shown as parent IGSN                                                                   |
| External parent sample type                 | External parent object type                         | Mapped through the object-type list                                                                                     |
| Other names (`sample_additional_name`)      | Other names                                         | Copied as additional names on the sample                                                                                |
| Platform name / type / description          | Platform                                            | One platform record (name, type, owner, description). Different descriptions are distinct platforms                     |
| Launch platform name / launch type          | Launch platform                                     |                                                                                                                         |
| Launch ID                                   | Launch ID (`launch_label`)                          | Same idea, stored as launch label                                                                                       |
| Collector / collector detail                | Collectors                                          | Collector name is the agent; collector detail is the collector description                                              |
| Current / original archive                  | Current / original archive, or **storage location** | If the archive string was a personal storage place, it went to storage location instead of an archive record            |
| Easting, northing, zone                     | Geospatial location                                 | UTM is stored separately; it does not replace latitude and longitude                                                    |


**External sample ID** was copied only when it differed from the sample name.

**Continent** is new: it is filled from the sample’s country.

## Combined text

**Sample description** is the old **description**, **classification comment**, and **sample comment**, joined with `;`. If the age unit could not be mapped, `Legacy age unit: …` was added.

## Related records (not a single sample field)


| SESAR 1.0                                   | Now                                                                                        |
| ------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Sample documents (`sample_doc`)             | Related resources (`uri_type` local file). Type from MIME (image, text, dataset, or other) |
| Publication URLs (`sample_publication_url`) | Related resources. DOI URLs keep type DOI when possible; other URLs are **Other**          |
| Groups                                      | Sample groups                                                                              |
| Sample delete request                       | Sample deactivate request (`delete_reason` → deactivate reason)                            |


## Not carried onto the sample

These legacy sample columns were not written as sample fields:


| SESAR 1.0                   | What happened                               |
| --------------------------- | ------------------------------------------- |
| `sample_unit`               | Not migrated                                |
| `igsn_digit`, `igsn_to_int` | Internal IGSN counters; not sample metadata |


Internal registrant and owner IDs were copied. They are not fields you edit on the sample form.