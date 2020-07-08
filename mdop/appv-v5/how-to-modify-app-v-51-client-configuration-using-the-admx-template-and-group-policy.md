---
title: 如何使用 ADMX 範本和群組原則來修改 App-V 5.1 用戶端組態
description: 如何使用 ADMX 範本和群組原則來修改 App-V 5.1 用戶端組態
author: dansimp
ms.assetid: 0d9cf13a-b29c-4c87-a776-15fea34027dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 18363b4fb904d995862ac30634be1350c972d918
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800440"
---
# 如何使用 ADMX 範本和群組原則來修改 App-V 5.1 用戶端組態


使用 Microsoft Application Virtualization （App-v） 5.1 ADMX 範本，以使用 ADMX 範本和群組原則來設定 App-v 5.1 用戶端設定。

**使用群組原則修改 App-v 5.1 用戶端設定**

1.  若要修改 App-v 5.1 用戶端設定，請找出可在 App-v 5.1 中使用的**ADMXTemplate**檔案。

    **記事** 使用下列連結下載 app-v 5.1 **ADMX 範本**： <https://go.microsoft.com/fwlink/p/?LinkId=393941> 。

     

2.  在您管理群組原則的電腦（通常是網網域控制站），請將範本**admx**檔案複製到下列目錄： ** &lt; 安裝磁片磁碟機 &gt; \\ Windows \\ PolicyDefinitions**。

    接著，在同一部電腦上，將**adml**檔案複製到下列目錄： ** &lt; InstallationDrive &gt; \\ Windows \\ PolicyDefinitions \ en-us**。

3.  將檔案複製到 [群組原則管理主控台] 後，若要修改與您的 App 相關聯的原則-v 5.1 用戶端，請流覽至 [**電腦**設定  /  **原則**] 的 [  /  **管理範本**  /  **系統**]  /  **App-v**。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[部署 App-V 5.1](deploying-app-v-51.md)

[關於 Client 組態設定](about-client-configuration-settings51.md)

 

 





