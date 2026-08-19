---
description: Register a sample with the SESAR API.
icon: plus
---

# Register a sample

This is the shortest path to mint an IGSN from the API. Field names, types, and optional nested objects are in the OpenAPI reference under **Samples** → **Register a new sample**.

You need a JWT access token. See [Authentication](authentication.md).

To **publish**, send **sample name**, **object type** (the leaf label, for example `Individual sample`), **latitude**, **longitude**, and your **SESAR code**. Omit `igsn` and SESAR assigns one.

{% code title="Register a sample" %}
```bash
curl -X POST "https://api.geosamples.org/api/samples/" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "sesar_code": "YOUR_SESAR_CODE",
    "name": "My sample",
    "object_type": "Individual sample",
    "latitude": 41.5,
    "longitude": -72.8
  }'
```
{% endcode %}

A successful response is `201` and includes the new `igsn`. Fetch it with [Find or fetch a sample](find-or-fetch-a-sample.md). Change it later with [Update a sample](update-a-sample.md).

Save a draft without coordinates by adding `"is_draft": true`. Latitude and longitude are required when you publish a new sample. End coordinates, parent IGSN, platform, collectors, and other metadata are optional — send them as shown in the OpenAPI schema.
