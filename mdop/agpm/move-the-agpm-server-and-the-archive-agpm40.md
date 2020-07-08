---
title: 移動 AGPM 伺服器和封存
description: 移動 AGPM 伺服器和封存
author: dansimp
ms.assetid: 9ec48d3a-c293-45f0-8939-32ccdc062303
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 61ad2eb6e0ea46eef89379894a99469254e0fd5e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809411"
---
# 移動 AGPM 伺服器和封存


如果您要取代 AGPM 服務器和存放封存的伺服器，您必須移動 AGPM 服務和封存。 如果您想要的話，您可以將 AGPM 服務和封存分別放在一起。

**注意**  
-   AGPM 服務器是主持 AGPM 服務的電腦，以及安裝 Microsoft 高級群組原則管理（伺服器）的電腦。

-   根據預設，封存是存放在 AGPM 服務器上，但您可以指定封存路徑，將它裝載在另一個伺服器上。

 

您必須擁有網域系統管理員群組成員的使用者帳戶，且有權存取前一個與新的 AGPM 服務器，才能完成此程式。 此外，您必須為要由新的 AGPM 服務器使用的 AGPM 服務帳戶提供認證，才能完成此程式。

**將 AGPM 服務及封存移至不同的伺服器或伺服器**

1.  備份封存。 如需詳細資訊，請參閱[備份](back-up-the-archive-agpm40.md)封存。

2.  移動 AGPM 服務：

    1.  停止 AGPM 服務。 如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm40.md)。

    2.  在新伺服器上安裝 Microsoft 高級群組原則管理-伺服器，該伺服器將主持 AGPM 服務。 在此程式中，您會指定新的封存路徑、封存相對於 AGPM 服務器的位置。 如需詳細資訊，請參閱[Microsoft 高級群組原則管理4.0 的逐步指南](https://go.microsoft.com/fwlink/?LinkId=153505)（ https://go.microsoft.com/fwlink/?LinkId=153505) 以及[Microsoft 高級群組原則管理的規劃指南](https://go.microsoft.com/fwlink/?LinkId=156883)（） https://go.microsoft.com/fwlink/?LinkId=156883) 。

    3.  AGPM 管理員（完全控制）必須針對將使用新的 AGPM 服務器並移除舊的 AGPM 服務器連線的所有群組原則管理員，設定 AGPM 服務器連線，否則每個群組原則管理員都必須手動設定新的 AGPM 服務器連線，並移除舊的 AGPM 服務器連線（適用于電腦上的 AGPM 管理單元）。 如需詳細資訊，請參閱[設定 AGPM 服務器](configure-agpm-server-connections-agpm40.md)連線。

        **記事** 最佳做法，您應該從先前的 AGPM 服務器卸載 Microsoft 高級群組原則管理-伺服器。 這可確保 AGPM 服務無法在該伺服器上無意間重新開機，而且如果有任何 AGPM 服務器連線，可能會造成混淆。

         

3.  將封存從備份複製到將主持封存的新伺服器。 如需詳細資訊，請參閱[從備份還原](restore-the-archive-from-a-backup-agpm40.md)封存。

    **重要** 如果您移動封存，但不同時移動 AGPM 服務：

    1.  您必須變更封存路徑，以指向與 AGPM 服務器相關的封存新位置。 如需詳細資訊，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm40.md)。

    2.  您必須重新輸入並確認 [**網域委派**] 索引標籤上的密碼。如需詳細資訊，請參閱[設定電子郵件通知](configure-e-mail-notification-agpm40.md)。

     

### 其他參考資料

-   [備份封存](back-up-the-archive-agpm40.md)

-   [從備份還原封存](restore-the-archive-from-a-backup-agpm40.md)

-   [設定 AGPM 伺服器連線](configure-agpm-server-connections-agpm40.md)

-   [修改 AGPM 服務](modify-the-agpm-service-agpm40.md)

-   [Microsoft 高級群組原則管理4.0 的逐步指南](https://go.microsoft.com/fwlink/?LinkId=153505)（https://go.microsoft.com/fwlink/?LinkId=153505)

-   [Microsoft 高級群組原則管理的規劃指南](https://go.microsoft.com/fwlink/?LinkId=156883)（https://go.microsoft.com/fwlink/?LinkId=156883)

-   [執行 AGPM 系統管理員工作](performing-agpm-administrator-tasks-agpm40.md)

 

 





