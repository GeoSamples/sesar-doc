---
description: How SESAR 1.0 sample type values map to object type.
icon: right-left
---

# Sample type → object type

SESAR 1.0 stored **sample type** and optional **sample subtype** as a pair. Migrated samples use one [object type](renamed-vocabularies.md#object-type-was-sample-type) value: the leaf label. If a subtype was set, that is the value that was mapped.

The original pair is kept as **legacy sample type**. The catalog can show `object type (previously legacy sample type)`.

API registration uses the **object type** leaf label. The form shows the **object type path**.

| SESAR 1.0 | Object type | Object type path |
| --------- | ----------- | ---------------- |
| Core | Core | Marine and lacustrine samples > Core |
| Core Catcher | Core catcher | Marine and lacustrine samples > Core catcher |
| Core Half Round | Core half round | Marine and lacustrine samples > Core half round |
| Core Piece | Core piece | Marine and lacustrine samples > Core piece |
| Core Quarter Round | Core quarter round | Marine and lacustrine samples > Core quarter round |
| Core Section | Core section | Marine and lacustrine samples > Core section |
| Core Section Half | Core section half | Marine and lacustrine samples > Core section half |
| Core Slab | Slab | Analytical preparations > Slab |
| Core Sub-Piece | Core subpiece | Marine and lacustrine samples > Core subpiece |
| Core U-Channel | Core U-channel sample | Marine and lacustrine samples > Core U-channel sample |
| Core Whole Round | Core whole round | Marine and lacustrine samples > Core whole round |
| CTD | CTD sample | Marine and lacustrine samples > CTD sample |
| Cuttings | Cuttings | Marine and lacustrine samples > Cuttings |
| Dredge | Dredge | Marine and lacustrine samples > Dredge |
| Experimental Specimen | Experiment product | Analytical preparations > Experiment product |
| Experimental Specimen > Other | Analytical preparations | Analytical preparations |
| Experimental Specimen > Thin Section | Thin section | Analytical preparations > Sectioned specimen > Thin section |
| Grab | Grab | Marine and lacustrine samples > Grab |
| Hole | Hole | Sampling features > Hole |
| Individual Sample | Individual sample | General sample types > Individual sample |
| Individual Sample > Bead | Bead | Analytical preparations > Bead |
| Individual Sample > Chemical Fraction | Chemical fraction | Analytical preparations > Chemical fraction |
| Individual Sample > Cube | Cube | General sample types > Cube |
| Individual Sample > Culture | Cell culture | Analytical preparations > Cell culture |
| Individual Sample > Cylinder | Cylinder | General sample types > Cylinder |
| Individual Sample > Gas | Gas in container | General sample types > Gas in container |
| Individual Sample > Human Tissue Sample | Human tissue | Biological samples > Human tissue |
| Individual Sample > Liquid | Liquid in container | General sample types > Liquid in container |
| Individual Sample > Mechanical Fraction | Mechanical fraction | Analytical preparations > Mechanical fraction |
| Individual Sample > Powder | Powder | Analytical preparations > Powder |
| Individual Sample > Slab | Slab | Analytical preparations > Slab |
| Individual Sample > Smear | Glass slide smear | Analytical preparations > Glass slide smear |
| Individual Sample > Specimen | Individual sample | General sample types > Individual sample |
| Individual Sample > Squeeze Cake | Squeeze cake | Analytical preparations > Squeeze cake |
| Individual Sample > Thin Section | Thin section | Analytical preparations > Sectioned specimen > Thin section |
| Individual Sample > Toothpick | Toothpick | General sample types > Toothpick |
| Individual Sample > Wedge | Wedge | Analytical preparations > Wedge |
| Oriented Core | Oriented Core | General sample types > Oriented Core |
| Other | Material sample | Material sample |
| Rock Powder | Powder | Analytical preparations > Powder |
| Site | Site | Sampling features > Site |
| Terrestrial Section | Terrestrial section | Sampling features > Terrestrial section |
| Trawl | Trawl | Marine and lacustrine samples > Trawl |
