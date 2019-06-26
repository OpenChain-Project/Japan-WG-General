# Guideline for Exchanging License Information between Organization

This document describes a procedure to create artifacts for exchaninging license information between organizations, to comply with oss license. In this document, the supposed product type is embedded systems.

## Table of Contents

1. The need of license information  
1. Mandatory items as license information  
1. How to get license information 
1. How to create license information
1. Samples of license information  

## 1. The Need of License Information 

Open Source Software (OSS) has become essential to modern software development. OSS can be freely used, modified, and distributed by anyone who complies with the associated license conditions. To comply with the terms and conditions of the license, license information of the OSS is required. 

Please read "Open Source Software License Compliance General Public Guide", if you need more detail.
https://github.com/OpenChain-Project/curriculum/tree/master/supplier-leaflet

#### SPDX

SPDX®（Software Package Data Exchange®） project, hosted by the Linux Foundation, has a standardized format for exchanging license information, such as software name, version, license and copyright text of software package.
https://spdx.org/


#### SPDX Lite

The SPDX specification defines the excellent format to exchange license information between organization. However, the format defined by the SPDX specification is not so easy for beginners to create and use it, due to the required data related to software package is huge. 

The SPDX Lite defines the subset that is the minimum requirement of the SPDX foramt. 

The following is a sample of the SPDX Lite.
The SPDX Lite format can be easily created by spread sheet.

![spdx-lite](https://user-images.githubusercontent.com/21073492/59993340-ee596500-968a-11e9-8783-5cf9a95ee351.png)

## 3. How to create license information materials manually

The following explains how to manually write the required items in `SPDX-Lite`.

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

## 4. Examples of creating license materials

In the software supply chain, the side that receives license information needs as much information as possible to comply with the license.  
Therefore, it is recommended to describe as much license information as possible even if it is not clear for you. And in that case, you should show that it is not clear in the comments.

### 4.1 an Example how to create the license information from only binary package

`TBD`

### 4.2 an Example how to create the license information from the source code

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

## 5. More complicated examples

`TBD`
