---
title: 如何修復已移動的磁碟機
description: 如何修復已移動的磁碟機
author: dansimp
ms.assetid: 697cd78d-962c-411e-901a-2e9220ba6552
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bd0d43f2eea95fe71225a50e7fa68d4fb1c35485
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810929"
---
# 如何修復已移動的磁碟機


當您移動使用 Microsoft BitLocker 管理和監視（MBAM）加密的作業系統磁片磁碟機時，由於受信任的平臺模組（TPM）晶片的變更，磁片磁碟機不會接受先前電腦上所使用的 PIN。 若要使用移動的磁片磁碟機，您需要取得修復金鑰識別碼以取得復原密碼的方式。 使用下列程式來復原已移動的磁片磁碟機。

**若要復原移動的磁片磁碟機**

1.  在包含已移動的磁片磁碟機的電腦上，在 Windows 復原環境（WinRE）模式中啟動電腦，或使用 Microsoft 診斷與修復工具組（DaRT）啟動電腦。

2.  電腦開始使用 WinRE 或 DaRT 之後，Microsoft BitLocker 管理和監控就會將移動的作業系統磁片磁碟機視為資料硬碟。 MBAM 接著會顯示磁碟機的復原密碼識別碼，並要求您提供復原密碼。

    **記事** 在某些情況下，您可能可以在啟動期間按一下 [**我忘記 PIN** ]，然後輸入 [恢復] 模式來顯示覆原金鑰識別碼。

     

3.  使用復原金鑰識別碼來檢索復原密碼，然後從管理和監控網站解除鎖定磁片磁碟機。

4.  如果移動的磁片磁碟機已設定為在原始電腦上使用 TPM 晶片，您必須在解除硬碟鎖定並完成開始程式後採取其他步驟。 在 WinRE 模式中，開啟命令提示字元，然後使用 [ **manage-bde** ] 工具來解密磁片磁碟機。 使用這個工具是移除 TPM 加上不含原始 TPM 晶片的 PIN 保護器的唯一方法。

5.  完成移除後，請正常啟動電腦。 MBAM 代理程式現在將強制執行原則，以新電腦的 TPM 加上 PIN 來加密磁片磁碟機。

## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





