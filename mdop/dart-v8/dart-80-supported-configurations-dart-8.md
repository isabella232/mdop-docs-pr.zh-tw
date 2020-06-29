---
title: DaRT 8.0 支援的組態
description: DaRT 8.0 支援的組態
author: dansimp
ms.assetid: 95d68e5c-d202-4f4a-adef-d2098328172e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02c891555992652bf2a9b2b674ab8377536ef9d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810250"
---
# DaRT 8.0 支援的組態


本主題指定安裝並在您的環境中執行 Microsoft Diagnostics 和復原工具集（DaRT）8.0 所需的必備軟體和支援的設定需求。 系統會指定執行 DaRT 8.0 所需的作業系統需求與系統需求。 如需考慮建立 DaRT 復原影像所需考慮的先決條件資訊，請參閱[規劃以建立 dart 8.0 恢復影像](planning-to-create-the-dart-80-recovery-image-dart-8.md)。

如需適用于日後發行的支援設定，請參閱適用版本的檔。

您可以透過兩種方式之一來安裝 DaRT。 您可以在 IT 系統管理員電腦上安裝所有功能，您將會執行所有與執行的 DaRT 相關聯的工作。 或者，您也可以在系統管理員電腦上，只安裝建立復原影像的 DaRT 功能，然後在技術支援部電腦上安裝用於執行 DaRT （也就是 DaRT 遠端連線檢視器）的功能。

## <a href="" id="---------dart-8-0-prerequisite-software"></a> DaRT 8.0 必備軟體


在安裝 DaRT 之前，請務必符合下列先決條件。

### 系統管理員電腦的先決條件

下表列出安裝 DaRT 8.0 和所有 DaRT 工具時系統管理員電腦的安裝先決條件。

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
<td align="left"><p><strong>.NET Framework 4。5</strong></p></td>
<td align="left"><p>DaRT 復原映射嚮導所需。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 開發套件或軟體發展套件（選用）</strong></p></td>
<td align="left"><p>故障分析程式需要 Windows 驅動程式套件的 Windows 8 調試工具來分析記憶體傾印檔案。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows 8 64 位 ISO 影像</strong></p></td>
<td align="left"><p>DaRT 需要 Windows 8 媒體的 Windows 復原環境（Windows RE）影像。 根據您想要建立的 DaRT 復原影像類型，下載32位或64位版本的 Windows 8。 如果您在您的環境中同時支援這兩種系統類型，請下載這兩個版本的 Windows 8。</p></td>
</tr>
</tbody>
</table>

 

### 協助桌上型電腦必備元件

下表列出執行 DaRT 8.0 遠端連線檢視器時，支援中心電腦的安裝先決條件。

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
<td align="left"><p><strong>DaRT 8.0 遠端連線檢視器</strong></p></td>
<td align="left"><p>必須安裝在 Windows 8 作業系統上。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>NET Framework 4。5</strong></p></td>
<td align="left"><p>DaRT 復原映像嚮導所需</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 版調試工具</strong></p></td>
<td align="left"><p>只有在安裝 [損毀分析程式] 工具時才需要</p></td>
</tr>
</tbody>
</table>

 

### 最終使用者電腦必備元件

除了 Windows 8 作業系統之外，不需要在最終使用者電腦上安裝任何必備軟體。

## <a href="" id="---------dart-operating-system-requirements"></a> DaRT 作業系統需求


### 管理員電腦系統需求

下表列出 DaRT 系統管理員電腦安裝支援的作業系統。

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
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準，企業，資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>512 MB</p></td>
<td align="left"><p>1. 0 GB</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> DaRT 問訊台電腦系統需求

如果您允許服務台遠端對電腦進行疑難排解，您必須在技術支援部電腦上安裝遠端連線檢視器。 您可以選擇性地在技術支援部電腦上安裝 [崩潰分析工具]。

DaRT 8.0 可讓技術支援人員使用 DaRT 7.0 或 DaRT 8.0 遠端連線檢視器連線至 DaRT 8.0 電腦。 DaRT 7.0 遠端連線檢視器需要 Windows 7 作業系統，而 DaRT 8.0 遠端連線檢視器需要 Windows 8。 DaRT 8.0 遠端連線檢視器和所有其他的 DaRT 8.0 工具只能安裝在執行 Windows 8 的電腦上。

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
<td align="left"><p>51</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
</tbody>
</table>

 

DaRT 在最終使用者電腦中也有下列最低硬體需求：

CD 或 DVD 光碟機或 USB 埠-只有當您在企業中使用 CD、DVD 或 USB 部署 DaRT 時才需要。

從 CD 或 DVD、USB 快閃記憶體磁片磁碟機或從遠端或復原分區啟動電腦的 BIOS 支援。

### <a href="" id="-------------dart-end-user-computer-system-requirements"></a> DaRT 最終使用者電腦系統需求

DaRT 中的 [診斷與修復工具集] 視窗要求最終使用者電腦使用下列其中一個作業系統，以及適用于 DaRT 的指定系統記憶體數量：

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
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>所有版本</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準，企業，資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>512 MB</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[規劃部署 DaRT 8.0](planning-to-deploy-dart-80-dart-8.md)

 

 





