---
title: 如何修復處於修復模式的磁碟機
description: 如何修復處於修復模式的磁碟機
author: dansimp
ms.assetid: e126eaf8-9ae7-40fe-a28e-dbd78d26859e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d15f33f461e60fceeed3acbce3a0c82b02b56f98
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809914"
---
# 如何修復處於修復模式的磁碟機


本主題說明如何使用管理和監控網站（也稱為說明服務台）來取得恢復密碼，以便在其受 BitLocker 保護的磁碟機進入復原模式時提供給最終使用者。 如果使用者遺失或忘記其 PIN 或密碼，或受信任的模組平臺（TPM）晶片偵測到電腦的 BIOS 或啟動檔案變更，磁碟機就會進入 [復原模式]。

若要取得復原密碼，請使用 [管理] 和 [監視] 網站的 [**磁碟機恢復**] 區域。 您必須獲指派 MBAM 技術支援人員的使用者角色，或 MBAM [高級支援人員] 使用者角色，才能存取網站的此區域。

**注意**  
您可能會在建立這些角色時，為它們指定不同的名稱。 如需詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。



**重要**  
在單一使用之後，復原密碼就會過期。 在操作系統磁碟機和固定資料磁碟機上，會自動套用單一用途規則。 在抽取式磁碟磁碟機上，在已啟用群組原則設定以管理抽取式磁碟磁碟機的電腦上，移除該磁碟機，然後將它重新插入並解除鎖定時，就會套用它。



**在復原模式中復原磁片磁碟機**

1.  開啟網頁瀏覽器，然後流覽至 [**管理] 和 [監視] 網站**。

2.  在左窗格中，選取 [**磁片磁碟機**復原] 以開啟 [**復原存取加密的磁碟機**] 頁面。

3.  輸入使用者的 Windows 登入網域和使用者名稱，以查看恢復資訊。

    **注意**  
    如果您在 [MBAM 高級服務台使用者] 群組中，則不需要 [使用者網域] 和 [使用者識別碼] 欄位。



4.  輸入復原金鑰識別碼的前八位數，以查看可能符合的復原金鑰清單，或輸入整個復原金鑰識別碼來取得確切的復原金鑰。

5.  從 [**磁片磁碟機解除鎖定的原因**] 清單中，選取其中一個預先定義的選項，然後按一下 [**提交**]。

    MBAM 會傳回下列內容：

    -   找不到符合的復原密碼時的錯誤訊息

    -   如果使用者有多個相符的恢復密碼，可能會有多個可能的相符專案

    -   已提交使用者的復原密碼及復原套件

        **注意**  
        如果您要復原已損壞的磁片磁碟機，recover 套裝程式選項會提供 BitLocker，其中包含復原磁片磁碟機所需的重要資訊。



~~~
After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

6. 若要複製密碼，請按一下 [**複製金鑰**]，然後將恢復密碼貼到電子郵件訊息中。 或者，按一下 [**儲存**] 以將復原密碼儲存至檔案。

   當使用者在系統中輸入復原密碼或使用復原套件時，磁片磁碟機就會解除鎖定。



## 相關主題


[使用 MBAM 2.5 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)



## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





