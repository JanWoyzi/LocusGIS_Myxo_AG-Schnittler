# Myxomycete field collection template for Locus GIS

This repository provides a Locus GIS XML layer template for recording myxomycete samples during fieldwork with multiple collectors.

## Installation

1. Install Locus GIS on your Android device.
2. Download [Nivicolous_myxos_2024.xml](./Nivicolous_myxos_2024.xml) from this repository using GitHub's download raw file option. Save the XML file, not the GitHub web page.
3. Open the project in Locus GIS in which you want to collect samples.
4. Use the application's create-layer-from-template function and select `Nivicolous_myxos_2024.xml`.
5. Check that the resulting layer is named `Nivicolous myxos` and contains the parameters listed below.

The exact menu sequence and any required file-placement steps have not yet been verified for a specific Locus GIS version. If the template is not available for selection, these version-specific steps still need to be documented. The official Locus GIS support forum describes the [create-layer-from-template functionality](https://help.locusgis.com/support/discussions/topics/47000642020).

## Parameters

Empty cells indicate information that has not yet been established. Required status, field types, options, and defaults are taken from the XML template.

| Parameter | Expected entry or configured value | Required | Description |
|---|---|---|---|
| `Accession` | Automatically numbered integer; starts at `1`; editable | Yes | Accession number; used as the primary display attribute and map label. |
| `Box` | Integer | Yes | number of boxes with the same accession number. |
| `Species` | Text | Yes | Species entry. |
| `Location` | Select one: `Loc01`, `Loc02` | No | Personalized location code. |
| `Size` | Integer | No | Estimate of colony size. |
| `Sub_type` | Select one: `tw`, `lh`, `ll` | No | Substrate type on which the colony was found: tw = twig, lh = , ll =  |
| `Sub_art` | Text | No | Species name of substrate if possible. |
| `Life` | Boolean (`true` or `false`); default `false` | No | Is substrate alive or dead? |
| `Height_cm` | Integer | No | Height (in cm) of the colony, measured from the ground. |
| `Snow_dist_m` | Integer | No | Distance to the next snow edge or patch in meters. |
| `Date` | Date; default `CURRENT_TIME` | Yes | Date field; automatic. |
| `X_coordinate` | Geometry-derived X coordinate | Yes | Expression transforms the geometry to CRS `4326`, extracts X, and rounds to eight decimal places. |
| `Y_coordinate` | Geometry-derived Y coordinate | Yes | Expression transforms the geometry to CRS `4326`, extracts Y, and rounds to eight decimal places. |
| `XY_prec` | Locus GIS horizontal-accuracy field (`ACCURACY_HOR_AVG`) | No | |
| `Elevation` | Geometry-derived Z coordinate | No | Expression extracts Z from the geometry and rounds to two decimal places. |
| `Elev_prec` | Locus GIS vertical-accuracy field (`ACCURACY_VER_AVG`) | No | |
| `Remark` | Text | No | Place for remarks. |

## Use with multiple collectors

Use the same template and agree on field definitions and numbering before collecting samples. The template starts accession numbering at `1` and does not define a cross-device numbering or synchronization mechanism. Ensure that physical samples can be matched unambiguously to their digital records when combining records from different collectors.

## License

See [LICENSE](./LICENSE) for the MIT license.
