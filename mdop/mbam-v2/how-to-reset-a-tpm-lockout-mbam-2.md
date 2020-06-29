---
title: 如何重設 TPM 鎖定
description: 如何重設 TPM 鎖定
author: dansimp
ms.assetid: 20719ab2-18ae-4d3b-989a-539341909816
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6453473ec09c2033346c7e464c08dbfdfe046d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810923"
---
# 如何重設 TPM 鎖定


Microsoft BitLocker 管理與監視（MBAM）的加密磁片磁碟機復原功能包含了資料的捕獲與儲存，以及管理受信任的平臺模組（TPM）所需的工具可用性。 本主題說明如何在 [管理與監控] 網站中存取集中式金鑰復原資料系統，這可以在提供電腦識別碼及相關聯的使用者識別碼時提供 TPM 擁有者密碼檔案。

如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。 在 TPM 鎖定前，使用者可以輸入不正確 PIN 的次數，會因製造商而異。

您只能在 MBAM 擁有 TPM 時重設 TPM 封鎖。

**重設 TPM 封鎖**

1.  開啟網頁瀏覽器，然後流覽至 [管理] 和 [監視] 網站。

2.  在左側功能窗格中，選取 [**管理 tpm** ] 以開啟 [**管理 tpm** ] 頁面。

3.  輸入電腦和電腦名稱稱的完整功能變數名稱，然後輸入使用者的 Windows 登入網域和使用者的使用者名稱，以取得 TPM 擁有者密碼檔案。

4.  從 [**要求 TPM 擁有者密碼**檔案的原因] 清單中，選取要求的原因，然後按一下 [**提交**]。

    MBAM 會傳回下列其中一項：

    -   找不到符合的 TPM 擁有者密碼檔的錯誤訊息

    -   已提交電腦的 TPM 擁有者密碼檔

    **注意**  
    如果您是「高級服務台」使用者，則不需要 [使用者網域] 和 [使用者識別碼] 欄位。



~~~
After the TPM owner password is retrieved, the owner password is displayed.
~~~

5. 若要將密碼儲存至 tpm 檔案，請按一下 [**儲存**] 按鈕。

   使用者會執行 TPM 管理主控台，選取 [**重設 tpm 封鎖**] 選項，並提供 tpm 擁有者密碼檔來重設 tpm 封鎖。

   **重要**  
   技術支援中心系統管理員不應將 TPM 雜湊值或 TPM 擁有者密碼檔提供給最終使用者。 TPM 資訊不會變更，因此如果將檔案提供給使用者，就可能會造成安全風險。



## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)









