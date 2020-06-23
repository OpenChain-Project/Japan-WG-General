# X Usecase Profile

Xは、章番号

## Overview


---------
< Manage licenses compatible with the final product and clarify responsibility in the supply chain>

下記を先行して記載を試みる

下記の各アイテムを、タグ名(Field)に分解するところから

・ Product information ( Product name, product number, etc. )

・ Compatible license with final product or not

下記についても、まずは、同Profile内で提案する

・ Who adopted the package

・ When adopted the package

・ Temporary adoption or using for Final Product

(If the package is temporary adoption)

   -The schedule of remove
   
   -Who has the responsibility of remove

・Schedule of next report

下記については、先送りの可能性も考慮

<Functional Safety>

・ Who obtained certification

・ Information of authentication
  
  FuSaに関して、ガワだけ作って、後から成型、というのがＯＫか、あるいは、SPDX 3.0からドロップか要議論
  
<Clarification of who contributed to the community>

・ Who contributed to the community in the Supply Chain

・ The evidences of the contribution
  
  別Profileとすべきか
  

-----

# X Product information fields

## X.1 Product information field <a name="X.1"></a>

### X.1.1 Description

Identify the full name of the target product. The metadata for the SPDX version field is shown in Table XX1.

Table XX1 — Metadata for the product information field

| Attribute | Value |
| --------- | ----- |
| Required | Yes |
| Cardinality | 1..1 |
| Format | Single line of text. |

<br>

### X.1.2 Intent

The name of each package is an important conventional technical identifier to be maintained for each package.

### X.1.3 Examples

EXAMPLE 1 Tag: `ProductInformation:`

```text
ProductInformation: SPDX_hogehoge_COMPANYs_Product_Loutched_2112TBD
```



以下は、Licensing Profileからのコピー

### Entities
| Entity | Parent | Required | Cardinality |
| ------ | ------ | -------- | ----------- |
| [Product Information](#product-information) | [Artifact](2-base-profile.md#artifact) ([Package](2-base-profile.md#package), [File](2-base-profile.md#file), [Snippet](2-base-profile.md#snippet)) | Yes | 1..1 |
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
