---
title: AGPM 4.0 SP2 的新功能
description: AGPM 4.0 SP2 的新功能
author: dansimp
ms.assetid: 5c0dcab4-f27d-4153-8b8e-b280b080be51
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56369207780cf0795f16eda91f249a26270c4b47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801701"
---
# AGPM 4.0 SP2 的新功能


此內容說明 Microsoft Advanced 群組原則管理（AGPM）4.0 服務 Pack2 （SP2）的增強功能和支援的設定。 如果此內容與其他 AGPM 檔之間有差異，請考慮此內容的權威性，並假設它取代其他檔。

## <a href="" id="what-s-new"></a>新功能


AGPM 4.0 SP2 支援下列功能和功能。

### Windows 8.1 和 Windows Server2012 R2 的支援

AGPM 4.0 SP2 新增 Windows 8.1 和 Windows Server2012 R2 作業系統的支援。

### 新的及變更的用戶端延伸

已新增或變更 AGPM 的群組原則用戶端延伸，以支援 Windows 8.1 中的新原則設定。 這些原則設定可讓群組原則管理員管理和追蹤在兩個群組原則物件（Gpo）或範本之間變更的 Windows 8.1 專用原則設定。 若要查看用戶端延伸，請使用在 AGPM 用戶端中提供的 [設定] 和 [差異] 報告。

新的和已變更的群組原則用戶端延伸為：

-   **指定 [工作資料夾] 設定**。 如果您啟用此原則設定，IT 系統管理員可以將工作資料夾設定為自動建立。 [工作資料夾] 功能可讓使用者將檔案從其 Windows 桌面裝置同步處理到其他裝置。 使用此原則設定，在最終使用者的裝置上建立同步處理關聯，並設定如何識別儲存使用者工作資料夾的檔案伺服器。 如果您選取 [**自動設定同步**處理] 核取方塊，就會建立不含使用者輸入的同步處理合作關係，而且資料會自動開始同步處理到使用者的裝置。 如果您沒有選取 [**自動設定同步**處理] 核取方塊，使用者就必須提供輸入才能啟動同步處理。

-   **針對所有使用者強制執行自動設定**。 如果您啟用此原則設定，IT 管理員可以決定是否要在最終使用者裝置上自動建立工作資料夾共同作業，而不需要使用者輸入。 如果您啟用此原則設定，就會根據您設定 [**指定工作資料夾設定**] 策略設定的方式，來設定同步處理。 如果您將 [**強制自動設定**] 策略設定為 [**已停用**] 或 [**未設定**]，則會根據您在 [**指定工作資料夾設定**] 設定策略設定中設定**自動提供**選項的方式，設定 [工作資料夾合作關係]。

如需工作資料夾功能的詳細資訊，請參閱[工作資料夾概覽](https://go.microsoft.com/fwlink/?LinkId=330444)。

### 客戶意見反應與修補程式匯總

AGPM 4.0 SP2 包括修正在 AGPM 4.0 服務 Pack1 （SP1）發行後發現的問題的修復程式匯總。 AGPM 4.0 SP2 包含最新的修正程式，包括 Microsoft 高級群組原則管理 4.0 SP1 Hotfix1。 如需詳細資訊，請參閱知識庫文章[2873472](https://go.microsoft.com/fwlink/?LinkId=325400)）。

### [設定] 和 [差異] 報告中的新群組原則延伸

新的群組原則延伸已新增至 [設定] 和 [差異] 報告中。

### 安裝程式變更與支援

AGPM 4.0 SP2 安裝程式的變更和支援包括：

-   如果您在 Windows 8 或 Windows Server 2012 作業系統或更新版本的作業系統上安裝 AGPM 4.0 SP2，AGPM 安裝程式會驗證已安裝必要的必備軟體（群組原則管理主控台（GPMC）及 Microsoft .NET Framework 3.5）。 如果未安裝此必備軟體，則會封鎖 AGPM 4.0 SP2 安裝。

-   當您安裝 AGPM 服務器時，會自動啟用 WCF 啟用、非 HTTP 啟用和 Windows Process Activation Service。

-   在 WindowsVista 用戶端作業系統及更新版本的作業系統上，在安裝 AGPM 4.0 SP2 之前，請先為您的作業系統下載適當版本的遠端系統管理工具。

-   AGPM 4.0 SP2 支援與舊版支援的作業系統提供向後相容性。

### 能夠升級至 AGPM 4.0 SP2，而不需重新加入設定參數

您可以將 AGPM 用戶端或 AGPM 服務器升級至 AGPM 4.0 SP2，而不會提示您重新輸入來自 AGPM 4.0 後的配置參數（稱為 [智慧升級]），如下表所示。 如果您要從其他版本的 AGPM 升級到 AGPM 4.0 SP2，如資料表所示，您必須使用 [傳統升級]，這需要您重新輸入配置參數。 由於每個版本的 AGPM 都與特定的作業系統相關聯，請參閱[選擇要安裝的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，並確認您在升級 AGPM 之前，請先升級您的作業系統。

**AGPM 4.0 SP2 支援的升級**

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>您可以升級的 AGPM 版本</strong></p></td>
<td align="left"><p><strong>2.5</strong></p></td>
<td align="left"><p><strong>3.0</strong></p></td>
<td align="left"><p><strong>4.0</strong></p></td>
<td align="left"><p><strong>4.0 SP1</strong></p></td>
<td align="left"><p><strong>4.0 SP2</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>2.5</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>傳統升級</p></td>
<td align="left"><p>傳統升級</p></td>
<td align="left"><p>安裝遭到封鎖</p></td>
<td align="left"><p>安裝遭到封鎖</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3.0</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>傳統升級</p></td>
<td align="left"><p>安裝遭到封鎖</p></td>
<td align="left"><p>安裝遭到封鎖</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>智慧升級</p></td>
<td align="left"><p>智慧升級</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.0 SP1</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>智慧升級</p></td>
</tr>
</tbody>
</table>

 

## 支援的設定


AGPM 4.0 SP2 支援下表中的配置。 雖然 AGPM 支援混合式設定，但我們強烈建議您在相同的作業系統行上執行 AGPM 用戶端和 AGPM 服務器，例如，使用 Windows Server2012 R2、Windows 8 和 Windows Server 2012 的 windows 8.1 等。

**AGPM 4.0 SP2 支援的作業系統與原則設定**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>AGPM 服務器支援的設定</strong></th>
<th align="left"><strong>適用于 AGPM 用戶端的支援設定</strong></th>
<th align="left"><strong>AGPM 支援</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2、Windows Server 2012、Windows 8.1 或 Windows 8</p></td>
<td align="left"><p>Windows Server 2012 或 Windows 8</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8.1 或 Windows 8 的原則設定或喜好設定專案</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1、Windows 8 或 Windows7 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</p></td>
<td align="left"><p>不支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法報告或編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1、Windows 8 或 Windows7 中的原則設定或喜好設定專案</p></td>
</tr>
</tbody>
</table>

 

## 安裝 AGPM 4.0 SP2 的先決條件


下表說明當 .NET Framework 3.5 或遠端伺服器管理工具中的 GPMC 遺失時，Windows 8.1 上的 AGPM 4.0 SP2 用戶端和伺服器安裝程式的行為。

**AGPM 用戶端**

**AGPM 服務器**

**作業系統**

**.NET Framework**

**遠端伺服器管理工具**

**.NET Framework**

**遠端伺服器管理工具**

**Windows 8。1**

如果沒有啟用或安裝 .NET Framework 3.5，安裝程式會封鎖安裝。

如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。

如果沒有啟用或安裝 .NET Framework 3.5，安裝程式會封鎖安裝。

如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。

**Windows Server2012 R2**

如果沒有啟用或安裝 .NET Framework 3.5，安裝程式會封鎖安裝。

如果未啟用 GPMC，安裝程式會在安裝期間啟用它。

如果沒有啟用或安裝 .NET Framework 3.5，安裝程式會封鎖安裝。

如果未啟用 GPMC，安裝程式會在安裝期間啟用它。

 

## 如何取得 MDOP 技術


AGPM 4.0 SP2 是 Microsoft 桌面優化套件（MDOP）的一部分。 MDOP 是 Microsoft 軟體保證的一部分。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相關主題


[進階群組原則管理](index.md)

[Microsoft 進階群組原則管理 4.0 SP2 版本資訊](release-notes-for-microsoft-advanced-group-policy-management-40-sp2.md)

[選擇要安裝的 AGPM 版本](choosing-which-version-of-agpm-to-install.md)

 

 





