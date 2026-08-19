---
description: Old SESAR vocabulary names and the lists they map to now.
icon: tags
---

# Renamed vocabularies

Several SESAR 1.0 lists kept their terms but changed names. A few were restructured. Current labels are in the **Vocabularies** section. Field names that are not lists (for example `user_code` → `sesar_code`) belong on [Field crosswalk (old -> new)](field-crosswalk-old-greater-than-new.md).

The web form still shows some old names next to the new ones so existing users can find the field.

| SESAR 1.0 | Now | Form label | API / JSON |
| --------- | --- | ---------- | ---------- |
| Sample type and sample subtype | Object type | Object type | `object_type` |
| Collection method | Sampling method | Sampling method | `sampling_method` |
| Collection method description | Sampling method description | Sampling method description | `sampling_method_detail` |
| Navigation type | Location method | Navigation type / Location method | `location_method` |
| Material | General material type | Material | `general_material_type` |
| Classification | Material types | Material type | `material_types` |
| Platform type | Platform type | Platform type | `platform.platform_type` |
| Launch type | Launch type | Launch type | `launch_platform.launch_type` |

Country was not renamed. It is still a controlled list; API writes use the country **label**, and search filters use the ISO 3166 code.

## Object type (was sample type)

SESAR 1.0 used **sample type** and optional **sample subtype** as a pair (for example Individual Sample + Thin Section). That is now one **object type** value: the leaf label in a hierarchy (for example `Thin Section`).

- Prefer the most specific term that fits. The form shows the full path; API registration uses the leaf label.
- If both type and subtype were set, subtype is the object type.
- Legacy sample-type names that are not current object-type labels may still resolve through a mapping. The value pairs are on [Sample type → object type](sample-type-to-object-type.md). The catalog can show `object type (previously legacy sample type)`.
- Object type is required to register. The list is controlled; request a term in **Vocabularies** if you need a new one.

## Material types (was material and classification)

SESAR 1.0 stored **material** as a top-level class (for example Rock) and **classification** as one more-specific value, often with `>` in the string (`Igneous>Plutonic`).

Now:

- **General material type** is that top-level class.
- **Material types** are more specific terms. A sample can have more than one. A `>` string is still **one** label, not a split into several types. If the classification started with `{material}>`, that prefix is dropped.

Migrated samples can still show the old classification next to the new labels. Use the current material-type list for new registration.

## Sampling method (was collection method)

**Collection method** is **sampling method**. Extra equipment or procedure text is **sampling method description** (formerly collection method description).

Sampling method is a recommended list, not a closed vocabulary: prefer an existing label; a new label creates a new row.

## Location method (was navigation type)

**Navigation type** is **location method** (GPS, DVL, LBL, and so on). The list is controlled. The form and batch spreadsheet still title the field **Navigation type / Location method**.

## Platform type and launch type

These lists kept their names. Platform type is recommended (you can add a new type). Launch type is controlled and describes the vehicle or device launched from a platform, not the platform itself.
