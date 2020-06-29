---
title: 產生 MBAM 2.5 獨立報告
description: 產生 MBAM 2.5 獨立報告
author: dansimp
ms.assetid: 0ec623ff-5155-4906-aef2-20cdc0f84667
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: e1c6b33de26cce5d9ad8d20461dbe0ea0f138c78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809765"
---
# 產生 MBAM 2.5 獨立報告


當您將 Microsoft BitLocker 管理和監視（MBAM）設定為獨立拓朴時，您可以產生報告來監視 BitLocker 磁片磁碟機加密的使用方式及合規性。 本主題包含下列程式：

-   [開啟 [管理及監視] 網站](#bkmk-openadmin)

-   [產生企業合規性報告](#bkmk-enterprise)

-   [產生電腦合規性報告](#bkmk-computercomp)

-   [產生復原金鑰審核報告](#bkmk-recoverykey)

如需獨立報表的說明，請參閱[瞭解 MBAM 2.5 獨立的報表](understanding-mbam-25-stand-alone-reports.md)。

**記事** 若要執行報表，您必須是您在 Active Directory 網域服務中設定之**MBAM Report Users**群組的成員。 如需詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md)。

 

<a href="" id="bkmk-openadmin"></a>**開啟 [管理及監視] 網站**

1.  開啟網頁瀏覽器，然後流覽至 [管理] 和 [監視] 網站。 [管理] 和 [監視] 網站的預設 URL 為：

    *HTTP （s）// &lt; MBAMAdministrationServerName &gt; ： &lt; 埠 &gt; /Helpdesk*

2.  在左窗格中，按一下 [**報表**]。 從上方的功能表列中，選取您要執行的報表。

    MBAM 用戶端資料會保留在合規性和審核資料庫中，以便在電腦遺失或被盜時進行歷史參考。 在執行企業報告時，建議您使用適當的開始和結束日期，將報告的時間範圍從1到兩周，以提高報告資料的精確度。

    產生報告之後，您可以將結果儲存為不同的格式，例如 HTML、Microsoft Word 及 Microsoft Excel。

    **記事** 設定 SQL Server Reporting Services （SSRS），以使用安全通訊端層（SSL），然後再設定管理和監視網站。 如果由於任何原因而未將 SSRS 設定為使用 SSL，當您設定管理和監控網站時，報告的 URL 就會設定為 HTTP，而不是 HTTPS。 如果您接著移至 [管理及監視] 網站並選取報表，則會顯示下列訊息：「只會顯示安全內容」。 若要顯示報表，請按一下 [**顯示所有內容**]。

     

<a href="" id="bkmk-enterprise"></a>**產生企業合規性報告**

1.  從 [管理和監控] 網站，從左側流覽窗格中選取 [**報表**] 節點，選取 [**企業合規性報告**]，然後選取您要使用的篩選。 企業合規性報告可用的篩選器包括：

    -   **合規性狀態**。 使用此篩選指定報表的合規性狀態類型（例如，合規或不相容）。

    -   **錯誤狀態**。 使用這個篩選指定報告的錯誤狀態類型（例如，沒有錯誤或錯誤）。

2.  按一下 [**查看報表**] 以顯示選取的報表。

3.  選取電腦名稱稱，以在電腦合規性報告中查看電腦的相關資訊。

4.  選取電腦名稱稱旁的加號（+），以查看電腦上的磁片卷的相關資訊。

<a href="" id="bkmk-computercomp"></a>**產生電腦合規性報告**

1.  從 [管理和監控] 網站，從左側流覽窗格中選取 [**報表**] 節點，然後選取 [**電腦合規性報告**]。 使用電腦相容性報告來搜尋**使用者名稱**或**電腦名稱稱**。

2.  按一下 [**查看報表**]，以查看電腦合規性報告。

3.  選取電腦名稱稱，以在電腦合規性報告中顯示電腦的詳細資訊。

4.  選取電腦名稱稱旁的加號（+），以查看電腦上的磁片卷的相關資訊。

    **記事** 如果電腦符合或超過 MBAM 群組原則設定的需求，則會認為 MBAM 用戶端電腦符合規範。

<a href="" id="bkmk-recoverykey"></a>**產生復原金鑰審核報告**

1.  從 [管理和監控] 網站，選取左側流覽窗格中的 [**報表**] 節點，然後選取 [復原**審核報告**]。 選取您的 [復原金鑰] 審核報告篩選器。 復原金鑰審核的可用篩選器如下所示：

    -   **支援人員的使用者**。 此篩選可讓使用者指定申請者的使用者名稱。 申請者是技術支援人員中代表使用者存取金鑰的人員。

    -   **使用者**。 此篩選可讓使用者指定 requestee 的使用者名稱。 Requestee 是呼叫技術支援人員以取得復原金鑰的使用者。

    -   **要求結果**。 此篩選可讓使用者指定要作為報表基礎的要求結果類型（例如，成功或失敗）。 例如，使用者可能會想要查看失敗的按鍵存取嘗試。

    -   **金鑰類型**。 此篩選可讓使用者指定要作為報告基礎的金鑰類型（例如，復原金鑰密碼或 TPM 密碼雜湊）。

    -   **開始日期**。 這個篩選器可用來定義使用者想要報告的日期範圍的開始日期部分。

    -   [**結束日期**]。 這個篩選器可用來定義使用者要報告的日期範圍的結束日期部分。

2.  按一下 [**查看報表**]，即可查看報表。



## 相關主題


[使用 MBAM 2.5 監視與報告 BitLocker 符合性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[了解 MBAM 2.5 獨立報告](understanding-mbam-25-stand-alone-reports.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





