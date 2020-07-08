---
title: 使用 MBAM 執行 BitLocker 管理
description: 使用 MBAM 執行 BitLocker 管理
author: dansimp
ms.assetid: 9bfc6c67-f12c-4daa-8f08-5884fb47443c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d261ec4fa789cd331209afe1c2f1858d627209a3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811792"
---
# 使用 MBAM 執行 BitLocker 管理


規劃並部署 Microsoft BitLocker 管理與監控（MBAM）之後，您可以設定並使用它來管理企業 BitLocker 加密。 本節中的資訊說明安裝後的每日 BitLocker 加密管理工作，這些工作是使用 Microsoft BitLocker 管理和監控完成的。

## 使用 MBAM 重設 TPM 封鎖


受信任的平臺模組（TPM）是專門用來提供基本安全相關功能的微晶片，主要涉及加密金鑰。 TPM 通常是安裝在電腦或膝上型電腦的主機板上，並使用硬體匯流排與系統的其餘部分進行通訊。 加入 TPM 的電腦能夠建立加密金鑰並對其進行加密，使其只能由 TPM 解密。

如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。 在 TPM 鎖定前，使用者可以輸入不正確 PIN 的次數，會因製造商而異。 您可以在 [管理和監控] 網站中使用 MBAM 來存取集中式金鑰復原資料系統，在此您可以在提供電腦識別碼及相關的使用者識別碼時，取得 TPM 擁有者密碼檔。

[如何重設 TPM 鎖定](how-to-reset-a-tpm-lockout-mbam-2.md)

## 使用 MBAM 復原磁片磁碟機


當您處理資料加密時（尤其是在企業環境中），請考慮在發生硬體故障、人員或其他可能會遺失加密金鑰的情況下，可以如何復原資料。

MBAM 的加密磁片磁碟機復原功能可確保您可以捕獲並儲存資料，以及在 BitLocker 進入 [恢復] 模式時，可使用所需的工具存取受 BitLocker 保護的磁片卷，或遭到損毀。

[如何修復處於修復模式的磁碟機](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

[如何修復已移動的磁碟機](how-to-recover-a-moved-drive-mbam-2.md)

[如何修復損毀的磁碟機](how-to-recover-a-corrupted-drive-mbam-2.md)

## 使用 MBAM 來判斷遺失的電腦的 BitLocker 加密狀態


您可以使用 MBAM 來判斷已遺失或被盜電腦的最近已知 BitLocker 加密狀態。

[如何判斷遺失的電腦之 BitLocker 加密狀態](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

## 使用自助入口網站來重新取得電腦的存取權


如果最終使用者從 BitLocker 封鎖 Windows，則可以使用本節中的指示來取得 BitLocker 復原金鑰，以重新取得其電腦的存取權。

[如何使用自助入口網站重新取得電腦的存取權](how-to-use-the-self-service-portal-to-regain-access-to-a-computer.md)

## 使用 MBAM 執行 BitLocker 管理的其他資源


[適用於 MBAM 2.0 的操作](operations-for-mbam-20-mbam-2.md)

 

 





