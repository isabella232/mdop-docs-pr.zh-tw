---
title: 使用 MBAM 執行 BitLocker 管理
description: 使用 MBAM 執行 BitLocker 管理
author: dansimp
ms.assetid: 2d24390a-87bf-48b3-96a9-3882d6f2a15c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d0de3711d5b7c3696783a054ee7c7f8220b5356
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811427"
---
# 使用 MBAM 執行 BitLocker 管理


在您部署 Microsoft BitLocker 管理和監控（MBAM）之後，您可以設定及使用 MBAM 來管理企業 BitLocker 加密。 本節說明安裝後的 BitLocker 加密管理工作（可以使用 MBAM 來完成）。

## 使用 MBAM 重設 TPM 鎖定


受信任的平臺模組（TPM）微晶片提供基本的安全性相關功能。 這些函數主要是由使用加密金鑰所完成。 TPM 通常是安裝在電腦或膝上型電腦的主機板上，並使用硬體匯流排與系統的其餘部分進行通訊。 加入 TPM 的電腦可以建立只能由 TPM 解密的加密金鑰。 如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。 在 TPM 鎖定前，使用者可以輸入不正確 PIN 的次數，會因製造商而異。 MBAM 管理網站上的金鑰復原資料系統可讓您取得 reset TPM 擁有者密碼檔。

[如何重設 TPM 鎖定](how-to-reset-a-tpm-lockout-mbam-1.md)

## 使用 MBAM 復原磁片磁碟機


請確定您知道如何在硬體失敗、人員中的變更或加密金鑰遺失的其他情況下，嘗試從加密的磁片恢復資料。 MBAM 的加密磁片磁碟機復原功能提供了在大量移至 [恢復] 模式、移動或損毀時，可存取受 BitLocker 保護的卷所需的資料和可用性的捕獲與儲存。

[如何修復處於修復模式的磁碟機](how-to-recover-a-drive-in-recovery-mode-mbam-1.md)

[如何修復已移動的磁碟機](how-to-recover-a-moved-drive-mbam-1.md)

[如何修復損毀的磁碟機](how-to-recover-a-corrupted-drive-mbam-1.md)

## 使用 MBAM 來判斷遺失的電腦的 BitLocker 加密狀態


當您使用 MBAM 時，您可以判斷已遺失或被盜電腦的最近已知 BitLocker 加密狀態。

[如何判斷遺失的電腦的 BitLocker 加密狀態](how-to-determine-the-bitlocker-encryption-state-of-a-lost-computers-mbam-1.md)

## 使用 MBAM 執行 BitLocker 管理的其他資源


[適用於 MBAM 1.0 的操作](operations-for-mbam-10.md)

 

 





