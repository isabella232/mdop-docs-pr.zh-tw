---
title: 如何針對 App-V Management Server 設定 Windows Server 2008
description: 如何針對 App-V Management Server 設定 Windows Server 2008
author: dansimp
ms.assetid: 38b4016f-de82-4209-9159-387d20ddee25
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d1cd7e84ffc0036c98e70a9a0ee1fd3a4ade790
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801530"
---
# 如何針對 App-V Management Server 設定 Windows Server 2008


安裝 Microsoft Application Virtualization （App-v）管理 Web 服務的 Windows Server 2008 server 上，需要將 Internet Information Services （IIS）安裝為伺服器上的角色。 使用下列程式來設定 Windows Server 2008，以支援應用程式 Vserver 安裝。

**在 Windows Server2008 電腦上安裝 IIS**

1.  在 Windows Server2008 電腦上，按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**管理工具**]，然後按一下 [**伺服器管理員**] 來啟動伺服器管理員。 在伺服器管理員中，以滑鼠右鍵按一下 [**角色**] 節點，然後按一下 [**新增角色**]，啟動 [**新增角色] 嚮導**。

2.  在 [**新增角色] 嚮導**的 [**選取伺服器角色**] 頁面上，選取 [ **Web 服務器（IIS）**]。 出現提示時，請按一下 [**新增必要的功能**] 來新增相依功能。

3.  在 [**選取伺服器角色**] 頁面上，按一下 **[下一步**]，然後再按一下 **[下一步]** 。

4.  在 [**新增角色] 嚮導**中的 [**選取角色服務**] 頁面上：

    1.  在 [**應用程式開發**] 底下，選取 [ **ASP.NET** ]，然後在出現提示時，按一下 [**新增必要的角色服務**] 來新增相依角色服務和功能。

    2.  在 [**安全性**] 底下，選取 [ **Windows 驗證**]。

    3.  在 [**管理工具**] 節點中，選取 [ **IIS 管理腳本與工具**]。 在 [ **IIS6 管理相容性**] 底下，請確定已選取**IIS6 元資料庫相容性**和**IIS6 WMI 相容性**，然後按 **[下一步]**。

5.  在 [**確認安裝選項**] 頁面上，按一下 [**安裝**]，然後完成嚮導的其餘部分。

6.  按一下 [**關閉**] 以結束 [**新增角色] 嚮導**，然後關閉 [伺服器管理員]。

## 相關主題


[Application Virtualization 部署需求](application-virtualization-deployment-requirements.md)

[Application Virtualization 部署與升級檢查清單](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





