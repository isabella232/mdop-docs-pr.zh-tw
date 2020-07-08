---
title: 如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫
description: 如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫
author: dansimp
ms.assetid: d186bdb7-e522-4124-bc6d-7d5a41ba8266
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f20f1ce16c3f0168d1c797efd816d4125c0f1f53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800480"
---
# 如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫


使用下列程式在獨立電腦上安裝報表伺服器，並將它連線至資料庫。

**重要**  
在執行下列程式之前，您應該閱讀並瞭解[app-v 5.0 報告](about-app-v-50-reporting.md)。



**在獨立電腦上安裝報表伺服器並將它連線至資料庫**

1.  將 App-v 5.0 server 安裝檔案複製到您要安裝它的電腦上。 若要啟動 App-v 5.0 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。 按一下 **\[安裝\]**。

2.  在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。

3.  在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。** 若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。 按 **\[下一步\]**。

4.  在**功能選取**頁面上，選取 [**報表伺服器**] 核取方塊，然後按一下 **[下一步]**。

5.  在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。

6.  在 [**設定現有的報表資料庫**] 頁面上，選取 [**使用遠端 SQL server**]，然後輸入執行 Microsoft SQL server 之電腦的電腦名稱稱，例如**SqlServerMachine**。

    **注意**  
    如果 Microsoft SQL Server 部署在同一台伺服器上，請選取 [**使用本機 SQL server**]。



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this reporting server will use, for example **AppvReporting**.
~~~

7. 在 [**設定報表伺服器設定**] 頁面上。

   -   指定您要用於報表服務的網站名稱。 如果您沒有自訂名稱，請將預設值保持不變。

   -   針對**埠**系結，請指定將由 app-v 5.0 使用的唯一端口號碼（例如**55555**）。 您也應該確保指定的埠未由其他網站使用。

8. 按一下 **\[安裝\]**。

   您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[關於 App-V 5.0 報表](about-app-v-50-reporting.md)

[部署 App-V 5.0](deploying-app-v-50.md)

[如何使用 PowerShell 在 App-V 5.0 用戶端上啟用報表](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)









