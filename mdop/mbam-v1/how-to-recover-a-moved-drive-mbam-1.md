---
title: 如何修復已移動的磁碟機
description: 如何修復已移動的磁碟機
author: dansimp
ms.assetid: 0c7199d8-9463-4f44-9af3-b70eceeaff1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e73e0878a3102d56494feb33efa69182029988c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800216"
---
# 如何修復已移動的磁碟機


當您移動先前已使用 Microsoft BitLocker 管理和監控（MBAM）加密的作業系統磁片磁碟機時，您必須解決特定問題。 將 PIN 附加到新電腦之後，此磁碟機將不會接受在先前電腦中使用的啟動 PIN。 因為信任的平臺模組（TPM）晶片變更，所以系統會認為 PIN 無效。 您必須取得復原金鑰識別碼，才能取得恢復密碼，以便使用移動的磁片磁碟機。 若要這樣做，請使用下列程式。

**若要復原移動的磁片磁碟機**

1.  在包含已移動的磁片磁碟機的電腦上，從 Windows 復原環境（WinRE）模式開始，或使用 Microsoft Diagnostics 和復原工具組（DaRT）來啟動電腦。

2.  電腦開始使用 WinRE 或 DaRT 之後，MBAM 會將移動的作業系統磁片磁碟機視為資料磁片磁碟機。 MBAM 接著會顯示磁碟機的復原密碼識別碼，並要求您提供復原密碼。

    **記事** 在某些情況下，您可能可以在啟動程式中，按一下 [**我不在 PIN** ]，進入復原模式。 這也會顯示 [復原金鑰識別碼]。

     

3.  在 MBAM 管理網站上，使用復原金鑰識別碼來取得恢復密碼並解除鎖定磁片磁碟機。

4.  如果移動的磁片磁碟機已設定為在原始電腦上使用 TPM 晶片，您必須在解除硬碟鎖定並完成開始程式後採取其他步驟。 在 WinRE 模式中，開啟命令提示字元，然後使用 [ **manage-bde** ] 工具來解密磁片磁碟機。 此工具的使用方式是在沒有原始 TPM 晶片的情況下，移除 TPM 外加 PIN 保護的唯一方法。

5.  完成移除之後，請正常啟動系統。 MBAM 代理程式將繼續執行原則，以使用新電腦的 TPM plus PIN 來加密磁片磁碟機。

## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam.md)

 

 





