---
title: DaRT 10 支援的組態
description: DaRT 10 支援的組態
author: dansimp
ms.assetid: a07d6562-1fa9-499f-829c-9cc487ede0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 414b9d5cb7bf78dcfeda3fafc1c476e367709446
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800268"
---
# DaRT 10 支援的組態


本主題指定在您的環境中安裝並執行 Microsoft Diagnostics 和復原工具集（DaRT）10所需的必備軟體和支援的設定需求。 系統會指定執行 DaRT 10 所需的作業系統需求與系統需求。 如需需要考慮建立 DaRT 復原影像的先決條件資訊，請參閱[規劃以建立 dart 10 復原影像](planning-to-create-the-dart-10-recovery-image.md)。

如需適用于日後發行的支援設定，請參閱適用版本的檔。

您可以透過兩種方式之一來安裝 DaRT。 您可以在 IT 系統管理員電腦上安裝所有功能，您將會執行所有與執行的 DaRT 相關聯的工作。 或者，您也可以在系統管理員電腦上，只安裝建立復原影像的 DaRT 功能，然後在技術支援部電腦上安裝用於執行 DaRT （也就是 DaRT 遠端連線檢視器）的功能。

## DaRT 10 必備軟體


在安裝 DaRT 之前，請務必符合下列先決條件。

### 系統管理員電腦的先決條件

下表列出安裝 DaRT 10 和所有 DaRT 工具時系統管理員電腦的安裝先決條件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Windows 評估與開發套件（ADK）</strong></p></td>
<td align="left"><p>DaRT 復原映射嚮導所需。 包含部署工具，可用於自訂、部署及服務 Windows 影像，以及包含 Windows 預先安裝環境（Windows PE）。 如果您只安裝遠端連線檢視器和/或故障分析程式，則不需要 ADK。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows 開發套件或軟體發展套件（選用）</strong></p></td>
<td align="left"><p>故障分析程式需要來自 Windows 驅動程式套件的 Windows 10 調試工具來分析記憶體傾印檔案。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 10 64 位或32位 ISO 影像</strong></p></td>
<td align="left"><p>DaRT 需要 windows 10 媒體的 Windows 復原環境（Windows RE）影像。 根據您想要建立的 DaRT 復原影像類型，下載32位或64位版本的 Windows 10。 如果您在您的環境中同時支援這兩種系統類型，請下載這兩個版本的 Windows 10。</p></td>
</tr>
</tbody>
</table>

 

### 協助桌上型電腦必備元件

下表列出執行 DaRT 10 遠端連線檢視器時，協助台電腦的安裝先決條件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>DaRT 10 遠端連線檢視器</strong></p></td>
<td align="left"><p>必須安裝在 Windows 10 作業系統上。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows 版調試工具</strong></p></td>
<td align="left"><p>只有在安裝 [損毀分析程式] 工具時才需要</p></td>
</tr>
</tbody>
</table>

 

### 最終使用者電腦必備元件

除了 Windows 10 作業系統之外，不需要在最終使用者電腦上安裝任何必備軟體。

## <a href="" id="---------dart-10-operating-system-requirements"></a> DaRT 10 作業系統需求


### 管理員電腦系統需求

下表列出 DaRT 10 系統管理員電腦安裝支援的作業系統。

**記事** 針對您想要在系統管理員電腦上安裝的任何其他工具，請務必為您分配足夠的空間。

 

**記事** Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。

 

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
<th align="left">作業系統需求</th>
<th align="left">執行 DaRT 所需的 RAM 需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> DaRT 問訊台電腦系統需求

如果您允許服務台遠端對電腦進行疑難排解，您必須在技術支援部電腦上安裝遠端連線檢視器。 您可以選擇性地在技術支援部電腦上安裝 [崩潰分析工具]。

DaRT 10 可讓技術支援人員使用 DaRT 7.0、DaRT 8.0、DaRt 8.1 或 DaRT 10 遠端連線檢視器，連線至 DaRT 10 電腦。 DaRT 7.0、DaRT 8.0 和 DaRt 8.1、遠端連線檢視器分別需要 Windows 7、Windows 8 或 Windows 8.1 作業系統，而 DaRT 10 遠端連線檢視器需要 Windows 10。 DaRT 10 遠端連線檢視器和所有其他 DaRT 10 工具只能安裝在執行 Windows 10 的電腦上。

下表列出 DaRT 問訊台電腦安裝支援的作業系統。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
<th align="left">作業系統需求</th>
<th align="left">運行 DaRT 的記憶體需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows10 （僅適用于遠端連線檢視器10.0）</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8 （僅適用于遠端連線檢視器8.0）</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7 （僅適用于遠端連線檢視器7.0）</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>SP1、SP2</p></td>
<td align="left"><p>64位或32位</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>無</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準，企業，資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WindowsServer 2012 R2</p></td>
<td align="left"><p>標準，企業，資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
</tbody>
</table>

 

DaRT 在最終使用者電腦中也有下列最低硬體需求：

CD 或 DVD 光碟機或 USB 埠-只有當您在企業中使用 CD、DVD 或 USB 部署 DaRT 時才需要。

從 CD 或 DVD、USB 快閃記憶體磁片磁碟機或從遠端或復原分區啟動電腦的 BIOS 支援。

### <a href="" id="-------------dart-10-end-user-computer-system-requirements"></a> DaRT 10 端使用者電腦系統需求

DaRT 10 中的 [診斷與修復工具組] 視窗要求最終使用者電腦使用下列其中一個作業系統，以及適用于 DaRT 的指定系統記憶體數量：

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
<th align="left">作業系統需求</th>
<th align="left">RAM 需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[規劃部署 DaRT 10](planning-to-deploy-dart-10.md)

 

 





