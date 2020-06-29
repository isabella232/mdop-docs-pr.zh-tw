---
title: 規劃要與 UE-V 1.0 同步處理的應用程式
description: 規劃要與 UE-V 1.0 同步處理的應用程式
author: dansimp
ms.assetid: c718274f-87b4-47f3-8ef7-5e1bd5557a9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f2b04942588d0f6efad03d5e0249534cd325c09
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800088"
---
# 規劃要與 UE-V 1.0 同步處理的應用程式


Microsoft 使用者體驗虛擬化（UE-V）使用設定位置範本（XML 檔案）來定義由 UE-V 捕獲並套用的設定。 UE-V 包含一組預先定義的設定位置範本，也可讓系統管理員為在企業中使用的協力廠商或商務用端應用程式建立自訂設定位置範本。

如果您是系統管理員，當您認為要在 UE-V 方案中包含哪些應用程式時，請考慮使用者可以自訂哪些設定，以及應用程式儲存其設定的方式和位置。 並非所有應用程式都有可自訂或經常由使用者自訂的設定。 此外，並非所有應用程式設定都能安全地跨多部電腦或環境進行漫遊。 同步處理符合下列準則的設定：

-   儲存在使用者可存取位置的設定。 例如，請勿同步處理在 system32 或在 registry 的 [在 HKCU 中] 區段中儲存的設定。

-   特定電腦不專用的設定。 例如，排除網路或硬體設定。

-   可以在電腦之間同步處理的設定，不會造成資料損毀的風險。 例如，請勿使用儲存在資料庫檔案中的設定。

## UE-V 提供的設定位置範本


**UE-V 應用程式設定位置範本**

UE-V agent 安裝軟體會安裝代理程式，並為常見的 Microsoft 應用程式登錄預設的設定位置範本組。 這些設定位置範本會捕獲下列應用程式的設定值：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>應用程式類別</strong></th>
<th align="left"><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Office 2010 應用程式</p></td>
<td align="left"><p>Microsoft Word 2010</p>
<p>Microsoft Excel 2010</p>
<p>Microsoft Outlook 2010</p>
<p>Microsoft Access 2010</p>
<p>Microsoft Project 2010</p>
<p>Microsoft PowerPoint 2010</p>
<p>Microsoft Publisher 2010</p>
<p>Microsoft Visio 2010</p>
<p>Microsoft SharePoint Workspace 2010</p>
<p>Microsoft InfoPath 2010</p>
<p>Microsoft Lync 2010</p>
<p>Microsoft OneNote 2010</p></td>
</tr>
<tr class="even">
<td align="left"><p>瀏覽器選項（Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10）</p></td>
<td align="left"><p>[我的最愛]、[首頁]、[定位點] 和工具列</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 附件</p></td>
<td align="left"><p>[計算機]、[記事本]、[寫字板]。</p></td>
</tr>
</tbody>
</table>

 

當應用程式啟動時，應用程式設定會套用到應用程式。 當應用程式關閉時，就會儲存這些專案。

**UE-V Windows 設定位置範本**

使用者體驗虛擬化包括設定位置範本，可捕獲下列 Windows 設定的設定值：

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows 設定</th>
<th align="left">描述</th>
<th align="left">適用</th>
<th align="left">預設狀態</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>桌面背景</p></td>
<td align="left"><p>目前處於作用中桌面的背景。</p></td>
<td align="left"><p>登入、解除鎖定、遠端連線。</p></td>
<td align="left"><p>啟用</p></td>
</tr>
<tr class="even">
<td align="left"><p>輕鬆存取</p></td>
<td align="left"><p>[協助工具] 和 [輸入設定]、[放大鏡]、[朗讀程式] 和螢幕小鍵盤。</p></td>
<td align="left"><p>登入、解除鎖定、遠端連線。</p></td>
<td align="left"><p>停用</p></td>
</tr>
<tr class="odd">
<td align="left"><p>桌面設定</p></td>
<td align="left"><p>[開始] 功能表和工作列設定、[資料夾選項]、[預設桌面圖示]、[其他時鐘] 和 [地區及語言設定]。</p></td>
<td align="left"><p>僅限登入。</p></td>
<td align="left"><p>停用</p></td>
</tr>
</tbody>
</table>

 

當使用者登入時、電腦已解除鎖定，或遠端連線至其他電腦時，就會套用 Windows 桌面背景和 [輕鬆存取] 設定。 當使用者登出、電腦鎖定時，或當遠端連線中斷時，agent 會儲存這些設定。 根據預設，Windows 桌面背景設定是在相同作業系統版本的電腦之間漫遊。

Windows 桌面和 [輕鬆存取] 設定會在登入桌面之後套用至使用者。 若要優化登入體驗，預設不會漫遊這些設定。 您可以使用群組原則、PowerShell 及 WMI 來啟用 [桌面] 和 [輕鬆存取] 設定。

UE-V 不支援在不同語言的作業系統之間漫遊設定。 例如，不支援英文與德文之間的同步處理。 UE-V 漫遊使用者設定必須符合的所有電腦的語言。

**記事** 如果您變更 Microsoft 所提供的設定位置範本，使用者體驗虛擬化可能無法針對指定的應用程式或 Windows 設定群組正常運作。

 

## <a href="" id="prevent-unintentional-user-settings-configuration-"></a>防止無意間的使用者設定設定


使用者體驗虛擬化會檢查新的使用者設定資訊，並從設定儲存位置下載該資訊。 然後，在下列情況下，它會將設定套用到本機電腦：

-   每次啟動應用程式時，都會有已註冊的 UE-V 範本。

-   當使用者登入電腦時。

-   當使用者解除鎖定電腦時。

-   在已安裝 UE-V 的遠端桌面電腦建立連線時。

如果 UE-V 是安裝在電腦 A 和電腦 B 上，且應用程式所需的設定是在電腦 A 上，那麼電腦 A 必須先開啟並關閉應用程式。 如果應用程式先于電腦 B 開啟和關閉，則電腦 A 上的應用程式設定將會設定為與電腦 B 上的應用程式設定相同。

此案例也適用于 Windows 設定。 如果電腦 B 上的 Windows 設定應該與電腦 A 上的 Windows 設定相同，則使用者必須先登入和登出電腦 A。

如果以錯誤的順序套用所需的使用者設定，就可以在重寫設定的電腦上，針對特定的應用程式或 Windows 設定執行還原作業來復原這些設定。 如需詳細資訊，請參閱[還原與 ue-v 1.0 同步處理的應用程式和 Windows 設定](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)。

## 自訂 UE-V 設定位置範本


您可以使用 UE-V 發生器來建立自訂設定位置範本。 在測試環境中建立並測試自訂設定位置範本之後，您可以將設定位置範本部署到企業中的電腦。 自訂設定位置範本必須使用現有的部署基礎結構（例如企業軟體發佈（ESD）方法）及喜好設定，或設定 UE-V 設定範本目錄來部署。 使用 [ESD] 或 [群組原則] 部署的範本，必須使用 UE-V WMI 或 PowerShell 進行註冊。 如需自訂設定位置範本的詳細資訊，請參閱[規劃 ue-v 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

如需有關企業相關應用程式是否應進行同步處理的指導方針，請參閱[評估 ue-v 1.0 的商務用行應用程式的檢查清單](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md)。

## 相關主題


[為 UE-V 1.0 進行規劃](planning-for-ue-v-10.md)

[規劃 UE-V 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)

[部署 UE-V 1.0](deploying-ue-v-10.md)

 

 





