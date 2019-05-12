# Proposal of SPDX Lite

### This has been proposed by the OpenChain Japan Work Group / License Info Subgroup. 


## Appendix-xx SPDX Lite

## 1. Explanation of SPDX Lite 

The SPDX Lite defines the subset of the SPDX specification, from the point of view of use cases in industries. The SPDX Lite aims at the balance between the SPDX standard and actual workflows in industries. 

The SPDX Lite is the subset of the SPDX specification. The SPDX Lite consists of mandatory part of the Document Creation and Package Information and other basic information. 

The mandatory part of the Package information in the SDPX Lite is basic but indispensable for complying with licenses. It is easy to understand licensing information by reading an SPDX Lite file. It is easy to create manually an SPDX Lite file by anyone who does not have enough knowledge about licensing infomation, so that tools are not necessarily required to create an SPDX Lite file. 

The SPDX Lite has the affinity with SPDX tools due to its containing the mandatory part of the Document Creation and Package Information in the SDPX Lite. 

An SPDX Lite file can be used parallel with an SPDX file in software supply chains. 



## 2. Table of SPDX Lite

| SPDX Lite section no. | corresponding SPDX section no. | License Info. | Tag  | Rationale      |
|:-------|:-------|:--------|:-------|:------------------|
|L1.1	|2.4	|Document Name	| DocumentName |To identify SPDX Lite document	|
|L1.2	|2.5	|SPDX Document Namespace	| DocumentNamespace |To identify SPDX Lite document name	|
|L1.3	|2.8	|Creator	| Creator |To identify creator	|
|L2.1	|3.1	|Package Name	| PackageName |To identify software	|
|L2.2	|3.2	|Package SPDX Identifier	| SPDXID | To keep compatibility with SPDX. Feedback from SPDX team. |
|L2.3	|3.3	|Package Version	| PackageVersion |To identify specific version	|
|L2.4	|3.4	|Package File Name	| PackageFileName	|To identify specific package|
|L2.5	|3.7	|Package Download Location 	| PackageDownloadLocation |To get the identical software	|
|L2.6	|3.8	|Files Analyzed	|	FilesAnalyzed | In SPDX Lite, to set "false". To keep compatibility with SPDX. Feedback from SPDX team. |
|L2.7	|3.11	|Package Home Page	| PackageHomePage	|To verify relevant information|
|L2.8	|3.13	|Concluded License	| PackageLicenseConcluded	||
|L2.9	|3.15	|Declared License	| PackageLicenseDeclared	||
|L2.10	|3.16	|Comments on License	| PackageLicenseComments	|To verify additional conditions|
|L2.11	|3.17	|Copyright Text	| PackageCopyrightText	||
|	|	|	+ modification record| ExternalRef |To comply with license obligation|
|L3.1	|6.1	|License Identifier	| LicenseID	|To specify licenses which are not on the SPDX license list / To specify dual license|
|L3.2	|6.2	|Extracted Text	| ExtractedText	|To specify licenses which are not on the SPDX license list / To specify dual license|
|L3.3	|6.3	|License Name	| LicenseName	|To specify licenses which are not on the SPDX license list / To specify dual license|
|L3.4	|6.5	|License Comment	| LicenseComment	|To specify licenses which are not on the SPDX license list / To specify dual license|


## 3. Specification of SPDX Lite 

### L1. Document Creation 

### L1.1 (2.4) Document Name <a name="2.4"></a>

**L1.1.1 (2.4.1)** Purpose: Identify name of this document as designated by creator.

**L1.1.2 (2.4.3)** Cardinality: Mandatory, one.

**L1.1.3 (2.4.4)** DataFormat: Single line of text.

**L1.1.4 (2.4.5)** Tag: `DocumentName:`

Example:

    DocumentName: glibc-v2.3

    DocumentName: ubuntu-14.04

**L1.1.5 (2.4.6)** RDF: Property `spdx:name` in class `Document`

Example:

    <SpdxDocument rdf:about="...">
      <name>glibc-v2.3</name>
    </SpdxDocument>

    <SpdxDocument rdf:about="...">
      <name>ubuntu-14.04</name>
    </SpdxDocument>

### L1.2 (2.5) SPDX Document Namespace <a name="2.5"></a>

**L1.2.1 (2.5.1)** Purpose: Provide an SPDX document specific namespace.

The URI must be unique for the SPDX document including the specific version of the SPDX document. If the SPDX document is updated, thereby creating a new version, a new URI for the updated document must be used. There can only be one URI for an SPDX document and only one SPDX document for a given URI.

**L1.2.2 (2.5.3)** Cardinality: Mandatory, one.

**L1.2.3 (2.5.4)** Data Format: unique absolute Uniform Resource Identifier (URI) as specified in [RFC-3986](https://tools.ietf.org/html/rfc3986), with the following exceptions:

The SPDX Document URI cannot contain a URI "part" (e.g. the `#` delimiter), since the `#` is used to uniquely identify SPDX element identifiers.
The URI must contain a scheme (e.g. `https:`).

The URI must be unique for the SPDX document including the specific version of the SPDX document. If the SPDX document is updated, thereby creating a new version, a new URI for the updated document must be used. There can only be one URI for an SPDX document and only one SPDX document for a given URI.

**L1.2.4 (2.5.5)** Tag: `DocumentNamespace:`

Example:

    DocumentNamespace: http://spdx.org/spdxdocs/spdx-tools-v1.2-3F2504E0-4F89-41D3-9A0C-0305E82...

**L1.2.5 (2.5.6)** RDF: The unique ID is the URI for the SPDX document

Example:

    <SpdxDocument rdf:about="http://spdx.org/spdxdocs/spdx-tools-v1.2-3F2504E0-4F89-41D3-9A0C-0305E82...">
        <rdfs:comment>This document was created using SPDX 2.0 using licenses from the web site.</rdfs:comment>
    </SpdxDocument>

### L1.3 (2.8) Creator <a name="2.8"></a>

**L1.3.1 (2.8.1)** Purpose: Identify who (or what, in the case of a tool) created the SPDX file. 

**L1.3.2 (2.8.3)** Cardinality: Mandatory, one or many.

**L1.3.3 (2.8.4)** Data Format: Single line of text with the following keywords:

    ”Person: person name” and optional “(email)”
    "Organization: organization” and optional “(email)”
    "Tool: toolidentifier-version”

**L1.3.4 (2.8.5)** Tag: `Creator:`

Example:

    Creator: Person: Jane Doe ()
    Creator: Organization: ExampleCodeInspect ()
    Creator: Tool: LicenseFind-1.0

**L1.3.5 (2.8.6)** RDF: Property `spdx:creator` in class `spdx:CreationInfo`

Example:

    <CreationInfo>
        <creator> Person: Jane Doe () </creator>
        <creator> Organization: ExampleCodeInspect () </creator>
        <creator> Tool: LicenseFind-1.0 </creator>
    </CreationInfo>

### L2. Pacage Information

### L2.1 (3.1) Package Name <a name="3.1"></a>

**L2.1.1 (3.1.1)** Purpose: Identify the full name of the package as given by the [Package Originator](#3.6).

**L2.1.2 (3.1.3)** Cardinality: Mandatory, one.

**L2.1.3 (3.1.4)** Data Format: Single line of text.

**L2.1.4 (3.1.5)** Tag: `PackageName:`

Example:

    PackageName: glibc

**L2.1.5 (3.1.6)** RDF: property `spdx:name` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        <name>glibc</name>
    </Package>

### L2.2 (3.2) Package SPDX Identifier <a name="3.2"></a>

**L2.2.1 (3.2.1)** Purpose: Uniquely identify any element in an SPDX document which may be referenced by other elements. These may be referenced internally and externally with the addition of the SPDX Document Identifier.

**L2.2.2 (3.2.3)** Cardinality: Mandatory, one.

**L2.2.3 (3.2.4)** Data Format: "SPDXRef-"`[idstring]`

where `[idstring]` is a unique string containing letters, numbers, `.`, and/or `-`.

**L2.2.4 (3.2.5)** Tag: `SPDXID:`

Example:

    SPDXID: SPDXRef-1

**L2.2.5 (3.2.6)** RDF: The URI for the element will follow the form:

    [SPDX DocumentNamespace]#[SPDX Identifier]

See [section 2.5](2-document-creation-information.md#2.5) for the definition of the SPDX Document Namespace and [section 2.3](2-document-creation-information.md#2.3) for the definition of the SPDX Identifier

Example using `xml:base`:

    <rdf:RDF xml:base="http://acme.com/spdxdocs/acmeproj/v1.2/1BE2A4FF-5F1A-48D3-8483-28A9B0349A1B">
        ...
        <Package rdf:ID="SPDXRef-1">
        ...
        </Package>
    </rdf:RDF>

Example using document URI:

    <Package rdf:about="http://acme.com/spdxdocs/acmeproj/v1.2/1BE2A4FF-5F1A-48D3-8483-28A9B0349A1B">
        ...
    </Package>

### L2.3 (3.3) Package Version <a name="3.3"></a>

**L2.3.1 (3.3.1)** Purpose: Identify the version of the package.

**L2.3.2 (3.3.3)** Cardinality: Optional, one.

**L2.3.3 (3.3.4)** Data Format: Single line of text.

**L2.3.4 (3.3.5)** Tag: `PackageVersion:`

Example:

    PackageVersion: 2.11.1

**L2.3.5 (3.3.6)** RDF: property `spdx:versionInfo` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <versionInfo>2.11.1</versionInfo>
        ...
    </Package>

### L2.4 (3.4) Package File Name <a name="3.4"></a>

**L2.4.1 (3.4.1)** Purpose: Provide the actual file name of the package, or path of the directory being treated as a package. This may include the packaging and compression methods used as part of the file name, if appropriate.

**L2.4.2 (3.4.3)** Cardinality: Optional, one.

**L2.4.3 (3.4.4)** Data Format: Single line of text.

**L2.4.4 (3.4.5)** Tag: `PackageFileName:`

Example:

    PackageFileName: glibc-2.11.1.tar.gz

Example (subdirectory being treated as a package):

    PackageFileName: ./myrootdir/mysubdir1

**L2.4.5 (3.4.6)** RDF: property `spdx:packageFileName` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <packageFileName>glibc 2.11.1.tar.gz</packageFileName>
        ...
    </Package>

Example (subdirectory being treated as a package):

    <Package rdf:about="...">
       ...
       <packageFileName>./myrootdir/mysubdir1</packageFileName>
       ...
    </Package>

### L2.5 (3.7) Package Download Location <a name="3.7"></a>

**L2.5.1 (3.7.1)** Purpose: This section identifies the download Universal Resource Locator (URL), or a specific location within a version control system (VCS) for the package at the time that the SPDX file was created.

Use:

* `NONE` if there is no download location whatsoever.
* `NOASSERTION` if:

    (i) the SPDX file creator has attempted to but cannot reach a reasonable objective determination;

    (ii) the SPDX file creator has made no attempt to determine this field; or

    (iii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

**L2.5.2 (3.7.3)** Cardinality: Mandatory, one.

**L2.5.3 (3.7.4)** Data Format: uniform resource locator | VCS location | `NONE` | `NOASSERTION`

**L2.5.4 (3.7.5)** Tag: `PackageDownloadLocation:`

Examples if ambiguous:

    PackageDownloadLocation: NOASSERTION

    PackageDownloadLocation: NONE

Example for a plain URL:

    PackageDownloadLocation: http://ftp.gnu.org/gnu/glibc/glibc-ports-2.15.tar.gz


**L2.5.5 (3.7.6)** RDF: property `spdx:downloadLocation` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        <downloadLocation>http://ftp.gnu.org/gnu/glibc/glibc-ports-2.15.tar.gz</downloadLocation>
    </Package>

    <Package rdf:about="...">
        <downloadLocation>
            git+https://git.myproject.org/MyProject.git@v10.0#src/lib.c
        </downloadLocation>
    </Package>

    <Package rdf:about="...">
        <downloadLocation rdf:resource="http://spdx.org/rdf/terms#noassertion"/>
    </Package>

    <Package rdf:about="...">
        <downloadLocation rdf:resource="http://spdx.org/rdf/terms#none"/>
    </Package>

### L2.6 (3.8) Files Analyzed <a name="3.8"></a>

**L2.6.1 (3.8.1)** Purpose: Indicates whether the file content of this package has been available for or subjected to analysis when creating the SPDX document. If `false`, indicates packages that represent metadata or URI references to a project, product, artifact, distribution or a component. If `false`, the package must not contain any files. 

### Note: In the SPDX Lite, `false` must be set. 

**L2.6.2 (3.8.3)** Cardinality: Optional, one.  If omitted, the default value of `true` is assumed.

**L2.6.3 (3.8.4)** Data Format: Boolean

**L2.6.4 (3.8.5)** Tag: `FilesAnalyzed`

Example:

    FilesAnalyzed: false

**L2.6.5 (3.8.6)** RDF: property `spdx:filesAnalyzed` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <filesAnalyzed>false</filesAnalyzed>
        ...
    </Package>

### L2.7 (3.11) Package Home Page <a name="3.11"></a>

**L2.7.1 (3.11.1)** Purpose: Provide a place for the SPDX file creator to record a web site that serves as the package's home page. This link can also be used to reference further information about the package referenced by the SPDX file creator.

Use:

* `NONE` if there is no package home page whatsoever.
* `NOASSERTION` if:

    (i) the SPDX file creator has attempted to but cannot reach a reasonable objective determination;

    (ii) the SPDX file creator has made no attempt to determine this field; or

    (iii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

**L2.7.2 (3.11.3)** Cardinality: Optional, one.

**L2.7.3 (3.11.4)** Data Format: uniform resource locator | `NONE` | `NOASSERTION`

**L2.7.4 (3.11.5)** Tag: `PackageHomePage:`

Example:

    PackageHomePage: http://ftp.gnu.org/gnu/glibc

**L2.7.5 (3.11.6)** RDF: property `doap:homepage` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        <doap:homepage >http://ftp.gnu.org/gnu/glibc/</doap:homepage>    </Package>

### L2.8 (3.13) Concluded License <a name="3.13"></a>

**L2.8.1 (3.13.1)** Purpose: Contain the license the SPDX file creator has concluded as governing the package or alternative values, if the governing license cannot be determined.

The options to populate this field are limited to:

* A valid SPDX License Expression as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md);
* `NONE`, if the SPDX file creator concludes there is no license available for this package; or
* `NOASSERTION` if:

    (i) the SPDX file creator has attempted to but cannot reach a reasonable objective determination;

    (ii) the SPDX file creator has made no attempt to determine this field; or

    (iii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

If the Concluded License is not the same as the [Declared License](#3.15), a written explanation should be provided in the Comments on License field [(section 3.16)](#3.16). With respect to `NOASSERTION`, a written explanation in the Comments on License field [(section 3.16)](#3.16) is preferred.

**L2.8.2 (3.13.3)** Cardinality: Mandatory, one.

**L2.8.3 (3.13.4)** Data Format: `<SPDX License Expression>` | `NONE` | `NOASSERTION`

where:

`<SPDX License Expression>` is a valid SPDX License Expression as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md).

**L2.8.4 (3.13.5)** Tag: `PackageLicenseConcluded:`

Example:

    PackageLicenseConcluded: LGPL-2.0

Example:

    PackageLicenseConcluded: (LGPL-2.0 OR LicenseRef-3)

**L2.8.5 (3.13.6)** RDF: property `spdx:licenseConcluded` in `class spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <licenseConcluded rdf:resource="http://spdx.org/licenses/LGPL-2.0" />
        ...
    </Package>

Example:

    <Package rdf:about="...">
        ...
        <licenseConcluded>
             <DisjunctiveLicenseSet>
                 <member rdf:resource="http://spdx.org/licenses/LGPL-2.0" />
                 <member rdf:resource="LicenseRef-3" />
            </DisjunctiveLicenseSet>
        </licenseConcluded>
        ...
    </Package>

### L2.9 (3.15) Declared License <a name="3.15"></a>

**L2.9.1 (3.15.1)** Purpose: List the licenses that have been declared by the authors of the package. Any license information that does not originate from the package authors, e.g. license information from a third party repository, should not be included in this field.

The options to populate this field are limited to:

* A valid SPDX License Expression as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md);
* `NONE`, if the package contains no license information whatsoever; or
* `NOASSERTION` if:

    (i) the SPDX file creator has made no attempt to determine this field; or

    (ii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

**L2.9.2 (3.15.3)** Cardinality: Mandatory, one.

**L2.9.3 (3.15.4)** Data Format: `<SPDX License Expression>` | `NONE` | `NOASSERTION`

where:

* `<SPDX License Expression>` is a valid SPDX License Expression as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md).

**L2.9.4 (3.15.5)** Tag: `PackageLicenseDeclared:`

Example:

    PackageLicenseDeclared: LGPL-2.0

Example:

    PackageLicenseDeclared: (LGPL-2.0 AND LicenseRef-3)

**L2.9.5 (3.15.6)** RDF: property `spdx:licenseDeclared` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <licenseDeclared rdf:resource="http://spdx.org/licenses/LGPL-2.0" />
        ...
    </Package>


Example:

    <Package rdf:about="...">
        ...
         <licenseDeclared>
             <ConjunctiveLicenseSet>
                 <member rdf:resource="http://spdx.org/licenses/LGPL-2.0" />
                 <member rdf:resource="#LicenseRef-3" />
             </ConjunctiveLicenseSet>
        </licenseDeclared>
        ...
    </Package>

### L2.10 (3.16) Comments on License <a name="3.16"></a>

**L2.10.1 (3.16.1)** Purpose: This field provides a place for the SPDX file creator to record any relevant background information or analysis that went in to arriving at the Concluded License for a package. If the Concluded License does not match the Declared License or License Information from Files, this should be explained by the SPDX file creator. Its is also preferable to include an explanation here when the Concluded License is `NOASSERTION`.

**L2.10.2 (3.16.3)** Cardinality: Optional, one.

**L2.10.3 (3.16.4)** Data Format: free form text that can span multiple lines.

In `tag:value` format this is delimited by `<text>...</text>`.

In RDF, it is delimited by `<licenseComment>`.

**L2.10.4 (3.16.5)** Tag: `PackageLicenseComments:`

Example:

    PackageLicenseComments: <text>The license for this project changed with the release of version 1.4.
    The version of the project included here post-dates the license change.</text>

**L2.10.5 (3.16.6)** RDF: property `spdx:licenseComments` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <licenseComments>
            This package has been shipped in source and binary form.
            The binaries were created with gcc 4.5.1 and expect to link to
            compatible system run time libraries.
        </licenseComments>
        ...
    </Package>

### L2.11 (3.17) Copyright Text <a name="3.17"></a>

**L2.11.1 (3.17.1)** Purpose: Identify the copyright holders of the package, as well as any dates present. This will be a free form text field extracted from package information files. The options to populate this field are limited to:

* Any text related to a copyright notice, even if not complete;
* `NONE` if the package contains no copyright information whatsoever; or
* `NOASSERTION`, if

    (i) the SPDX document creator has made no attempt to determine this field; or

    (ii) the SPDX document creator has intentionally provided no information (no meaning should be implied by doing so).

**L2.11.2 (3.17.3)** Cardinality: Mandatory, one.

**L2.11.3 (3.17.4)** Data Format: free form text that can span multiple lines | `NONE` | `NOASSERTION`

**L2.11.4 (3.17.5)** Tag: `PackageCopyrightText:`

In `tag:value` format multiple lines are delimited by `<text>...</text>`.

Example:

    PackageCopyrightText: <text>Copyright 2008-2010 John Smith</text>

**L2.11.5 (3.17.6)** RDF: property `spdx:copyrightText` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <copyrightText>Copyright 2008-2010 John Smith</copyrightText>
        ...
    </Package>
    
### L3. Other Licensing Information

### L3.1 (6.1) License Identifier <a name="6.1"></a>

**L3.1.1 (6.1.1)** Purpose: Provide a locally unique identifier to refer to licenses that are not found on the SPDX License List. This unique identifier can then be used in the packages and files sections of the SPDX file (sections [3](3-package-information.md) and [4](4-file-information.md), respectively).

**L3.1.2 (6.1.3)** Cardinality: Conditional (mandatory, one) if license is not on SPDX License List.

**L3.1.3 (6.1.4)** Data Format: "LicenseRef-"`[idstring]`

where

`[idstring]` is a unique string containing letters, numbers, `.` and/or `-`.

**L3.1.4 (6.1.5)** Tag: `LicenseID:`

Examples:

    LicenseID: LicenseRef-1

    LicenseID: LicenseRef-Beerware-4.2

**L3.1.5 (6.1.6)** RDF: Property `spdx:licenseID` in class `spdx:ExtractedLicensingInfo`

Examples:

    <ExtractedLicensingInfo rdf:about="licenseRef-1">
       <licenseId>LicenseRef-1</licenseId>
    </ExtractedLicensingInfo>

    <ExtractedLicensingInfo rdf:about="licenseRef-Beerware-4.2">
        <licenseId>LicenseRef-Beerware-4.2</licenseId>
    </ExtractedLicensingInfo>

### L3.2 (6.2) Extracted Text <a name="6.2"></a>

**L3.2.1 (6.2.1)** Purpose: Provide a copy of the actual text of the license reference extracted from the package or file that is associated with the License Identifier to aid in future analysis.

**L3.2.2 (6.2.3)** Cardinality: Conditional (Mandatory, one) if there is a License Identifier assigned.

**L3.2.3 (6.2.4)** Data Format: Free form text field that may span multiple lines.

**L3.2.4 (6.2.5)** Tag: `ExtractedText:`

In `tag:value` format multiple lines are delimited by `<text> .. </text>`.

Example 1 (if only short reference to license present in File):

    ExtractedText: <text>This software is licensed under the Beer License.</text>

Example 2 (if indeed full text of license present in File):

    ExtractedText: <text>"THE WHISKEY-WARE LICENSE": whiskeyfan@example.com wrote this file. As long as you retain this notice you can do whatever you want with this stuff. If we meet some day, and you think this stuff is worth it, you can buy me a bottle of whiskey in return </text>

**L3.2.5 (6.2.6)** RDF: Property `spdx:extractedText` in class `spdx:ExtractedLicensingInfo`

Example 1 (if only short reference to license present in File):

    <ExtractedLicensingInfo rdf:about="licenseRef-Whiskeyware">
        <licenseId>LicenseRef-Whiskeyware</licenseId>
        <extractedText>This software is licensed under the WHISKEY-WARE LICENSE.</extractedText>
    </ExtractedLicensingInfo>

Example 2 (if indeed full text of license present in File):

    <ExtractedLicensingInfo rdf:about="licenseRef-Whiskeyware">
        <licenseId>LicenseRef-Whiskeyware</licenseId>
        <extractedText>""THE WHISKEY-WARE LICENSE": whiskeyfan@example.com wrote this file. As long as you retain this notice you can do whatever you want with this stuff. If we meet some day, and you think this stuff is worth it, you can buy me a bottle of whiskey in return.</extractedText>
    </ExtractedLicensingInfo>

### L3.3 (6.3) License Name <a name="6.3"></a>

**L3.3.1 (6.3.1)** Purpose: Provide a common name of the license that is not on the SPDX list.

Use `NOASSERTION` If there is no common name or it is not known.

**L3.3.2 (6.3.3)** Cardinality: Conditional (mandatory, one) if license is not on SPDX License List.

**L3.3.3 (6.3.4)** Data Format: Single line of text | `NOASSERTION`.

**L3.3.4 (6.3.5)** Tag: `LicenseName:`

Example:

    LicenseName: Whiskey-Ware License

**L3.3.5 (6.3.6)** RDF: Property `spdx:licenseName` in class `spdx:ExtractedLicensingInfo`

Example:

    <ExtractedLicensingInfo rdf:about="licenseRef-Whiskey-Ware">
       <name>Whiskey-Ware License </name>
    </ExtractedLicensingInfo>


### L3.4 (6.5) License Comment <a name="6.5"></a>

**L3.4.1 (6.5.1)** Purpose: This field provides a place for the SPDX file creator to record any general comments about the license.

**L3.4.2 (6.5.3)** Cardinality: Optional, one.

**L3.4.3 (6.5.4)** Data Format: Free form text that can span multiple lines

**L3.4.4 (6.5.5)** Tag: `LicenseComment:`

In `tag:value` format multiple lines are delimited by `<text> .. </text>`.

Example:

    LicenseComment: <text>The Whiskey-Ware License has a couple of other standard variants.</text>

**L3.4.5 (6.5.6)** RDF: Property `rdfs:comment` in class `spdx:ExtractedLicensingInfo`

Example:

    <ExtractedLicensingInfo rdf:about="licenseRef-1">
        <rdfs:comment> The Whiskey-Ware License has a couple of other standard variants.</rdfs:comment>
    </ExtractedLicensingInfo>
