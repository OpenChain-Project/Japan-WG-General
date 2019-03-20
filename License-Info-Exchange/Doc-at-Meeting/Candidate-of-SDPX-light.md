## Candidate of SPDX light (under discussion)

Yes: Candidate

P: There was a proposal, but is not selected as the candidate.

| SPDX section no. | License Info. | Info. name in Japanese  | Tag  | SPDX Light  | Rationale      |
|:------------|:-------------|:------------------|:------------------|:------------------|:------------------|
|2.	|Document Creation Information	|	||||	
|2.1	|SPDX Version	|		| |||
|2.2	|Data License	|	|	|||
|2.3	|SPDX Identifier	|	|	|||
|2.4	|Document Name	|	|	|||
|2.5	|SPDX Document Namespace	|	|	|||
|2.6	|External Document References	|	|	||
|2.7	|License List Version	|	|	|||
|2.8	|Creator	|	|	|||
|2.9	|Created	|	|	|||
|2.10	|Creator Comment	|	|	|||
|2.11	|Document Comment	|	|	|||
|	|	+ SPDX info. creation date|	| 	|P||
|	|	+ SPDX info. creator |	| |P||
|3.	|Package Information	|	| |||
|3.1	|Package Name	|	| PackageName |Yes|To identify software	|
|3.2	|Package SPDX Identifier	|	| SPDXID|Yes| To keep compatibility with SPDX. Feedback from SPDX team. |
|3.3	|Package Version	|	| PackageVersion |Yes|To identify specific version	|
|3.4	|Package File Name	|	| PackageFileName	|Yes|To identify specific package|
|3.5	|Package Supplier	|	|	|||
|3.6	|Package Originator	|	| 	|P||
|3.7	|Package Download Location 	|	| PackageDownloadLocation |Yes|To get the identical software	|
|3.8	|Files Analyzed	|	|	FilesAnalyzed |Yes| In SPDX Lite, to set "false". To keep compatibility with SPDX. Feedback from SPDX team. |
|3.9	|Package Verification Code	|	|	|| It is mandatory in SPDX. But, in SPDX Lite, this is not needed if 3.8 is set to "false". |
|3.10	|Package Checksum	|	|	|||
|3.11	|Package Home Page	|	| PackageHomePage	|Yes|To verify relevant information|
|3.12	|Source Information	|	| 	|P|To specify source code or binary|
|3.13	|Concluded License	|	| PackageLicenseConcluded	|Yes||
|	| +	License file list || 	|P|To specify a license when muliple licenses exist |
|3.14	|All Licenses Information from Files	|	| 	|P|To specify all license. It is mandatory in SPDX. But, in SPDX Lite, this is not needed if 3.8 is set to "false".|
|3.15	|Declared License	|	| PackageLicenseDeclared	|Yes||
|3.16	|Comments on License	|	| PackageLicenseComments	|Yes|To verify additional conditions|
|3.17	|Copyright Text	|	| PackageCopyrightText	|Yes||
|3.18	|Package Summary Description	|	| 	|P|To verify risk of OSS(quality, license, patent)|
|3.19	|Package Detailed Description	|	| 	|P|To verify risk of OSS(quality, license, patent)|
|3.20	|Package Comment	|	| 	|P|To verify modification from original code in file level|
|3.21	|External Reference	|	|	|||
|3.22	|External Reference Comment	|	|	|||
|	|	+ URL of OSS license|	| 	|P|To double-check OSS license|
|	|	+ License text|	| 	|P|To specify a license in case where the license is not registered|
|	|	+ modification record|	| ExternalRef |Yes|To comply with license obligation|
|	|	+ Patent related notice|	| 	|P||
|	|	+ License term |	| 	|P|To verify license obiligation|
|4.	|File Information	|	||||	
|4.1	|File Name	|	| 	|P||
|4.2	|File SPDX Identifier	|	|	|||
|4.3	|File Type	|	|	|||
|4.4	|File Checksum	|	|	|||
|4.5	|Concluded License	|	|	|||
|4.6	|License Information in File	|	| 	|P||
|4.7	|Comments on License	|	|	|||
|4.8	|Copyright Text	|	| 	|P||
|4.9	|Artifact of Project Name	|	|	|||
|4.10	|Artifact of Project Homepage	|	|	|||
|4.11	|Artifact of Project Uniform Resource Identifier	|	|	|||
|4.12	|File Comment	|	| 	|P||
|4.13	|File Notice	|	|	|||
|4.14	|File Contributor	|	|	|||
|4.15	|File Dependencies	|	|	|||
|5.	|Snippet Information	|	| 	|||
|5.1	|Snippet SPDX Identifier	|	|	|||
|5.2	|Snippet from File SPDX Identifier	|	|	|||
|5.3	|Snippet Byte Range	|	|	|||
|5.4	|Snippet Line Range	|	|	|||
|5.5	|Snippet Concluded License	|	|	|||
|5.6	|License Information in Snippet	|	|	|||
|5.7	|Snippet Comments on License	|	|	|||
|5.8	|Snippet Copyright Text	|	|	|||
|5.9	|Snippet Comment	|	|	|||
|5.10	|Snippet Name	|	|	|||
|6.	|Other Licensing Information Detected	|	||	|||
|6.1	|License Identifier	|	| LicenseID	|Yes|To specify licenses which are not on the SPDX license list / To specify dual license|
|6.2	|Extracted Text	|	| ExtractedText	|Yes|To specify licenses which are not on the SPDX license list / To specify dual license|
|6.3	|License Name	|	| LicenseName	|Yes|To specify licenses which are not on the SPDX license list / To specify dual license|
|6.4	|License Cross Reference	|	|	|||
|6.5	|License Comment	|	| LicenseComment	|Yes|To specify licenses which are not on the SPDX license list / To specify dual license|
|7.	|Relationships between SPDX Elements	|	|	|||
|7.1	|Relationship	|	| 	|P|To verify the influence over othre modules, in case of GPL family|
|7.2	|Relationship Comment	|	|	|||
|8.	|Annotations	|	|	|||
|8.1	|Annotator	|	|	|||
|8.2	|Annotation Date	|	|	|||
|8.3	|Annotation Type	|	|	|||
|8.4	|SPDX Identifier Reference	|	|	|||
|8.5	|Annotation Comment	|	|	|||
|9.	|Review Information 	|	|	|||


|SPDX節番号	| SPDX項目 | SPDX項目の説明 | Tag | SPDX light | コメント(目的など)|
|:------|:-----------|:-----|:-----|:-----|:------------------|
|2.	|Document Creation Information	|文書作成情報	||||	
|2.1	|SPDX Version	|SPDXバージョン		| |||
|2.2	|Data License	|データ ライセンス	|	|||
|2.3	|SPDX Identifier	|SPDX識別子	|	|||
|2.4	|Document Name	|文書名	|	|||
|2.5	|SPDX Document Namespace	|SPDX文書名前空間	||	||
|2.6	|External Document References	|外部文書参照	||	||
|2.7	|License List Version	|ライセンス リスト バージョン	||	||
|2.8	|Creator	|作成者	||	||
|2.9	|Created	|作成日時	||	||
|2.10	|Creator Comment	|作成者コメント	||	||
|2.11	|Document Comment	|文書コメント	||	||
|	|	+ SPDX情報の生成日時|	|| P	||
|	|	+ SPDX情報の生成手段|	|| P	||
|3.	|Package Information	|パッケージ情報	||||	
|3.1	|Package Name	|パッケージ名	|PackageName| Yes |作者によって付けられたソフトウェアの名前を識別するために必要です。名前からソフトウェアの機能がわかることが多く、ライセンスや修正情報の調査を行う場合の参考になります。|
|3.2	|Package SPDX Identifier	|パッケージSPDX識別子	|SPDXID|	Yes | SPDX仕様との互換性確保。SPDXチームからのフィードバック。|
|3.3	|Package Version	|パッケージ バージョン	|PackageVersion| Yes |使用しているソフトウェアのバージョンを特定するために必要です。同じソフトウェアでもバージョンによってライセンスや著作権情報が異なる場合があります。|
|3.4	|Package File Name	|パッケージ ファイル名	|PackageFileName| Yes	|パッケージを特定するために必要です。同じファイルを取得する際に使います。|
|3.5	|Package Supplier	|パッケージ提供者	||	||
|3.6	|Package Originator	|パッケージ原作者	|| P	||
|3.7	|Package Download Location 	|パッケージ ダウンロード位置	|PackageDownloadLocation| Yes |	ソースコードの調査を行う場合に、使用しているものと同じソースコードを取得するために必要。3.5のPackage File Nameと組み合わせて使用する。|
|3.8	|Files Analyzed	|解析したファイル	|FilesAnalyzed| Yes	| ”false“にセット。SPDX仕様との互換性確保。SPDXチームからのフィードバック。|
|3.9	|Package Verification Code	|パッケージ検証コード	||	| SPDX仕様では必須。3.8がFalseにセットされているときは記載不要。|
|3.10	|Package Checksum	|パッケージ チェックサム	||	||
|3.11	|Package Home Page	|パッケージ ホーム ページ	|PackageHomePage| Yes	|ソフト内容、修正情報などを確認できるようにしておくために必要です。プロジェクトの活動状況を調査する場合にも利用します。ソースコードからライセンスや著作権情報を得られない場合の手掛かりになります。|
|3.12	|Source Information	|ソース情報	|| P	|ソースコード or バイナリの識別|
|3.13	|Concluded License	|結論されたライセンス	|PackageLicenseConcluded| Yes	|Concluded License…複数ライセンスの場合にどのライセンスを適用するかを使用者が決定した結果。最初に使うと決めた人がまず定義する。サプライチェーンの途中で判断が変わる場合は変更すれば良い。最終利用者が判断できない場合があるため、供給者側で判断する。Declared License…作者が定めたライセンス。使用可能なライセンスかどうかを判断するために必要。|
|	|	+ 当該ライセンスのファイル一覧|	|| P	|複数ライセンスを持つ場合の識別用 File情報の利用でも可|
|3.14	|All Licenses Information from Files	|ファイルからの全ライセンス情報	|| P	|全てのファイルからライセンスが抽出されていることが重要。SPDX仕様では必須。3.8がFalseにセットされているときは記載不要。|
|3.15	|Declared License	|宣言されたライセンス	|PackageLicenseDeclared| Yes	|Concluded License…複数ライセンスの場合にどのライセンスを適用するかを使用者が決定した結果。最初に使うと決めた人がまず定義する。サプライチェーンの途中で判断が変わる場合は変更すれば良い。最終利用者が判断できない場合があるため、供給者側で判断する。Declared License…作者が定めたライセンス。使用可能なライセンスかどうかを判断するために必要。|
|3.16	|Comments on License	|ライセンスへのコメント	 |PackageLicenseComments| Yes	|ライセンスを結論づけた時の記録や、補足事項を記載する。ソフトウェアの組み合わせによっては使用の可否判断が変わるため、複数のライセンスから一つを選択した場合などは記載が必要。|
|3.17	|Copyright Text	|著作権テキスト	|PackageCopyrightText| Yes	|コピーライト表記が必要なライセンスのための情報。ライセンス文にコピーライトが書かれていない場合は抽出しておく必要がある。|
|3.18	|Package Summary Description	|パッケージ要約記述	|| P	|OSSのリスク(品質, ライセンス, 特許)確認用|
|3.19	|Package Detailed Description	|パッケージ要約記述	|| P	|OSSのリスク(品質, ライセンス, 特許)確認用|
|3.20	|Package Comment	|パッケージ コメント	| P	|オリジナルからの改変の有無を個々で記述(SK)|
|3.21	|External Reference	|外部参照	|	|||
|3.22	|External Reference Comment	|外部参照コメント	||	||
|	|	+ OSSライセンスのURL|	||　P	|OSSライセンスに言及しているURL(ライセンスの検証用)|
|	|	+ ライセンスファイルそのもの|	|| P	|SPDX未登録の場合の確認用|
|	|	+ オリジナルからの改変の有無|	|ExternalRef| Yes	|V-up版への入れ替え可否|
|	|	+ 特許に関する特記事項の有無|	|| P	||
|	|	+ ライセンス条件|	|| P	|ソース開示の要否等 (ライセンスに関する義務の確認用)|
|4.	|File Information	|ファイル情報	|| ||	
|4.1	|File Name	|文書名	|| P	||
|4.2	|File SPDX Identifier	|ファイルSPDX識別子	||	||
|4.3	|File Type	|ファイル タイプ	||	||
|4.4	|File Checksum	|ファイル チェックサム	||	||
|4.5	|Concluded License	|結論されたライセンス|	|	||
|4.6	|License Information in File	|ファイル中のライセンス情報	||P	||
|4.7	|Comments on License	|ライセンスへのコメント	||	||
|4.8	|Copyright Text	|著作権テキスト	|| P	||
|4.9	|Artifact of Project Name	|派生元プロジェクト名(廃止予定)	||	||
|4.10	|Artifact of Project Homepage	|派生元プロジェクト名（廃止予定)	||	||
|4.11	|Artifact of Project Uniform Resource Identifier	|派生元プロジェクト統一資源識別子(廃止予定)	||	||
|4.12	|File Comment	|ファイル コメント	|| P	||
|4.13	|File Notice	|ファイル表記	||	||
|4.14	|File Contributor	|ファイル貢献者	||	||
|4.15	|File Dependencies	|ファイル依存関係(廃止予定)	||	||
|5.	|Snippet Information	|コード断片情報	||	||
|5.1	|Snippet SPDX Identifier	|コード断片SPDX識別子	||	||
|5.2	|Snippet from File SPDX Identifier	|ファイル由来コード断片SPDX識別子	||	||
|5.3	|Snippet Byte Range	|コード断片バイト範囲	||	||
|5.4	|Snippet Line Range	|コード断片ライン範囲	||	||
|5.5	|Snippet Concluded License	|コード断片結論されたライセンス	||	||
|5.6	|License Information in Snippet	|コード断片中のライセンス情報	||	||
|5.7	|Snippet Comments on License	|コード断片結論されたライセンス	||	||
|5.8	|Snippet Copyright Text	|コード断片著作権テキスト	||	||
|5.9	|Snippet Comment	|コード断片コメント	||	||
|5.10	|Snippet Name	|コード断片名	||	||
|6.	|Other Licensing Information Detected	|検出された他ライセンス情報	||	||
|6.1	|License Identifier	|ライセンス識別子	|LicenseID| Yes	|SPDXで定義されていないライセンスの場合に、その情報を記述する。|
|6.2	|Extracted Text	|抽出されたテキスト	|ExtractedText| Yes	|SPDXで定義されていないライセンスの場合に、その情報を記述する。|
|6.3	|License Name	|ライセンス名	|LicenseName| Yes	|SPDXで定義されていないライセンスの場合に、その情報を記述する。|
|6.4	|License Cross Reference	|ライセンス相互参照	||	||
|6.5	|License Comment	|ライセンス コメント	|LicenseComment| Yes	|SPDXで定義されていないライセンスの場合に、その情報を記述する。|
|7.	|Relationships between SPDX Elements	|SPDX要素間の関係	||	||
|7.1	|Relationship	|関係	|| P	|GPL等の場合、OSSと他のプログラムとの連携の有無|
|7.2	|Relationship Comment	|関係コメント	||	||
|8.	|Annotations	|注釈	||	||
|8.1	|Annotator	|注釈者	||	||
|8.2	|Annotation Date	|注釈日時	||	||
|8.3	|Annotation Type	|注釈タイプ	||	||
|8.4	|SPDX Identifier Reference	|SPDX識別子参照	||	||
|8.5	|Annotation Comment	|注釈コメント	||	||
|9.	|Review Information 	|レビュー情報(廃止予定)	||	||

