---

## description: Fields SESAR requires to register a sample.
icon: list-check

# Field obligations

To **register** (publish) a sample, SESAR requires three things: **object type**, **sample name**, and **latitude and longitude**. Everything else is optional.

You can **save a draft** with only object type and name. Latitude and longitude are required when you publish a new sample. UTM or other coordinates do not replace them.


| Field                          | When it is required                   | Notes                                                                                                                                                         |
| ------------------------------ | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Object type**                | Always — drafts and published samples | Controlled list. The web form shows the full path; API writes use the leaf label.                                                                             |
| **Sample name**                | Always — drafts and published samples | The collector's name for the sample. In a batch spreadsheet, each name must be unique in that file.                                                           |
| **Latitude** and **longitude** | When you publish a new sample         | WGS84 decimal degrees. Provide both, or neither on a draft. Latitude must be between −90 and 90; longitude between −180 and 180. South and west are negative. |



End latitude and end longitude are optional. Use them together when the sampling location is a line (for example a dredge track). They are not a substitute for the required start coordinates.