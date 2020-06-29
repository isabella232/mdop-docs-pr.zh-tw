---
title: 從舊版移轉
description: 從舊版移轉
author: dansimp
ms.assetid: a13cd353-b22a-48f7-af1e-5d54ede2a7e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a05bbd498cdb77a1ddf694b1aab6aeb42124775b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800373"
---
# 從舊版移轉


借助 App-V 5.0，您可以將現有的 App-v 4.6 基礎結構遷移至更具彈性、整合且更輕鬆管理的 App-v 5.0 基礎結構。

規劃您的遷移策略時，請考慮下列各節：

**記事** 如需 App-v 4.6 與 App-v 5.0 之間差異的詳細資訊，請參閱[關於 app-v 5.0](about-app-v-50.md)的**app-v 4.6 與 app-v 5.0 區段之間的差異**。

 

## 轉換使用舊版 App-v （V）建立的套件


使用套件轉換器實用程式來升級使用舊版 App-V 所建立的虛擬應用程式套件。 套件轉換器使用 PowerShell 來轉換套件，如果您有多個需要轉換的套件，就能協助自動處理常式。

**重要** 在您轉換現有的套件之後，您應該先測試套件，然後再部署套件，以確保轉換程式已成功完成。

 

**轉換現有套件前的須知事項**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">因應措施</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>不會轉換套件腳本。</p></td>
<td align="left"><p>測試已轉換的套件。 如有需要，請轉換腳本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>不會轉換套件註冊設定覆寫。</p></td>
<td align="left"><p>測試已轉換的套件。 如有需要，請重新新增登錄覆寫。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在轉換之後，使用 DSC 的虛擬套件不會連結。</p></td>
<td align="left"><p>使用連線群組連結封裝。 請參閱 <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)"> 管理連線群組 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在轉換期間偵測到環境變數衝突。</p></td>
<td align="left"><p>解決相關的 .osd 檔案中的任何衝突 <strong> </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在轉換期間檢測到硬編碼路徑。</p></td>
<td align="left"><p>硬編碼路徑難以正確轉換。 套件轉換器會檢測並傳回內含硬編碼路徑之檔案的套件。 使用硬編碼路徑來查看檔案，並判斷套件是否需要該檔案。 如果是，建議您重新排列套件。</p></td>
</tr>
</tbody>
</table>

 

轉換套件時，請檢查是否有失敗的檔案或快速鍵。 在 App-v 4.6 套件中找出該專案。 可能是硬式編碼路徑。 轉換路徑。

**記事** 建議您使用 App-v 5.0 sequencer 來轉換需要利用功能的重要應用程式或應用程式。 請參閱[如何使用 app-v 5.0 來排序新的應用程式](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)。

如果轉換後的套件未在轉換後開啟，建議您使用 App-v 5.0 排序器重新排序應用程式。

 

[如何轉換在舊版 App-V 中建立的套件](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

## 遷移用戶端


下表顯示升級用戶端的建議方法。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>將您的環境升級至 App-V 4.6 SP2</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">應用程式虛擬化部署和升級考慮 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>安裝 App-V 5.0 用戶端（含共存功能）。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)">如何在同一部電腦上部署 app-v 4.6 和 App-v 5.0 用戶端 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>順序及推出 app-v 5.0 套件。 視需要，取消發佈 App-v 4.6 套件。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.0](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)">如何使用 App-v 5.0 來排序新的應用程式 </a> 。</p></td>
</tr>
</tbody>
</table>

 

**重要** 您必須執行 App-V 4.6 SP3，才能使用共存模式。 此外，當您排列套件時，您必須設定 [管理機構] 設定（位於 **[使用者設定**] 中的 [**使用者**設定] 區段中）。

 

## 遷移 app-v 5.0 Server 的完整基礎結構


沒有直接的方法可升級至完整的 App-v 5.0 基礎結構。 請使用下一節中的資訊，以取得有關升級 App-v 伺服器的資訊。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>將您的環境升級到 App V 4.6 SP3。</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">應用程式虛擬化部署和升級考慮 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>部署 app-v 5.0 版本的用戶端。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)">如何部署 App-v 用戶端 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>安裝 App-V 5.0 server。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)">如何部署 app-v 5.0 伺服器 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[遷移現有的套件]。</p></td>
<td align="left"><p>請參閱本文中的 [ <strong> 使用先前版本的 app-v 建立的套件] </strong> 區段。</p></td>
</tr>
</tbody>
</table>

 

## 其他遷移任務


您也可以執行額外的遷移工作，例如重新配置端點，以及開啟在執行 App-v 5.0 用戶端的電腦上使用先前版本建立的套件。 下列連結提供執行這些工作的詳細資訊。

[如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.0 封裝](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

[如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.0](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

[如何為特定電腦上的所有使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[如何為特定使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-a-specific-user.md)







## 執行 App-v 遷移任務的其他資源


[App-V 5.0 作業](operations-for-app-v-50.md)

[簡化的 Microsoft App-v 5.1 管理伺服器升級程式](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





