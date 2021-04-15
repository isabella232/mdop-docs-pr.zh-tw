---
title: 使用群組原則物件來配置 UE-V 2.x
description: 使用群組原則物件來配置 UE-V 2.x
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
ms.openlocfilehash: b6c9636df36a53cbf65bf1904965f2809484b99c
ms.sourcegitcommit: bdc377477a8cc9e973fbcdd67c2f07b882c5d61e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "11494058"
---
# <a name="configuring-ue-v-2x-with-group-policy-objects"></a>使用群組原則物件來配置 UE-V 2.x


某些 Microsoft 使用者體驗虛擬化 (UE-V) 2.0、2.1 和 2.1 SP1 群組原則設定可以定義電腦，也可以定義其他群組原則設定給使用者。 若要瞭解如何安裝 UE-V 群組原則 ADMX 檔案，請參閱安裝 [UE-V 2 群組原則 ADMX 範本](https://technet.microsoft.com/library/dn458891.aspx#admx)。

您可以針對 UE-V 設定下列策略設定。

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
<td align="left"><p>設定同步處理方法</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>您可以使用此群組原則設定來設定使用者體驗虛擬化 (UE-V) 同步提供者功能。 此策略設定也可讓您在延遲使用者設定輸入時顯示通知。</p></td>
<td align="left"><p>啟用此設定以設定 UE-V 代理程式不使用同步處理提供者，或使用外部同步處理引擎。</p></td>
</tr>
<tr class="even">
<td align="left"><p>連上 IT 連結文字</p></td>
<td align="left"><p>僅適用于電腦</p></td>
<td align="left"><p>此群組原則設定會指定公司設定中心中連絡人 IT URL 超連結的文字。</p></td>
<td align="left"><p>如果您啟用此群組原則設定，公司設定中心會在連絡人 IT URL 的連結中顯示指定的文字。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>與 IT URL 聯繫</p></td>
<td align="left"><p>僅適用于電腦</p></td>
<td align="left"><p>此群組原則設定會指定公司設定中心中連絡人 IT 連結的 URL。</p></td>
<td align="left"><p>如果您啟用這項設定，公司設定中心會連至指定的 URL 連至 IT 文字。 連結可以是任何標準通訊協定，例如 HTTP 或 mailto。</p></td>
</tr>
<tr class="even">
<td align="left"><p>第一次使用通知</p></td>
<td align="left"><p>僅適用于電腦</p></td>
<td align="left"><p>此群組原則設定可在 UE-V 出現時，通知區域中顯示的通知</p>
<p>代理程式第一次執行。</p></td>
<td align="left"><p>預設為啟用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步之前，先 Ping 設定儲存位置</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此策略設定可讓 UE-V 同步處理提供者的設定在嘗試同步處理設定之前，先 ping 設定儲存路徑，以驗證連接。</p></td>
<td align="left"><p>啟用或停用此群組原則設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定套件大小警告閾值</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定可讓您設定 UE-V Agent，以在設定套件檔案大小達到定義的臨界值時報告。</p></td>
<td align="left"><p>指定以 KB 為單位設定套件大小 (閾值) 。</p>
<p>根據預設，UE-V Agent 沒有封裝檔案大小閾值。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定儲存路徑</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定會設定要儲存使用者設定的位置。</p></td>
<td align="left"><p>在 UNC 中輸入通用命名慣例 (UNC) 路徑和變數，例如 \Server\SettingsShare%username%%。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定範本目錄路徑</p></td>
<td align="left"><p>僅適用于電腦</p></td>
<td align="left"><p>此群組原則設定會設定自訂設定位置範本的儲存位置。 此策略設定也會設定是否要使用目錄取代以 UE-V Agent 安裝的預設 Microsoft 範本。</p></td>
<td align="left"><p>在 UNC 路徑中 (通用) ，例如 \Server\TemplateShare 或電腦中的資料夾位置。</p>
<p>選取核取方塊以取代預設的 Microsoft 範本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在計量計費的連接上同步設定</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定會定義 UE-V 是否以計量計費連接同步設定。</p></td>
<td align="left"><p>根據預設，UE-V Agent 不會以計量計費連接同步設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>即使漫遊時，也使用計量計費連接同步設定</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定會定義 UE-V 是否同步處理家用提供者網路外部的計量計費連接設定，例如資料連線在漫遊模式中時。</p></td>
<td align="left"><p>根據預設，UE-V 不會在漫遊模式中，以計量計費連接同步設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步處理超時</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定會設定電腦在從遠端設定位置中取回使用者設定時，在延遲前等待的毫秒數。 如果遠端儲存位置無法使用，且使用者不使用同步處理提供者，應用程式啟動會延遲這麼多毫秒。</p></td>
<td align="left"><p>指定偏好的同步處理時間，以毫秒為單位。 預設值為 2000 毫秒。</p></td>
</tr>
<tr class="even">
<td align="left"><p>同步 Windows 設定 </p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定會設定 Windows 設定同步處理。</p></td>
<td align="left"><p>選取電腦之間同步的 Windows 設定。</p>
<p>根據預設，Windows 主題、桌面設定和輕鬆存取設定會同步設定于相同作業系統版本的電腦之間。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>工作列圖示</p></td>
<td align="left"><p>僅適用于電腦</p></td>
<td align="left"><p>此群組原則設定會啟用 UE-V 工作列圖示。</p></td>
<td align="left"><p>預設為啟用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用使用者體驗虛擬化 (UE-V) </p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定可讓您啟用或停用 UE-V。</p></td>
<td align="left"><p>啟用或停用此群組原則設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VDI 組組</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此策略設定會針對在集中式 VDI 環境中執行的電腦設定 UE-V 卷回信息的同步處理。 如果啟用此策略，UE-V 復原狀態會複製到登出時設定儲存位置，登入時還原。</p></td>
<td align="left"><p>啟用或停用此群組原則設定。</p></td>
</tr>
</tbody>
</table>

 

**注意**  
此外，許多桌面應用程式和 Windows 應用程式都提供群組原則設定。 您可以使用這些設定來啟用或停用特定應用程式的設定同步處理。

 

**Windows App 群組原則設定**

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
<td align="left"><p>請勿同步 Windows App</p></td>
<td align="left"><p>電腦和使用者</p></td>
<td align="left"><p>此群組原則設定會定義 UE-V Agent 是否同步 Windows 應用程式的設定。</p></td>
<td align="left"><p>預設為同步 Windows App。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 應用程式清單</p></td>
<td align="left"><p>電腦與使用者</p></td>
<td align="left"><p>此設定會列出 Windows App 的家庭套件名稱，並明確列出 UE-V 是否同步處理該應用程式的設定。</p></td>
<td align="left"><p>您可以使用此設定來指定應用程式設定永遠不會由 UE-V 同步，即使所有其他 Windows 應用程式的設定已同步。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步未列出的 Windows App</p></td>
<td align="left"><p>電腦與使用者</p></td>
<td align="left"><p>此群組原則設定會定義 Windows App 清單中未明確列出的 Windows App UE-V Agent 的預設設定同步處理行為。</p></td>
<td align="left"><p>根據預設，UE-V Agent 只會同步顯示于 Windows 應用程式清單中的 Windows App 設定。</p></td>
</tr>
</tbody>
</table>

 

有關同步化 Windows 應用程式的資訊，請參閱 [Windows 應用程式清單](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

**設定電腦目標群組策略設定**

1.  在做為網域控制站的電腦上，使用群組原則管理主控台 (GPMC) 或進位群組原則管理 (AGPM) 來管理 UE-V 電腦的群組原則設定。 流覽至 **電腦群組**組，選取 [ **策略**>、選取 **[系統管理範本**>、按一下 **[Windows 元件**，然後選取 **Microsoft 使用者體驗虛擬化**>。

2.  選取要編輯的群組原則設定。

**設定使用者目標群組策略設定**

1.  使用網域控制站電腦上 Microsoft 桌面優化套件 (MDOP) 中的群組原則管理主控台 (GPMC) 或進位群組原則管理 (AGPM) 工具來管理 UE-V 的群組原則設定。 流覽至 **[使用者組**配置>、選取 [ **策略**、 **選取系統管理範本**、按一下 **Windows 元件**，然後選取 Microsoft **使用者體驗虛擬化**。」。

2.  選取已編輯的群組原則設定。

UE-V Agent 會使用下列優先順序順序來決定同步處理。

**UE-V 設定優先順序順序**

1.  由群組原則設定管理的使用者目標設定 - 這些設定設定會依據群組原則儲存在登錄金鑰中，位於 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 下的群組原則。

2.  由群組原則設定管理的電腦目標設定 - 這些設定設定會依據群組原則儲存在登錄機碼中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` ，

3.  目前使用者使用 Windows PowerShell 或 Windows 管理工具 (WMI) 定義的設定設定 - 這些設定設定是由 UE-V Agent 在此登錄位置下儲存 `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` ：.

4.  使用 Windows PowerShell 或 WMI 為電腦定義的設定設定。 這些設定設定是由 UE-V Agent 在此註冊表位置下儲存： `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` .

    **有 UE-V 的建議嗎**？ 在這裡新增或投票支援 [建議](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)。 **有 UE-V 問題嗎**？ 使用 [UE-V TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。

## <a name="related-topics"></a>相關主題


[管理 UE-V 2.x](administering-ue-v-2x-new-uevv2.md)

[管理 UE-V 2.x 的設定](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 
