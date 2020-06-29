---
title: 管理 MBAM 2.0 功能
description: 管理 MBAM 2.0 功能
author: dansimp
ms.assetid: 065e0704-069e-4372-9b86-0b57dd7638dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 35bb855e185ad8e3fa6880853938074cf6185a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809998"
---
# 管理 MBAM 2.0 功能


完成所有必要的規劃，然後部署 Microsoft BitLocker 管理與監控（MBAM）之後，您可以設定並使用它來管理整個企業的 BitLocker 加密本區段中的資訊說明安裝後的日常 Microsoft BitLocker 管理及監視功能作業工作。

## 管理 MBAM 管理員角色


完成所有伺服器功能的 MBAM 設定之後，系統必須授與系統管理員的存取權。 最佳做法是將管理或使用 MBAM 伺服器功能的系統管理員指派給 Active Directory 網域服務安全性群組，然後將那些群組新增至適當的 MBAM 系統管理本機群組。

[如何管理 MBAM 系統管理員角色](how-to-manage-mbam-administrator-roles-mbam-2.md)

## 管理 BitLocker 加密免除


MBAM 可讓您將加密免除授權給不需要或不想要加密之磁片磁碟機的特定使用者。 當公司擁有不需要加密的電腦（例如在開發或測試中使用的電腦），或是不支援 BitLocker 的舊版電腦時，通常會使用電腦例外。 在某些情況下，當地法律也可能需要特定電腦不加密。

[如何管理使用者 BitLocker 加密豁免](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)

## 使用 [控制台] 管理 MBAM 用戶端 BitLocker 加密選項


MBAM 提供一個名為 [BitLocker 加密選項] 的自訂控制台，這些面板會出現在 [**系統及安全性**] 下。 MBAM [控制台] 可用來解除鎖定加密的固定和移除磁片磁碟機，也可管理 PIN 或密碼。

**記事** 這個自訂的 [控制台] 不會取代預設的 Windows BitLocker [控制台]。

 

[如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-2.md)

## 管理 MBAM 功能的其他資源


[適用於 MBAM 2.0 的操作](operations-for-mbam-20-mbam-2.md)

 

 





