# Guideline for SPDX Lite

This document describes a procedure to create artifacts for exchaninging 'license information'(* ) between organizations, to comply with oss license, when organization exchange open source software (OSS) and other software packages. In this document, the 'SPDX Lite' is explained for the format in exchanging license information. The supposed product types are consumer products (embedded systems) that are widely distributed (sold) to end users. 

(* )In this document, 'license information' is used for describing the whole set of the artifacts, software packages and other information that are required to be provided when distributing OSS. 


# Table of Contents

1. The need of license information  
1. Mandatory items as license information  
1. How to create license information
1. Samples of license information  


# 1. The Need of License Information 

Open Source Software (OSS) has become essential to modern software development. OSS can be freely used, modified, and distributed by anyone who complies with the associated license conditions. To comply with the terms and conditions of the license, license information of the OSS is required. 

Regarding the shipment of a product that OSS is incorporated into, many companies are involved, such as a module company, a final product company and a sales company. To comply with OSS license for the product, all the companies in the supply chain are required to provide exact license information. Even if only one company fails to provide the proper license information, all the companies in the downstream of the supply chain cannot comply with OSS license. When everyone who engages in the supply chain understandands correctly, the OSS license compliance is achieved appropriately. 

Please read "Open Source Software License Compliance General Public Guide", if you need more detail.
https://github.com/OpenChain-Project/curriculum/tree/master/supplier-leaflet

There are major two challenges for excanging license information between organizations.

  * Regarding license information, there are many items, such as the name of OSS, the version of OSS, the origin of the source code and other various stuff. This complexity of license information may cause the difficulty for the staff to understand all the license information.
  * Regarding the exchanged format, the format requested by a recipient may differ from those requested by other recipients depending on organizations. These differences may cause the diffculty for providers to create and manage many different formats.

To overcome these challenges, this document defines the minimum and neccessary license information, so that anyone can easily create a simple and correct license information. This minimum and neccessary format is called the SPDX Lite. In the following section, the SPDX and the SPDX Lite are explained briefly. 


### SPDX

SPDX®（Software Package Data Exchange®） project, hosted by the Linux Foundation, has a standardized format for exchanging license information, such as software name, version, license and copyright text of software package.
https://spdx.org/


### SPDX Lite

The SPDX specification defines the excellent format to exchange license information between organizations. However, the format defined by the SPDX specification is not so easy for beginners to create and use it without the deep knowledge and tools, due to the required license information related to software package is huge and complex. Therefore, the SPDX Lite has been defined as the minimum format for the oss license compliance in the software supply chain. The fields in the SPDX Lite have been defined collecting from the actual business use cases, so that the SPDX Lite has been well defined to represent license information. The SPDX Lite file can be created and reviewed manually without tools.

The following is a sample of the SPDX Lite. The SPDX Lite format can be easily created by spread sheet.


![spdx-lite](https://user-images.githubusercontent.com/21073492/59993340-ee596500-968a-11e9-8783-5cf9a95ee351.png)

### Relation between SPDX and SPDX Lite

The fields of the SPDX Lite have been selected from the point of view of the manual creation and review, so that the SPDX Lite has defined the minimum format. All the mandatory fields in the SPDX are included in the SPDX Lite as mandatory. The SPDX Lite has the following features.

  * It is very easy for beginners to understand. 
  * It can be the starting point of oss license compliance. 
  * The way describing license information and a software package one by one, which is not complex and is easy to read, enables manual review. 
  * The compatibility between the SPDX and SPDX Lite enables the use of the same compliance tools.

On the other hand, the SPDX can describe wider range of information in software packages.

The use of the SPDX and the SPDX Lite can be selected in negotiation between organizations in the software supply chain in each cases. 


# 2. Mandatory items as license information

The following explains items of SPDX Lite and the necessary reasons for each item.

## SPDX Lite Item List

| SPDX Lite section no. | corresponding SPDX section no. | License Info. | Tag  | 
|:-------|:-------|:--------|:-------|
|L1.1  |2.1  | SPDX Version           |Mandatory, one |
|L1.2  |2.2  | Data License           |Mandatory, one |
|L1.3  |2.3  | SPDX Identifier        |Mandatory, one |
|L1.4	 |2.4	 | Document Name	        | Mandatory, one |
|L1.5	 |2.5	 | SPDX Document Namespace| Mandatory, one |
|L1.6	 |2.8	 | Creator	              | Mandatory, one or many |
|L1.7  |2.9  | Created                | Mandatory, one |
|L2.1	 |3.1	 | Package Name	          | Mandatory, one |
|L2.2	 |3.2	 | Package SPDX Identifier| Mandatory, one |
|L2.3	 |3.3	 | Package Version        | Optional, one |
|L2.4	 |3.4	 | Package File Name      | Optional, one |
|L2.5	 |3.7	 | Package Download Location | Mandatory, one |
|L2.6	 |3.8	 | Files Analyzed         | Optional, one |
|L2.7  |3.11 | Package Home Page      | Optional, one |
|L2.8	 |3.13 | Concluded License      | Mandatory, one |
|L2.9	 |3.15 | Declared License       | Mandatory, one |
|L2.10 |3.16 | Comments on License    | Optional, one |
|L2.11 |3.17 | Copyright Text         | Mandatory, one |
|L2.12 |3.20 | Package Comment        | Optional, one |
|L3.1	 |6.1	 | License Identifier     | Conditional (mandatory, one) |
|L3.2	 |6.2	 | Extracted Text         | Conditional (mandatory, one) |
|L3.3	 |6.3	 | License Name           | Conditional (mandatory, one) |
|L3.4	 |6.5	 | License Comment        | Conditional (mandatory, one) |


If you do not know a value of fields, write "NOASSERTION".

### L1.1　SPDX Version
This field is the version number of the SPDX specification. This value identifies the SPDX specification that is used in an SPDX Lite file.

### L1.2　Data License
This field is the license for an SPDX file. In an SPDX Lite case, the value is set "CC0-1.0".

### L1.3　SPDX Identifier
This field is the identifier for an SPDX Lite file. The value is set a unique number in each SPDX file.

### L1.4　Document Name
This field is the name of an SPDX Lite file.

### L1.5　SPDX Document Namespace
This field is the document namespace of an SPDX Lite file. The namespace is written by Uniform Resource Identifier (URI). The namespace is used when the SPDX Lite file is referenced externally.

### L1.6　Creator
This field is the creator of an SPDX Lite file. This field identifies who created the SPDX Lite file. If the SPDX Lite file was created by an individual, indicate the person's name. If the SPDX Lite file was created on behalf of a company or organization, indicate the entity name. If the SPDX Lite file was created using a software tool, indicate the name and version for that tool. If multiple participants or tools were involved, use multiple instances of this field. Person name or organization name may be designated as “anonymous” if appropriate.

”Person: person name” and optional “(email)”
"Organization: organization” and optional “(email)”
"Tool: toolidentifierversion”

### L1.7　Created
This field is the date when the SPDX Lite file was created.

### L2.1　Package Name
This field is the name of the software package. This field identifies the software used.

### L2.2　Package SPDX Identifier
This field is the identifier that makes the software package unique in the SPDX Lite file. Software package is referenced by this field. This field distinguishes uniquely the package from the same software package. The uniqueness of the identifier is ensured by the creator.

### L2.3　Package Version
This field is the software package version. This field identifies the version of software.

### L2.4　Package File Name
This field is the actual file name of the software package. This item is used to identify the actual file of the software being used. This item is necessary because Package Name and the actual file may not be related due to the difference in the name.

### L2.5　Package Download Location
This field is the location where the software package was obtained. This field is used to obtain the same software being used.

### L2.6　Files Analyzed
This field indicates whether the file content of this package has been available for or subjected to analysis when creating the SPDX document. Write "false" when creating SPDX Lite file manually.

### L2.7　Package Home Page
This field is the home page of the software package. This field is used to obtain community information such as vulnerability information of the software being used.
(Note the difference between this field and L2.5 Package Download Location)

### L2.8　Concluded License
This is the license that the creator of the SPDX Lite file concludes that it applies to the software package. If the Concluded License is different from the Declared License, you should provide a description on the Comments on License. For NOASSERTION, it is better to describe in Comments on License. This field identifies the license of the software being used.

In addition, it is recommended to describe the license name to be described according to the Identifier of SPDX License List at the following URL.
https://spdx.org/licenses/

### L2.9　Declared License
This is the license declared by the creator of the software package. If the Concluded License is different from the Declared License, you should provide a description on the Comments on License. For NOASSERTION, it is better to describe in Comments on License.This field identifies the license of the software being used.

In addition, it is recommended to describe the license name to be described according to the Identifier of SPDX License List at the following URL.
https://spdx.org/licenses/

### L2.10　Comments on License
This field is the reason for the creator of the SPDX Lite file to conclude the information related to the license and the license. This field is used to supplement the license of the software being used.

Also, describe either the dynamic link or static link for the software being used.If the compile option excludes the specific license of the software you are using, the compile option will be described in this item. Certain licenses affect other things depending on how the software is linked. Therefore, this item is used to specify how to link software.


### L2.11　Copyright Text
This field is the copyright information of the software package. If it is difficult to extract all copyright information, we will provide the source code together.

Certain licenses require that you provide copyright information at the time of distribution. This item is used to identify the copyright information of the software being used.


### modification record

Write "true" if the software package has been modified.
If the software package has not been modified, "false" is described.

In order to make your own modifications to the OSS source code or to judge that the OSS source code has been partially modified, "true" is described.

This item does not exist in SPDX. This item is unique to SPDX Lite.
Certain licenses have licensing terms that you must follow when modifying the software. Therefore, this item is used to specify software modifications.

### License Identifier

For licenses not listed in the SPDX License List, enter a unique identifier.
This item is used to identify the license of the software being used.

### Extracted Text

If the license is not listed in the SPDX License List, enter the license terms.
This item is used to supplement the license of the software being used.

### License Name

SPDX license For licenses not listed, enter the license name.
This item is used to identify the license name of the software being used.

### License Comment

SPDX License For licenses not listed, provide information related to the license.
This item is used to supplement the license of the software being used.

### Remarks

For items that can not be described, describe "NOASSERTION" and provide contact information that can be used to inquire about the software package being used.

# 3. How to create license information materials manually

It is important to describe license information as much as possible. The recipient of OSS  needs license information as much as possible for complying with OSS licenses. Even if you do not know exact information, it is recommended to describe license information with a comment to explain. 

An SPDX or SPDX Lite file can be created by either a scanning tool or manual work. 

## 3.1 tools for creating license information files

The Linux Foundation provides resources for tools.

  * Japanese: https://www.linuxfoundation.jp/resources/open-source-guides/tools-managing-open-source-programs/ 
  * English: https://www.linuxfoundation.org/resources/open-source-guides/tools-managing-open-source-programs/

## 3.2 manually creating license information files 

In the following section, a sample procedure is explained. The procedure create a sample license information file for the software package "busybox-1.30.1". In this example, the software package file "busybox-1.30.1.tar.bz2" is assumed to be provided. 



### PackageName, PackageVersion, PackageFileName

Obtain the target source code or the target software package.  
And identify these from files such as "README" in the acquired source code.

### SPDXID

Write any string that can be uniquely identified.

### PackageDownloadLocation

Identify the origin of the software.  
If you obtained the software from a third party vendor etc, please get the information from that company.  

### FilesAnalyzed

Just fill fixed value of `false` when creating manually.

### PackageHomePage

Search the website for the software from the package name.  
If you find more than one target website, please check based on the download location, version and its feature.  

### PackageLicenseConcluded, PackageLicenseDeclared

Check files such as "COPYING", "LICENSE" and "README" in the package or search license comments in source code header. If you can not find anything in the source code, please also check the website of the package.  
And state the appropriate [SPDX-Short-Identifier](https://spdx.org/licenses/) you choose as a license.

### PackageLicenseComments

Write comments if any. And if not, leave blank.

### PackageCopyrightText

Check files such as "COPYING", "LICENSE" and "README" in the package or search copyright text in source code header. And fill the copyright text here.

### ModifiedStatus `TBD`

If the supplier has modified the original source code, write `true` here. If not, write `false`.

### LicenseID, ExtractedText, LicenseName, LicenseComment

Write information about licenses that are not found on the [SPDX&reg; License List](https://spdx.org/license-list).
For details, please refer to `6.1 License Identifier` of [SPDX&reg; Specification](https://spdx.org/specifications).

- LicenseID  
Write any string that can be uniquely identified.

- ExtractedText  
Write a copy of the actual text of the license reference extracted from the package or file that is associated with the LicenseID.

- LicenseName  
Write a common name of the license that is not on the SPDX list.

- LicenseComment  
Write comments if any. And if not, leave blank.

# 4. Examples of creating license materials

In the software supply chain, the side that receives license information needs as much information as possible to comply with the license.  
Therefore, it is recommended to describe as much license information as possible even if it is not clear for you. And in that case, you should show that it is not clear in the comments.

## 4.1 an Example how to create the license information from only binary package

`TBD`

## 4.2 an Example how to create the license information from the source code

Using [busybox-1.30.1](https://git.busybox.net/busybox/tree/?h=1_30_stable) located at https://busybox.net/ as an example.

- PackageName  
`busybox`  
Judged from [README](https://git.busybox.net/busybox/tree/README?h=1_30_stable) file.

- SPDXID  
`SPDXRef-1`  
Filled arbitrary string.

- PackageVersion  
`1.30.1`  
Judged from [Makefile](https://git.busybox.net/busybox/tree/Makefile?h=1_30_stable) file.

- PackageFileName  
`busybox-1.30.1.tar.bz2`  

- PackageDownloadLocation  
`https://busybox.net/downloads/busybox-1.30.1.tar.bz2`  

- FilesAnalyzed  
`false`  

- PackageHomePage  
`https://busybox.net/about.html`  

- PackageLicenseConcluded  
`GPL-2.0-only`  
Judged from [LICENSE](https://git.busybox.net/busybox/tree/LICENSE?h=1_30_stable) file.

- PackageLicenseDeclared  
`GPL-2.0-only`  
Judged from [LICENSE](https://git.busybox.net/busybox/tree/LICENSE?h=1_30_stable) file.

- PackageLicenseComments  
`blank`  

- PackageCopyrightText  
`NOASSERTION`  
Since busybox has many different copyright notices, provide source code together with NOASSERTION.

- ModificationStatus  
`false`  
Leave blank because there are no modification.

- License Identifier, Extracted Text, License Name, License Comment  
`blank`  
Leave blank because there are no licenses not listed in the SPDX&reg; license list.

# 5. Other complicated examples

`TBD`
