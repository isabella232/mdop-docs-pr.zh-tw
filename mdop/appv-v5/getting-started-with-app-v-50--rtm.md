---
title: App-V 5.0 入門
description: App-V 5.0 入門
author: dansimp
ms.assetid: 3e16eafb-ce95-4d06-b214-fe0f4b1b495f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a7979c81b7b57107f824b96d9fef8049a00c5b08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800622"
---
# App-V 5.0 入門


App-V 5.0 可讓系統管理員根據需要，在即時部署、更新及支援應用程式。 個別的應用程式是從本機安裝的產品轉換成集中管理的服務，且無論您在哪裡，都能隨時隨地存取，而不需要預先設定電腦或變更作業系統設定。

App-v 包含下列元素：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元素</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 管理伺服器</p></td>
<td align="left"><ul>
<li><p>提供管理 App-v 基礎結構的中央位置，這會將虛擬應用程式提供給 App-v Desktop 用戶端和遠端桌面服務（舊稱終端服務）用戶端。</p></li>
<li><p>針對其資料存放區使用 Microsoft SQL Server®，其中一個或多個 App-v 管理伺服器可以共用單一的 SQL Server 資料存放區。</p></li>
<li><p>驗證要求並提供安全性、測定、監視及資料收集。 伺服器使用 Active Directory 和支援工具來管理使用者和應用程式。</p></li>
<li><p>具有 Silverlight®的管理網站，可讓您從任何電腦設定 App-v 基礎結構。 您可以新增及移除應用程式、操縱快速鍵、指派存取權限給使用者和群組，以及建立連線群組。</p></li>
<li><p>啟用 App-v Web 管理主控台與 SQL Server 資料存放區之間的通訊。 這些元件都可以安裝在單一伺服器電腦或一或多個不同的電腦上，視所需的系統架構而定。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 發佈伺服器</p></td>
<td align="left"><ul>
<li><p>為特定使用者提供具有資格的應用程式的 App-v 用戶端</p></li>
<li><p>承載用於流式處理的虛擬應用程式套件。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v Desktop 用戶端</p></td>
<td align="left"><ul>
<li><p>檢索虛擬應用程式</p></li>
<li><p>在用戶端發佈應用程式</p></li>
<li><p>在 Windows 端點上的執行時間自動設定及管理虛擬環境。</p></li>
<li><p>在每個使用者&#39;s 設定檔中儲存使用者特定的虛擬應用程式設定，例如登錄和檔案變更。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 遠端桌面服務（RDS）用戶端</p></td>
<td align="left"><p>啟用遠端桌面工作階段主機伺服器，以使用 App-v Desktop 用戶端的共用桌面會話功能。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><ul>
<li><p>是您用來將傳統應用程式轉換成虛擬應用程式的嚮導工具。</p></li>
<li><p>產生應用程式 "套件"，其中包含：</p>
<ol>
<li><p>已排序的應用程式（APPV）檔案</p></li>
<li><p>可部署至針對獨立作業設定之用戶端的 Windows Installer 檔案（MSI）</p></li>
<li><p>幾個 XML 檔案，包括 Report.XML、PackageName_DeploymentConfig.XML 及 PackageName_UserConfig.XML。 UserConfig 和 DeploymentConfig XML 檔案是用來將自訂變更設定為套件的預設行為。</p></li>
</ol></li>
</ul></td>
</tr>
</tbody>
</table>

 

如需這些元素的詳細資訊，請參閱[app-v 5.0 的高層次架構](high-level-architecture-for-app-v-50.md)。

如果您是本產品的新使用者，建議您仔細閱讀檔。 在您將它部署到生產環境之前，我們也建議您在測試網路環境中驗證您的部署規劃。 您也可以考慮參與相關技術的課程。 如需 Microsoft 訓練商機的詳細資訊，請參閱 Microsoft 訓練概覽 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。

**記事** 此系統管理員指南的可下載版本無法使用。 不過，您可以瞭解 TechNet 文件庫的特殊模式，讓您選取文章、將其群組在集合中，或在 <https://go.microsoft.com/fwlink/?LinkId=272491> （ https://go.microsoft.com/fwlink/?LinkId=272491) 。

 

App-V 5.0 系統管理員指南的本節包含 App-V 5.0 的高層資訊，讓您在開始進行部署規劃之前先對產品有基本的瞭解。

## App 快速入門-V 5。0


-   [關於 App-V 5.0](about-app-v-50.md)

    提供 App-V 5.0 的高層概覽，以及如何在您的組織中使用它。

-   [關於 App-V 5.0 SP1](about-app-v-50-sp1.md)

    提供 App-V 5.0 SP1 以及它在您組織中的使用方式的高層次概覽。

-   [關於 App-V 5.0 SP2](about-app-v-50-sp2.md)

    提供 App-V 5.0 SP2 以及它在您組織中的使用方式的高層次概覽。

-   [關於 App-V 5.0 SP3](about-app-v-50-sp3.md)

    提供 App-V 5.0 SP2 以及它在您組織中的使用方式的高層次概覽。

-   [評估 App-V 5.0](evaluating-app-v-50.md)

    提供關於您在組織中使用 App-v 5.0 的最佳評估方式的相關資訊。

-   [App-V 5.0 的高階架構](high-level-architecture-for-app-v-50.md)

    提供應用程式 V 5.0 功能的說明，以及它們如何共同運作。

-   [App-V 5.0 的協助工具](accessibility-for-app-v-50.md)

    提供有關讓殘障人士更容易存取本產品及其對應檔的功能與服務的相關資訊。

## <a href="" id="other-resources-for-this-product-"></a>此產品的其他資源


-   [Microsoft Application Virtualization 5.0 系統管理員指南](microsoft-application-virtualization-50-administrators-guide.md)

-   [為 App-V 5.0 進行規劃](planning-for-app-v-50-rc.md)

-   [部署 App-V 5.0](deploying-app-v-50.md)

-   [App-V 5.0 作業](operations-for-app-v-50.md)

-   [疑難排解 App-V 5.0](troubleshooting-app-v-50.md)






 

 





