---
title: 隱藏控制台中預設的 BitLocker 磁碟機加密項目
description: 隱藏控制台中預設的 BitLocker 磁碟機加密項目
author: dansimp
ms.assetid: 6e2a9a02-a809-43a1-80a3-1b03c7192c89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af395928ca8934bfea4eeb848bbd4ee377987293
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809752"
---
# 隱藏控制台中預設的 BitLocker 磁碟機加密項目


本主題描述如何隱藏 [ **BitLocker 磁碟機加密**] 控制台專案，該專案預設會顯示在 [控制台] 中，成為 Windows 作業系統的一部分。

**記事** Microsoft BitLocker 管理和監控（MBAM）會建立另一個自訂的 [控制台] 專案（稱為 [ **BitLocker 加密選項**]），讓使用者能夠管理其 PIN 與密碼、開啟磁片磁碟機的 BitLocker，以及檢查加密。

 

請參閱[瞭解 [控制台] 中的 [Bitlocker 加密選項] 和 [Bitlocker 磁片磁碟機加密專案](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)]，瞭解：

-   MBAM 和預設 [控制台] 專案間的差異

-   **管理**當您以滑鼠右鍵按一下 Windows 資源管理器中的磁片磁碟機時所顯示的 BitLocker 快捷方式功能表

**重要** 請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定。 如果您這樣做，MBAM 將無法正常運作。 當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定**BitLocker 磁片磁碟機加密**設定。

 

**若要在 [控制台] 中隱藏預設的 BitLocker 磁片磁碟機加密專案**

1.  在 [群組原則管理主控台（GPMC）] 或 [高級群組原則管理] 中，流覽至 [**使用者**設定原則] 的 [系統 &gt; **Policies** &gt; **管理範本** &gt; **] 控制台**。

2.  在 [**詳細資料**] 窗格中，按兩下 [**隱藏指定**的 [控制台專案]，然後按一下 [**啟用**]。

3.  按一下 [**顯示**]，按一下 [**新增**]，然後輸入**BitLockerDriveEncryption**。



## 相關主題


[了解控制台中的 BitLocker 加密選項與 BitLocker 磁碟機加密項目](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)

[部署 MBAM 2.5 群組原則物件](deploying-mbam-25-group-policy-objects.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





