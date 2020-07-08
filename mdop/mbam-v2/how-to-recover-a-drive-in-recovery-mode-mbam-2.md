---
title: 如何修復處於修復模式的磁碟機
description: 如何修復處於修復模式的磁碟機
author: dansimp
ms.assetid: 8b792bc8-b671-4345-9d37-0208db3e5b03
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d5ce509599d0eb800a71360e3be9d0fa3b33f4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810928"
---
# 如何修復處於修復模式的磁碟機


Microsoft BitLocker 管理與監控（MBAM）的加密磁片磁碟機復原功能可確保在 BitLocker 進入復原模式時，捕獲和儲存存取受 BitLocker 保護的磁片所需的工具資料和可用性。 當 PIN 或密碼遺失或忘記，或當受信任的模組平臺（TPM）晶片偵測到電腦的 BIOS 或啟動檔案變更時，BitLocker 受保護的卷就會進入 [復原模式]。

使用此程式來存取集中式金鑰復原資料系統，如果提供了復原密碼識別碼及相關聯的使用者識別碼，就可以提供復原密碼。

**重要**  
Microsoft BitLocker 管理和監控使用的單一用途修復金鑰會在使用時過期。 復原密碼的單一用途會自動套用至作業系統磁片磁碟機和固定磁片磁碟機。 在抽取式磁碟磁碟機上，當您移除該磁碟機，然後在已啟用群組原則設定的電腦上重新插入並解除鎖定時，就會套用它，以管理抽取式磁碟磁碟機。



**在復原模式中復原磁片磁碟機**

1.  開啟網頁瀏覽器，然後流覽至 [管理] 和 [監視] 網站。

2.  在 [功能窗格] 中，按一下 [**磁片磁碟機**復原]。 隨即會開啟「復原加密的磁片磁碟機存取」網頁。

3.  輸入使用者的 Windows 登入網域和使用者名稱，以查看復原資訊，以及復原金鑰識別碼的前八位數，以接收符合實際復原金鑰的可能相符的復原金鑰清單或整個復原金鑰識別碼。

4.  從 [**硬碟解除鎖定的原因**] 清單中選取其中一個預先定義的選項，然後按一下 [**提交**]。

    **注意**  
    如果您是 MBAM 高級支援人員的使用者，則不需要使用者網域和使用者識別碼專案。



~~~
MBAM returns the following:

-   An error message if no matching recovery password is found

-   Multiple possible matches if the user has multiple matching recovery passwords

-   The recovery password and recovery package for the submitted user

    **Note**  
    If you are recovering a damaged drive, the recovery package option provides BitLocker with critical information that it needs to recover the drive.



After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

5. 若要複製密碼，請按一下 [**複製金鑰**]，然後將恢復密碼貼到電子郵件訊息中。 或者，按一下 [**儲存**] 以將復原密碼儲存至檔案。

   當使用者在系統中輸入復原密碼或使用復原套件時，磁片磁碟機就會解除鎖定。

## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)









