---

## description: How SESAR sample metadata maps to DataCite DOI records.
icon: barcode

# DataCite

SESAR registers each sample IGSN as a DataCite DOI with `resourceTypeGeneral` **PhysicalObject**. This page is the mapping SESAR uses when it creates or updates that record.

The landing-page URL is `{https://app.geosamples.org}/sample/igsn/{IGSN}`. Publisher is always **SESAR**.

## Field mapping


| DataCite                        | SESAR source                                                                                                                                |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `doi` / `id`                    | Sample IGSN                                                                                                                                 |
| `publicationYear`               | Year of **publish date**                                                                                                                    |
| `types.resourceTypeGeneral`     | Always `PhysicalObject`                                                                                                                     |
| `types.resourceType`            | Object type hierarchical path (for example `Marine and lacustrine samples > Core`). If none, legacy sample type name. If neither, `Sample`. |
| `titles`                        | **Sample name**, then object type path, then material path, then **material name (verbatim)**, joined with spaces                           |
| `subjects`                      | Object type path; **geological age**; material path (see below)                                                                             |
| `creators`                      | Registrant, then owner if different (see [Creators](#creators))                                                                             |
| `contributors`                  | **Current archive** as `HostingInstitution` (organizational). Affiliation is the archive's parent institution, with ROR when present.       |
| `dates`                         | **Last update date** → `Updated`; **sampling start date** → `Collected` (date only, `YYYY-MM-DD`)                                           |
| `geoLocations.geoLocationPoint` | **Longitude** and **latitude**                                                                                                              |
| `geoLocations.geoLocationPlace` | **Locality**, **country**, **city**, **province / state**, and **county**, joined with spaces                                               |
| `relatedIdentifiers`            | Parent sample and related resources (see [Related identifiers](#related-identifiers))                                                       |
| `alternateIdentifiers`          | **External sample ID** and **other names**, type `Local` (see [Alternate identifiers](#alternate-identifiers))                              |


Object type in DataCite is the full hierarchical label. Material is **general material type > specific material types** when both exist; otherwise whichever material labels are present. If the sample still has only legacy classification, DataCite uses `legacy top-level > legacy classification` (or whichever of those is set).

## Creators

Creators are ordered:

1. **Registrant** — a personal creator from the registrant's individual record (`Family, Given` when first and last names exist; otherwise the individual label or the user string). ORCID is included when the SESAR user has one. Affiliations come from the individual's current institution affiliations (ROR when the institution has one). If there are no current affiliations, SESAR uses **institution detail** as a name-only affiliation.
2. **Owner**, only if it is not the same person as the registrant:
  - **Team owner** (when set) — an organizational creator using the team's display name, or the team name. Affiliations are the team's institutions, with ROR when present.
  - Otherwise **user owner** — same personal-creator rules as the registrant.

Duplicate institution affiliations are omitted (same ROR, or same name if there is no ROR).

## Related identifiers

On every write SESAR sends:


| Relation         | Type           | SESAR source                                                                                 |
| ---------------- | -------------- | -------------------------------------------------------------------------------------------- |
| `IsPartOf`       | `IGSN`         | Parent sample IGSN, when the sample has a parent                                             |
| `IsReferencedBy` | `DOI` or `URL` | Each related resource URI. `DOI` stays `DOI`; any other non-local URI type is sent as `URL`. |


On **update**, SESAR also keeps existing DataCite related identifiers whose relation is `IsIdenticalTo` (used for legacy IGSN identity).

## Alternate identifiers


| Type          | SESAR source                                 |
| ------------- | -------------------------------------------- |
| `Local`       | **External sample ID**                       |
| `Local`       | All **other names**                          |
| `Legacy IGSN` | IGSN value from before migration to Datacite |


