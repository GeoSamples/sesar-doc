---
description: Search the catalog or fetch one sample by IGSN.
icon: magnifying-glass
---

# Find or fetch a sample

Use `GET /api/samples/` to search. Use `GET /api/samples/{igsn}/` when you already have the IGSN. Filter names are in the OpenAPI reference under **Samples** → **Search and list samples**.

Search does **not** require a token. Without `Authorization`, results are **public** published samples only. With a token, the default `scope` is **`personal`** (your samples, including drafts). Pass `scope=public` if you are authenticated and still want the catalog.

{% code title="Search public samples" %}
```bash
curl "https://api.geosamples.org/api/samples/?q=basalt&country=US&page_size=25"
```
{% endcode %}

Useful query parameters:

| Parameter | What it matches |
| --------- | --------------- |
| `q` | Substring of IGSN or sample name |
| `name` | Sample name |
| `igsn` | IGSN substring |
| `object_type` | Object type **leaf** label(s), comma-separated |
| `country` | ISO 3166 code(s), comma-separated (`US,CA`) |
| `scope` | `public`, `personal`, `shared`, or `personal_and_shared` |
| `is_draft` | `true` or `false` (authenticated; `personal` scope) |
| `page` / `page_size` | Pagination (default 25, max 2000) |

The list response is paginated: `data` is the page of samples; `count`, `next`, `previous`, `current_page`, and `total_pages` describe the rest.

{% code title="Fetch one sample" %}
```bash
curl "https://api.geosamples.org/api/samples/10.58052/YOURIGSN/"
```
{% endcode %}

Published samples are readable without a token. Drafts, pending-review, embargoed (`publish_date` in the future), and samples you do not own need a JWT and view permission. Deactivated samples are not returned.
