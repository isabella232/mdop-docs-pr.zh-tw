---
title: 如何使用自助入口網站重新取得電腦的存取權
description: 如何使用自助入口網站重新取得電腦的存取權
author: dansimp
ms.assetid: 3c24b13a-d1b1-4763-8ac0-0b2db46267e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cde9c71a957a5270d69aa8388455895f1cb2432b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811913"
---
# 如何使用自助入口網站重新取得電腦的存取權


自助服務入口網站是 IT 系統管理員設定為其 Microsoft BitLocker 管理與監控（MBAM）2.5 部署的一部分的網站。 如果使用者被封鎖在 Windows 之外，該網站可讓使用者獨立地重新取得其電腦的存取權。 自助服務入口網站不需要技術支援人員的協助。

下列指示是從使用者的角度來撰寫，但資訊對 IT 系統管理員而言可能很有説明。

**重要** 使用者至少必須以自助入口網站的方式，才能以實際登入電腦（而非遠端登入）一次來復原其金鑰。 否則，他們必須使用支援人員入口網站進行金鑰復原。

 

如果最終使用者遇到下列情況，可能會發生鎖定：

-   忘記其密碼或 PIN

-   變更作業系統檔案、BIOS 或受信任的平臺模組（TPM）

**記事** 如果 IT 系統管理員設定了 IIS 會話狀態超時，就會在自助服務入口網站的超時前60秒顯示一則訊息。

 

**使用自助入口網站來重新取得電腦的存取權**

1.  在 [復原金鑰 **] 欄位中**，輸入您電腦的 BitLocker 復原畫面上所顯示的32位數 BITLOCKER 金鑰識別碼中至少有八個。 如果前八位數符合多個按鍵，則會顯示一則訊息，要求您輸入所有32位數的復原金鑰識別碼。

2.  在 [**原因**] 欄位中，選取您要求的復原金鑰原因。

3.  按一下 [**取得金鑰**]。 您的 BitLocker 復原金鑰會顯示在 [**您的 bitlocker 復原金鑰**] 欄位中。

4.  在電腦上的 BitLocker 恢復畫面中輸入48位數的代碼，以重新取得電腦的存取權。



## 相關主題


[使用 MBAM 2.5 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





