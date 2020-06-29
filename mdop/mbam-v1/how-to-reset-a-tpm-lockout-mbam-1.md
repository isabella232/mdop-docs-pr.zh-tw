---
title: 如何重設 TPM 鎖定
description: 如何重設 TPM 鎖定
author: dansimp
ms.assetid: 91ec6666-1ae2-4e76-9459-ad65c405f639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dde77a12e97d050777dac15d4106124ec111b3cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800214"
---
# 如何重設 TPM 鎖定


Microsoft BitLocker 管理與監視（MBAM）的加密磁片磁碟機復原功能包含了資料的捕獲與儲存，以及管理受信任的平臺模組（TPM）所需的工具可用性。 本主題涵蓋如何在 _admmon \ _tlanextref 管理網站中存取集中式金鑰復原資料系統。 金鑰復原資料系統可在提供電腦身分識別及相關聯的使用者識別碼時提供 TPM 擁有者密碼檔案。

如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。 在 TPM 封鎖之前，使用者可以輸入不正確 PIN 的次數，以電腦製造商的規格為基礎。

**重設 TPM 封鎖**

1.  開啟 [MBAM 管理] 網站。

2.  在 [功能窗格] 中，選取 [**管理 TPM**]。 這會開啟 [**管理 TPM** ] 頁面。

3.  輸入電腦和電腦名稱稱的完整功能變數名稱（FQDN）。 輸入使用者的 Windows 登入網域和使用者的使用者名稱。 在 [**要求 TPM 擁有者密碼**檔案的原因] 下拉式功能表中，選取其中一個預先定義的選項。 按一下 **\[提交\]**。

4.  MBAM 將會返回下列其中一項：

    -   找不到符合的 TPM 擁有者密碼檔案時的錯誤訊息

    -   已提交電腦的 TPM 擁有者密碼檔

    **記事** 如果您是「高級服務台」使用者，則不需要 [使用者網域] 和 [使用者識別碼] 欄位。

     

5.  檢索時，會顯示擁有者密碼。 若要將此密碼儲存至 tpm 檔案，請按一下 [**儲存**] 按鈕。

6.  使用者會執行 TPM 管理主控台，然後選取 [**重設 tpm 封鎖**] 選項，並提供 tpm 擁有者密碼檔來重設 tpm 封鎖。

## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam.md)

 

 





