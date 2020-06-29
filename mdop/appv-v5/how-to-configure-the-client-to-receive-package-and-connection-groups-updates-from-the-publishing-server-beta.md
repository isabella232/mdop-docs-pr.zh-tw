---
title: 如何設定用戶端以從發佈伺服器接收套件與連線群組更新
description: 如何設定用戶端以從發佈伺服器接收套件與連線群組更新
author: dansimp
ms.assetid: f5dfd96d-4b63-468c-8d93-9dfdf47c28fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e9df1f8b324430449d8d1dd3624d9f1157968a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800581"
---
# 如何設定用戶端以從發佈伺服器接收套件與連線群組更新


使用 App-v 5.0 發佈伺服器部署套件和連線群組非常有用，因為它提供單一點管理和高伸縮性。

使用下列步驟，將 App-v 5.0 用戶端設定為從發佈伺服器接收更新。

**記事** 針對下列程式，管理伺服器已安裝在名為**MyMgmtSrv**的電腦上，且發佈伺服器已安裝在名為**MyPubSrv**的電腦上。

 

**若要將 App-v 5.0 用戶端設定為從發佈伺服器接收更新**

1.  部署 app-v 5.0 管理與發佈伺服器，並新增必要的套件和連線群組。 如需新增套件和連線群組的詳細資訊，請參閱[如何使用管理主控台新增或升級套件](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)，以及[如何建立連線群組](how-to-create-a-connection-group.md)。

2.  若要開啟管理主控台，請按一下下列連結，開啟瀏覽器，並輸入以下內容： http://MyMgmtSrv/AppvManagement/Console.html 在網頁瀏覽器中，然後匯入、發佈及 entitle 特定使用者組所需的所有套件和連線群組。

3.  在執行 App-v 5.0 用戶端的電腦上，開啟提升許可權的 PowerShell 命令提示字元，執行下列命令：

    **AppvPublishingServer-Name ABC-URL HTTP://MyPubSrv/AppvPublishing**

    這個命令會設定指定的發佈伺服器。 您應該會看到類似以下的輸出：

    Id：1

    SetByGroupPolicy： False

    名稱： ABC

    URL： HTTP://MyPubSrv/AppvPublishing

    GlobalRefreshEnabled： False

    GlobalRefreshOnLogon： False

    GlobalRefreshInterval：0

    GlobalRefreshIntervalUnit： Day

    UserRefreshEnabled： True

    UserRefreshOnLogon： True

    UserRefreshInterval：0

    UserRefreshIntervalUnit： Day

    傳回的識別碼（在此例中為1）

4.  在執行 App-V 5.0 用戶端的電腦上，開啟 PowerShell 命令提示字元，然後輸入下列命令：

    **同步處理-AppvPublishingServer-ServerId 1**

    根據管理伺服器上設定的套件和連線群組的權利，該命令會針對您需要針對此特定用戶端新增或移除之套件與連接群組的發佈伺服器進行查詢。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)

 

 





