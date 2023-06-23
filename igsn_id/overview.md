---
name: igsn_id_overview
title: IGSN ID Overview
date: 06/01/2023
layout: default
---

The IGSN ID has gone through a few changes as a result of partnership between the International Generic Sample Number (IGSN) e.V. and DataCite. As of January 2023, IGSN IDs now follow the DataCite DOI format which includes the addition of a prefix to the existing IGSN structure. SESAR’s shared prefix for sample registrations is 10.58052.

#### New IGSN ID Structure/Syntax
<img src="{{site.baseurl}}/assets/images/IGSNFormat.png" alt="New IGSN ID Structure/Syntax" width="750"/>

#### IGSN ID Metadata Mapping
Below is a table detailing the mapping of SESAR fields to the DataCite metadata schema. 

| DataCite        | SESAR           |
| ------------- |---------------|
| Idneitifer      | IGSN ID |
| Creator      | Collector* |
| Title      | Sample Name |
| Publisher      | "SESAR"** |
| Publication Year      | Publish Date |
| resourceType      | Sample Type |
| resourceTypeGeneral      | "Physical Object"** |

\* If the necessary collector information is missing, the original registrant will be used instead.

** These values will always be the same.