---
title: 選擇要安裝的 AGPM 版本
description: 選擇要安裝的 AGPM 版本
author: dansimp
ms.assetid: 31357d2a-bc23-4e15-93f4-0beda8ab7a7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/05/2017
ms.openlocfilehash: f8a69fb323d9f47c5b906ac3abc6ec59376ee6f7
ms.sourcegitcommit: 0a7dee11289780336d9c24ebbf27c5c1ffee441c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "10905600"
---
# 選擇要安裝的 AGPM 版本


每個版本的 MicrosoftAdvanced 群組原則管理 (AGPM) 都支援特定版本的 Windows 作業系統。 我們強烈建議您在相同的作業系統行上執行 AGPM 用戶端和 AGPM 服務器。 例如，windows 10 與 Windows Server 2016、Windows 8.1 （含 Windows Server2012 R2）等等。

我們建議您在網域中的最新版本的作業系統上安裝 AGPM 服務器。 AGPM 使用群組原則管理主控台 (GPMC) 來備份及還原 (Gpo) 的群組原則物件。 因為更新版本的 GPMC 提供其他不在舊版中提供的原則設定，您可以使用最新版本的作業系統來管理更多原則設定。

所有版本的 AGPM 只能管理在運行 AGPM 的相同版本或舊版作業系統中所引進的原則設定。 例如，如果您在 Windows Server 2012 上安裝了 AGPM 4.0 SP2，您可以管理在 Windows Server 2012 或較舊版本中推出的原則設定，但您無法管理稍後在 Windows 8.1 或 Windows Server2012 R2 中推出的原則設定。

如果您的 AGPM 服務器上的 GPMC 版本比管理員用來管理群組原則之電腦上的版本舊，則 AGPM 服務器將無法儲存不在舊版 GPMC 中的任何原則設定。 如需 Windows 中隨附的群組原則設定試算表，請參閱[適用於 Windows 和 Windows Server 的群組原則設定參考](https://go.microsoft.com/fwlink/p/?LinkId=613627)。

## AGPM 4.0 SP3


如果您使用執行 Windows 10 的電腦來管理 Gpo，您必須使用 AGPM 4.0 SP3。 您無法在執行 Windows 10 作業系統的電腦上安裝舊版的 AGPM。

表格1列出您可以安裝 AGPM 4.0 SP3 的作業系統，以及您可以使用 AGPM 4.0 SP3 管理的原則設定。

**表格1： AGPM 4.0 SP3 支援的作業系統與原則設定**

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
<td align="left"><p>Windows Server 2019 或 Windows 10</p></td>
<td align="left"><p>Windows Server 2019 或 Windows 10</p></td>
<td align="left"><p>支援</p></td>
</tr>
 <tr class="even">
<td align="left"><p>Windows Server 2019 或 Windows 10</p></td>
<td align="left"><p>Windows Server 2019 或 Windows 10</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="edd">
<td align="left"><p>Windows Server2012 R2</p></td>
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>支援 KB 4015786 中所述的注意事項 <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)"></a>
</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server2012 R2 或 Windows 8。1</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 WindowsVista Service Pack 1 (SP1) </p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</p></td>
<td align="left"><p>不支援</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法報告或編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 SP2


如果您使用的電腦執行的是 Windows Server2012 R2 或 Windows 8.1 來管理 Gpo，您必須使用 AGPM 4.0 SP2。 您無法在執行這些作業系統的電腦上安裝舊版的 AGPM。

表格1列出您可以安裝 AGPM 4.0 SP2 的作業系統，以及您可以使用 AGPM 4.0 SP2 管理的原則設定。

**表格2： AGPM 4.0 SP2 支援的作業系統與原則設定**

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
<td align="left"><p>Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>Windows Server 2012 或 Windows 8。1</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 WindowsVista Service Pack 1 (SP1) </p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>不支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法報告或編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 SP1


表格2列出您可以安裝 AGPM 4.0 SP1 的作業系統，以及可使用 AGPM 4.0 SP1 管理的原則設定。

**表格3： AGPM 4.0 SP1 支援的作業系統與原則設定**

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
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows 8.1 的原則設定或喜好設定專案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法編輯只有在 Windows Server2008R2 或 Windows7 中存在的原則設定或喜好設定專案</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法報告或編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4。0


表格3列出您可以安裝 AGPM 4.0 的作業系統，以及可使用 AGPM 4.0 管理的原則設定。

**資料表4： AGPM 4.0 支援的作業系統與原則設定**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">AGPM 服務器支援的作業系統</th>
<th align="left">適用于 AGPM 用戶端的支援作業系統</th>
<th align="left">AGPM 支援</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>不支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法報告或編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</p></td>
</tr>
</tbody>
</table>

 

## 在 AGPM 4.0 之前的 AGPM 版本


資料表4列出您可以在其中安裝 agpm 4.0 之前的 AGPM 版本的作業系統。 如果沒有列出作業系統，您就無法在該作業系統上安裝 AGPM。

**表5：在 AGPM 4.0 之前的 AGPM 版本支援的作業系統**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">可安裝的 AGPM 版本</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>3.0</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista （含 SP1）</p></td>
<td align="left"><p>3.0</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WindowsVista 沒有安裝 service pack (32 位) </p></td>
<td align="left"><p>2.5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 (32 位) </p></td>
<td align="left"><p>2.5</p></td>
</tr>
</tbody>
</table>

 

## 如何取得 MDOP 技術


AGPM 4.0 SP2 是 Microsoft 桌面優化套件 (MDOP) 的一部分。 MDOP 是 Microsoft 軟體保證的一部分。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相關主題


[進階群組原則管理](index.md)

 

 





