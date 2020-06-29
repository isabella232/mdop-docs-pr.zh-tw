---
title: 使用群組原則物件設定 UE-V 2. x
description: 使用群組原則物件設定 UE-V 2. x
author: dansimp
ms.assetid: 2bb55834-26ee-4f19-9860-dfdf3c797143
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bdff63b948752b9bec83e77e275f1cb20a384463
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810545"
---
# 使用群組原則物件設定 UE-V 2. x


部分 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 群組原則設定可為電腦定義，而其他群組原則設定則可以為使用者定義。 如需如何安裝 UE-V 群組原則 ADMX 檔案的相關資訊，請參閱[安裝 ue-v 2 群組原則 Admx 範本](https://technet.microsoft.com/library/dn458891.aspx#admx)。

您可以針對 UE-V 設定下列原則設定。

**群組原則設定**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">群組原則設定名稱</th>
<th align="left">Target</th>
<th align="left">群組原則設定描述</th>
<th align="left">設定選項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>聯繫 IT 連結文字</p></td>
<td align="left"><p>僅限電腦</p></td>
<td align="left"><p>這個群組原則設定會指定公司設定中心中的 [連絡人 IT URL] 超連結的文字。</p></td>
<td align="left"><p>如果您啟用此群組原則設定，[公司設定中心] 會在連結中顯示指定的文字，以取得連絡人的連絡人 URL。</p></td>
</tr>
<tr class="even">
<td align="left"><p>聯繫 IT URL</p></td>
<td align="left"><p>僅限電腦</p></td>
<td align="left"><p>這個群組原則設定會指定 [公司設定] 中心中的 [連絡人 IT] 連結的 URL。</p></td>
<td align="left"><p>如果您啟用此設定，公司設定中心就會與它相關的文字連結至指定的 URL。 連結可以是任何標準通訊協定，例如 HTTP 或 mailto。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>請勿使用同步處理提供者</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>您可以使用此群組原則設定，設定 UE-V 是否使用同步處理提供程式功能。 您也可以使用此原則設定，讓您在使用者的匯入設定延遲時，顯示通知。</p></td>
<td align="left"><p>啟用此設定以設定 UE-V Agent 不使用同步處理提供者。</p></td>
</tr>
<tr class="even">
<td align="left"><p>第一次使用通知</p></td>
<td align="left"><p>僅限電腦</p></td>
<td align="left"><p>這個群組原則設定可讓您在 UE-V 時顯示的通知區域中的通知</p>
<p>代理程式第一次執行。</p></td>
<td align="left"><p>預設值為 [已啟用]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>漫遊 Windows 設定</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>這個群組原則設定會配置 Windows 設定的同步處理。</p></td>
<td align="left"><p>選取 [在電腦之間同步處理的 Windows 設定]。</p>
<p>根據預設，Windows 主題、[桌面設定] 和 [輕鬆存取設定] 會在相同作業系統版本的電腦之間同步處理設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定套件大小警告閾值</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定可讓您設定 UE-V Agent 在設定套件檔案大小達到已定義的閾值時進行報告。</p></td>
<td align="left"><p>指定設定套件大小的喜好閾值（KB）。</p>
<p>根據預設，UE-V Agent 沒有套件檔案大小閾值。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定儲存路徑</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>這個群組原則設定會配置要儲存使用者設定的位置。</p></td>
<td align="left"><p>輸入通用命名慣例（UNC）路徑和變數，例如 \Server\SettingsShare%username%。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定範本目錄路徑</p></td>
<td align="left"><p>僅限電腦</p></td>
<td align="left"><p>這個群組原則設定會配置自訂設定位置範本的儲存位置。 此原則設定也會配置是否要使用目錄來取代與 UE-V Agent 一起安裝的預設 Microsoft 範本。</p></td>
<td align="left"><p>在電腦上輸入通用命名慣例（UNC）路徑，例如 \Server\TemplateShare 或資料夾位置。</p>
<p>選取要取代預設 Microsoft 範本的核取方塊。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在計量付費連線上同步處理設定</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定會定義 UE-V 是否要同步處理通過計量付費連線的設定。</p></td>
<td align="left"><p>根據預設，UE-V Agent 不會在計量付費連線上同步處理設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>即使在漫遊時也能在計量付費連線上同步處理設定</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>這個群組原則設定會定義 UE-V 是否與家用提供者網路以外的計量付費連線同步處理設定，例如，當資料連線處於漫遊模式時。</p></td>
<td align="left"><p>根據預設，UE-V 不會在處於漫遊模式時，透過計量付費連線同步處理設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步處理超時</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>這個群組原則設定會設定電腦從遠端設定位置中檢索使用者設定時，等待超時的毫秒數。 如果遠端儲存位置無法使用，且使用者不使用同步處理提供者，應用程式的啟動會延遲數毫秒。</p></td>
<td align="left"><p>指定最佳同步處理超時（以毫秒為單位）。 預設值為2000毫秒。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[工作列] 圖示</p></td>
<td align="left"><p>僅限電腦</p></td>
<td align="left"><p>此群組原則設定會啟用使用者體驗虛擬化（UE-V）工作列圖示。</p></td>
<td align="left"><p>預設值為 [已啟用]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用使用者體驗虛擬化（UE-V）</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>這個 [群組原則] 設定可讓您啟用或停用使用者體驗虛擬化（UE-V）。</p></td>
<td align="left"><p>啟用或停用此群組原則設定。</p></td>
</tr>
</tbody>
</table>

 

**記事** 此外，有許多桌面應用程式和 Windows 應用程式都可以使用群組原則設定。 您可以使用這些設定來啟用或停用特定應用程式的設定同步處理。

 

**Windows 應用程式群組原則設定**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">群組原則設定名稱</th>
<th align="left">Target</th>
<th align="left">群組原則設定描述</th>
<th align="left">設定選項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>不要同步處理 Windows 應用程式</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定會定義 UE-V Agent 是否同步處理 Windows 應用程式的設定。</p></td>
<td align="left"><p>預設是同步處理 Windows 應用程式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 應用程式清單</p></td>
<td align="left"><p>電腦與使用者</p></td>
<td align="left"><p>此設定會列出 Windows 應用程式的家庭套件名稱，並明確指出 UE-V 是否要同步處理該 app 的設定。</p></td>
<td align="left"><p>您可以使用這個設定來指定 app 的設定永遠不會由 UE-V 進行同步處理，即使已同步處理所有其他 Windows 應用程式的設定也一樣。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步未列出的 Windows 應用程式</p></td>
<td align="left"><p>電腦與使用者</p></td>
<td align="left"><p>這個群組原則設定會定義 windows 應用程式的 UE-V Agent 的預設設定同步處理行為，該 app 未明確列出在 Windows 應用程式清單中。</p></td>
<td align="left"><p>根據預設，UE-V Agent 只會同步處理包含在 Windows 應用程式清單中的那些 Windows 應用程式的設定。</p></td>
</tr>
</tbody>
</table>

 

如需有關同步處理 Windows 應用程式的詳細資訊，請參閱[Windows 應用程式清單](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

**設定以電腦為目標的群組原則設定**

1.  在電腦上使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM），作為網網域控制站，以管理 UE-V 電腦的群組原則設定。 流覽至 [**電腦**設定]，選取 [**原則**]，選取 [系統**管理範本**]，按一下 [ **Windows 元件**]，然後選取 [ **Microsoft 使用者體驗虛擬化**]。

2.  選取要編輯的 [群組原則] 設定。

**設定以使用者為目標的群組原則設定**

1.  在網網域控制站電腦上的 Microsoft 桌面優化套件（MDOP）中，使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）工具來管理 UE-V 的群組原則設定。 流覽至 [**使用者**設定]，選取 [**原則**]，選取 [系統**管理範本**]，按一下 [ **Windows 元件**]，然後選取 [ **Microsoft 使用者體驗虛擬化**]。

2.  選取已編輯的群組原則設定。

UE-V Agent 會使用下列優先順序順序來判斷同步處理。

**UE-V 設定的優先順序順序**

1.  由群組原則設定所管理的使用者設定目標設定-這些設定的設定會依群組原則儲存在登錄機碼中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

2.  由群組原則設定所管理的電腦設定目標設定-這些設定的設定會依群組原則儲存在登錄機碼中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

3.  由目前使用者使用 Windows PowerShell 或 Windows 管理工具（WMI）所定義的設定設定，這些設定設定是由 UE-V Agent 儲存在此登錄位置： `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` 。

4.  使用 Windows PowerShell 或 WMI 為電腦定義的配置設定。 UE-V Agent 會將這些設定設定儲存在此登錄位置： `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` 。

    **為 ue-v 提供建議**嗎？ 在[此](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)新增或投票建議。 是否**有 ue-v 問題**？ 使用[Ue-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。

## 相關主題


[管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)

[管理 UE-V 2.x 的設定](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





