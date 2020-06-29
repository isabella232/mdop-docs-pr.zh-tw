---
title: 僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件
description: 僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件
author: dansimp
ms.assetid: 74180d8d-7b0f-460f-b301-53595cde8381
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd9b89e1a1383997d6ebc92f8e034fbf2945823f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800125"
---
# 僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件


如果您是使用 System Center Configuration Manager 整合功能安裝 Microsoft BitLocker 管理和監控（MBAM）2.5，您必須完成本主題所述的先決條件，以及[適用于獨立與 Configuration Manager 整合拓朴的 MBAM 2.5 伺服器先決條件](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)。 您也必須建立或修改 Configuration Manager 整合拓朴所需的 mof 檔案。

## Configuration Manager 整合功能的必要條件


如果您是使用 System Center Configuration Manager 整合拓朴來設定 MBAM，則必須完成 Configuration Manager 所需的其他先決條件。

[Configuration Manager 整合功能的必要條件](prerequisites-for-the-configuration-manager-integration-feature.md)

## 編輯 Configuration （mof）檔案


若要讓用戶端電腦透過 MBAM Configuration Manager 報告來報告 BitLocker 合規性詳細資料，您必須編輯 Configuration. SystemCenter2012 ConfigurationManager 和 Microsoft System Center Configuration Manager 2007 的 mof 檔案。

[編輯 Configuration.mof 檔案](edit-the-configurationmof-file-mbam-25.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a>建立或編輯 Sms \ _def 的 mof 檔案


若要讓用戶端電腦在 MBAM Configuration Manager 報告中報告 BitLocker 相容性詳細資料，您必須建立或編輯 Sms \ _def. mof 檔案。 如果您使用的是 SystemCenter2012 ConfigurationManager，則必須建立檔案。 在 Configuration Manager 2007 中，檔案已經存在，因此您必須編輯現有的檔案，但不需要覆寫該檔案。

[建立或編輯 Sms \ _def 的 mof 檔案](create-or-edit-the-sms-defmof-file-mbam-25.md)


## 相關主題


[MBAM 2.5 的環境準備](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 支援的組態](mbam-25-supported-configurations.md)

[規劃部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

 

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




