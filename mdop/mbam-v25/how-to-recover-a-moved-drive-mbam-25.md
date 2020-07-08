---
title: 如何修復已移動的磁碟機
description: 如何修復已移動的磁碟機
author: dansimp
ms.assetid: 0d38ce7e-bc64-473e-ae85-99b7099ca758
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 9e7e03846e0a94902b699377043237c651939a07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809897"
---
# 如何修復已移動的磁碟機
本主題說明如何使用管理和監控網站（也稱為說明服務台）來復原在由 Microsoft BitLocker 管理和監控（MBAM）加密之後所移動的作業系統磁片磁碟機。 移動磁碟機後，就不會再接受先前電腦上所用的 PIN，因為受信任的平臺模組（TPM）晶片已變更。 若要復原移動的磁片磁碟機，您必須取得修復金鑰識別碼，才能取得恢復密碼。

若要復原移動的磁片磁碟機，您必須使用 [管理] 和 [監視] 網站的 [**磁碟機恢復**] 區域。 若要存取**磁片磁碟機**復原區域，您必須獲指派 MBAM [支援人員] 的使用者角色或 MBAM [高級支援人員] 使用者角色。 如需有關這些角色的詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。

**若要復原移動的磁片磁碟機**
1.  在包含已移動的磁片磁碟機的電腦上，在 Windows 復原環境（WinRE）模式中啟動電腦，或使用 Microsoft 診斷與修復工具組（DaRT）啟動電腦。

2.  電腦開始使用 WinRE 或 DaRT 之後，MBAM 會將移動的作業系統磁片磁碟機視為固定的資料磁碟機。 MBAM 接著會顯示磁碟機的復原密碼識別碼，並要求您提供復原密碼。

    **記事** 在某些情況下，您可能可以在啟動期間按一下 [**我忘記 PIN** ]，然後輸入 [恢復] 模式來顯示覆原金鑰識別碼。

     

3.  使用復原金鑰識別碼來檢索復原密碼，然後從管理和監控網站解除鎖定磁片磁碟機。 如需相關指示，請參閱[如何在復原模式中復原磁片磁碟機](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)。

    如果移動的磁片磁碟機已設定為在原始電腦上使用 TPM 晶片，請完成下列其他步驟。 否則，恢復程式就完成了。

4.  解除鎖定磁片磁碟機並完成開始程式後，請以 WinRE 模式開啟命令提示字元，並使用 `manage-bde` 命令來解密磁片磁碟機。 使用這個工具是移除 TPM 的唯一方法，以及不含原始 TPM 晶片的 PIN 保護器。 如需有關命令的資訊 `manage-bde` ，請參閱[manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)。

5.  完成移除後，請正常啟動電腦。 MBAM agent 現在將強制執行原則，以使用新電腦的 TPM 加上 PIN 來加密磁片磁碟機。



## 相關主題


[使用 MBAM 2.5 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





