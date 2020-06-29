---
title: 如何為 App-V 設定 Microsoft SQL Server 鏡像支援
description: 如何為 App-V 設定 Microsoft SQL Server 鏡像支援
author: dansimp
ms.assetid: 6d069eb5-109f-460a-836a-de49473b7035
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fb572442cd12bb32fc9406de65f05a3bf061f946
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801614"
---
# 如何為 App-V 設定 Microsoft SQL Server 鏡像支援


您可以使用下列程式來設定您的 Microsoft Application Virtualization （App-v）環境，以使用 Microsoft SQL Server 資料庫鏡像。 設定資料庫鏡像可協助災害復原與容錯移轉案例。 App-V 4.5 SP2 支援 Microsoft SQL Server 2005 和 SQL Server 2008 目前可使用的所有資料庫鏡像模式。

**注意**  
這個程式是針對熟悉使用 Microsoft SQL Server 設定及設定 SQL Server 資料庫及資料庫鏡像的系統管理員所撰寫，因此只涵蓋 App-v 所特有的特定配置設定。



**設定您的 App-v 環境以使用 Microsoft SQL Server 資料庫鏡像**

1.  在資料庫鏡像的標準商務做法之後，設定 App V 資料庫的 SQL Server 資料庫鏡像。 針對執行 Microsoft SQL Server 資料庫鏡像的一般資訊，請使用下列連結：

    -   **MICROSOFT SQL 2005**-[設定資料庫鏡像](https://go.microsoft.com/fwlink/?LinkId=187478)（https://go.microsoft.com/fwlink/?LinkId=187478)

    -   **MICROSOFT SQL 2008**-[設定資料庫鏡像](https://go.microsoft.com/fwlink/?LinkId=187477)（https://go.microsoft.com/fwlink/?LinkId=187477)

    此外，您可以在[資料庫鏡像最佳做法和效能考慮](https://go.microsoft.com/fwlink/?LinkId=190270)（.）中找到最佳做法資訊 https://go.microsoft.com/fwlink/?LinkId=190270) 。

2.  在設定鏡像之後，請確認 App-v 資料庫顯示狀態為 **[主體]、[已同步**處理]，且鏡像資料庫顯示狀態為 **[（鏡像]、[已同步處理/正在還原]）**。 先解決任何鏡像問題，然後再繼續進行下一個步驟。 如需有關監控狀態的其他資訊，請參閱[監視鏡像狀態](https://go.microsoft.com/fwlink/?LinkId=190279)（ https://go.microsoft.com/fwlink/?LinkId=190279) 。

3.  在託管 app-v 資料庫鏡像的 sql server 電腦上，使用 [帳戶名稱** &lt; 網域 &gt; \\ &lt; ManagementServerHostName &gt; $ **] 建立 app-v 管理伺服器的網路服務帳戶的 sql server 登入。

4.  在 App-V 管理伺服器上安裝 Microsoft SQL Server Native Client，以及在執行 App-v Management Web 服務的電腦（如果安裝在其他電腦上的話）。 如果您打算將其他 App-v 管理伺服器連線到鏡像的 SQL 資料庫以進行負載平衡，您也必須在這些電腦上安裝 Microsoft SQL Server Native 用戶端。 您可以從 microsoft 下載中心的 [ [MICROSOFT Sql server 2008 功能套件](https://go.microsoft.com/fwlink/?LinkId=187479)] 頁面下載 Microsoft Sql Server Native Client https://go.microsoft.com/fwlink/?LinkId=187479) 。

5.  檢查登錄機碼**HKEY _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlservername** ，並確認它只包含 SQL Server 的主機名稱。 如果它包含實例名稱（例如*serverhostname\\instancename*），則必須移除實例名稱。

    **重要**  
    App-V 管理伺服器會使用 TCP/IP 網路文件庫，在啟用資料庫鏡像時與 SQL Server 通訊，因此不能使用實例名稱。 您必須在登錄機碼中指定埠號碼。



6.  檢查登錄機碼**HKEY _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlserverport** ，並確認它包含在 sql Server 電腦上用於 sql 的埠號碼。 如果您使用的是命名實例，此金鑰值必須設定為命名實例所用的埠。

7.  建立登錄機碼**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverservername**做為 REG \ _SZ 然後將此值設定為裝載鏡像之 SQL Server 的主機名稱。

8.  建立登錄機碼**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverserverport**作為 DWORD，然後在執行 sql Server 的電腦上，將此值設定為使用 sql Server 託管鏡像的埠號碼。 如果您使用的是鏡像的命名實例，此鍵值必須設定為命名實例所用的埠號碼。

9.  在執行 App-v Management Web 服務的電腦上，設定 [通用資料連結（UDL）] 文字檔。 在安裝 App-v 的目錄中，按兩下**SftMgmt** ，然後指定下列值：

    -   在 [**提供者**] 索引標籤上，選取 [OLE DB 提供者**SQL Server 原生用戶端 10.0**]。

    -   按一下 **[下一步** **]，選取 [連線] 索引**標籤。在 [**伺服器名稱**] 方塊中，輸入 SQL 伺服器的伺服器名稱。 接著，選取 [**使用 WINDOWS NT 整合的安全性**]。 最後，按一下清單**選取資料庫**，然後選取 app-v 資料庫的名稱。

    -   按一下 [**全部**] 索引標籤，然後選取 [專案**容錯移轉] 合作夥伴**。 按一下 [**編輯值**]，然後輸入容錯移轉 SQL server 的伺服器名稱。 按一下 \[確定\] ****。

    **重要**  
    App-v 系統會使用 Kerberos 驗證。 因此，當您設定在 SQL Server 上啟用 Kerberos 驗證的 SQL 鏡像，且 SQL Server 服務在網域使用者帳戶下執行時，您必須手動設定 SPN。 如需詳細資訊，請參閱針對[分散式環境設定 App-v 管理一](https://go.microsoft.com/fwlink/?LinkId=203186)文中的「SQL 服務使用網域版帳戶」 https://go.microsoft.com/fwlink/?LinkId=203186) 。



10. 若要確認資料庫鏡像正常執行，請測試容錯移轉並確認 App-v 管理伺服器繼續正常運作。

    **重要**  
    請務必小心，並遵循您的標準商務做法，以確保系統操作不會在發生失敗時中斷。



~~~
After the failover has occurred successfully, as verified by using the SQL Server status monitoring information, right-click the **Applications** node in the App-V Management Console, and then select **Refresh**. The list of applications should display normally if the system is working correctly.
~~~

## 相關主題


[如何在 Application Virtualization 伺服器管理主控台中執行系統管理工作](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)









