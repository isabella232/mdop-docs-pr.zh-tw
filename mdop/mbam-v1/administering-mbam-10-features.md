---
title: 管理 MBAM 1.0 功能
description: 管理 MBAM 1.0 功能
author: dansimp
ms.assetid: dd9a9eff-f1ad-4af3-85d9-c19131a4ad22
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a99ac556227c0f113fb20f3aca32d21c204877b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808625"
---
# 管理 MBAM 1.0 功能


完成所有必要的 Microsoft BitLocker 管理和監控（MBAM）規劃與部署之後，您可以設定及使用 MBAM 來管理企業 BitLocker 加密。 本節中的資訊說明安裝後的日常 MBAM 功能作業作業。

## 管理 MBAM 管理員角色


完成所有伺服器功能的 MBAM 設定之後，系統必須授與系統管理員對這些伺服器功能的存取權。 最佳做法是，要管理或使用 MBAM 伺服器功能的系統管理員應該指派給 Active Directory 安全性群組，然後將那些群組新增至適當的 MBAM 系統管理本機群組。

[如何管理 MBAM 系統管理員角色](how-to-manage-mbam-administrator-roles-mbam-1.md)

## 管理硬體相容性


MBAM 硬體相容性功能可協助您確保只有您指定為支援 BitLocker 的電腦硬體會受到加密。 開啟此功能時，bit _admmontla 只會加密標示為相容的電腦。

**重要** 關閉此功能時，系統會將部署 MBAM 原則的所有電腦加密。

 

如果您部署了 [允許硬體相容性檢查] 群組原則，MBAM 可以收集用戶端電腦的品牌與型號資訊。 如果您設定此原則，當您在用戶端電腦上部署 MBAM 用戶端時，MBAM 代理會向 MBAM 伺服器報告電腦品牌和模型資訊。

[如何管理硬體相容性](how-to-manage-hardware-compatibility-mbam-1.md)

[如何管理使用者 BitLocker 加密豁免](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)

## 管理 BitLocker 加密免除


MBAM 可以從 BitLocker 加密中授予兩種形式的免除：電腦豁免與使用者豁免。 當公司擁有不需要加密的電腦（例如在開發或測試中使用的電腦），或是不支援 BitLocker 的舊版電腦時，通常會使用電腦例外。 在某些情況下，當地法律也可能需要特定電腦不加密。 您也可以選擇免除不需要或不想要加密其磁片磁碟機的使用者。

[如何管理電腦 BitLocker 加密豁免](how-to-manage-computer-bitlocker-encryption-exemptions.md)

## 使用 [控制台] 管理 MBAM 用戶端 BitLocker 加密選項


如果透過群群組原則物件（GPO）啟用，則會在 [**系統及安全性**] 下提供一個名為 [BitLocker 加密選項] 的自訂 MBAM [控制台]。 這個自訂的 [控制台] 會取代預設的 Windows BitLocker [控制台]。 [MBAM 控制台] 可讓您解除鎖定加密的磁碟機（固定和移除），也可協助您管理 PIN 或密碼。

[如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-1.md)

## 管理 MBAM 功能的其他資源


[適用於 MBAM 1.0 的操作](operations-for-mbam-10.md)

 

 





