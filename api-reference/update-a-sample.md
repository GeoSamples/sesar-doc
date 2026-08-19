---
description: Change metadata on a sample you can edit.
icon: pencil
---

# Update a sample

Send a **PATCH** to `/api/samples/{igsn}/`. You need a JWT and edit permission on that sample (you own it, or a team grants you permission). See [Authentication](authentication.md).

Do not use PUT. You cannot change `igsn` or `sesar_code`.

{% code title="Update a sample" %}
```bash
curl -X PATCH "https://api.geosamples.org/api/samples/10.58052/YOURIGSN/" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Updated name",
    "location_description": "Outcrop west of the road"
  }'
```
{% endcode %}

Only send fields you want to change. Omitted fields stay as they are.

Lists you **do** send are replaced, not merged: `other_names`, `material_types`, `collectors`, and non-image `related_resources`. Omit them to leave the existing lists alone.

Latitude and longitude:

- If they are already set, you cannot clear them (`null` is rejected).
- You can still PATCH a sample that never had coordinates (legacy records). Publishing a **new** sample still requires lat/lon; that rule does not apply to updates.

To publish a draft, PATCH `"is_draft": false`.
