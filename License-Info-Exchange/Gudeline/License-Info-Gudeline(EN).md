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

SPDXはライセンス情報を共有するために非常に優れたフォーマットです。
しかし、ソフトウェア パッケージに関連する情報が膨大にあり、初心者が扱う事は難しいです。
SPDX Liteはソフトウェアサプライチェーンにおいて、最低限は必要のライセンス情報をSPDXから抽出したフォーマットです。  

以下はSPDX-Liteのサンプルです。
spread sheetなどに必要なライセンス情報を入力するだけで簡単に作成する事が出来ます。

![spdx-lite](https://user-images.githubusercontent.com/21073492/59993340-ee596500-968a-11e9-8783-5cf9a95ee351.png)

