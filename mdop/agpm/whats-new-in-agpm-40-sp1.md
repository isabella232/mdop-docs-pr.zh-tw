---
title: AGPM 4.0 SP1 的新功能
description: AGPM 4.0 SP1 的新功能
author: dansimp
ms.assetid: c6a3d94a-13c3-44e6-a466-c3011879999e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca1ee4a1c2eb943a25246dc31b127eaf72ff5fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801702"
---
# AGPM 4.0 SP1 的新功能


此「新增功能」內容描述 Microsoft 高級群組原則管理（AGPM） 4.0 SP1 的增強功能和支援的設定。 如果此內容與其他 AGPM 檔之間有差異，此內容應該被視為權威性，而且應該取代本產品隨附的內容。

## <a href="" id="what-s-new"></a>新功能


AGPM 4.0 SP1 支援下列增強功能：

### 新的及變更的用戶端延伸

已針對 AGPM 新增或變更群組原則用戶端延伸（CSEs），以支援 Windows 8 和 Windows Server 2012 中的新群組原則。 這些群組原則可讓群組原則管理員管理和追蹤在兩個群組原則物件（Gpo）或範本之間變更的 Windows 8 特定群組原則設定。 您也可以使用 Windows 8 專用的設定來建立自訂 Gpo，並設定並將 Gpo 儲存為範本。 若要查看您的 CSEs，請使用在 AGPM 4.0 SP1 用戶端中提供的 [設定] 和 [差異] 報告。

新的和已變更的群組原則用戶端延伸為：

-   **中心存取原則：** 可讓群組原則管理員在群組原則伺服器上指定中心存取原則，例如，檔案伺服器。 [中心存取原則] 是由 GPO 專案所指定並套用至原則目標的授權原則，可協助集中存取及控制資源。 您必須在 Active Directory 中的群群組原則用戶端電腦上設定這些中心存取原則。 群組原則會將適用之中心存取原則的知識發佈到必須強制執行的電腦上。

-   **名稱解析原則變更：** 可讓群組原則管理員在 DNS 用戶端電腦上設定 DNS 安全與 DirectAccess 的設定。 已新增配置一般 DNS 伺服器設定和編碼設定的新索引標籤。

-   **群組原則喜好設定變更：** 新增針對 Windows 8 所新增之 Internet Explorer 10 設定的設定和管理的支援。

-   **遠端應用程式和桌面連線：** 讓群組原則管理員指定用於遠端應用程式和桌面連線的預設連線 URL。

-   **Windows 移至 [啟動] 選項：** 讓群組原則管理員設定在已連接包含 Windows To Go 工作區的 USB 裝置時，電腦是否會引導至 Windows。

-   **Windows To Go 休眠選項：** 可讓群組原則管理員設定電腦從 Windows 移至 [前往] 工作區時，電腦是否可以使用休眠睡眠狀態（S4）。

### 客戶意見反應與修補程式匯總

AGPM 4.0 SP1 包含修正在 AGPM 4.0 發行後發現問題的修正程式。 AGPM 4.0 SP1 包含最新的修正程式，包括 Microsoft 高級群組原則管理4.0 修正程式1。

### [設定與差異] 報告顯示新的群組原則延伸

新的群組原則延伸已新增至 [設定] 和 [差異] 報告中。

### 安裝程式變更與支援

AGPM 4.0 SP1 安裝程式的變更與支援為：

-   如果您在 Windows 8 或 Windows Server 2012 上安裝 AGPM 4.0 SP1，AGPM 安裝程式會驗證是否已安裝所需的必備軟體（群組原則管理主控台和 .NET 3.5 架構）。 如果未安裝這些必備元件，則會封鎖 AGPM 4.0 SP1 安裝。

-   當您安裝 [AGPM 4.0 SP1]、[WCF 啟動]、[非 HTTP 啟用] 和 [Windows Process Activation Service] 時，系統會自動啟用。

-   在 Windows Vista、Windows 7 和 Windows 8 用戶端作業系統上，請先下載適用于您作業系統的遠端系統管理工具組版本，然後再安裝 AGPM 4.0 SP1。

-   支援與舊版支援的作業系統進行向後相容性。

### 能夠升級或更新到 AGPM 4.0 SP1，而不需重新輸入配置參數

您只能從 AGPM 4.0 將 AGPM 用戶端或伺服器升級至 AGPM 4.0 SP1，而不會提示您重新輸入設定參數（稱為「智慧升級」），如下表所示。 如果您要從其他版本的 AGPM 升級到 AGPM 4.0 SP1 （如下表所示），您必須使用 [傳統升級]，這需要您重新輸入配置參數。 由於每個版本的 AGPM 都與特定的作業系統相關聯，請參閱[選擇要安裝的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，並在執行升級前，務必要升級作業系統。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>您可以升級的 AGPM 版本</strong></p></td>
<td align="left"><p><strong>2.5</strong></p></td>
<td align="left"><p><strong>3.0</strong></p></td>
<td align="left"><p><strong>4.0</strong></p></td>
<td align="left"><p><strong>4.0 SP1</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>2.5</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>傳統升級</p></td>
<td align="left"><p>傳統升級</p></td>
<td align="left"><p>安裝遭到封鎖</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3.0</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>傳統升級</p></td>
<td align="left"><p>安裝遭到封鎖</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>智慧升級</p></td>
</tr>
</tbody>
</table>

 

## 支援的設定


AGPM 支援下表中的設定。 雖然 AGPM 支援混合式設定，但強烈建議您在相同的作業系統系列上執行 AGPM 用戶端和伺服器，例如 windows 8 與 Windows Server 2012、Windows 7 和 Windows Server 2008 R2 等。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>針對 AGPM 4.0 SP1 伺服器所支援的設定</strong></p></td>
<td align="left"><p><strong>適用于 AGPM 4.0 SP1 用戶端的支援配置</strong></p></td>
<td align="left"><p><strong>AGPM 4.0 SP1 支援</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8 或 Windows Server 2012</p></td>
<td align="left"><p>Windows 8 或 Windows Server 2012</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2 或 Windows 7</p></td>
<td align="left"><p>Windows Server 2008 R2 或 Windows 7</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2 或 Windows 7 或 Windows 8 或 windows Server 2012</p></td>
<td align="left"><p>Windows Server 2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows Server 2008 R2 或 windows 7 或 Windows 8 中的原則設定或喜好設定專案。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server 2008 R2 或 Windows 7 或 Windows 8 或 windows Server 2012</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server 2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法報告或編輯僅存在於 Windows Server 2008 R2 或 windows 7 或 Windows 8 中的原則設定或喜好設定專案</p></td>
</tr>
</tbody>
</table>

 

## 安裝 AGPM 4.0 SP1 的先決條件


下表說明當 .NET 3.5 或遠端伺服器管理工具（RSAT）中的群組原則管理主控台遺失時，在 AGPM 4.0 SP1 用戶端和伺服器安裝程式的 Windows 8 上的行為。

**AGPM 用戶端 4.0 SP1**

**AGPM Server 4.0 SP1**

**作業系統**

**.NET**

**RSAT**

**.NET**

**RSAT**

**Windows8**

如果未啟用或未安裝 .NET 3.5，安裝程式會封鎖安裝。

如果系統上未啟用或安裝 GPMC，安裝程式會封鎖安裝。

如果未啟用或未安裝 .NET 3.5，安裝程式會封鎖安裝。

如果系統上未啟用或安裝 GPMC，安裝程式會封鎖安裝。

**Windows Server 2012**

如果未啟用或未安裝 .NET 3.5，安裝程式會封鎖安裝。

如果未啟用 GPMC，安裝程式會在安裝期間啟用它。

如果未啟用或未安裝 .NET 3.5，安裝程式會封鎖安裝。

如果未啟用 GPMC，安裝程式會在安裝期間啟用它。

 

## 相關主題


[進階群組原則管理](index.md)

[Microsoft 進階群組原則管理 4.0 SP1 版本資訊](release-notes-for-microsoft-advanced-group-policy-management-40-sp1.md)

 

 





