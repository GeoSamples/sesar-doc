---
description: Call the SESAR API to register, find, and update sample metadata.
icon: code
---

# Overview

This section is for software that talks to SESAR. The **OpenAPI reference** (next in the sidebar) is the contract: every path, field, and status code. The pages after it are short how-tos for the workflows the spec does not spell out in order.

The production API root is `https://api.geosamples.org/api/`. Send JSON. Writes and private reads need `Authorization: Bearer` plus an access token from [Authentication](authentication.md). Listing published samples does not.

| If you want to… | Start here |
| --------------- | ---------- |
| Get a JWT | [Authentication](authentication.md) |
| Mint an IGSN | [Register a sample](register-a-sample.md) |
| Search or load one sample | [Find or fetch a sample](find-or-fetch-a-sample.md) |
| Change metadata | [Update a sample](update-a-sample.md) |
| Move off `upload.php` / XML | [Migrating from v1 web services](migrating-from-v1-web-services.md) |
| See every field | OpenAPI reference, grouped by tag |

Allowed values live in the **Vocabularies** section. What each sample field means, and which ones are required, is in **Metadata Schema**.
