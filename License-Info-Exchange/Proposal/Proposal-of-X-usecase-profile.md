# X Usecase Profile

Xは、章番号

## Overview
---------
< Manage licenses compatible with the final product and clarify responsibility in the supply chain>
・ Product information ( Product name, product number, etc. )
・ Compatible license with final product or not
・ Who adopted the package
・ When adopted the package
・ Temporary adoption or using for Final Product
  (If the package is temporary adoption)
   -The schedule of remove
   -Who has the responsibility of remove
・Schedule of next report
<Functional Safety>
・ Who obtained certification
・ Information of authentication
<Clarification of who contributed to the community>
・ Who contributed to the community in the Supply Chain
・ The evidences of the contribution
< Using Facets defined by "ClearlyDefined " for classification of compatibility with the final product >
core - The files that go into making the release of the component.
data - The files included in any data distribution of the component.
dev - Files primarily used at development time (e.g., build utilities) and not distributed with the component
docs - Documentation files.
examples – Like docs, examples may be included in the main component release or separately.
tests – Test files may include code, data and other artifacts.
-----

以下は、Licensing Profileからのコピー

### Entities
| Entity | Parent | Required | Cardinality |
| ------ | ------ | -------- | ----------- |
| [License Information](#license-information) | [Artifact](2-base-profile.md#artifact) ([Package](2-base-profile.md#package), [File](2-base-profile.md#file), [Snippet](2-base-profile.md#snippet)) | Yes | 1..1 |
| [License Reference](#license-reference) | [Document Root](2-base-profile.md#document-root) | No | 0..* |

## License Information

Parent: Package, File, Snippet, or External Artifact
Cardinality: 1 per Artifact

### Fields
| Field | Required | Cardinality |
| ----- | -------- | ----------- |
| [Discovered License](#discovered-license) | Yes | 1..1 |
| [Declared License](#declared-license) | Yes | 1..1 |
| [Concluded License](#concluded-license) | Yes | 1..1 |
| [Distributed License](#distributed-license) | Yes | 1..1 |
| [Copyright Text](#copyright-text) | Yes | 1..1 |

### Discovered License
#### Purpose

#### Intent
Here, the intent is to provide the license information actually in the file, as compared to the Concluded License field.

**4.6.3** Cardinality: Mandatory, one or many.

**4.6.4** Data Format: `<SPDX License Expression>` |

 ["DocumentRef-"`[idstring]`":"]"LicenseRef-"`[idstring]` |

 | `NONE` | `NOASSERTION`

where:

`<SPDX License Expression>` is a valid SPDX License Expression

as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md).

"DocumentRef-"`[idstring]`: is an optional reference to an external SPDX

document as described in [section 2.6](2-document-creation-information.md#2.6)

`[idstring]` is a unique string containing letters, numbers, `.` and/or `-`

**4.6.5** Tag: `LicenseInfoInFile:`

Example:

    LicenseInfoInFile: GPL-2.0-only
    LicenseInfoInFile: LicenseRef-2

**4.6.6** RDF: Property `spdx:licenseInfoInFile` in class `spdx:File`
