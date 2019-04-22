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


## 5. 

Fields:

## 3.1 Package Name <a name="3.1"></a>

**3.1.1** Purpose: Identify the full name of the package as given by the [Package Originator](#3.6).

**3.1.2** Intent: The name of each package is an important conventional technical identifier to be maintained for each package.

**3.1.3** Cardinality: Mandatory, one.

**3.1.4** Data Format: Single line of text.

**3.1.5** Tag: `PackageName:`

Example:

    PackageName: glibc

**3.1.6** RDF: property `spdx:name` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        <name>glibc</name>
    </Package>

## 3.2 Package SPDX Identifier <a name="3.2"></a>

**3.2.1** Purpose: Uniquely identify any element in an SPDX document which may be referenced by other elements. These may be referenced internally and externally with the addition of the SPDX Document Identifier.

**3.2.2** Intent: There may be several versions of the same package within an SPDX document. Each element needs to be able to be referred to uniquely so that relationships between elements can be clearly articulated.

**3.2.3** Cardinality: Mandatory, one.

**3.2.4** Data Format: "SPDXRef-"`[idstring]`

where `[idstring]` is a unique string containing letters, numbers, `.`, and/or `-`.

**3.2.5** Tag: `SPDXID:`

Example:

    SPDXID: SPDXRef-1

**3.2.6** RDF: The URI for the element will follow the form:

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

## 3.3 Package Version <a name="3.3"></a>

**3.3.1** Purpose: Identify the version of the package.

**3.3.2** Intent: The versioning of a package is a useful for identification purposes and for indicating later changes of the package version.

**3.3.3** Cardinality: Optional, one.

**3.3.4** Data Format: Single line of text.

**3.3.5** Tag: `PackageVersion:`

Example:

    PackageVersion: 2.11.1

**3.3.6** RDF: property `spdx:versionInfo` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <versionInfo>2.11.1</versionInfo>
        ...
    </Package>

## 3.4 Package File Name <a name="3.4"></a>

**3.4.1** Purpose: Provide the actual file name of the package, or path of the directory being treated as a package. This may include the packaging and compression methods used as part of the file name, if appropriate.

**3.4.2** Intent: The actual file name of the compressed file containing the package may be a significant technical element that needs to be included with each package identification information. If a grouping, like a set of files in a subdirectory, is being treated as a package, the subdirectory name may be appropriate to provide. Subdirectory name is preceeded with a `./`. See [RFC 3986][rfc3986] for syntax.

**3.4.3** Cardinality: Optional, one.

**3.4.4** Data Format: Single line of text.

**3.4.5** Tag: `PackageFileName:`

Example:

    PackageFileName: glibc-2.11.1.tar.gz

Example (subdirectory being treated as a package):

    PackageFileName: ./myrootdir/mysubdir1

**3.4.6** RDF: property `spdx:packageFileName` in class `spdx:Package`

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

## 3.7 Package Download Location <a name="3.7"></a>

**3.7.1** Purpose: This section identifies the download Universal Resource Locator (URL), or a specific location within a version control system (VCS) for the package at the time that the SPDX file was created.

Use:

* `NONE` if there is no download location whatsoever.
* `NOASSERTION` if:

    (i) the SPDX file creator has attempted to but cannot reach a reasonable objective determination;

    (ii) the SPDX file creator has made no attempt to determine this field; or

    (iii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

**3.7.2** Intent: Where and how to download the exact package being referenced is critical verification and tracking data.

**3.7.3** Cardinality: Mandatory, one.

**3.7.4** Data Format: uniform resource locator | VCS location | `NONE` | `NOASSERTION`

For version-controlled files, the VCS location syntax is similar to a URL and has the:

    <vcs_tool>+<transport>://<host_name>[/<path_to_repository>][@<revision_tag_or_branch>][#<sub_path>]

This VCS location compact notation (inspired and mostly adopted from [pip][pip-vcs] as of 2015-02-20) supports referencing locations in version control systems such as [Git][], [Mercurial][], [Subversion][] and [Bazaar][], and specifies the type of VCS tool using url prefixes: `git+`, `hg+`, `bzr+`, `svn+` and specific transport schemes such as SSH or HTTPS.

Specifying sub-paths, branch names, a commit hash, a revision or a tag name is recommended, and supported using the `@` delimiter for commits and the `#` delimiter for sub-paths.

Using user names and password in the `<host_name>` is not supported and should be considered as an error. User access control to URLs or VCS repositories must be handled outside of an SPDX document.

In VCS location compact notations, the trailing slashes in `<host_name>`, `<path_to_repository>` are not significant. Leading and trailing slashes in `<sub_path>` are not significant.

**3.7.5** Tag: `PackageDownloadLocation:`

Examples if ambiguous:

    PackageDownloadLocation: NOASSERTION

    PackageDownloadLocation: NONE

Example for a plain URL:

    PackageDownloadLocation: http://ftp.gnu.org/gnu/glibc/glibc-ports-2.15.tar.gz

Example for [Git][]:

SPDX supported schemes are: `git`, `git+git`, `git+https`, `git+http`, and `git+ssh`. `git` and `git+git` are equivalent.

Here are the supported forms:

    PackageDownloadLocation: git://git.myproject.org/MyProject

    PackageDownloadLocation: git+https://git.myproject.org/MyProject.git

    PackageDownloadLocation: git+http://git.myproject.org/MyProject

    PackageDownloadLocation: git+ssh://git.myproject.org/MyProject.git

    PackageDownloadLocation: git+git://git.myproject.org/MyProject

    PackageDownloadLocation: git+git@git.myproject.org:MyProject

To specify a sub-path to a file or directory inside a repository use the `#` delimiter:

    PackageDownloadLocation: git://git.myproject.org/MyProject#src/somefile.c

    PackageDownloadLocation: git+https://git.myproject.org/MyProject#src/Class.java

To specify branch names, a commit hash or a tag name, use the `@` delimiter:

    PackageDownloadLocation: git://git.myproject.org/MyProject.git@master

    PackageDownloadLocation: git+https://git.myproject.org/MyProject.git@v1.0

    PackageDownloadLocation: git://git.myproject.org/MyProject.git@da39a3ee5e6b4b0d3255bfef95601890afd80709

Sub-paths and branch names or commit hash can be combined too:

    PackageDownloadLocation: git+https://git.myproject.org/MyProject.git@master#/src/MyClass.cpp

    PackageDownloadLocation: git+https://git.myproject.org/MyProject@da39a3ee5e6b4b0d3255bfef95601890afd80709#lib/variable.rb

Example for [Mercurial][]:

SPDX supported schemes are: `hg+http`, `hg+https`, `hg+static-http`, and `hg+ssh`.

The supported forms are:

    PackageDownloadLocation: hg+http://hg.myproject.org/MyProject

    PackageDownloadLocation: hg+https://hg.myproject.org/MyProject

    PackageDownloadLocation: hg+ssh://hg.myproject.org/MyProject

To specify a sub-path to a file or directory inside a repository use the `#` delimiter:

    PackageDownloadLocation: hg+https://hg.myproject.org/MyProject#src/somefile.c

    PackageDownloadLocation: hg+https://hg.myproject.org/MyProject#src/Class.java

To pass branch names, a commit hash, a tag name or a local branch name use the `@` delimiter:

    PackageDownloadLocation: hg+https://hg.myproject.org/MyProject@da39a3ee5e6b

    PackageDownloadLocation: hg+https://hg.myproject.org/MyProject@2019

    PackageDownloadLocation: hg+https://hg.myproject.org/MyProject@v1.0

    PackageDownloadLocation: hg+https://hg.myproject.org/MyProject@special_feature

Sub-paths and branch names or commit hash can be combined too:

    PackageDownloadLocation: hg+https://hg.myproject.org/MyProject@master#/src/MyClass.cpp

    PackageDownloadLocation: hg+https://hg.myproject.org/MyProject@da39a3ee5e6b#lib/variable.rb

Example for [Subversion][]:

SPDX supported schemes are: `svn`, `svn+svn`, `svn+http`, `svn+https`, `svn+ssh`. `svn` and `svn+svn` are equivalent.

The supported forms are:

    PackageDownloadLocation: svn://svn.myproject.org/svn/MyProject

    PackageDownloadLocation: svn+svn://svn.myproject.org/svn/MyProject

    PackageDownloadLocation: svn+http://svn.myproject.org/svn/MyProject/trunk

    PackageDownloadLocation: svn+https://svn.myproject.org/svn/MyProject/trunk

To specify a sub-path to a file or directory inside a repository use the `#` delimiter:

    PackageDownloadLocation: svn+https://svn.myproject.org/MyProject#src/somefile.c

    PackageDownloadLocation: svn+https://svn.myproject.org/MyProject#src/Class.java

This support is less important for SVN since the URL path can also contain sub-paths; this two forms are equivalent:

    PackageDownloadLocation: svn+https://svn.myproject.org/MyProject/trunk#src/somefile.c

    PackageDownloadLocation: svn+https://svn.myproject.org/MyProject/trunk/src/somefile.c

You can specify a revision using the `@` delimiter:

    PackageDownloadLocation: svn+https://svn.myproject.org/svn/MyProject/trunk@2019

Sub-paths and revisions can be combined too:

    PackageDownloadLocation: svn+https://svn.myproject.org/MyProject@123#/src/MyClass.cpp

    PackageDownloadLocation: svn+https://svn.myproject.org/MyProject/trunk@1234#lib/variable/variable.rb

Example for [Bazaar][]:

SPDX supported schemes are: `bzr+http`, `bzr+https`, `bzr+ssh`, `bzr+sftp`, `bzr+ftp`, and `bzr+lp`.

The supported forms are:

    PackageDownloadLocation: bzr+https://bzr.myproject.org/MyProject/trunk

    PackageDownloadLocation: bzr+http://bzr.myproject.org/MyProject/trunk

    PackageDownloadLocation: bzr+sftp://myproject.org/MyProject/trunk

    PackageDownloadLocation: bzr+ssh://myproject.org/MyProject/trunk

    PackageDownloadLocation: bzr+ftp://myproject.org/MyProject/trunk

    PackageDownloadLocation: bzr+lp:MyProject

To specify a sub-path to a file or directory inside a repository use the `#` delimiter:

    PackageDownloadLocation: bzr+https://bzr.myproject.org/MyProject/trunk#src/somefile.c

    PackageDownloadLocation: bzr+https://bzr.myproject.org/MyProject/trunk#src/Class.java

You can specify a revision or tag using the `@` delimiter:

    PackageDownloadLocation: bzr+https://bzr.myproject.org/MyProject/trunk@2019

    PackageDownloadLocation: bzr+http://bzr.myproject.org/MyProject/trunk@v1.0

Sub-paths and revisions can be combined too:

    PackageDownloadLocation: bzr+https://bzr.myproject.org/MyProject/trunk@2019#src/somefile.c

**3.7.6** RDF: property `spdx:downloadLocation` in class `spdx:Package`

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

## 3.8 Files Analyzed <a name="3.8"></a>

**3.8.1** Purpose: Indicates whether the file content of this package has been available for or subjected to analysis when creating the SPDX document. If `false`, indicates packages that represent metadata or URI references to a project, product, artifact, distribution or a component. If `false`, the package must not contain any files.

**3.8.2** Intent: A package can refer to a project, product, artifact, distribution or a component that is external to the SPDX document.

Some examples:

A bundle of external products: Package A can be metadata about Packages and their dependencies. It may also be a loosely organized manifest of references to Packages involved in a product or project. Build or execution may transitively discover more Packages and dependencies. All of these referenced Packages can have their own SPDX Documents. In this case, Package A may be defined with its File Analyzed attribute set to `false`. Package A includes External Document References to SPDX documents containing Packages referenced in all the available relationships. The Relationships section then relates the SPDX documents and contained SPDX elements with appropriate semantics per the dependencies in the scope of Package A.
Package relation to external product: Package A can have a STATIC_LINK relationship to Package B, but the binary representation of Package B is furnished by the build process and thus not contained in the file list of Package A. In this case, Package B needs to be defined with its Files Analyzed attribute set to false and all the other attributes subject to the subsequently defined constraints. Then, the relationship between Package A and Package B can be documented as described in [Section 7](7-relationships-between-SPDX-elements.md).
File derived from external product: Package A contains multiple files derived from an outside project. Rather than use the `artifactOf*` attributes (Sections 4.9-4.11) to describe the relation of these files to their project, the outside project can be represented by another package, Package B, whose [`FilesAnalyzed`](#3.8) attribute is set to `false`. Each of the binary files can then have a relationship to package B (Section 6). This allows the outside project to be represented by a single SPDX identifier (the identifier of Package B). It also allows the relationship(s) between the outside project and each of the files be represented in much more detail.

**3.8.3** Cardinality: Optional, one.  If omitted, the default value of `true` is assumed.

**3.8.4** Data Format: Boolean

**3.8.5** Tag: `FilesAnalyzed`

Example:

    FilesAnalyzed: false

**3.8.6** RDF: property `spdx:filesAnalyzed` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <filesAnalyzed>false</filesAnalyzed>
        ...
    </Package>

## 3.11 Package Home Page <a name="3.11"></a>

**3.11.1** Purpose: Provide a place for the SPDX file creator to record a web site that serves as the package's home page. This link can also be used to reference further information about the package referenced by the SPDX file creator.

Use:

* `NONE` if there is no package home page whatsoever.
* `NOASSERTION` if:

    (i) the SPDX file creator has attempted to but cannot reach a reasonable objective determination;

    (ii) the SPDX file creator has made no attempt to determine this field; or

    (iii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

**3.11.2** Intent: Save the recipient of the SPDX file who is looking for more info from having to search for and verify a match between the package and the associated project homepage.

**3.11.3** Cardinality: Optional, one.

**3.11.4** Data Format: uniform resource locator | `NONE` | `NOASSERTION`

**3.11.5** Tag: `PackageHomePage:`

Example:

    PackageHomePage: http://ftp.gnu.org/gnu/glibc

**3.11.6** RDF: property `doap:homepage` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        <doap:homepage >http://ftp.gnu.org/gnu/glibc/</doap:homepage>    </Package>

## 3.13 Concluded License <a name="3.13"></a>

**3.13.1** Purpose: Contain the license the SPDX file creator has concluded as governing the package or alternative values, if the governing license cannot be determined.

The options to populate this field are limited to:

* A valid SPDX License Expression as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md);
* `NONE`, if the SPDX file creator concludes there is no license available for this package; or
* `NOASSERTION` if:

    (i) the SPDX file creator has attempted to but cannot reach a reasonable objective determination;

    (ii) the SPDX file creator has made no attempt to determine this field; or

    (iii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

If the Concluded License is not the same as the [Declared License](#3.15), a written explanation should be provided in the Comments on License field [(section 3.16)](#3.16). With respect to `NOASSERTION`, a written explanation in the Comments on License field [(section 3.16)](#3.16) is preferred.

**3.13.2** Intent: Here, the intent is for the SPDX file creator to analyze the license information in package, and other objective information, e.g., COPYING file, together with the results from any scanning tools, to arrive at a reasonably objective conclusion as to what license governs the package.

**3.13.3** Cardinality: Mandatory, one.

**3.13.4** Data Format: `<SPDX License Expression>` | `NONE` | `NOASSERTION`

where:

`<SPDX License Expression>` is a valid SPDX License Expression as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md).

**3.13.5** Tag: `PackageLicenseConcluded:`

Example:

    PackageLicenseConcluded: LGPL-2.0

Example:

    PackageLicenseConcluded: (LGPL-2.0 OR LicenseRef-3)

**3.13.6** RDF: property `spdx:licenseConcluded` in `class spdx:Package`

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

## 3.15 Declared License <a name="3.15"></a>

**3.15.1** Purpose: List the licenses that have been declared by the authors of the package. Any license information that does not originate from the package authors, e.g. license information from a third party repository, should not be included in this field.

The options to populate this field are limited to:

* A valid SPDX License Expression as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md);
* `NONE`, if the package contains no license information whatsoever; or
* `NOASSERTION` if:

    (i) the SPDX file creator has made no attempt to determine this field; or

    (ii) the SPDX file creator has intentionally provided no information (no meaning should be implied by doing so).

**3.15.2** Intent: This is simply the license identified in text in one or more files (for example COPYING file) in the source code package. This field is not intended to capture license information obtained from an external source, such as the package website. Such information can be included in Concluded License [(section 3.13)](#3.13). This field may have multiple Declared Licenses, if multiple licenses are declared at the package level.

**3.15.3** Cardinality: Mandatory, one.

**3.15.4** Data Format: `<SPDX License Expression>` | `NONE` | `NOASSERTION`

where:

* `<SPDX License Expression>` is a valid SPDX License Expression as defined in [Appendix IV](appendix-IV-SPDX-license-expressions.md).

**3.15.5** Tag: `PackageLicenseDeclared:`

Example:

    PackageLicenseDeclared: LGPL-2.0

Example:

    PackageLicenseDeclared: (LGPL-2.0 AND LicenseRef-3)

**3.15.6** RDF: property `spdx:licenseDeclared` in class `spdx:Package`

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

## 3.16 Comments on License <a name="3.16"></a>

**3.16.1** Purpose: This field provides a place for the SPDX file creator to record any relevant background information or analysis that went in to arriving at the Concluded License for a package. If the Concluded License does not match the Declared License or License Information from Files, this should be explained by the SPDX file creator. Its is also preferable to include an explanation here when the Concluded License is `NOASSERTION`.

**3.16.2** Intent: Here, the intent is to provide the recipient of the SPDX file with a detailed explanation of how the Concluded License was determined if it does not match the License Information from the files or the source code package, is marked `NOASSERTION`, or other helpful information relevant to determining the license of the package.

**3.16.3** Cardinality: Optional, one.

**3.16.4** Data Format: free form text that can span multiple lines.

In `tag:value` format this is delimited by `<text>...</text>`.

In RDF, it is delimited by `<licenseComment>`.

**3.16.5** Tag: `PackageLicenseComments:`

Example:

    PackageLicenseComments: <text>The license for this project changed with the release of version 1.4.
    The version of the project included here post-dates the license change.</text>

**3.16.6** RDF: property `spdx:licenseComments` in class `spdx:Package`

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

## 3.17 Copyright Text <a name="3.17"></a>

**3.17.1** Purpose: Identify the copyright holders of the package, as well as any dates present. This will be a free form text field extracted from package information files. The options to populate this field are limited to:

* Any text related to a copyright notice, even if not complete;
* `NONE` if the package contains no copyright information whatsoever; or
* `NOASSERTION`, if

    (i) the SPDX document creator has made no attempt to determine this field; or

    (ii) the SPDX document creator has intentionally provided no information (no meaning should be implied by doing so).

**3.17.2** Intent: Record any copyright notices for the package.

**3.17.3** Cardinality: Mandatory, one.

**3.17.4** Data Format: free form text that can span multiple lines | `NONE` | `NOASSERTION`

**3.17.5** Tag: `PackageCopyrightText:`

In `tag:value` format multiple lines are delimited by `<text>...</text>`.

Example:

    PackageCopyrightText: <text>Copyright 2008-2010 John Smith</text>

**3.17.6** RDF: property `spdx:copyrightText` in class `spdx:Package`

Example:

    <Package rdf:about="...">
        ...
        <copyrightText>Copyright 2008-2010 John Smith</copyrightText>
        ...
    </Package>
    


## 6.1 License Identifier <a name="6.1"></a>

**6.1.1** Purpose: Provide a locally unique identifier to refer to licenses that are not found on the SPDX License List. This unique identifier can then be used in the packages and files sections of the SPDX file (sections [3](3-package-information.md) and [4](4-file-information.md), respectively).

**6.1.2** Intent: Create a human readable short form license identifier for a license not on the SPDX License List. This identifier should be unique within the SPDX file. In previous versions of SPDX, the references were required to be sequential numbers, but as of version 1.2, creators may specify references that are easier for humans to remember and mentally map.

**6.1.3** Cardinality: Conditional (mandatory, one) if license is not on SPDX License List.

**6.1.4** Data Format: "LicenseRef-"`[idstring]`

where

`[idstring]` is a unique string containing letters, numbers, `.` and/or `-`.

**6.1.5** Tag: `LicenseID:`

Examples:

    LicenseID: LicenseRef-1

    LicenseID: LicenseRef-Beerware-4.2

**6.1.6** RDF: Property `spdx:licenseID` in class `spdx:ExtractedLicensingInfo`

Examples:

    <ExtractedLicensingInfo rdf:about="licenseRef-1">
       <licenseId>LicenseRef-1</licenseId>
    </ExtractedLicensingInfo>

    <ExtractedLicensingInfo rdf:about="licenseRef-Beerware-4.2">
        <licenseId>LicenseRef-Beerware-4.2</licenseId>
    </ExtractedLicensingInfo>

# 6.2 Extracted Text <a name="6.2"></a>

**6.2.1** Purpose: Provide a copy of the actual text of the license reference extracted from the package or file that is associated with the License Identifier to aid in future analysis.

**6.2.2** Intent: Provide the actual text as found in the package or file for a license that is not on the SPDX License List.

**6.2.3** Cardinality: Conditional (Mandatory, one) if there is a License Identifier assigned.

**6.2.4** Data Format: Free form text field that may span multiple lines.

**6.2.5** Tag: `ExtractedText:`

In `tag:value` format multiple lines are delimited by `<text> .. </text>`.

Example 1 (if only short reference to license present in File):

    ExtractedText: <text>This software is licensed under the Beer License.</text>

Example 2 (if indeed full text of license present in File):

    ExtractedText: <text>"THE WHISKEY-WARE LICENSE": whiskeyfan@example.com wrote this file. As long as you retain this notice you can do whatever you want with this stuff. If we meet some day, and you think this stuff is worth it, you can buy me a bottle of whiskey in return </text>

**6.2.6** RDF: Property `spdx:extractedText` in class `spdx:ExtractedLicensingInfo`

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

# 6.3 License Name <a name="6.3"></a>

**6.3.1** Purpose: Provide a common name of the license that is not on the SPDX list.

Use `NOASSERTION` If there is no common name or it is not known.

**6.3.2** Intent: Provides a human readable name suitable for use as a title or label of the license when showing compact lists of licenses from the SPDX data to humans.

**6.3.3** Cardinality: Conditional (mandatory, one) if license is not on SPDX License List.

**6.3.4** Data Format: Single line of text | `NOASSERTION`.

**6.3.5** Tag: `LicenseName:`

Example:

    LicenseName: Whiskey-Ware License

**6.3.6** RDF: Property `spdx:licenseName` in class `spdx:ExtractedLicensingInfo`

Example:

    <ExtractedLicensingInfo rdf:about="licenseRef-Whiskey-Ware">
       <name>Whiskey-Ware License </name>
    </ExtractedLicensingInfo>


# 6.5 License Comment <a name="6.5"></a>

**6.5.1** Purpose: This field provides a place for the SPDX file creator to record any general comments about the license.

**6.5.2** Intent: Here, the intent is to provide the recipient of the SPDX file with more information determined after careful analysis of a license, or addition cross references.

**6.5.3** Cardinality: Optional, one.

**6.5.4** Data Format: Free form text that can span multiple lines

**6.5.5** Tag: `LicenseComment:`

In `tag:value` format multiple lines are delimited by `<text> .. </text>`.

Example:

    LicenseComment: <text>The Whiskey-Ware License has a couple of other standard variants.</text>

**6.5.6** RDF: Property `rdfs:comment` in class `spdx:ExtractedLicensingInfo`

Example:

    <ExtractedLicensingInfo rdf:about="licenseRef-1">
        <rdfs:comment> The Whiskey-Ware License has a couple of other standard variants.</rdfs:comment>
    </ExtractedLicensingInfo>
