---
title: 部署 MBAM 2.0 用戶端
description: 部署 MBAM 2.0 用戶端
author: dansimp
ms.assetid: 3dd584fe-2a54-40f0-9bab-13ea74040b01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa42c8ab3adc273f0e00ba56a59f487deba89c6f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809962"
---
# 部署 MBAM 2.0 用戶端


Microsoft BitLocker 管理和監控（MBAM）用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。 您可以透過電子軟體發佈系統（例如 Active Directory 網域服務）部署用戶端，或直接加密用戶端電腦做為初始影像程式的一部分，將 BitLocker 用戶端整合到組織中。

根據您部署 Microsoft BitLocker 管理和監視用戶端的時機，您可以在最終使用者接收電腦前，或透過使用企業軟體部署系統來部署 MBAM 用戶端軟體，在組織中的電腦上啟用 BitLocker 加密。

## 將 MBAM 用戶端部署到桌上型電腦或膝上型電腦


設定群組原則之後，您可以使用企業軟體部署系統產品（例如 Microsoft System Center Configuration Manager 2012 或 Active Directory 網域服務），將 MBAM 用戶端安裝 Windows 安裝程式檔案部署至目的電腦。 您可以使用32位或64位 MbamClientSetup.exe 檔案，或是使用 MBAM 軟體提供的32位或 64 MBAMClient.msi 檔案來部署用戶端。 如需有關部署 MBAM 群組原則物件的詳細資訊，請參閱[部署 MBAM 2.0 群組原則物件](deploying-mbam-20-group-policy-objects-mbam-2.md)。

[如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-2.md)

## 部署 MBAM 用戶端做為 Windows 部署的一部分


在已集中接收和設定電腦的組織中，您可以安裝 MBAM 用戶端，在每個電腦上管理 BitLocker 加密，然後再寫入任何使用者資料。 此程式的優點是，每個電腦都是相容的 BitLocker 加密。 這個方法不依賴使用者的動作，因為系統管理員已經將電腦加密。 這個案例的主要假設是，在電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。 如果已將群組原則設定為需要 PIN，則會在使用者收到群組原則之後提示使用者設定 PIN。

[如何將 MBAM 用戶端部署為 Windows 部署的一部分](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-2.md)

## 如何使用命令列安裝 MBAM 用戶端


本節說明如何使用命令列來安裝 MBAM 用戶端。

[如何使用命令列安裝 MBAM 用戶端](how-to-use-a-command-line-to-install-the-mbam-client.md)

## 部署 MBAM 用戶端的其他資源


[部署](deploying-mbam-20-mbam-2.md)[MBAM 2.0 用戶端部署的](planning-for-mbam-20-client-deployment-mbam-2.md)MBAM 2.0 規劃

 

 





