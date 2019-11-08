# License-Info-Guideline (JP)

本文書は、組織間で授受されるオープン ソース ソフトウェア (Open Source Software, OSS)に関して、OSSのライセンスを遵守するために必要となる「ライセンス情報(* )」を作成する手順を示す事を目的としています。応用分野としては、一般ユーザーに広範囲に配布（販売）される製品（組込み機器）を想定して記載しています。

(* )本ドキュメントではOSSの配布に伴い提供すべき各種情報を、総称して「ライセンス情報」と記載します。

## 目次

1. ライセンス情報の必要性
1. 必要なライセンス情報の項目
1. ライセンス情報の収集方法
1. ライセンス情報の作成手順
1. ライセンス情報のサンプル

## 1. ライセンス情報の必要性 

OSSは、ソフトウェア開発には必要不可欠なものとなっています。OSSは誰でも自由に利用する事ができますが、利用するためには一定の条件に従う必要があります。その条件に従うために、利用しているOSSのライセンス情報が必要になります。

OSSが製品に組み込まれて販売されるまでには、OSSを入手して部品に組み込む会社、その部品を入手して製品に組み込む会社、その製品を購入してエンドユーザへ販売する会社といったように複数の企業が関係します。OSSのライセンスを遵守するためには、これらサプライチェーン上に位置する全ての企業が正確なライセンス情報を提供することが必要になります。サプライチェーン上で1社でもライセンス情報の提供を正確に提供することができないと、その企業より下流にある企業全てがOSSライセンスを遵守できなくなります。OSSのサプライチェーンに関係する担当者全員が理解して正確に作業することによって、適切にOSSの各ライセンスの条件を遵守することが可能になります。

ライセンス情報の必要性についての詳細は、「オープンソースソフトウェアライセンス遵守に関する一般公衆ガイド」を参照して下さい。
https://github.com/OpenChain-Project/curriculum/tree/master/supplier-leaflet

組織間でOSSを授受する際に、同時にライセンス情報を添付するには、以下の二つの課題があります。

・ライセンス情報には、OSS名や、そのバージョン、入手先など多岐に渡る情報が含まれるため、担当者が全体を正確に理解しないと、不十分な情報しか提供されない可能性があります。

・受け取る側が要求するフォーマットや、そのフォーマットに含まれる情報は、組織によって異なることがあるため、提供側組織における業務が煩雑になる可能性があります。

上記課題を検討した上で、本文書は、必要十分で最低限のライセンス情報を定義することで、簡単で正確なライセンス情報の生成が誰にでも可能となることを目指しています。また、必要十分で最低限のライセンス情報をSPDX Liteとして定義し、SPDX仕様に提案しています。以下では、簡単にSPDXおよびSPDX Liteについて説明します。

#### SPDX

ライセンス情報を扱うためのプロジェクトとして、Linux Foundation傘下にSoftware Package Data Exchange Workgroup (SPDX)があります。 https://spdx.org/

SPDX Workgroupは、SPDXフォーマットを定義しており、このフォーマットは、ソフトウェア パッケージに関連するソフトウェア名やバージョン、ライセンス、著作権表示などの情報を共有するための標準的なフォーマットです。以下、単にSPDXと記載した場合には、SPDXフォーマットのことを示します。また、OSSのコードをスキャンしてSPDXフォーマットでライセンス情報を出力するツール（FOSSology等）も公開されています。

#### SPDX Lite

SPDXはライセンス情報を共有するために非常に優れたフォーマットです。 しかし、ツールのスキャンにより得られるSPDX準拠のライセンス情報は、えてして膨大なものとなり、手作業によりライセンス情報を作成する組織において、コンプライアンス維持の上で課題となっていることも事実です。 そこで、SPDX Liteが、サプライチェーンにおけるライセンス条件の遵守のために、最低限の必須情報を記述するためのフォーマットとして、定義されました。 実ビジネスで運用されていて実績のあるデータを集め、それらを、定義するために十分な内容としています。 したがって、ツールによるライセンス情報収集と並行して、手作業・目視によるライセンス情報授受が可能な項目をリストアップしています。

以下はSPDX-Liteのサンプルです。 spread sheetなどに必要なライセンス情報を入力するだけで簡単に作成する事が出来ます。

![spdx-lite](https://user-images.githubusercontent.com/21073492/59993340-ee596500-968a-11e9-8783-5cf9a95ee351.png)

#### SPDXとSPDX Liteの位置づけ

SPDX Liteは、必要な項目（タグ）について、手書き入力や人手による視認を行う際の作業を考慮し、必要な情報に厳選しています。 SPDXの定義で必須とされるタグについてはSPDX Liteでも含まれており、下記の特徴を持っています。

 ・記載内容が厳選されている一方で必須なライセンス情報は含むため、議論のベース、初心者の誘導という点でSPDX Liteはベスト

・一つのソフトウェア　パッケージに、一つのライセンス情報を記載する、平易な記載には、付加的な情報が含まれないSPDX Liteファイルを用いることで、人による可読性を維持できる

・SPDX LiteはSPDXのMandatoryな項目を包含しているため、SPDX関連の各種ツールを用いたSPDX Liteファイルの運用も容易にできる

当然ながら、SPDXフォーマットによるライセンス情報は、細やかな記載が可能であり、ソフトウェア　パッケージ全体に含まれる全てのソースコードの情報を詳細に記載することもできるため、目的に応じて、SPDXでもSPDX Liteでも、ビジネス当事者の議論で決めればよい、と言えます。

## 2. 必要なライセンス情報の項目

SPDX Liteの項目と各項目の必要な理由を以下に記載します。

### SPDX Liteの項目一覧
| # | corresponding SPDX section no. | License Info. (tag) |
|:-----|:----|:-----------------------|
|L1.1  |2.1  | SPDX Version           |
|L1.2  |2.2  | Data License           |
|L1.3  |2.3  | SPDX Identifier        |
|L1.4	 |2.4	 | Document Name	        | 
|L1.5	 |2.5	 | SPDX Document Namespace| 
|L1.6	 |2.8	 | Creator	              | 
|L1.7  |2.9  | Created                |
|L2.1	 |3.1	 | Package Name	          | 
|L2.2	 |3.2	 | Package SPDX Identifier| 
|L2.3	 |3.3	 | Package Version        | 
|L2.4	 |3.4	 | Package File Name      | 
|L2.5	 |3.7	 | Package Download Location | 
|L2.6	 |3.8	 | Files Analyzed         | 
|L2.7  |3.11 | Package Home Page      | 
|L2.8	 |3.13 | Concluded License      | 
|L2.9	 |3.15 | Declared License       | 
|L2.10 |3.16 | Comments on License    | 
|L2.11 |3.17 | Copyright Text         | 
|L2.12 |3.20 | Package Comment        | 
|L3.1	 |6.1	 | License Identifier     | 
|L3.2	 |6.2	 | Extracted Text         | 
|L3.3	 |6.3	 | License Name           | 
|L3.4	 |6.5	 | License Comment        | 

各タグの内容で特定できない項目がある場合は、" NOASSERTION”を記載します。

### L1.1　SPDX Version
（説明を追記要）

### L1.2　Data License
（説明を追記要）

### L1.3　SPDX Identifier
（説明を追記要）

### L1.4　Document Name
（説明を追記要）

### L1.5　SPDX Document Namespace
（説明を追記要）

### L1.6　Creator
（説明を追記要）

### L1.7　Created
（説明を追記要）

### L2.1　Package Name
ソフトウェア パッケージの名称を記載します。
本項目は使用しているソフトウェアを特定するために利用します。
フィールド選択の背景・論拠:

### L2.2　Package SPDX Identifier
SPDX Liteファイルの中でソフトウェア パッケージが一意になる識別子を記載します。
本項目は同一ソフトウェア パッケージの別バージョンと区別するために利用します。
（どの範囲で一意なのか、誰が決めて記載するのかを追記要、ファイル内で良いのか、その場合、一ファイル一OSSパッケージを所与のものとしてよいのか、要確認。運用上は、一納品物のなかで独立していた方が良い）

### L2.3　Package Version
ソフトウェア パッケージのバージョンを記載します。
本項目は使用しているソフトウェアのバージョンを特定するために利用します。

### L2.4　Package File Name
ソフトウェア パッケージの実ファイル名を記載します。
本項目は使用しているソフトウェアの実ファイルを特定するために利用します。 これはPackage Nameと実ファイルが名称の違いにより、関連付け出来ない場合があるため本項目を必要とします。

### L2.5　Package Download Location
ソフトウェア パッケージの入手先を記載します。
本項目は使用しているソフトウェアと同じソフトウェアを入手するために利用します。

### L2.6　Files Analyzed
SPDX Liteファイルを手作業で作成する場合に"false"を記載します。（なぜ"false"を記載するのか説明要、手書きだからソースコード全体をスキャンしたとは言えないため”false”になると記載すべき）

### L2.7　Package Home Page
ソフトウェア パッケージのホームページを記載します。
本項目は使用しているソフトウェアの脆弱性情報などのコミュニティ情報を入手するために利用します。
（L2.5　 Package Download Locationとの違いが分かるといいかも）

### L2.8　Concluded License
SPDX Liteファイルの作成者がソフトウェア パッケージに適用されると結論したライセンスを記載します。 Concluded LicenseがDeclared Licenseと異なる場合、Comments on Licenseに説明を記載すべきです。 NOASSERTIONに関しては、Comments on Licenseに説明を記載した方が良いです。 本項目は使用しているソフトウェアのライセンスを特定するために利用します。
なお、記載するライセンス名は下記URLのSPDX License ListのIdentifierに従って記載する事を推奨します。 https://spdx.org/licenses/

### L2.9　Declared License
ソフトウェア パッケージの作成者が宣言したライセンスを記載します。
なお、記載するライセンス名は下記URLのSPDX License ListのIdentifierに従って記載する事を推奨します。 https://spdx.org/licenses/

### L2.10　Comments on License
SPDX Liteファイルの作成者がライセンスに関連する情報やライセンスを結論した理由を記載します。 本項目は使用しているソフトウェアのライセンスを補足するために利用します。
このタグには、「"Concluded License"記載の論拠」などライセンスに関わる情報に絞って記載されます。

### L2.11　Copyright Text
ソフトウェア パッケージの著作権情報を記載します。
すべての著作権情報を抽出する事が難しい場合はソースコードを一緒に提供します。
特定のライセンスでは配布時に著作権情報を提供する必要があります。本項目は使用しているソフトウェアの著作権情報を特定するために利用します。

### L2.12　Package Comment
ソフトウェア　パッケージに関する、追加情報を記載します。 SPDX Liteでは、このタグに、以下のような情報が収められることを想定しています。

(1)modification record
ソフトウェア パッケージが改変されている場合は”true”を記載します。
ソフトウェア パッケージが改変されていない場合は”false”を記載します。
OSSのソースコードに独自の修正を加えたり、OSSのソースコードを一部流用する場合は改変されていると判断するため”true”を記載します。
この項目はSPDXには存在しません。SPDX Liteの独自の項目です。
特定のライセンスではソフトウェアを改変した時に従う必要があるライセンス条件があります。そのため、ソフトウェアの改変を明示するために本項目を利用します。 ソフトウェア　パッケージが、『「Package Download Location」に記載された入手先からダウンロードしたソフトウェアそのものと、それに対するパッチファイル』が、それぞれ別個のSPDX Liteファイルで分離管理され、コンパイル段階でパッチが適用されているならば、ソフトウェア　パッケージとして提供されるコンパイル前のソフトウェアは、改変されておらず"false"として記載されることになります。

(2)compile options
コンパイル オプションによって、使用しているソフトウェアの特定のライセンスが対象外となる場合、本項目にコンパイル オプションを記載します。

(3)link methodology
特定のライセンスではソフトウェアのリンク方法によって、他にも影響を与えます。そのため、ソフトウェアのリンク方法を明示するために本項目を利用します。 ソフトウェア　パッケージに含まれるソフトウェアが動的リンク又は静的リンクのどちらを用いているかを記載します。

### L3.1　License Identifier
SPDX License Listに掲載されていないライセンスの場合、一意になる識別子を記載します。
本項目は使用しているソフトウェアのライセンスを特定するために利用します。
（どの範囲で一意なのか、誰が決めて記載するのかを追記要）

### L3.2　Extracted Text
SPDX License Listに掲載されていないライセンスの場合、ライセンス条文を記載します。
本項目は使用しているソフトウェアのライセンスを補足するために利用します。

### L3.3　License Name
SPDXライセンス リストに掲載されていないライセンスの場合、ライセンス名を記載します。
本項目は使用しているソフトウェアのライセンス名を特定するために利用します。

### L3.4　License Comment
SPDXライセンス リストに掲載されていないライセンスの場合、ライセンスに関連する情報を記載します。
本項目は使用しているソフトウェアのライセンスを補足するために利用します。


## 3. ライセンス情報の収集方法

SPDX Liteの各タグの情報をどのようにして収集することができるかを以下に記載します。
(すべてのタグを列記すべきか、NO ASSATIONで良いタグは、記述をスキップするか、NO ASSATIONと書け、と明記するか、要検討)

#### Package Name, Package Version, Package File Name
対象のソースコード又はソフトウェア パッケージを入手してください。

#### Package Download Location
入手した対象のソースコード又はソフトウェア パッケージの取得先を確認してください。 納品でCDなど物理デバイスから入手した時は納品先に取得元を確認してください。

#### Package Home Page
特定したPackage Nameを元にインターネットで検索してください。 ホームページが複数見つかる場合はソースコードの入手先やバージョンと照らし合わせて確認してください。

#### Concluded License, Declared License
入手したソースコード内の「COPYING」,「LICENSE」,「README」などのファイルや各ソースファイルのヘッダー部分を確認してください。 ソースコード内にライセンスが記載されたファイルが無い場合は、特定したPackage Home Pageにライセンスの情報があるか確認してください。


## 4. ライセンス情報の作成手順

ライセンス情報は分かる範囲でできる限り記載する事が大切です。 ソフトウェアサプライチェーンにおいて、ライセンス情報を受け取る側はライセンスを遵守するために少しでも多くの情報を必要とします。そのため、明確でない場合も出来る限りのライセンス情報を記載してコメントに明確でない旨を記載する事を推奨します。

### 手作業でバイナリファイルを対象に作成する場合
※要追記

### 手作業でソースコードを対象に作成する場合
例としてbusybox-1.30.1のライセンス情報を手作業で作成する手順を以下に記載します。 ここではbusybox-1.30.1のソースコードの「busybox-1.30.1.tar.bz2」が入手済みである事を想定します。

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
-> GPL-2.0-only
ソースコード内の「LICENSE」やホームページ内から判断して記載します。

#### Declared License
-> GPL-2.0-only
ソースコード内の「LICENSE」やホームページ内から判断して記載します。

#### Comments on License
-> busyboxは他のソフトウェアとはリンクせず、コマンドのみを使用します
ライセンス情報の補足を記載する。またリンクの有無を記載します。

#### Copyright Text
-> NOASSERTION
一緒にソースコードを提供するならば、すべての著作権表示を抽出する事が難しいとして、NOASSERTIONを記載して構いません。

#### modification record
-> false
改変せずに使用するためfalseを記載します。

#### License Identifier, Extracted Text, License Name, License Comment
SPDXライセンス リストに掲載されていないライセンスは無いため、本項目は記載しません。

## 5. ライセンス情報のサンプル

#### OSS単独の構成
例)SPDX tools https://github.com/OpenChain-Project/Japan-WG-General/blob/master/License-Info-Exchange/SPDX-Lite-sample/SPDXtools-SPDXLite.txt

#### 受託開発の納品物でOSSを利用している構成
受託開発の納品物で複数のOSSを利用している場合の記載例
https://github.com/OpenChain-Project/Japan-WG-General/blob/master/License-Info-Exchange/SPDX-Lite-sample/spreadsheet_sample2/SPDX-Lite-sample_20190920.xlsx

その他の記載例
https://github.com/OpenChain-Project/Japan-WG-General/blob/master/License-Info-Exchange/SPDX-Lite-sample


#### 組込み製品でOSSを活用している構成
例)Linux kernelソースコードの入手先が変わる一例


#### サプライチェーンで受け渡す際の構成
4社の受託開発の納品物で複数のOSSを利用している場合の記載例
4社からそれぞれ納品されるOSS情報を1ファイルに纏め、
サプライチェーン上流にOSS情報を受け渡す場合の例になります。
![SupplyChain](./SupplyChain-en.png)

4社のSPDX-Liteファイル
https://github.com/OpenChain-Project/Japan-WG-General/blob/master/License-Info-Exchange/SPDX-Lite-sample/spreadsheet_sample3

4社の納品物のOSS情報を1ファイルに纏めたファイル
https://github.com/OpenChain-Project/Japan-WG-General/blob/master/License-Info-Exchange/SPDX-Lite-sample/spreadsheet_sample3/spdx_lite_sample_all.xlsx

