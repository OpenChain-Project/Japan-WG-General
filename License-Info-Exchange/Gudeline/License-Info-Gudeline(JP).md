# License-Info-Gudeline (JP)

本文書はOSSコンプライアンスを遵守するために必要なライセンス情報を作成する手順を示す事を目的としており、組込み機器を想定して記載しています。

## 目次

1. ライセンス情報の必要性
1. 必要なライセンス情報の項目
1. ライセンス情報の収集方法
1. ライセンス情報の作成手順
1. ライセンス情報のサンプル

## 1. ライセンス情報の必要性 

オープン ソース ソフトウェア (Open Source Software, OSS)は現代のソフトウェアには必要不可欠なものです。
OSSは誰でも自由に使用する事が出来ますが、使用するためには一定の条件に従う必要があります。
その条件に従うためには、使用しているOSSのライセンス情報が必要になります。

ライセンス情報の必要性について、詳細は「オープンソースソフトウェアライセンス遵守に関する一般公衆ガイド」を参照します。
https://github.com/OpenChain-Project/curriculum/tree/master/supplier-leaflet

#### SPDX

ライセンス情報を扱うためには、Linux Foundation傘下のプロジェクトにSoftware Package Data Exchange (SPDX)があります。
https://spdx.org/

SPDXはソフトウェア パッケージに関連するソフトウェア名やバージョン、ライセンス、著作権表示などの情報を共有するための標準的なフォーマットです。

#### SPDX Lite

SPDXはライセンス情報を共有するために非常に優れたフォーマットです。
しかし、ソフトウェア パッケージに関連する情報が膨大にあり、初心者が扱う事は難しいです。
SPDX Liteはソフトウェアサプライチェーンにおいて、最低限は必要のライセンス情報をSPDXから抽出したフォーマットです。  

以下はSPDX-Liteのサンプルです。
spread sheetなどに必要なライセンス情報を入力するだけで簡単に作成する事が出来ます。

![spdx-lite](https://user-images.githubusercontent.com/21073492/59993340-ee596500-968a-11e9-8783-5cf9a95ee351.png)


## 2. 必要なライセンス情報の項目

SPDX Liteの項目と各項目の必要な理由を以下に記載します。

### SPDX Liteの項目一覧

| SPDX Lite section no. | corresponding SPDX section no. | License Info. | Tag  | 
|:-------|:-------|:--------|:-------|
|L2.1	|3.1	|Package Name	| PackageName |
|L2.2	|3.2	|Package SPDX Identifier	| SPDXID |
|L2.3	|3.3	|Package Version	| PackageVersion |
|L2.4	|3.4	|Package File Name	| PackageFileName	|
|L2.5	|3.7	|Package Download Location 	| PackageDownloadLocation |
|L2.6	|3.8	|Files Analyzed	|	FilesAnalyzed |
|L2.7	|3.11	|Package Home Page	| PackageHomePage	|
|L2.8	|3.13	|Concluded License	| PackageLicenseConcluded	||
|L2.9	|3.15	|Declared License	| PackageLicenseDeclared	||
|L2.10	|3.16	|Comments on License	| PackageLicenseComments	|
|L2.11	|3.17	|Copyright Text	| PackageCopyrightText	||
|	|	|	+ modification record| ExternalRef |
|L3.1	|6.1	|License Identifier	| LicenseID	|
|L3.2	|6.2	|Extracted Text	| ExtractedText	|
|L3.3	|6.3	|License Name	| LicenseName	|
|L3.4	|6.5	|License Comment	| LicenseComment	|

### Package Name

ソフトウェア パッケージの名称を記載します。  
本項目は使用しているソフトウェアを特定するために利用します。

### Package SPDX Identifier

SPDX Liteファイルの中でソフトウェア パッケージが一意になる識別子を記載します。  
本項目は同一ソフトウェア パッケージの別バージョンと区別するために利用します。

### Package Version

ソフトウェア パッケージのバージョンを記載します。  
本項目は使用しているソフトウェアのバージョンを特定するために利用します。

### Package File Name

ソフトウェア パッケージの実ファイル名を記載します。  
本項目は使用しているソフトウェアの実ファイルを特定するために利用します。
これはPackage Nameと実ファイルが名称の違いにより、関連付け出来ない場合があるため本項目を必要とします。

### Package Download Location

ソフトウェア パッケージの入手先を記載します。  
本項目は使用しているソフトウェアと同じソフトウェアを入手するために利用します。

### Files Analyzed 

SPDX Liteファイルを手作業で作成する場合に"false"を記載します。

### Package Home Page

ソフトウェア パッケージのホームページを記載します。  
本項目は使用しているソフトウェアの脆弱性情報などのコミュニティ情報を入手するために利用します。

### Concluded License

SPDX Liteファイルの作成者がソフトウェア パッケージに適用されると結論したライセンスを記載します。
Concluded LicenseがDeclared Licenseと異なる場合、Comments on Licenseに説明を記載すべきです。
NOASSERTIONに関しては、Comments on Licenseに説明を記載した方が良いです。
本項目は使用しているソフトウェアのライセンスを特定するために利用します。

なお、記載するライセンス名は下記URLのSPDX License ListのIdentifierに従って記載する事を推奨します。
https://spdx.org/licenses/

### Declared License

ソフトウェア パッケージの作成者が宣言したライセンスを記載します。
Concluded LicenseがDeclared Licenseと異なる場合、Comments on Licenseに説明を記載すべきです。
NOASSERTIONに関しては、Comments on Licenseに説明を記載した方が良いです。
本項目は使用しているソフトウェアのライセンスを特定するために利用します。

なお、記載するライセンス名は下記URLのSPDX License ListのIdentifierに従って記載する事を推奨します。
https://spdx.org/licenses/

### Comments on License

SPDX Liteファイルの作成者がライセンスに関連する情報やライセンスを結論した理由を記載します。
本項目は使用しているソフトウェアのライセンスを補足するために利用します。  

また、使用しているソフトウェアが動的リンク又は静的リンクのどちらかを記載します。  
コンパイル オプションによって、使用しているソフトウェアの特定のライセンスが対象外となる場合、本項目にコンパイル オプションを記載します。  
特定のライセンスではソフトウェアのリンク方法によって、他にも影響を与えます。そのため、ソフトウェアのリンク方法を明示するために本項目を利用します。

### Copyright Text

ソフトウェア パッケージの著作権情報を記載します。  
すべての著作権情報を抽出する事が難しい場合はソースコードを一緒に提供します。

特定のライセンスでは配布時に著作権情報を提供する必要があります。本項目は使用しているソフトウェアの著作権情報を特定するために利用します。

### modification record

ソフトウェア パッケージが改変されている場合は”true”を記載します。  
ソフトウェア パッケージが改変されていない場合は”false”を記載します。  

OSSのソースコードに独自の修正を加えたり、OSSのソースコードを一部流用する場合は改変されていると判断するため”true”を記載します。

この項目はSPDXには存在しません。SPDX Liteの独自の項目です。  
特定のライセンスではソフトウェアを改変した時に従う必要があるライセンス条件があります。そのため、ソフトウェアの改変を明示するために本項目を利用します。

### License Identifier

SPDX License Listに掲載されていないライセンスの場合、一意になる識別子を記載します。  
本項目は使用しているソフトウェアのライセンスを特定するために利用します。

### Extracted Text

SPDX License Listに掲載されていないライセンスの場合、ライセンス条文を記載します。  
本項目は使用しているソフトウェアのライセンスを補足するために利用します。

### License Name

SPDXライセンス リストに掲載されていないライセンスの場合、ライセンス名を記載します。  
本項目は使用しているソフトウェアのライセンス名を特定するために利用します。

### License Comment

SPDXライセンス リストに掲載されていないライセンスの場合、ライセンスに関連する情報を記載します。  
本項目は使用しているソフトウェアのライセンスを補足するために利用します。

### 備考

記載出来ない項目については"NOASSERTION"を記載して、使用しているソフトウェア パッケージについて問い合わせ可能な連絡先を提供します。

## 3. ライセンス情報の収集方法

#### Package Name, Package Version, Package File Name

対象のソースコード又はソフトウェア パッケージを入手してください。

#### Package Download Location

入手した対象のソースコード又はソフトウェア パッケージの取得先を確認してください。
納品でCDなど物理デバイスから入手した時は納品先に取得元を確認してください。

#### Package Home Page

特定したPackage Nameを元にインターネットで検索してください。
ホームページが複数見つかる場合はソースコードの入手先やバージョンと照らし合わせて確認してください。

#### Concluded License, Declared License

入手したソースコード内の「COPYING」,「LICENSE」,「README」などのファイルや各ソースファイルのヘッダー部分を確認してください。
又は特定したホームページ内にライセンスの情報があるか確認してください。


## 4. ライセンス情報の作成手順

ライセンス情報は分かる範囲で出来る限り記載する事が大切です。
ソフトウェアサプライチェーンにおいて、ライセンス情報を受け取る側はライセンスを遵守するために少しでも多くの情報を必要とします。そのため、明確でない場合も出来る限りのライセンス情報を記載してコメントに明確でない旨を記載する事を推奨します。

### 手作業でバイナリファイルを対象に作成する場合

※要追記

### 手作業でソースコードを対象に作成する場合

例としてbusybox-1.30.1のライセンス情報を手作業で作成する手順を以下に記載します。
ここではbusybox-1.30.1のソースコードの「busybox-1.30.1.tar.bz2」が入手済みである事を想定します。

#### Package Name
 -> busybox
 
  入手したソースコードのファイル名やソースコード内の「README」から判断して記載します。

#### Package SPDX Identifier
 -> SPDXRef-1
 
  一意に識別するために任意の文字列を記載します。

#### Package Version
 -> 1.30.1
 
  入手したソースコードのファイル名から判断して記載します。

#### Package File Name
 -> busybox-1.30.1.tar.bz2
 
  入手したソースコードのファイル名から判断して記載します。

#### Package Download Location
 -> https://busybox.net/downloads/busybox-1.30.1.tar.bz2
 
  ソースコードの入手先のURLを記載します。

#### Files Analyzed
 -> false
 
  手作業で作成しているためfalseを記載します。

#### Package Home Page
 -> https://busybox.net/about.html
 
  インターネットでbusyboxのホームページを検索して記載します。

#### Concluded License
 ->  GPL-2.0-only
 
  ソースコード内の「LICENSE」やホームページ内から判断して記載します。

#### Declared License
 -> GPL-2.0-only
 
  ソースコード内の「LICENSE」やホームページ内から判断して記載します。

#### Comments on License
 -> busyboxは他のソフトウェアとはリンクせず、コマンドのみを使用します
 
  ライセンス情報の補足を記載する。またリンクの有無を記載します。

#### Copyright Text
 -> NOASSERTION
 
  すべての著作権表示を抽出する事が難しいため、NOASSERTIONを記載して一緒にソースコードを提供します。

#### modification record
 -> false
 
  改変せずに使用するためfalseを記載します。

#### License Identifier, Extracted Text, License Name, License Comment

SPDXライセンス リストに掲載されていないライセンスは無いため、本項目は記載しません。

## 5. ライセンス情報のサンプル

#### OSS単独の構成
例)SPDX tools
https://github.com/OpenChain-Project/Japan-WG-General/blob/master/License-Info-Exchange/SPDX-Lite-sample/SPDXtools-SPDXLite.txt

#### 受託開発の納品物でOSSを利用している構成
#### 組込み製品でOSSを活用している構成
#### サプライチェーンで受け渡す際の構成

