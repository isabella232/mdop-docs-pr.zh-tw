---
title: 修改 AGPM 服務帳戶
description: 修改 AGPM 服務帳戶
author: dansimp
ms.assetid: 0d8d8c7b-f299-4fee-8414-406492156942
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0672ceed2fba17060e17d2ffcfa264da458b9897
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802650"
---
# 修改 AGPM 服務帳戶


AGPM 服務是一個充當安全性 proxy 的 Windows 服務，管理用戶端對封存和生產環境中的群組原則物件（Gpo）的存取權。 如果此服務已停止或停用，則 AGPM 用戶端無法透過伺服器執行作業。

封存路徑和 AGPM 服務帳戶是在安裝 AGPM 服務器期間進行設定，您可以在此後透過 [**新增或移除程式**] 在 AGPM 服務器上變更。

**小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來修改 AGPM 服務的設定。 如此一來，就能防止 AGPM 服務啟動。

 

使用者帳戶是 Domain Admins 群組的成員，且有權存取 AGPM 服務器（安裝 Microsoft 高級群組原則管理-伺服器的電腦）需要完成此程式。

**重要** AGPM 服務帳戶必須擁有對其所管理之 Gpo 的完整存取權，並將其授**與服務許可權登**入。 如果您要在單一網域上管理 Gpo，您可以將 [本機系統] 帳戶設為主要網網域控制站（AGPM 服務帳戶）。

如果您要管理多個網域上的 Gpo，或如果成員伺服器將是 AGPM 服務器，您應該將另一個帳戶設定為 AGPM 服務帳戶，因為一個網網域控制站的本機系統帳戶無法存取其他網域上的 Gpo。

 

**修改 AGPM 服務帳戶**

1.  在已安裝 Microsoft 高級群組原則管理-伺服器的電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**新增或移除程式**]。

2.  按一下 [ **Microsoft 高級群組原則管理-伺服器**]，然後按一下 [**變更**]。

3.  按一下 **[下一步]**，然後按一下 [**修改**]。

4.  依照螢幕上的指示來設定 AGPM 服務的設定：

    1.  針對封存路徑，確認或變更封存相對於 AGPM 服務器的位置。 封存路徑可以指向 AGPM 服務器或其他位置的資料夾，但該位置應該有足夠的空間來儲存此 AGPM 服務器所管理的所有 Gpo 及歷程記錄資料。

    2.  輸入 AGPM 服務帳戶的新認證。

    3.  針對封存擁有者，輸入 AGPM 系統管理員的認證（[完全控制]）。

5.  按一下 [**變更**]，完成安裝後，按一下 **[完成]**。

### 其他參考資料

-   [管理 AGPM 服務](managing-the-agpm-service.md)

 

 





