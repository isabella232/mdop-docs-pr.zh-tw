---
title: 如何重設 TPM 鎖定
description: 如何重設 TPM 鎖定
author: dansimp
ms.assetid: dd20a728-c52e-48e6-9f6c-1311c71dee74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5aea277e80c54fb01d1a6c00b62f0c617d1ad12
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809885"
---
# 如何重設 TPM 鎖定


本主題說明如何使用管理和監控網站（也稱為說明服務台）來重設 TPM 封鎖。 如果使用者輸入錯誤的 PIN 太多次，就會發生 TPM 鎖定。 在 TPM 鎖定前，使用者可以輸入不正確 PIN 的次數，會因製造商而異。

從管理和監控網站的 [**管理 TPM** ] 區域，您可以存取集中式金鑰復原資料系統，當您提供電腦識別碼及相關聯的使用者識別碼時，就會提供 TPM 擁有者密碼檔案。

若要存取 [管理] 和 [監視] 網站的 [管理 TPM] 區域，您必須獲指派 MBAM [支援人員] 的使用者角色或 MBAM [高級支援人員] 使用者角色。 這些角色是管理員在 Active Directory 中建立的群組。 您可以為這些群組使用任何名稱。 如需詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。

如需 MBAM 及 TPM 擁有權的相關資訊，請參閱[MBAM 2.5 安全考慮](mbam-25-security-considerations.md#bkmk-tpm)。

**重設 TPM 封鎖**

1.  開啟網頁瀏覽器，然後流覽至 [**管理] 和 [監視] 網站**。

2.  在左窗格中，按一下 [**管理 tpm** ] 以開啟 [**管理 tpm** ] 頁面。

3.  輸入電腦和電腦名稱稱的完整功能變數名稱。

4.  輸入使用者的 Windows 登入網域和使用者名稱，以取得 TPM 擁有者密碼檔。

    **記事** 如果您在 [MBAM 高級服務台使用者] 群組中，則不需要 [使用者網域] 和 [使用者識別碼] 欄位。

     

5.  從 [**要求 TPM 擁有者密碼**檔案的原因] 清單中，選取要求的原因，然後按一下 [**提交**]。

    MBAM 會傳回下列其中一項：

    -   找不到符合的 TPM 擁有者密碼檔案時的錯誤訊息

    -   已提交電腦的 TPM 擁有者密碼檔

    在您檢索 TPM 擁有者密碼之後，就會顯示擁有者密碼。

6.  若要將密碼儲存至 tpm 檔案，請按一下 [**儲存**] 按鈕。

7.  在 [管理]**和 [監視] 網站**的 [**管理 tpm** ] 區域中，選取 [**重設 tpm 封鎖**] 選項，並提供 TPM 擁有者密碼檔。

    TPM 封鎖會重定，而且最終使用者的存取權會還原。

    **重要** 請勿將 TPM 雜湊值或 TPM 擁有者密碼檔提供給最終使用者。 因為 TPM 資訊不會變更，所以提供給使用者的檔案會造成安全風險。

     



## 相關主題


[使用 MBAM 2.5 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





