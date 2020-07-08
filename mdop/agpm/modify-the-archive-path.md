---
title: 修改封存路徑
description: 修改封存路徑
author: dansimp
ms.assetid: 6d90daf9-58db-4166-b5b3-e84bb261164a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1fc6ba2bf415d3d1bc67144d0dec1030c6173026
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802638"
---
# 修改封存路徑


封存路徑是相對於 AGPM 服務器的封存位置。 封存路徑可以指向您在 AGPM 服務器上的資料夾，或是在同一林中的另一台伺服器上。

封存路徑和 AGPM 服務帳戶是在安裝 AGPM 服務器期間進行設定，您可以在此後透過 [**新增或移除程式**] 在 AGPM 服務器上變更。

使用者帳戶是 Domain Admins 群組的成員，且有權存取 AGPM 服務器（安裝 Microsoft 高級群組原則管理-伺服器的電腦）需要完成此程式。

**修改封存路徑**

1.  在已安裝 Microsoft 高級群組原則管理-伺服器的電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**新增或移除程式**]。

2.  按一下 [ **Microsoft 高級群組原則管理-伺服器**]，然後按一下 [**變更**]。

3.  按一下 **[下一步]**，然後按一下 [**修改**]。

4.  依照螢幕上的指示來設定 AGPM 服務的設定：

    1.  針對封存路徑，針對 AGPM 服務器輸入封存的新位置。 封存路徑可以指向 AGPM 服務器或其他位置的資料夾，但該位置應該有足夠的空間來儲存此 AGPM 服務器所管理的所有 Gpo 及歷程記錄資料。

    2.  輸入 AGPM 服務帳戶的認證。

        **重要** 修改安裝會清除 AGPM 服務帳戶的認證。 您必須重新輸入認證，但不需要符合在原始安裝期間所使用的認證。

        AGPM 服務帳戶必須擁有它將管理之 Gpo 的完整存取權。 如果您要在單一網域上管理 Gpo，您可以將 [本機系統] 帳戶設為主要網網域控制站（AGPM 服務帳戶）。

        如果您要管理多個網域上的 Gpo，或如果成員伺服器將是 AGPM 服務器，您應該將另一個帳戶設定為 AGPM 服務帳戶，因為一個網網域控制站的本機系統帳戶無法存取其他網域上的 Gpo。

         

    3.  針對封存擁有者，輸入 AGPM 系統管理員的認證（[完全控制]）。

5.  按一下 [**變更**]，完成安裝後，按一下 **[完成]**。

### 其他參考資料

-   [管理 AGPM 服務](managing-the-agpm-service.md)

 

 





