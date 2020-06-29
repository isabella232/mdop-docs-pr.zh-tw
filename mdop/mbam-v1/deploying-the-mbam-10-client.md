---
title: 部署 MBAM 1.0 用戶端
description: 部署 MBAM 1.0 用戶端
author: dansimp
ms.assetid: f7ca233f-5035-4ff9-ab3a-f2453b4929d1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dee8c2f4a9b398c9f0797ada35e4c36610c755b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809633"
---
# 部署 MBAM 1.0 用戶端


Microsoft BitLocker 管理和監控（MBAM）用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。 您可以透過使用 Active Directory 網域服務之類的工具部署用戶端，或直接加密用戶端電腦（作為初始影像處理常式的一部分），將 BitLocker 用戶端整合到組織中。

根據您部署 MBAM 用戶端的時機，您可以在您組織中的電腦上或在最終使用者接收電腦之前或之後啟用 BitLocker 加密。 若要控制此時間，您可以使用企業軟體部署系統來設定 [群組原則] 並部署 MBAM 用戶端軟體。

您可以在組織中使用其中一種或兩種方法。 如果您同時使用這兩種方法，就可以改善合規性、報告和金鑰復原支援。

## 將 MBAM 用戶端部署到桌上型電腦或膝上型電腦


在您設定好群組原則之後，您可以將 MBAM 用戶端安裝 Windows 安裝程式檔案部署至目的電腦。 您可以使用企業軟體部署系統產品（例如 Microsoft System Center 2012 Configuration Manager 或 Active Directory 網域服務）來執行此操作。 兩個可用的 MBAM 用戶端安裝 Windows 安裝程式檔案是 MBAMClient-64bit.msi 並 MBAMClient-32bit.msi。 這些檔案是由 MBAM 軟體提供。 如需如何部署 MBAM 群組原則物件的詳細資訊，請參閱[部署 MBAM 1.0 群組原則物件](deploying-mbam-10-group-policy-objects.md)。

[如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-1.md)

## 部署 MBAM 用戶端做為 Windows 部署的一部分


在某些組織中，新的電腦會集中接收並設定。 這種情況可讓系統管理員在任何使用者資料寫入電腦之前，安裝 MBAM 用戶端來管理每個電腦上的 BitLocker 加密。 這個方法可協助確保電腦正確地加密，因為系統管理員會執行動作，而不需要依靠最終使用者的動作。 這個案例的主要假設是，在電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。

[如何將 MBAM 用戶端部署為 Windows 部署的一部分](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-1.md)

## 部署 MBAM 用戶端的其他資源


[部署 MBAM 1.0](deploying-mbam-10.md)

[MBAM 1.0 用戶端部署規劃](planning-for-mbam-10-client-deployment.md)

 

 





