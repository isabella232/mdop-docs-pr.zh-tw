---
title: 疑難排解進階群組原則管理
description: 疑難排解進階群組原則管理
author: dansimp
ms.assetid: f58849cf-6c5b-44d8-b356-0ed7a5b24cee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c22b9a0983b26252ee0d9c8d99b63cd4ab5dc2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801742"
---
# 疑難排解進階群組原則管理


本節列出在使用高級群組原則管理（Gpo）管理群組原則物件時可能會遇到的一些常見問題。

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

### <a href="" id="bkmk-access-an-archive"></a>我無法存取封存

-   **原因**：您沒有選取正確的伺服器和埠來進行封存。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection.md)連線。

    -   如果您不是 AGPM 系統管理員：從 AGPM 系統管理員要求 AGPM 服務器的連線詳細資料。 請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection-reviewer.md)連線。

-   **原因**： [高級] 群組原則管理服務未執行。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：啟動 AGPM 服務。 如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service.md)。

    -   如果您不是 AGPM 系統管理員：請與 AGPM 系統管理員聯繫以取得協助。

### <a href="" id="bkmk-state-varies"></a>不同群組原則管理員的 GPO 狀態會有所不同

-   **原因**：不同的群組原則管理員針對相同的封存選取了不同的 AGPM 服務器。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection.md)連線。

    -   如果您不是 AGPM 系統管理員：從 AGPM 系統管理員要求 AGPM 服務器的連線詳細資料。 請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection-reviewer.md)連線。

### <a href="" id="bkmk-modify-archive-location"></a>我無法修改 AGPM 服務器連線

-   **原因**：如果 [ **agpm 伺服器**] 索引標籤上的 [設定] 無法使用，則 Agpm 伺服器已使用管理樣板集中進行集中設定。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：如果 [ **Agpm 伺服器**] 索引標籤上的 [設定] 無法使用，請參閱[設定 agpm 伺服器](configure-the-agpm-server-connection.md)連線。

    -   如果您不是 AGPM 系統管理員：如果 [ **Agpm 伺服器**] 索引標籤上的 [設定] 無法使用，您就不需要修改 agpm 伺服器。

### <a href="" id="bkmk-perform-task"></a>我無法變更預設範本或查看、建立、編輯、重新命名、部署或刪除 Gpo

-   **原因**：您沒有獲指派角色，且擁有執行任務所需的許可權。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：請參閱[委派網域層級存取](delegate-domain-level-access.md)權和[委派對個別 GPO 的存取權](delegate-access-to-an-individual-gpo.md)。 AGPM 許可權會從網域級聯到目前封存中的所有 Gpo。 隨著新的群組原則系統管理員新增在網域層級，他們的許可權必須設定為適用于**這個物件和嵌套物件**。 如需哪些角色可以執行工作的詳細資料，以及執行工作所需的許可權，請參閱該工作的說明。

    -   如果您不是 AGPM 系統管理員，且需要其他角色或許可權：請與 AGPM 系統管理員聯繫以取得協助。 請注意，如果您是「編輯」，您可以開始建立 GPO、部署 GPO 或從生產環境刪除 GPO 的程式，但核准者或 AGPM 管理員必須核准您的要求。

### <a href="" id="bkmk-use-particular-name"></a>我無法使用特定的 GPO 名稱

-   **原因**：此 gpo 名稱已在使用中，或您無權列出該 gpo。

-   **解決方案**：

    -   如果 GPO 名稱出現在 [**受控**]、[無法**控制**] 或 [**擱置**] 索引標籤上，請選擇其他名稱。 如果已部署的 GPO 已重新命名但尚未重新部署，則會顯示在生產環境中其舊名稱下方，因此舊名稱仍在使用中。 重新部署 GPO 以在生產環境中更新其名稱，然後發行該名稱以供另一個 GPO 使用。

    -   如果 GPO 名稱未出現在 [**受控**]、[無法**控制**] 或 [**擱置**中] 索引標籤上，您可能就無權列出該 gpo。 若要要求許可權，請聯絡 AGPM 系統管理員。

### <a href="" id="bkmk-email"></a>我沒有收到 AGPM 電子郵件通知

-   **原因**：尚未提供有效的 SMTP 電子郵件伺服器和電子郵件地址，或未採取任何產生電子郵件通知的動作。

-   **解決方案**：

    -   如果您是 AGPM 系統管理員：針對供 agpm 傳送之待執行動作的電子郵件通知，AGPM 管理員必須在 [**網域委派**] 索引標籤上為核准者提供有效的 SMTP 電子郵件伺服器和電子郵件地址。如需詳細資訊，請參閱[設定電子郵件通知](configure-e-mail-notification.md)。

    -   電子郵件通知只會在缺少建立、部署或刪除 GPO 所需許可權的編輯者、檢閱者或其他群組原則管理員處產生，以提交其中一個動作的要求。 不會自動通知核准或拒絕要求。

### <a href="" id="bkmk-port"></a>我無法將埠4600用於 AGPM 服務

-   **原因**：根據預設，AGPM 服務偵聽的埠是埠4600。

-   **解決方案**：如果 AGPM 服務無法使用埠4600，請修改每個封存索引檔案，以使用另一個埠，然後為所有群組原則管理員更新 AGPM 服務器。 如需詳細資訊，請參閱[修改 AGPM 服務偵聽的埠](modify-the-port-on-which-the-agpm-service-listens.md)。

### <a href="" id="bkmk-not-start"></a>AGPM 服務將無法啟動

-   **原因**：您在 [**管理工具**及**服務**] 底下的作業系統中修改了 AGPM 服務的設定。

-   **解決方案**：修改**Microsoft 高級群組原則管理的設定-伺服器（** 在 [**新增或移除程式**] 底下）。 如需詳細資訊，請參閱[修改 AGPM 服務帳戶](modify-the-agpm-service-account.md)。

### <a href="" id="bkmk-software-installation"></a>[群組原則軟體安裝] 無法安裝軟體

-   **原因**： AGPM 會保留群組原則軟體安裝套件的完整性。 雖然 Gpo 是以離線方式編輯，但會保留套件之間的連結，以及緩存的用戶端資訊。 這是原本設計的做法。

-   **解決方案**：使用 AGPM 離線編輯 GPO 時，請將另一個 gpo 中的任何群群組原則軟體安裝升級為參考已部署的 gpo，而不是取出的複本。 編輯器必須擁有已部署 GPO 的**讀取**許可權。

 

 





