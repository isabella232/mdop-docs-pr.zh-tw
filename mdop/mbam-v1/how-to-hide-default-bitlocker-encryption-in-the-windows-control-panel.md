---
title: 如何在 Windows 控制台中隱藏預設 BitLocker 加密
description: 如何在 Windows 控制台中隱藏預設 BitLocker 加密
author: dansimp
ms.assetid: c8503743-220c-497c-9785-e2feeca484d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67a61763e556f8c3b93825220dbbd61a14b7d6f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810598"
---
# 如何在 Windows 控制台中隱藏預設 BitLocker 加密


Microsoft BitLocker 管理與監控（MBAM）為名為「BitLocker 加密選項」的 MBAM 用戶端電腦提供自訂的 [控制台]。 這個自訂的 [控制台] 可以取代名為 [BitLocker 磁碟機加密] 的預設 Windows BitLocker [控制台]。 在 Windows [控制台] 中的 [系統及安全性] 底下的 [BitLocker 加密選項] 控制台，可讓使用者管理其 PIN 及密碼、解除鎖定磁片磁碟機，以及隱藏允許系統管理員解密磁片磁碟機或暫停或繼續 BitLocker 加密的介面。

**若要在 Windows [控制台] 中隱藏預設的 BitLocker 加密**

1.  使用群組原則管理主控台（GPMC）、高級群組原則管理（AGPM），或 BitLocker 群組原則電腦上的本機組策略編輯器，流覽至**使用者**設定。

2.  按一下 [**原則**]，選取 [系統**管理範本**]，然後按一下 [**控制台**]。

3.  在 [**詳細資料**] 窗格中，按兩下 [**隱藏指定**的 [控制台專案]，然後選取 [**啟用**]。

4.  按一下 [**顯示**]，**按一下 [新增 ...**]，然後輸入 BitLockerDriveEncryption。 此原則會從 Windows [控制台] 中隱藏預設的 Windows BitLocker 管理工具，並允許使用者從 Windows [控制台] 開啟 [更新的 MBAM BitLocker 加密選項] 工具。

## 相關主題


[部署 MBAM 1.0 群組原則物件](deploying-mbam-10-group-policy-objects.md)

 

 





