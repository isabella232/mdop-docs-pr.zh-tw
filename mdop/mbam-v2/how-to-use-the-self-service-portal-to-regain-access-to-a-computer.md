---
title: 如何使用自助入口網站重新取得電腦的存取權
description: 如何使用自助入口網站重新取得電腦的存取權
author: dansimp
ms.assetid: bcf095de-0237-4bb0-b450-da8fb6d6f3d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4abcffcf35e09bd5e24f4715a38dca74518ba29e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811540"
---
# 如何使用自助入口網站重新取得電腦的存取權


如果最終使用者忘記了自己的密碼或 PIN，或是變更了作業系統檔案，或是變更了 BIOS 或受信任的平臺模組（TPM），他們就可以使用自助入口網站來重新取得 Windows 的存取權，而不需向其技術支援人員尋求協助。

**記事** 如果 IT 系統管理員設定了 IIS 會話狀態超時，則會在超時前60秒顯示一則訊息。

 

**記事** 這些指示是針對最終使用者的觀點來撰寫和。

 

**使用自助入口網站來重新取得電腦的存取權**

1.  在 [復原金鑰 **] 欄位中**，輸入您電腦的 BitLocker 復原畫面上所顯示的32位數 BITLOCKER 金鑰識別碼中至少有八個。

    **記事** 如果前八位數符合多個按鍵，則會顯示一則訊息，要求您輸入所有32位數的復原金鑰識別碼。

     

2.  在 [**原因**] 欄位中，選取您要求的復原金鑰原因。

3.  按一下 [**取得金鑰**]。 您的 BitLocker 復原金鑰會顯示在 [您的 BitLocker 復原金鑰] 欄位中。

4.  在電腦上的 BitLocker 恢復畫面中輸入48位數的代碼，以重新取得電腦的存取權。

## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





