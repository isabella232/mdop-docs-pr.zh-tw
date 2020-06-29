---
title: 如何將 App-V SQL 資料庫移轉至不同的 SQL Server
description: 如何將 App-V SQL 資料庫移轉至不同的 SQL Server
author: dansimp
ms.assetid: 353892a1-9327-4489-a19c-4ec7bd1b736f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e3d84b0cb328873db3722ad3eb9af6a2b442fdcf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801270"
---
# 如何將 App-V SQL 資料庫移轉至不同的 SQL Server


下列程式詳細說明如何將 Microsoft Application Virtualization （App-v）管理伺服器的 SQL 資料庫遷移至不同的 SQL Server。

**重要** 這個程式需要停止 App-v server 服務，這會讓使用者無法使用其應用程式。

 

**若要備份 app-v SQL 資料庫**

1.  開啟 services.msc 程式，並在所有使用要遷移之資料庫的管理伺服器上停止 App-v Management Server 服務。

2.  在 App V 資料庫所在的電腦上，開啟 [SQL Server Management Studio]。

3.  展開 [**資料庫**] 節點並找到 app-v 資料庫（預設名稱為 APPVIRT）。

4.  以滑鼠右鍵按一下資料庫，然後選取 [**任務**]，然後選取 [**備份**]。

5.  確認 [**恢復模型**] 已設定為 [**簡易**]，且 [**備份類型**] 設定為 [**完整**]。 如有需要，請變更 [**備份組**] 和 [**目的地**] 設定。

6.  按一下 **[確定]** 以備份資料庫。 成功完成備份之後，按一下 **[確定]**。

7.  開啟 Windows 資源管理器，然後流覽至包含資料庫備份檔案的資料夾，例如 APPVIRT。.BAK. 將資料庫備份檔案複製到執行 SQL Server 的目的電腦。

**將 App-v SQL 資料庫還原到目的地電腦**

1.  在目的地電腦上，開啟 SQL Server Management Studio，以滑鼠右鍵按一下 [**資料庫**] 節點，然後選取 [**還原資料庫**]。

2.  在 [**還原的來源**] 底下，選擇 [**從裝置**]，然後按一下 [**...**]。 按鈕。

3.  在 [**指定備份**] 對話方塊中，確認**備份媒體**已設定為 [檔案] **，然後按一下**[**新增**]。

4.  選取您從執行 SQL Server 的原始電腦複製的備份檔案，然後按一下 **[確定]**。

5.  按一下 **[確定]** ，然後按一下以選取要還原的備份組。

6.  在 [**還原目的地**] 底下，按一下 [**資料庫**] 下拉式清單，然後選取 App-V 資料庫名稱（例如 APPVIRT）。

7.  按一下 **[確定]** 以開始還原。 成功完成還原之後，按一下 **[確定]**。

8.  展開 [**安全性**] 節點，以滑鼠右鍵按一下 [**登錄**]，然後選取 **[新增登**入]。

9.  在 [**登入名稱**] 欄位中，以 DOMAIN\\SERVERNAME $ 的格式輸入 App V 管理伺服器的網路服務帳戶詳細資料。

10. 在 [**預設資料庫**] 下的 **[一般**] 頁面上，選取 app-v 資料庫名稱（例如 APPVIRT），然後按一下 **[確定]**。

11. 在 [**選取頁面**] 底下，按一下以選取 [**使用者對應**] 頁面。 在 [**對應至此登**入的使用者] 下，按一下 [**對應**] 欄中的核取方塊以選取 app-v 資料庫。

12. 在 **： &lt; appvdatabasename &gt; 的 [資料庫角色成員資格**] 底下，按一下以選取 [ **SFTEveryone** ]，然後按一下 **[確定]**。

13. 確定執行 SQL Server 的新電腦上的 Windows 防火牆已設定為允許 App-v Management Server 存取系統。 在 [**管理工具**] 底下，使用 [**高級安全性**] 程式的 Windows 防火牆，為 SQL Server 所使用的埠建立**入站規則**（預設為埠1433）。

**遷移 app-v SQL Server 代理程式作業**

1.  在執行 SQL Server 的原始電腦上，在 SQL Server Management Studio 中，展開 [ **Sql Server 代理程式**] 節點，然後展開 [**作業**] 節點。

2.  以滑鼠右鍵按一下下列四個 App-v 作業，然後選取 [**腳本作業] 做為 |建立至 |檔案，並**將每個腳本儲存到一個資料夾，並為每個腳本指定一個描述性的名稱。

    -   **Softgrid 資料庫（appvdbname）檢查使用方式歷程記錄**

    -   **Softgrid 資料庫（appvdbname）關閉孤立的會話**

    -   **Softgrid 資料庫（appvdbname）強制大小限制**

    -   **Softgrid 資料庫（appvdbname）監視警報/作業狀態**

3.  將四個腳本檔案（.sql）複製到執行 SQL Server 的目的電腦，並開啟 SQL Server Management Studio。

4.  在 Windows 資源管理器中，以滑鼠右鍵按一下每個 .sql 檔案，然後按一下 [**執行**]。 每個腳本都會在 SQL Server Management Studio 中的查詢視窗中開啟。 針對每個腳本，按一下 [**執行**]，然後確認每個腳本都已順利完成。

5.  重新整理 [ **SQL Server 代理程式**] 節點下的 [**作業**] 節點，確認已成功建立四個作業。

**更新 App V 管理伺服器的設定**

1.  在 App-v Management Server 上，修改下列登錄機碼：

    -   **SQLServerName**  =  SQLServerName &lt;newservername&gt;

    -   **SQLServerPort**  =  SQLServerPort &lt;newserverport&gt;

    然後重新開機 App-v server 服務。

2.  流覽以尋找 App-v Management Server 安裝目錄下的 SftMgmt 檔案（預設為 C:\\program files Files\\Microsoft System Center App Virt 管理 Server\\App Virt 管理服務）。 以滑鼠右鍵按一下檔案，然後選取 [**開啟**]。

3.  **在 [連線**] 索引標籤上，輸入執行 SQL Server 之目的電腦的名稱，然後按一下 [**測試**連線]。 測試成功時，請按一下 **[確定]** ，然後再按一下 **[確定]** 。

4.  針對 4.5 SP2 之前的 App-v 管理伺服器版本，您必須更新 SQL 記錄設定。 在 [**伺服器群組**] 底下，以滑鼠右鍵按一下伺服器所屬的伺服器群組，然後選取 [**屬性**]。

5.  按一下 [**記錄**] 索引標籤上的 **[選取 SQL 資料庫**專案]，然後按一下 [**編輯**]。

6.  將**DNS 主機名稱**變更為執行 SQL Server 的新電腦的主機名稱，然後按一下 **[確定]**。 再按兩次 **[確定]** ，然後重新開機 app-v server 服務。

7.  開啟 App V 管理主控台，以滑鼠右鍵按一下 [**應用程式**] 節點，**然後選取 [** 重新整理]。 應用程式清單應該顯示為 [之前]。

 

 





