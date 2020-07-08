---
title: 如何在 Windows 控制台中隱藏預設 BitLocker 加密
description: 如何在 Windows 控制台中隱藏預設 BitLocker 加密
author: dansimp
ms.assetid: 6674aa51-2b5d-4e4a-8b43-2cc18d008285
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eda8fafbd7b3ebf414520354eba6def2e97f6237
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810341"
---
# 如何在 Windows 控制台中隱藏預設 BitLocker 加密


Microsoft BitLocker 管理與監控（MBAM）為 Microsoft BitLocker 管理和監視用戶端電腦（稱為 BitLocker 加密選項）提供自訂的 [控制台]。 這個自訂的 [控制台] 可以取代預設的 Windows BitLocker [控制台]，該面板稱為 [BitLocker 磁片磁碟機加密]。 [控制台] 中的 [系統及安全性] 底下的 [自訂控制台] 可讓使用者管理其 PIN 及密碼，以及解除鎖定磁片磁碟機，以及隱藏可讓系統管理員解密磁片磁碟機或暫停或繼續 BitLocker 磁片磁碟機加密的介面。

**若要在 Windows [控制台] 中隱藏預設的 BitLocker 磁片磁碟機加密**

1.  在 [群組原則管理主控台（GPMC）]、[高級] 群組原則管理（AGPM），或 [BitLocker 群組原則] 電腦上的 [本機組策略編輯器] 中，流覽至 [**使用者**設定]。

2.  接著，按一下 [**原則**]，選取 [系統**管理範本**]，然後按一下 [**控制台**]。

3.  按兩下 [**詳細資料**] 窗格中的 [**隱藏指定**的 [控制台專案]，然後選取 [**啟用**]。

4.  按一下 [**顯示**]，按一下 [**新增**]，然後輸入**BitLockerDriveEncryption**。 這個原則會從 Windows [控制台] 中隱藏預設的 Windows BitLocker 管理工具，並在 [控制台] 中，讓使用者開啟 [系統及安全性] 底下的 [更新的 MBAM BitLocker 加密選項] 工具。

## 相關主題


[部署 MBAM 2.0 群組原則物件](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





