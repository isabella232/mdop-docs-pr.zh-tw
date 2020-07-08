---
title: 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦
description: 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦
author: dansimp
ms.assetid: 3a7639e0-468e-4496-8be2-ed29b8e07c53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b67533a555da4dabec6654ed3f95f91ad8d37bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810580"
---
# 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦


本主題說明如何將 MBAM 用戶端部署到終端使用者的電腦。 您可以透過電子軟體發佈系統（例如 Active Directory 網域服務或 MicrosoftSystemCenterConfiguration 管理員）部署 MBAM 用戶端。

若要將 MBAM 用戶端部署為 Windows 部署的一部分，請參閱[如何使用 MBAM 來啟用 BitLocker，做為 Windows 部署的一部分](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)。

在您開始 MBAM 用戶端部署之前，請先查看[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。

**若要將 MBAM 用戶端部署到桌上型電腦或膝上型電腦**

1.  找出 MBAM 軟體隨附的 MBAM 用戶端安裝檔案。

2.  使用 Active Directory 網域服務，或 MicrosoftSystemCenterConfiguration Manager 等企業軟體部署工具，將 Windows 安裝程式套件部署至目的電腦。

3.  設定 [分發設定] 或 [群組原則] 設定，以執行 MBAM 用戶端安裝檔。

    成功安裝之後，MBAM 用戶端會套用從網網域控制站接收的群組原則設定，以開始 BitLocker 磁片磁碟機加密和管理功能。

    **重要** 如果遠端桌面通訊協定連線處於作用中狀態，則 MBAM 用戶端不會啟動 BitLocker 磁片磁碟機加密動作。 必須關閉所有遠端主控台連線，且必須先登入物理主機，然後才能開始 BitLocker 磁碟機加密。

     


## 相關主題
[部署 MBAM 2.5 用戶端](deploying-the-mbam-25-client.md)

[MBAM 2.5 用戶端部署規劃](planning-for-mbam-25-client-deployment.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





