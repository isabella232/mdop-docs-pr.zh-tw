---
title: AGPM 4.0 SP3 的新功能
description: AGPM 4.0 SP3 的新功能
author: dansimp
ms.assetid: df495d55-9fbf-4f7e-a7af-3905f4f8790e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: a98bda82fab561113522382b4de6539a9dc23d0c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802489"
---
# AGPM 4.0 SP3 的新功能


此內容說明 Microsoft Advanced 群組原則管理（AGPM）4.0 服務 Pack3 （SP3）的增強功能和支援的設定。 如果此內容與其他 AGPM 檔之間有差異，請考慮此內容的權威性，並假設它取代其他檔。

## <a href="" id="what-s-new"></a>新功能


AGPM 4.0 SP3 支援下列功能和功能。

### 支援 Windows10

AGPM 4.0 SP3 會新增 Windows10 和 Windows Server 2016 作業系統的支援。

### PowerShell 支援

AGPM 4.0 SP3 新增 PowerShell Cmdlet 的支援。 如需在 AGPM 4.0 SP3 中提供的 Cmdlet 清單，包括描述及語法，請參閱[使用 Windows PowerShell 的 Microsoft 桌面優化套件自動化](https://docs.microsoft.com/powershell/mdop/get-started?view=win-mdop2-ps)。

### 客戶意見反應與修補程式匯總

AGPM 4.0 SP3 包括所有修正的匯總，包括 Microsoft 高級群組原則管理 4.0 SP2，以及自 AGPM 4.0 SP2 之後發現問題的修正程式。

### 能夠升級至 AGPM 4.0 SP3，而不需重新輸入配置參數

您可以將 AGPM 用戶端或 AGPM 服務器升級至 AGPM 4.0 SP3，而不會提示您重新輸入來自 AGPM 4.0 和更新版本的設定參數（稱為 [智慧升級]），如下表所示。 如果您要從其他版本的 AGPM 升級到 AGPM 4.0 SP3 （如下表所示），您必須使用 [傳統升級]，這需要您重新輸入配置參數。 由於每個版本的 AGPM 都與特定的作業系統相關聯，請參閱[選擇要安裝的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，並確認您在升級 AGPM 之前，請先升級您的作業系統。

**AGPM 4.0 SP3 支援的升級**

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>您可以升級的 AGPM 版本</strong></p></td>
<td align="left"><p><strong>2.5</strong></p></td>
<td align="left"><p><strong>3.0</strong></p></td>
<td align="left"><p><strong>4.0</strong></p></td>
<td align="left"><p><strong>4.0 SP1</strong></p></td>
<td align="left"><p><strong>4.0 SP2</strong></p></td>
<td align="left"><p><strong>4.0 SP3</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>2.5</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>傳統升級</p></td>
<td align="left"><p>傳統升級</p></td>
<td align="left"><p>安裝遭到封鎖</p></td>
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
<td align="left"><p>安裝遭到封鎖</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>智慧升級</p></td>
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
<td align="left"><p>智慧升級</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0 SP2</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>智慧升級</p></td>
</tr>
</tbody>
</table>

 

## 支援的設定


AGPM 4.0 SP3 支援下表中的配置。 雖然 AGPM 支援混合式設定，但我們強烈建議您在相同的作業系統線路上執行 AGPM 用戶端和 AGPM 服務器，例如，Windows10 Windows Server 2016、Windows 8.1 Server 2012 R2 等。

**AGPM 4.0 SP3 支援的作業系統與原則設定**

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
<td align="left"><p>Windows Server 2016 或 Windows 10</p></td>
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>不支援</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法報告或編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</p></td>
</tr>
</tbody>
</table>

 

## 安裝 AGPM 4.0 SP3 的先決條件

下表說明當 .NET Framework 4.5.1、PowerShell 3.0 或遠端伺服器管理工具中的 GPMC 遺失時，AGPM 4.0 SP3 用戶端和伺服器安裝程式的行為。

| AGPM 用戶端            |                                                                                                 |                                                                            | AGPM 服務器                                                                     |                                                                                                 |                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| 作業系統       | .NET Framework                                                                                  | PowerShell                                                                 | 遠端伺服器管理工具                                              | .NET Framework                                                                                  | 遠端伺服器管理工具                                              |
| Windows 10             | 如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。 | 如果未安裝 Powershell 3.0，安裝程式會封鎖安裝。 | 如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。 | 如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。 | 如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。 |
| Windows 8.1            | 如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。 | 如果未安裝 Powershell 3.0，安裝程式會封鎖安裝。 | 如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。 | 如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。 | 如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。 |
| WindowsServer 2012 R2 | 如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。 | 如果未安裝 Powershell 3.0，安裝程式會封鎖安裝。 | 如果未啟用 GPMC，安裝程式會在安裝期間啟用它。   | 如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。 | 如果未啟用 GPMC，安裝程式會在安裝期間啟用它。   |

 

## 如何取得 MDOP 技術


AGPM 4.0 SP3 是您自 MDOP 2015 之後的 Microsoft 桌面優化套件（MDOP）的一部分。 MDOP 是 Microsoft 軟體保證的一部分。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相關主題


[進階群組原則管理](index.md)

[Microsoft 進階群組原則管理 4.0 SP3 版本資訊](release-notes-for-microsoft-advanced-group-policy-management-40-sp3.md)

[選擇要安裝的 AGPM 版本](choosing-which-version-of-agpm-to-install.md)

 

 





