---
title: 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦
description: 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦
author: dansimp
ms.assetid: 56744922-bfdd-48f6-ae01-645ff53b64a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 49340ae970dafc9d263f5564e7981a402da40f19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800236"
---
# 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦


Microsoft BitLocker 管理和監控（MBAM）用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。 您可以透過電子軟體發佈系統（例如 Active Directory 網域服務或 MicrosoftSystemCenterConfigurationManager）部署用戶端，將 BitLocker 用戶端整合到組織中。

**記事** 若要查看 Microsoft BitLocker 管理及監視用戶端系統需求，請參閱[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。

 

**若要將 MBAM 用戶端部署到桌上型電腦或膝上型電腦**

1.  找出 MBAM 軟體隨附的 MBAM 用戶端安裝檔案。

2.  使用 Active Directory 網域服務或企業軟體部署工具（例如 MicrosoftSystemCenterConfigurationManager），將 Windows 安裝程式套件部署至目的電腦。

3.  設定 [發佈設定] 或 [群組原則]，以執行 MBAM 用戶端安裝檔。 成功安裝之後，MBAM 用戶端會套用從網網域控制站接收的群組原則設定，以開始 BitLocker 加密和管理功能。 如需 MBAM 群組原則設定的詳細資訊，請參閱[規劃 MBAM 2.0 群組原則需求](planning-for-mbam-20-group-policy-requirements-mbam-2.md)。

    **重要** 如果遠端桌面通訊協定連線處於作用中狀態，則 MBAM 用戶端將無法啟動 BitLocker 加密動作。 必須先關閉所有遠端主控台連線，才能開始 BitLocker 加密。

     

## 相關主題


[部署 MBAM 2.0 用戶端](deploying-the-mbam-20-client-mbam-2.md)

 

 





