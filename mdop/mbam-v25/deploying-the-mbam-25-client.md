---
title: 部署 MBAM 2.5 用戶端
description: 部署 MBAM 2.5 用戶端
author: dansimp
ms.assetid: 0a96a0ee-f280-49d9-a244-88f4147fe9fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 375af8966c8e66a58baec5065d065891187899fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811660"
---
# 部署 MBAM 2.5 用戶端


Microsoft BitLocker 管理和監控（MBAM）用戶端軟體可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。 您可以透過電子軟體發佈系統（例如 Active Directory 網域服務）部署用戶端，或直接加密用戶端電腦做為初始影像程式的一部分，將 BitLocker 用戶端整合到組織中。

根據您部署 Microsoft BitLocker 管理和監視用戶端軟體的時間，您可以在最終使用者接收電腦之前，或透過使用企業軟體部署系統來部署 MBAM 用戶端軟體，在組織中的電腦上啟用 BitLocker 磁碟機加密。

## 將 MBAM 用戶端部署到桌上型電腦或膝上型電腦


在設定群組原則設定之後，您可以使用企業軟體部署系統產品（例如 MicrosoftSystemCenter2012 ConfigurationManager 或 Active Directory 網域服務），將 MBAM 用戶端安裝 Windows 安裝程式檔案部署至目的電腦。 您可以使用32位或64位 MbamClientSetup.exe 檔案，或是32或 64 MBAMClient.msi 位的檔案，這些檔案是由 MBAM 用戶端軟體所提供。 如需有關部署 MBAM 群組原則設定的詳細資訊，請參閱[部署 MBAM 2.5 群組原則物件](deploying-mbam-25-group-policy-objects.md)。

**記事** 從 MBAM 2.5 SP1 開始，MBAM 產品不再隨附個別的 MSI。 不過，您可以從隨附于產品的可執行檔（.exe）中解壓縮 MSI。

 

[如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25.md)

## 部署 MBAM 用戶端做為 Windows 部署的一部分


在已集中接收和設定電腦的組織中，您可以安裝 MBAM 用戶端，在每個電腦上管理 BitLocker 磁碟機加密，然後再寫入任何使用者資料。 此程式的優點是，每個電腦都是符合 BitLocker 磁片磁碟機加密規範的。 這個方法不依賴使用者的動作，因為系統管理員已經將電腦加密。 這個案例的主要假設是，在電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。 如果已將群組原則設定設定為 [需要 PIN]，系統會在收到原則之後提示使用者設定 PIN。

[如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)

## 如何使用命令列部署 MBAM 用戶端


本節說明如何使用命令列來安裝 MBAM 用戶端。

[如何使用命令列部署 MBAM 用戶端](how-to-deploy-the-mbam-client-by-using-a-command-line.md)

## 部署 MBAM 用戶端的其他資源


[部署 MBAM 2.5](deploying-mbam-25.md)



## 相關主題


[部署 MBAM 2.5](deploying-mbam-25.md)

[MBAM 2.5 規劃](planning-for-mbam-25.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





