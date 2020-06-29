---
title: 使用群組原則物件來設定 UE-V
description: 使用群組原則物件來設定 UE-V
author: dansimp
ms.assetid: 5c9be706-a05f-4397-9a38-e6b73ebff1e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e479e6bef1a2b38cf822ffca19ed4220b0c59fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811912"
---
# 使用群組原則物件來設定 UE-V


部分 Microsoft 使用者體驗虛擬化（UE-V）群組原則設定可以為電腦定義，而其他人可以為使用者定義。 UE-V agent 設定原則設定可以針對電腦或使用者進行定義。 如需如何安裝 UE-V 群組原則 ADMX 檔案的相關資訊，請參閱[安裝 Ue-v 群組原則 Admx 範本](installing-the-ue-v-group-policy-admx-templates.md)。

您可以針對 UE-V 設定下列原則設定：

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>原則設定名稱</strong></p></td>
<td align="left"><p><strong>Target</strong></p></td>
<td align="left"><p><strong>原則設定描述</strong></p></td>
<td align="left"><p><strong>設定選項</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>使用使用者體驗虛擬化（UE-V）</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此原則設定可讓您啟用或停用使用者體驗虛擬化（UE-V）。</p></td>
<td align="left"><p>啟用或停用此原則設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定儲存路徑</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此原則設定會配置將儲存使用者設定的位置。</p></td>
<td align="left"><p>提供通用命名慣例（UNC）路徑和變數，例如 \Server\SettingsShare%username%。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定範本目錄路徑</p></td>
<td align="left"><p>僅限電腦</p></td>
<td align="left"><p>此原則設定會配置自訂設定位置範本的儲存位置。 此原則設定也會配置是否要使用該目錄來取代與 UE-V agent 一起安裝的預設 Microsoft 範本。</p></td>
<td align="left"><p>提供通用命名慣例（UNC）路徑，例如 \Server\TemplateShare 或電腦上的資料夾位置。</p>
<p></p>
<p>選取要取代預設 Microsoft 範本的核取方塊。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>請勿使用離線檔案</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此原則設定可讓您設定 UE-V 是否會使用 Windows 離線檔案功能。 此原則設定也可讓您在 [匯入使用者設定] 延遲時啟用通知。</p></td>
<td align="left"><p>若要設定 UE-V Agent 不使用離線檔案，請啟用此設定。</p>
<p></p>
<p>指定當設定匯入延遲時，是否應給予通知。</p>
<p></p>
<p>指定通知出現前要等待的時間長度（以秒為單位）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>同步處理超時</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此原則設定會設定在從遠端設定位置檢索使用者設定時，電腦在超時之前等待的毫秒數。 如果 [遠端儲存位置] 無法使用，應用程式啟動會延遲數毫秒。</p></td>
<td align="left"><p>指定最佳同步處理超時（以毫秒為單位）。 2000毫秒的預設值。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>套件大小警告閾值</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此原則設定可讓您設定 UE-V agent 在設定套件檔案大小達到已定義的閾值時進行報告。</p></td>
<td align="left"><p>已指定設定套件大小的喜好閾值（以 kb 為單位）。</p>
<p>根據預設，UE-V agent 沒有套件檔案大小閾值。</p></td>
</tr>
<tr class="even">
<td align="left"><p>漫遊應用程式設定</p></td>
<td align="left"><p>僅限使用者</p></td>
<td align="left"><p>此原則設定會配置應用程式的使用者設定的漫遊。</p></td>
<td align="left"><p>選取哪些 Windows 設定將在電腦之間漫遊。</p>
<p>根據預設，由 UE-V 提供的應用程式的使用者設定範本是在電腦之間漫遊。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>漫遊 Windows 設定</p></td>
<td align="left"><p>僅限使用者</p></td>
<td align="left"><p>此原則設定會配置 Windows 設定的漫遊。</p></td>
<td align="left"><p>選取哪些應用程式將在電腦之間漫遊。</p>
<p>根據預設，Windows 主題是在相同作業系統版本的電腦之間漫遊。 Windows 桌面設定和 [輕鬆存取] 設定不是漫遊。</p></td>
</tr>
</tbody>
</table>

 

**設定以電腦為目標的原則**

1.  在管理 UE-V 電腦之群組原則的網網域控制站電腦上，使用 [群組原則管理主控台] （GPMC）或 [高級群組原則管理] （AGPM）。 流覽至 [**電腦**設定]，選取 [**原則**]，選取 [系統**管理範本**]，按一下 [ **Windows 元件**]，然後選取 [ **Microsoft 使用者體驗虛擬化**]。

2.  選取要編輯的原則設定。

**設定以使用者為目標的原則**

1.  在管理 UE-V 的群組原則之網網域控制站電腦上，使用 [群組原則管理主控台（GPMC）] 或 [高級群組原則管理（AGPM）] 工具，在 Microsoft 桌面優化套件（MDOP）中進行。 流覽至 [**使用者**設定]，選取 [**原則**]，選取 [系統**管理範本**]，按一下 [ **Windows 元件**]，然後選取 [ **Microsoft 使用者體驗虛擬化**]。

2.  選取已編輯的原則設定。

UE-V agent 會使用下列優先順序順序來判斷同步處理。

**UE-V 設定的優先順序順序**

1.  由群組原則管理的使用者設定目標設定-這些設定設定會依群組原則儲存在登錄機碼中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

2.  由群組原則管理的由電腦設定目標的設定-這些設定設定會依群組原則儲存在登錄機碼中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

3.  使用 PowerShell 或 WMI 的目前使用者所定義的配置設定，由 UE-V agent 儲存在此登錄位置： `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` 。

4.  使用 PowerShell 或 WMI 為電腦定義的配置設定。 這些設定的設定是由 UE-V agent 儲存在 `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration` 。

## 相關主題


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 作業](operations-for-ue-v-10.md)

 

 





