# Proposal of SPDX Lite

### Proposed by the OpenChain Japan Work Group / License Info Subgroup


## 1. Background



### 1.1 Issue of license

* Appropriate license information is not provided by suppliers. Some suppliers do not know OSS license.  (Knowledge)

* Other suppliers indirectly refuse to provide license info..  (Workload)
  * “I do not know OSS license...”
  * “Only your company requests such info...”

* Different customers ask different formats.  (No Standard)
  * In automotive industry, a supplier has many customer companies. 


### 1.2 Issues of copyright notice

Background
Companies want to do internal compliance process automatically by tools.

* Copyright notice is not at all written in the source code from upper stream.  (Knowledge)

* Copyright is written, but in the different ways in each source code. (No Standard)
  * There are too many patterns to scan automatically by tools. Therefore engineers do compliance tasks, instead of development.

## 2. Discussion 

It is nice to make a guideline for exchanging license info. including copyright notice. 
Exchanging license info. between organization is out of scope of the OpenChain.
Guideline does not give rules that a company must comply with. 
Guideline is a good way to show an appropriate procedure. 

There is the SPDX, we should use the standard. 
Reinvention is not good. Intermittent suppliers in the supply chain like semiconductor companies have to hold all the information.
If an intermittent supplier lose information, a company in down stream cannot recover it.
Some companies are using the SPDX.


However, in the supply chain, there are many small companies that cannot make an SPDX file by themselves.
SPDX specification is not broadly known by engineers.
Making an SPDX file requires to use compliance tools. 
In some cases, the size of an SPDX file is very huge due to “RELATIONSHIP”.

REUSE initiative gives us the good path to access OSS communities
It recommends a standard to write copyright notice and license notice.
Standardization of notice is good for machine to do compliance process.
It also recommends SPDX. 
Japan WG does not have the appropriate paths to OSS communities, but REUSE initiative can access broadly.


## 3. SPDX Lite

A proposal of newly creating "SPDX Lite" has been discussed in subgroup of Japan WG.
* SDPX Lite:
  * Should be easy to understand
  * Should be easy to make
  * Should have enough information to comply with OSS license
  * Should have the affinity with SPDX, that means the subset of SPDX.


We think SPDX and SPDX Lite can cover all the supply chain.

SPDX Lite is the entry point to the SPDX world.
We hope entry users change their format from SPDX Lite to SPDX.


Case study on actually used list.
Almost items are included in Package Information

Candidate is created by the lists that are actually used in business.

SPDX is designed to carry the information from upper stream to down stream. (Downward)

Some companies including OEM companies want to manage software in the supply chain.
A company’s policy may not allow to use copyleft license.
This means that an entity in down stream want to manage the stream(the supply chain). (Upward)

It is useful for business to define an additional file besides the SPDX file. (ongoing)

## 4. Table of SPDX Lite (Candidate)

| SPDX section no. | License Info. | Tag  | SPDX Lite  | Rationale      |
|:------------|:-------------|:------------------|:------------------|:------------------|
|3.1	|Package Name	| PackageName |Yes|To identify software	|
|3.2	|Package SPDX Identifier	| SPDXID|Yes| To keep compatibility with SPDX. Feedback from SPDX team. |
|3.3	|Package Version	| PackageVersion |Yes|To identify specific version	|
|3.4	|Package File Name	| PackageFileName	|Yes|To identify specific package|
|3.7	|Package Download Location 	| PackageDownloadLocation |Yes|To get the identical software	|
|3.8	|Files Analyzed	|	FilesAnalyzed |Yes| In SPDX Lite, to set "false". To keep compatibility with SPDX. Feedback from SPDX team. |
|3.11	|Package Home Page	| PackageHomePage	|Yes|To verify relevant information|
|3.13	|Concluded License	| PackageLicenseConcluded	|Yes||
|3.15	|Declared License	| PackageLicenseDeclared	|Yes||
|3.16	|Comments on License	| PackageLicenseComments	|Yes|To verify additional conditions|
|3.17	|Copyright Text	| PackageCopyrightText	|Yes||
|	|	+ modification record| ExternalRef |Yes|To comply with license obligation|
|6.1	|License Identifier	| LicenseID	|Yes|To specify licenses which are not on the SPDX license list / To specify dual license|
|6.2	|Extracted Text	| ExtractedText	|Yes|To specify licenses which are not on the SPDX license list / To specify dual license|
|6.3	|License Name	| LicenseName	|Yes|To specify licenses which are not on the SPDX license list / To specify dual license|
|6.5	|License Comment	| LicenseComment	|Yes|To specify licenses which are not on the SPDX license list / To specify dual license|


