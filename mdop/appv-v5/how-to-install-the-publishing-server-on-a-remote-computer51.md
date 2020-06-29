---
title: 如何在遠端電腦上安裝發佈伺服器
description: 如何在遠端電腦上安裝發佈伺服器
author: dansimp
ms.assetid: 1c903f78-0558-458d-a149-d5f6fb55aefb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a085d68305057538228599e35dd9500957342ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800479"
---
# 如何在遠端電腦上安裝發佈伺服器


使用下列程式在不同的電腦上安裝發佈伺服器。 在執行下列程式之前，請先確定資料庫和管理伺服器可供使用。

**在不同的電腦上安裝發佈伺服器**

1. 將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。 若要啟動 App-v 5.1 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。 按一下 **\[安裝\]**。

2. 在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。

3. 在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。** 若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。 按 **\[下一步\]**。

4. 在**功能選取**頁面上，選取 [**發佈伺服器**] 核取方塊，然後按一下 **[下一步]**。

5. 在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。

6. 在 [**設定發佈伺服器設定**] 頁面上，指定下列專案：

   -   發佈伺服器將連接至之管理服務的 URL。 例如， **http://ManagementServerName:12345** 。

   -   指定要用於發佈服務的網站名稱。 如果您沒有自訂名稱，請接受預設值。

   -   針對**埠**系結，請指定將由 app-v 5.1 使用的唯一端口號碼（例如**54321**）。

7. 在 [**準備安裝**] 頁面上，按一下 [**安裝**]。

8. 安裝完成後，發佈伺服器必須在管理伺服器上註冊。 在 App-V 5.1 管理主控台中，請使用下列步驟來註冊伺服器：

   1.  開啟 App-V 5.1 管理伺服器主控台。

   2.  在左窗格中，選取 [**伺服器**]，然後選取 [**註冊新的伺服器**]。

   3.  輸入此伺服器的名稱和描述（如果需要的話），然後按一下 [**新增**]。

9. 若要驗證發佈伺服器是否正常運作，您應該將套件匯入管理伺服器、將套件 entitle 到 AD 群組，然後發佈套件。 使用網際網路瀏覽器，開啟下列 URL： <strong> http://publishingserver:pubport </strong> 。 如果伺服器執行的是正確的資訊，則會顯示類似以下內容：

   ```xml
   <Publishing Protocol="1.0">
     <Packages>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" VersionId="5d03c08f-51dc-4026-8cf9-15ebe3d65a72" PackageUrl="\\server\share\file.appv" />
     </Packages>
     <NoGroup>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" />
     </NoGroup>
   </Publishing>
   ```

   您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[部署 App-V 5.1](deploying-app-v-51.md)

 

 





