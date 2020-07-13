# X Usecase Profile

Note: X is the undetermined Section Number

Profile name is still under discussion.

Candidates: \<Prerequisite Product Policy Profile\>, \<Applicable Condition Profile\>, \<Artifact Policy Profile\>

## Overview

When required license conditions or any requirements are changed dynamically such as in each development phase and in final product shipment to the public, software package supplyer need to tell its consumers detail conditions to be obey.
Especially in the large scale development which operated via multi layer software supply chain through upstream to downstream, community to industorial company, license conditions must be carried through upstream side to downstream side along with the software package through such multi layer supply chain.

On the other hand, each software package are used as in consumer's own will and purpose under the license condition. Even though the  software package supplyer able to notice detail usage and condition just their own prerequisite assumption.

With this profile, software package supplyer able to describe detail license conditions or any requirements to use software package along with its prerequisite assumptions of the detail descriptions. And also it's able to focus those informations for specific usecase of specific downstream consumer with mention the prerequisite product and the expiration date. 

---------
\< Manage licenses compatible with the final product and clarify responsibility in the supply chain\>

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

\<Quality Management\> \<Functional Safety\>
どこに入れるか含めて、相談

コミュニティの評価という側面を持つ

・ Who obtained certification

・ Information of authentication

  FuSaに関して、ガワだけ作って、後から成型、というのがＯＫか、あるいは、SPDX 3.0からドロップか要議論
  
  以下は、AGL IC-EGからの提案で、CommunityのFuSa(QM)関連の健全性情報がSPDXとして取り扱えると良い、という提案
  URL情報をSPDXに埋め込むなどとして、Ruleの所在有無をトレースできるようにしたい、とのこと

・ Contribution Rule

・ Coding Rule and/or Style Guide


\<Clarification of who contributed to the community\>

・ Who contributed to the community in the Supply Chain

・ The evidences of the contribution
  
  Fusa, Contribution責任は別Profileとすべきか要議論
  
  
  下記は、下流から上流への送付を前提とした記述が残っているので、要修正

-----

## License Compatibility For Prerequisite Product fields <a name="X.1"></a>

### Entities
| Entity | Parent | Required | Cardinality |
| ------ | ------ | -------- | ----------- |
| [Prerequisite Product Information](#prerequisite-product-information) | [Artifact](2-base-profile.md#artifact) ([Package](2-base-profile.md#package), [File](2-base-profile.md#file), [Snippet](2-base-profile.md#snippet)) | Yes | one |
| [License Compatiblity For Prerequisite Product](#license-compatibility-for-prerequisite-product) | [Prerequisite Product Information](X-usecase-profile.md#prerequisite-product-information) | No | 0..* |
| [Expriation Date of Usecase Information](#expiration-date-of-usecase-information) |  [Prerequisite Product Information](X-usecase-profile.md#prerequisite-product-information) | No | 0..* |

## Prerequisite Product Information

Parent: Package, File, Snippet, or External Artifact

Cardinality: upto 1 per Artifact

### Fields
| Field | Required | Cardinality |
| ----- | -------- | ----------- |
| [Prerequisite Product Name](#prerequisite-product-name-tag) | No | 0..1 |
| [Prerequisite Product Identifier](#prerequisite-product-identifier-tag) | Yes | one |
| [Prerequisite Product Version](#prerequisite-product-version-tag) | No | 0..* |

### Prerequisite Product Name
#### Purpose

Identify the name of the target product that used as the prerequisite for license compatibility assumption. The metadata for the Product Name field is shown in Table XX1.

Table XX1 — Metadata for the product information field

| Attribute | Value |
| --------- | ----- |
| Required | No |
| Cardinality | 0..1 |
| Format | Single line of text. |

<br>

#### Intent

Describe target product to be identified with this "usecase" profile to manage Lisence Information of software packages to be integrated. 

#### Tag: `PrerequisiteProductName:`

Examples:

```text
ProductName: ABC COMPANYs Product to be Launched at 20YYMM-TBD
```


### Prerequisite Product Identifier
#### Purpose

Identify the target product even if the name of product not determined yet.

| Attribute | Value |
| --------- | ----- |
| Required | Yes |
| Cardinality | One |
| Format | ["DocumentRef-"`[idstring]`":"`[SPDXID]`] \| `NONE` \| `NOASSERTION` |

where:

"DocumentRef-"`[idstring]`: is an optional reference to an external SPDX
document as described in [section 2.6](2-document-creation-information.md#2.6)
`[idstring]` is a unique string containing letters, numbers, `.` and/or `-`

`[NONE]`, if the file contains no target product information whatsoever; or

`[NOASSERTION]`, if:

(i) the SPDX file creator has made no attempt to determine this field; or
(ii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

<br>

#### Intent

Describe target product to be identified with this "usecase" profile to manage Lisence Information of software packages to be integrated. 

#### Tag: `PrerequisiteProductIdentifier:`

Examples:

```text
PrerequisiteProductIdentifier: DocumentRef-spdx-tool-1.2:SPDXRef-5
```

### Prerequisite Product Version

#### Purpose

Identify the version of the target product.


| Attribute | Value |
| --------- | ----- |
| Required | No |
| Cardinality | 0..* |
| Format | Single line of text. |

#### Intent

To describe license compatibility with the prerequisite product when it depend on the specific revision. 

#### Tag: `PrerequisiteProductVersion:`

## License Compatibility For Prerequisite Product

Parent: Prerequisite Product Information, or External Artifact


#### Fields
| Field | Required | Cardinality |
| ----- | -------- | ----------- |
| [License Compatibility For Prerequisite Prodcut](#license-compatibility-for-prerequisite-product-tag) | Yes | 1..1 |
| [Acceptable Usecase of the License](#acceptable-usecase-of-the-license-tag) | No | 0..* |


### License Compatibility For Prerequisite Product

#### Purpose

Identify compatibility of the license of the artifact compatible to prerequisite product.

| Attribute | Value |
| --------- | ----- |
| Required | No |
| Cardinality | 0..1 |
| Format | `<SPDX License Expression>` \| ["DocumentRef-"`[idstring]`":"`[SPDXID]`] \| `NONE` \| `NOASSERTION` |

where:

`<SPDX License Expression>` is a valid SPDX License Expression
as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md).

"DocumentRef-"`[idstring]`: is an optional reference to an external SPDX
document as described in [section 2.6](2-document-creation-information.md#2.6)
`[idstring]` is a unique string containing letters, numbers, `.` and/or `-`

`[NONE]`, if the file contains no target product information whatsoever; or

`[NOASSERTION]`, if:

(i) the SPDX file creator has made no attempt to determine this field; or
(ii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

<br>



#### Intent

To describe license compatibility with the prerequisite product when it used in the public or the market. 

#### Tag: `LicenseCompatibilityForPrerequisiteProduct:`

### Acceptable Condition 

Parent: Prerequisite Product Information, or External Artifact

#### Purpose

Identify the acceptable usecase or acceptable license condition on the prerequisite product development.

| Attribute | Value |
| --------- | ----- |
| Required | No |
| Cardinality | 0..* |
| Format | Single line of text. |

#### Intent

To describe any notice correspond to usage of Artifact, especially license compatibility, conditions to ovey license terms and/or usecase limitations under the conditions for development of prerequisite product.

In the case of description of license compatibility which depend on development phase of the prerequisite product development, it abl e to identfy with this field mentioned as "verification", "evaluation", etc.

In other case, to describe  
広告条項などの個別具体的な条文が関わる場合も含む

#### Tag: `AcceptableCondition:`


### Acceptable Artifact Inventory Deadline

#### Purpose

Identify the inventory deadline when the license/condition of the artifact is acceptable on the specific development phase.

| Attribute | Value |
| --------- | ----- |
| Required | No |
| Cardinality | 0..* |
| Format | Single line of text.  |

#### Fields
| Field | Required | Cardinality |
| ----- | -------- | ----------- |
| [Acceptable License Inventory Deadline](#acceptable-license-inventory-deadline-tag) | No | 0..* |


#### Intent

To describe final deadline to eliminate the artifact from the prerequisite product development environment, such as "Review for the mass production", "Preparation of final product build-up", "YYYY-MM-DDThh:mm:ssZ", etc.

#### Tag: `AcceptableLicenseInventoryDeadLine:`


## Expriation Date of Usecase Information

Parent: Prerequisite Product Information, or External Artifact

#### Fields
| Field | Required | Cardinality |
| ----- | -------- | ----------- |
| [Expriation Date of Usecase Information](#expiration-date-of-usecase-information-tag) | No | 0..1 |

### Expriation Date of Usecase Information

#### Purpose

Identify the period of the usecase information is in effect.

| Attribute | Value |
| --------- | ----- |
| Required | No |
| Cardinality | 0..* |
| Format | `[Date]`  |

#### Tag: `ExpriationDateOfUsecaseInformation:`




# From Here: Not modified yet.
# 以下は、Licensing Profileからのコピー
--------------------------------------------
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
