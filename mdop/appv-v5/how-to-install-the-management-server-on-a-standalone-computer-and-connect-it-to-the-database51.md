---
title: 如何在獨立電腦上安裝 Management Server 並將它連線到資料庫
description: 如何在獨立電腦上安裝 Management Server 並將它連線到資料庫
author: dansimp
ms.assetid: 3f83c335-d976-4abd-b8f8-d7f5e50b4318
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2cce96f914f65e7432b5ed9e7c5ecb1a6306990
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800487"
---
# 如何在獨立電腦上安裝 Management Server 並將它連線到資料庫


使用下列程式在獨立電腦上安裝管理伺服器，並將它連線至資料庫。

**在獨立電腦上安裝管理伺服器並將它連線至資料庫**

1.  將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。 若要啟動 App-v 5.1 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。 按一下 **\[安裝\]**。

2.  在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。

3.  在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。** 若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。 按 **\[下一步\]**。

4.  在**功能選取**頁面上，選取 [**管理伺服器**] 核取方塊，然後按一下 **[下一步]**。

5.  在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。

6.  在 [**設定現有的管理資料庫**] 頁面上，選取 [**使用遠端 SQL Server**]，然後輸入執行 Microsoft sql sql 的電腦的電腦名稱稱（例如**SqlServerMachine**）。

    **注意**  
    如果 Microsoft SQL Server 部署在同一台伺服器上，請選取 [**使用本機 SQL server**]。



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this management server will use, for example **AppvManagement**.
~~~

7. 在 [**設定管理伺服器設定**] 頁面上，指定將會連線至管理主控台以進行管理的 AD 群組或帳戶（例如**MyDomain\\MyUser**或**MyDomain\\AdminGroup**）。 您指定的帳號或 AD 群組將會透過管理主控台啟用以管理伺服器。 您可以在安裝後使用管理主控台新增其他使用者或群組

   指定您要用於管理服務的**網站名稱**。 如果您沒有自訂名稱，請接受預設值。 針對**埠**系結，請指定要使用的唯一端口號碼（例如**12345**）。

8. 按一下 **\[安裝\]**。

9. 若要確認安裝程式已順利完成，請開啟網頁瀏覽器，然後輸入下列 URL： http://managementserver:portnumber/Console 。 如果安裝成功，您應該會看到 [**管理主控台**] 出現，但不會顯示任何錯誤訊息或警告。

   您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[部署 App-V 5.1](deploying-app-v-51.md)









