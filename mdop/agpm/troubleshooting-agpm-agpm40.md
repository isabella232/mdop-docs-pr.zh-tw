---
title: 疑難排解 AGPM
description: 疑難排解 AGPM
author: dansimp
ms.assetid: bedcd817-beb2-47bf-aebd-e3923c4fd06f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b44612cb9e3737a8d8f3109f76b0c9325d183383
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802502"
---
# 疑難排解 AGPM


本節列出當您使用 [高級群組原則管理] （Gpo）管理群組原則物件時可能會遇到的常見問題。 若要診斷此處未列出的問題，可能會對 AGPM 系統管理員（完全控制）有用，以使用記錄和追蹤功能。 如需詳細資訊，請參閱[設定記錄和追蹤](configure-logging-and-tracing-agpm40.md)。

**注意**  
-   如需回退到舊版 GPO （如果有問題的話）的相關資訊，請參閱[回滾到舊版的 gpo](roll-back-to-an-earlier-version-of-a-gpo-agpm40.md)。

-   如需如何從備份還原完整封存的相關資訊，請參閱從[備份還原](restore-the-archive-from-a-backup-agpm40.md)封存。

 

## 您遇到什麼問題？


-   [我無法存取封存](#bkmk-access-an-archive)

-   [不同群組原則管理員的 GPO 狀態會有所不同](#bkmk-state-varies)

-   [我無法修改 AGPM 服務器連線](#bkmk-modify-archive-location)

-   [我無法變更預設範本或查看、建立、編輯、重新命名、部署或刪除 Gpo](#bkmk-perform-task)

-   [我無法使用特定的 GPO 名稱](#bkmk-use-particular-name)

-   [我沒有收到 AGPM 電子郵件通知](#bkmk-email)

-   [我無法將埠4600用於 AGPM 服務](#bkmk-port)

-   [AGPM 服務將無法啟動](#bkmk-not-start)

-   [[群組原則軟體安裝] 無法安裝軟體](#bkmk-software-installation)

-   [將封存還原到新的 AGPM 服務器時，發生錯誤](#bkmk-error-on-restore)

### <a href="" id="bkmk-access-an-archive"></a>我無法存取封存

-   **原因**：您沒有選取正確的伺服器和埠來進行封存。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：請參閱[設定 Agpm 伺服器](configure-agpm-server-connections-agpm40.md)連線。

    -   如果您不是 AGPM 系統管理員：從 AGPM 系統管理員要求 AGPM 服務器的連線詳細資料。 請參閱[設定 AGPM 服務器](configure-an-agpm-server-connection-agpm40.md)連線。

-   **原因**： AGPM 服務未執行。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：啟動 AGPM 服務。 如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm40.md)。

    -   如果您不是 AGPM 系統管理員：請與 AGPM 系統管理員聯繫以取得協助。

### <a href="" id="bkmk-state-varies"></a>不同群組原則管理員的 GPO 狀態會有所不同

-   **原因**：不同的群組原則管理員針對相同的封存選取了不同的 AGPM 服務器。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：請參閱[設定 Agpm 伺服器](configure-agpm-server-connections-agpm40.md)連線。

    -   如果您不是 AGPM 系統管理員：從 AGPM 系統管理員要求 AGPM 服務器的連線詳細資料。 請參閱[設定 AGPM 服務器](configure-an-agpm-server-connection-agpm40.md)連線。

### <a href="" id="bkmk-modify-archive-location"></a>我無法修改 AGPM 服務器連線

-   **原因**：如果 [ **agpm 伺服器**] 索引標籤上的 [設定] 無法使用，則 Agpm 伺服器已使用管理樣板集中進行集中設定。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：如果 [ **Agpm 伺服器**] 索引標籤上的 [設定] 無法使用，請參閱[設定 agpm 伺服器](configure-agpm-server-connections-agpm40.md)連線。

    -   如果您不是 AGPM 系統管理員：如果 [ **Agpm 伺服器**] 索引標籤上的 [設定] 無法使用，您就不需要修改 agpm 伺服器。

### <a href="" id="bkmk-perform-task"></a>我無法變更預設範本或查看、建立、編輯、重新命名、部署或刪除 Gpo

-   **原因**：您沒有獲指派角色，且擁有執行任務所需的許可權。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：請參閱[委派網域層級的存取權](delegate-domain-level-access-to-the-archive-agpm40.md)，並委派對封存[中個別 GPO 的存取權](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md)。 AGPM 許可權會從網域級聯到目前封存中的所有 Gpo。 如需哪些角色可以執行工作的詳細資料，以及執行工作所需的許可權，請參閱該工作的說明。

    -   如果您不是 AGPM 系統管理員，且需要其他角色或許可權：請與 AGPM 系統管理員聯繫以取得協助。 請注意，如果您是「編輯」，您可以開始建立 GPO、部署 GPO，或從網域的生產環境中刪除 GPO，但核准者或 AGPM 管理員必須核准您的要求。

### <a href="" id="bkmk-use-particular-name"></a>我無法使用特定的 GPO 名稱

-   **原因**：此 gpo 名稱已在使用中，或您無權列出該 gpo。

-   **解決方案**：

    -   如果 GPO 名稱出現在 [**受控**]、[無法**控制**] 或 [**擱置**] 索引標籤上，請選擇其他名稱。 如果部署的 GPO 已重新命名但尚未重新部署，則會在網域的生產環境中，以舊名稱顯示。 因此，仍在使用舊名稱。 重新部署 GPO 以在生產環境中更新其名稱，然後發行該名稱以供另一個 GPO 使用。

    -   如果 GPO 名稱未出現在 [**受控**]、[無法**控制**] 或 [**擱置**中] 索引標籤上，您可能就無權列出該 gpo。 若要要求許可權，請聯絡 AGPM 系統管理員。

### <a href="" id="bkmk-email"></a>我沒有收到 AGPM 電子郵件通知

-   **原因**：尚未提供有效的 SMTP 電子郵件伺服器和電子郵件地址，或未採取任何產生電子郵件通知的動作。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：針對供 agpm 傳送之待執行動作的電子郵件通知，AGPM 管理員必須在 [**網域委派**] 索引標籤上為核准者提供有效的 SMTP 電子郵件伺服器和電子郵件地址。如需詳細資訊，請參閱[設定電子郵件通知](configure-e-mail-notification-agpm40.md)。

    -   電子郵件通知只會在缺少建立、部署或刪除 GPO 所需許可權的編輯者、檢閱者或其他群組原則管理員處產生，以提交其中一個動作的要求。 不會自動通知核准或拒絕要求。

### <a href="" id="bkmk-port"></a>我無法將埠4600用於 AGPM 服務

-   **原因**：根據預設，AGPM 服務偵聽的埠是埠4600。

-   **解決方案**：如果 agpm 服務無法使用埠4600，請在 agpm 伺服器上修改埠設定，以使用另一個埠，然後在 Agpm 用戶端的 agpm 伺服器連線中更新埠。 如需詳細資訊，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm40.md)。

### <a href="" id="bkmk-not-start"></a>AGPM 服務將無法啟動

-   **原因**：您在 [**管理工具**及**服務**] 底下的作業系統中修改了 AGPM 服務的設定。

-   **解決方案**：修改**Microsoft 高級群組原則管理的設定-伺服器**[控制台] 中的 [**程式和功能**]。 如需詳細資訊，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm40.md)。

### <a href="" id="bkmk-software-installation"></a>[群組原則軟體安裝] 無法安裝軟體

-   **原因**： AGPM 會保留群組原則軟體安裝套件的完整性。 雖然 Gpo 是以離線方式編輯，但會保留封裝用戶端資訊以外的套件之間的連結。 這是原本設計的做法。

-   **解決方案**：當您使用 AGPM 離線編輯 GPO 時，請將另一個 gpo 中的任何群群組原則軟體安裝升級為參考已部署的 gpo，而非已取出的複本。 編輯器必須擁有已部署 GPO 的**讀取**許可權。

### <a href="" id="bkmk-error-on-restore"></a>將封存還原到新的 AGPM 服務器時，發生錯誤

-   **原因**：出於安全性考慮，保護在 [**網域委派**] 索引標籤上輸入之密碼的加密，如果將封存移到另一部電腦，就會導致密碼失敗。

-   **解決方案**：重新輸入並確認 [**網域委派**] 索引標籤上的密碼。如需詳細資訊，請參閱[設定電子郵件通知](configure-e-mail-notification-agpm40.md)。

 

 





