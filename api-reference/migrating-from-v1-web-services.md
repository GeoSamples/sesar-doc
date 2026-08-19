---
description: Move from SESAR 1.0 PHP web services to the JSON API.
icon: right-left
---

# Migrating from v1 web services

SESAR 1.0 clients posted XML to `/webservices/upload.php` and `/webservices/update.php`, often with GeoPass username and password. That stack is **deprecated**. New work should use JSON against `https://api.geosamples.org/api/` and a JWT from [Authentication](authentication.md).

The PHP paths still proxy into the new API so existing XML clients can keep running while you switch. Mapping is lossy in places — always check what was saved. New integrations must not start on XML.

## Endpoint map

| v1 | Now |
| -- | --- |
| `POST /webservices/upload.php` (`content` = XML) | [Register a sample](register-a-sample.md) — `POST /api/samples/` JSON. Compatibility: same PHP URL, or `POST /api/samples/legacy-xml/` |
| `POST /webservices/update.php` | [Update a sample](update-a-sample.md) — `PATCH /api/samples/{igsn}/`. Compatibility: same PHP URL (each `<sample>` needs `<igsn>`) |
| GeoPass / `get_token.php` / `credentials_service_v2.php` | JWT access token. `Authorization: Bearer …` |
| `refresh_token.php` | `POST /api/auth/token/refresh/` |

XML compatibility still expects a form (or JSON) field named `content` with a `<samples>` document. Responses stay XML (`<results>…`). JSON register/update responses are JSON.

## Auth

GeoPass username and password are not accepted on this stack. Mint an access token and a refresh token from Developer Settings, then send:

```
Authorization: Bearer ACCESS_TOKEN
```

See [Authentication](authentication.md).

## Prefer JSON

A v1 XML sample becomes a JSON body like this. Omit `igsn` to mint one. `object_type` is the **leaf** vocabulary label (`sample_subtype` if you had both type and subtype).

{% code title="JSON equivalent of a v1 XML sample" %}
```json
{
  "sesar_code": "UALIC",
  "name": "My slide",
  "object_type": "Thin Section",
  "general_material_type": "Rock",
  "material_types": ["Igneous>Plutonic"],
  "sample_description": "Olivine-rich",
  "latitude": 41.5,
  "longitude": -72.8,
  "collectors": [{ "individual": { "label": "Jane Doe" } }],
  "platform": { "label": "R/V Atlantis", "platform_type": "Ship" }
}
```
{% endcode %}

POST that to `/api/samples/` as in [Register a sample](register-a-sample.md). Field names, nested objects, and status codes are in the OpenAPI reference under **Samples**.

## Renamed fields

These XML element names do not match the JSON field. Unlisted elements keep the same name (`name`, `latitude`, `country`, …). Empty XML elements are dropped.

| v1 XML | JSON |
| ------ | ---- |
| `user_code` | `sesar_code` (if `sesar_code` is absent) |
| `sample_subtype` / `sample_type` | `object_type` (subtype wins) |
| `description` | `sample_description` |
| `age_min` / `age_max` / `age_unit` | `numeric_age_min` / `numeric_age_max` / `numeric_age_unit` |
| `geological_age` / `geological_unit` | `geologic_age_verbatim` / `geologic_unit` |
| `collection_method` / `collection_method_descr` | `sampling_method` / `sampling_method_detail` |
| `navigation_type` | `location_method` |
| `material` | `general_material_type` |
| `classification` | `material_types` (one-element list) |
| `parent_igsn` | `parent_sample` |
| `parent_name` / `parent_sample_type` | `external_parent_name` / `external_parent_object_type` |
| `sample_other_name` | `other_names` |
| `platform_name` / `platform_type` / `platform_descr` | `platform.label` / `platform.platform_type` / `platform.description` |
| `launch_platform_name` / `launch_type_name` | `launch_platform.label` / `launch_platform.launch_type` |
| `launch_id` | `launch_label` |
| `collection_start_date` / `collection_end_date` / `collection_date_precision` | `sampling_start_date` / `sampling_end_date` / `sampling_date_precision` |
| `collector` / `collector_detail` | `collectors[].individual.label` / `collectors[].description` |
| `current_archive` / `original_archive` | `current_archive.label` / `original_archive.label` |
| `external_url` (`url`, `description`) | related resource URI and description |

`sample_comment` and `classification_comment` are appended onto `sample_description`.

## Behavior that changed

- **`object_type`** must match a current object-type **label**, not a legacy sample-type ID. Subtype is used when both type and subtype are present.
- **`classification`** stays **one** material-type label. `Igneous>Plutonic` is not split into two types. If the string starts with `{material}>`, that prefix is stripped.
- **`is_private`** is ignored. Success XML may include a deprecation warning.
- **`external_url` `url_type`** is ignored; links are stored as a regular URL. File attachments on that element are ignored.
- **Collector detail** is free text on the collector agent. It is not parsed into ORCID or institution fields.
- **Location method** uses the location-method vocabulary, not the old navigation-type table.
- Publish rules are the same as JSON: name, object type, and lat/lon to register; drafts can omit coordinates. See [Register a sample](register-a-sample.md).

If you stay on XML for a while, keep the `<samples><sample>…` document, unique `<name>` per sample, and JWT on the request. For updates, every sample must include `<igsn>`.
