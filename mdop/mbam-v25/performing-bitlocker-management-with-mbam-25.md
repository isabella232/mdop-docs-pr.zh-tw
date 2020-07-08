---
title: 使用 MBAM 2.5 執行 BitLocker 管理
description: 使用 MBAM 2.5 執行 BitLocker 管理
author: dansimp
ms.assetid: 068f3ee0-300c-4083-ba18-7065eef997ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a0ee5802f945176914c56659e0ff7e34e93a969
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811498"
---
# 使用 MBAM 2.5 執行 BitLocker 管理


規劃並部署 Microsoft BitLocker 管理與監控（MBAM）之後，您可以設定並使用它來管理整個企業的 BitLocker 磁片磁碟機加密。 本節中的資訊說明安裝後的 BitLocker 加密管理工作（使用 Microsoft BitLocker 管理和監控完成）。

## 重設 TPM 封鎖


受信任的平臺模組（TPM）是專門用來提供基本安全相關功能的微晶片，主要涉及加密金鑰。 TPM 通常安裝在電腦的主機板上，而且它會使用主機匯流排配接器與系統的其餘部分進行通訊。 在併入 TPM 的電腦上，您可以建立加密金鑰並加以加密，以便只可由 TPM 解密。

如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。 在 TPM 鎖定之前，使用者可以輸入不正確 PIN 的次數，視製造商而定。 您可以在 [管理與監控] 網站上使用 MBAM 來存取集中式金鑰復原資料系統，您可以在提供電腦識別碼及相關聯的使用者識別碼時，取得 TPM 擁有者密碼檔案。

[如何重設 TPM 鎖定](how-to-reset-a-tpm-lockout-mbam-25.md)

## 復原磁片磁碟機


當您處理資料加密時（尤其是在企業環境中），請考慮在發生硬體故障、人員或其他可能會遺失加密金鑰的情況下，可以如何復原資料。

MBAM 中的加密磁片磁碟機復原功能可確保在 BitLocker 進入復原模式、移動或損毀時，可以捕獲並儲存資料，以及使用必要的工具存取受 BitLocker 保護的磁片。

[如何修復處於修復模式的磁碟機](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)

[如何修復已移動的磁碟機](how-to-recover-a-moved-drive-mbam-25.md)

[如何修復損毀的磁碟機](how-to-recover-a-corrupted-drive-mbam-25.md)

## 判斷遺失的電腦的 BitLocker 加密狀態


您可以使用 MBAM 來判斷已遺失或被盜電腦的最近已知 BitLocker 加密狀態。

[如何判斷遺失的電腦之 BitLocker 加密狀態](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)

## 使用自助入口網站來重新取得電腦的存取權


如果最終使用者從 BitLocker 封鎖 Windows，則可以使用本節中的指示來取得 BitLocker 復原金鑰，以重新取得其電腦的存取權。

[如何使用自助入口網站重新取得電腦的存取權](how-to-use-the-self-service-portal-to-regain-access-to-a-computer-mbam-25.md)



## 相關主題


[適用於 MBAM 2.5 的操作](operations-for-mbam-25.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





