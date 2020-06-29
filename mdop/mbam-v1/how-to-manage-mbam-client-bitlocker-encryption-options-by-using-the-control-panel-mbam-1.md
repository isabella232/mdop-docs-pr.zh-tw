---
title: 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項
description: 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項
author: dansimp
ms.assetid: c08077e1-5529-468f-9370-c3b33fc258f3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 271147d0e5581f6ce49fe0b46aa83dae6ae4556b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800223"
---
# 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項


在安裝 MBAM 用戶端時，**系統和安全性**下會提供 Microsoft BitLocker 管理與監視（MBAM）控制台應用程式（稱為 BitLocker 加密選項）。 這個自訂的 MBAM [控制台] 會取代預設的 Windows BitLocker [控制台]。 [MBAM 控制台] 可讓您解除鎖定加密的磁碟機（固定和移除），也可協助您管理 PIN 或密碼。 如需啟用 MBAM [控制台] 的詳細資訊，請參閱[如何在 Windows [控制台] 中隱藏預設的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)。

**記事** 對於 BitLocker 用戶端，系統會在 [事件檢視器] 中的 [**應用程式和服務記錄**  /  **Microsoft**  /  **Windows**  /  **BitLockerManagement**] 底下找到 [管理員] 和 [操作記錄] 檔案。

 

**使用 MBAM 用戶端控制台**

1.  若要開啟 BitLocker 加密選項，請按一下 [**開始**]，然後選取 [**控制台**]。 [**控制台**] 開啟時，選取 [**系統及安全性**]。

2.  按兩下 [ **BitLocker 加密選項**] 以開啟自訂的 MBAM [控制台]。 您將會看到電腦上所有硬碟磁碟機及其加密狀態的清單。 您也會看到管理 PIN 或密碼的選項。

3.  如果使用者和電腦免除原則已部署，請使用電腦上的硬碟清單來驗證加密狀態、解除鎖定磁片磁碟機，或要求提供 BitLocker 保護的免除。

4.  非系統管理員可以使用 BitLocker 加密選項控制台來管理 Pin 或密碼。 使用者可以選取 [**管理 PIN]，** 然後輸入目前的 pin 和新的 pin。 使用者也可以確認其新的 PIN。 **更新 pin**函數會將 PIN 重設為使用者選取的新帳戶。

5.  若要管理您的密碼，請選取 [**解鎖磁片磁碟機**]，然後輸入您目前的密碼。 一旦解除鎖定磁片磁碟機，請選取 [**重設密碼**] 變更您目前的密碼。

## 相關主題


[管理 MBAM 1.0 功能](administering-mbam-10-features.md)

 

 





