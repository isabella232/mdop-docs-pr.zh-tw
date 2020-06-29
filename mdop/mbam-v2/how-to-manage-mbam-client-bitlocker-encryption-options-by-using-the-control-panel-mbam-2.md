---
title: 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項
description: 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項
author: dansimp
ms.assetid: e2ff153e-5770-4a12-b79d-cda998b8a8ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a42901ac9d8a1a3527712f4cf342b5c0ca9ffdfd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810958"
---
# 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項


安裝 Microsoft BitLocker 管理及監視用戶端時，會在 [**系統及安全性**] 下提供 [Microsoft bitlocker 管理與監視（MBAM）] 控制台應用程式（稱為 [Bitlocker 加密選項]）。 這個自訂 MBAM [控制台] 是一個額外的 [控制台]。 它不會取代預設的 Windows BitLocker [控制台]。 MBAM [控制台] 可用來解除鎖定加密的固定和移除磁片磁碟機，也可管理 PIN 或密碼。 如需啟用 MBAM [控制台] 的詳細資訊，請參閱[如何在 Windows [控制台] 中隱藏預設的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)。

**使用 MBAM 用戶端控制台**

1.  若要開啟 BitLocker 加密選項，請按一下 [**開始**]，然後選取 [**控制台**]。 [**控制台**] 開啟時，選取 [**系統及安全性**]。

2.  按兩下 [ **BitLocker 加密選項**] 以開啟自訂的 MBAM [控制台]。 除了管理 PIN 或密碼的選項之外，您還會看到電腦上所有硬碟的清單及其加密狀態。

    如果已部署使用者和電腦例外原則，電腦上的硬碟清單可以用來驗證加密狀態、解除鎖定磁片磁碟機，或要求提供 BitLocker 保護的免除。

    BitLocker 加密選項控制台也可讓非管理員使用者管理其 PIN 或密碼。 選取 [**管理 PIN**] 時，系統會提示使用者輸入目前的 pin 和新 pin （除了確認新 pin）。 選取 [**更新 pin** ] 會將 PIN 重設為使用者選取的新帳戶。

    若要管理您的密碼，請選取 [**解鎖磁片磁碟機**]，然後輸入您目前的密碼。 一旦解除鎖定磁片磁碟機，請選取 [**重設密碼**] 變更您目前的密碼。

## 相關主題


[管理 MBAM 2.0 功能](administering-mbam-20-features-mbam-2.md)

 

 





