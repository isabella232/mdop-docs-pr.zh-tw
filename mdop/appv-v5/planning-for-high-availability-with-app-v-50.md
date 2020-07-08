---
title: App-V 5.0 高可用性規劃
description: App-V 5.0 高可用性規劃
author: dansimp
ms.assetid: 6d9a6492-23f8-465c-82e5-49c863594156
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ebf586de7cae19d40d76c9c0c845f93e7bd9021b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800357"
---
# App-V 5.0 高可用性規劃


Microsoft Application Virtualization 5.0 （App-v 5.0）系統組態可以利用維護高層次可用服務的選項。

使用下列各節中的資訊，協助您瞭解在高可用性配置中部署 app-v 5.0 的選項。

-   [Microsoft SQL Server 群集支援](#bkmk-sqlcluster)

-   [支援 IIS 網路負載平衡](#bkmk-iisloadbal)

-   [在執行時支援群集檔案伺服器（SCS）模式](#bkmk-clusterscsmode)

-   [Microsoft SQL Server 鏡像支援](#bkmk-sqlmirroring)

-   [Microsoft SQL Server 的支援永遠開啟](#bkmk-sqlalwayson)

## <a href="" id="bkmk-sqlcluster"></a>Microsoft SQL Server 群集支援


您可以在執行 Microsoft SQL Server 群集的電腦上執行 App-v 管理資料庫和報告資料庫。 不過，您必須使用腳本來安裝資料庫。

如需相關指示，請參閱[如何使用 SQL 腳本部署 App-v 資料庫](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)。

## <a href="" id="bkmk-iisloadbal"></a>支援 IIS 網路負載平衡


您可以使用 Internet Information Services （IIS）網路負載平衡，為執行 App-v 5 a.x 管理、發佈和報表服務的電腦（透過 IIS 部署）設定高可用性環境。

如需針對執行 Windows Server 作業系統的電腦設定 IIS 和網路負載平衡的詳細資訊，請參閱下列內容：

-   提供有關設定網際網路資訊服務（IIS）7.0 的資訊。

    [實現高可用性和可伸縮性-ARR 與 NLB](https://go.microsoft.com/fwlink/?LinkId=316369) （https://go.microsoft.com/fwlink/?LinkId=316369)

-   正在設定 Microsoft Windows Server

    [網路負載平衡](https://go.microsoft.com/fwlink/?LinkId=316370)（ https://go.microsoft.com/fwlink/?LinkId=316370) 。

    這項資訊也適用于 Windows Server2008、Windows Server2008R2 或 Windows Server2012 中的 IIS 網路負載平衡（NLB）群集。

    **記事** Windows Server2012 中的 IIS 網路負載平衡功能通常與 Windows Server2008R2 中的相同。 不過，某些任務的詳細資料會在 Windows Server2012 中變更。 如需新的執行工作方式的詳細資訊，請參閱[Windows Server 2012 R2 Preview 和 Windows server 2012 中的常見管理工作與流覽](https://go.microsoft.com/fwlink/?LinkId=316371)（ https://go.microsoft.com/fwlink/?LinkId=316371) 。

     

## <a href="" id="bkmk-clusterscsmode"></a>在執行時支援群集檔案伺服器（SCS）模式


支援在具有群集檔案伺服器的共用內容存放區（SCS）模式中執行 App-v 5.0。

您可以使用下列步驟來啟用此設定：

-   將 App-v 5.0 設定為在用戶端 SCS 模式中執行。 如需設定 App-v 5.0 SCS 模式的詳細資訊，請參閱[如何安裝 app-v 5.0 用戶端以取得共用內容存放區模式](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)。

-   在 Microsoft Server2012 橫向模式和使用虛擬 SAN 的**2012**模式中設定檔案伺服器群集。

您可以使用下列步驟來驗證配置：

1.  在發佈伺服器上新增套件。 如需有關新增套件的詳細資訊，請參閱[如何使用管理主控台新增或升級套件](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)。

2.  在執行 App-v 5.0 用戶端的電腦上執行發佈更新，並開啟應用程式。

3.  切換叢集節點的中間發佈更新及中端資料流程，以確保容錯移轉正常運作。

如需有關設定 Windows Server 容錯移轉叢集的詳細資訊，請參閱下列內容：

-   [檢查清單：建立群集檔案伺服器](https://go.microsoft.com/fwlink/?LinkId=316372)（ https://go.microsoft.com/fwlink/?LinkId=316372) 。

-   [在 Windows Server 2012 的 [容錯移轉叢集] 中使用群集共用的磁片](https://go.microsoft.com/fwlink/?LinkId=316373) https://go.microsoft.com/fwlink/?LinkId=316373) 。

## <a href="" id="bkmk-sqlmirroring"></a>Microsoft SQL Server 鏡像支援


5.0 如果您使用 Microsoft SQL Server 鏡像，即會支援 app-v 5.0 管理伺服器資料庫使用兩個 SQL Server 實例進行鏡像。

如需有關設定 Microsoft SQL Server 鏡像的詳細資訊，請參閱下列內容：

-   [操作方法：準備鏡像資料庫以進行鏡像（transact-sql）](https://go.microsoft.com/fwlink/?LinkId=316375) （https://go.microsoft.com/fwlink/?LinkId=316375)

-   [使用 Windows 驗證（SQL Server Management Studio）建立資料庫鏡像會話](https://go.microsoft.com/fwlink/?LinkId=316377)（https://go.microsoft.com/fwlink/?LinkId=316377)

您可以使用下列步驟來驗證配置：

1.  啟動 Microsoft SQL Server 鏡像會話。

2.  選取 [**容錯移轉**] 以指定新的主 Microsoft SQL Server 實例。

3.  驗證在容錯移轉之後，App-v 5.0 管理伺服器仍能正常發揮預期的作用。

管理伺服器上的連接字串可以修改，以包含**容錯移轉夥伴 = &lt; server2 &gt; **。 這只會在鏡像的主要元件容錯移轉到次要電腦，而執行 App-v 5.0 用戶端的電腦正在進行全新連線（例如重新開機之後）時提供協助。

使用下列步驟來修改連接字串，以包含**容錯移轉夥伴 = &lt; server2 &gt; **：

**重要** 本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。 如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。 變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。 Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。 變更註冊表的風險由您自行承擔。

 

1.  登入管理伺服器並開啟**regedit**。

2.  流覽至**HKEY \ _LOCAL \ _MACHINE**  \\  **軟體**  \\  **Microsoft**  \\  **AppV**  \\  **Server**  \\  **ManagementService**。

3.  使用**容錯移轉夥伴 = &lt; &gt; Server2**來修改**管理 \ _SQL \ _CONNECTION \ _STRING**值。

4.  使用 IIS 主控台重新開機管理服務。

    **記事** 資料庫鏡像是針對 Microsoft SQL Server2012 的已過時資料庫引擎功能清單，因為 Microsoft SQL Server 2012 提供了**AlwaysOn**功能。

     

如需詳細資訊，請按一下下列任何一個連結：

-   [操作方法：準備鏡像資料庫以進行鏡像（transact-sql）](https://go.microsoft.com/fwlink/?LinkId=394235) （ https://go.microsoft.com/fwlink/?LinkId=394235) 。

-   [操作方法：設定資料庫鏡像會話（SQL Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=394236) （ https://go.microsoft.com/fwlink/?LinkId=394236) 。

-   [使用 Windows 驗證（SQL Server Management Studio）建立資料庫鏡像會話](https://go.microsoft.com/fwlink/?LinkId=394237)（ https://go.microsoft.com/fwlink/?LinkId=394237) 。

-   [SQL Server 2012 中已過時的資料庫引擎功能](https://go.microsoft.com/fwlink/?LinkId=394238)（ https://go.microsoft.com/fwlink/?LinkId=394238) 。

## <a href="" id="bkmk-sqlalwayson"></a>Microsoft SQL Server 的支援總在設定上


App-v 5.0 管理伺服器資料庫支援使用 [**永遠開啟**] 設定，將部署到執行 Microsoft SQL server 的電腦。

## 相關主題


[規劃部署 App-V](planning-to-deploy-app-v.md)

 

 





