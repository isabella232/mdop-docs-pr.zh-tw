---
title: 如何在單一伺服器上安裝 MBAM 語言更新
description: 如何在單一伺服器上安裝 MBAM 語言更新
author: dansimp
ms.assetid: e6fe59a3-a3e1-455c-a059-1f23ee083cf6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94814158335430aba433c180cdba83d0cf15b760
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810743"
---
# 如何在單一伺服器上安裝 MBAM 語言更新


Microsoft BitLocker 管理與監控（MBAM）包括可在一或多部電腦上執行的四個伺服器角色。 不過，只有兩個 MBAM 伺服器功能需要更新，才能支援安裝 MBAM 1.0 語言發行和 MBAM 原則範本。 若要更新所有三個必要的 MBAM 功能，以在一部電腦上安裝，請執行本主題中所述的步驟。

**在單一伺服器上安裝 MBAM 語言更新**

1.  開啟 [網際網路資訊服務（IIS）管理主控台]，移至 [**網站**]，然後關閉 Microsoft BitLocker 管理及監視網站。

2.  編輯 MBAM 網站的系結，然後暫時修改網站的系結。 例如，將埠從443變更為9443。

3.  找出並執行 [MBAM 設定] 嚮導（MBAMsetup.exe），然後選取下列三個功能：

    1.  合規性與審計報告

    2.  管理和監控伺服器

    3.  群組原則範本

    **重要** MBAM 伺服器的功能必須以下列順序進行更新：合規性和審核報告，然後是系統管理與監控伺服器。 您可以隨時更新群組原則範本，而不需考慮順序。

     

4.  在您升級伺服器資料庫之後，請開啟 IIS 管理主控台並查看 Microsoft BitLocker 管理及監視網站的系結。

5.  刪除其中一個系結，並確認其餘的系結有正確的主機名稱、憑證和埠號碼供 MBAM 企業設定。

6.  重新開機 MBAM 網站。

7.  測試 MBAM 網站的功能：

    -   開啟 MBAM 網頁介面，並確保您可以取得用戶端的復原金鑰。

    -   強制加密新的或手動解密的用戶端電腦。

        **記事** MBAM 用戶端只會在能與恢復與硬體資料庫通訊時開啟。

         

## 相關主題


[部署 MBAM 1.0 語言版本更新](deploying-the-mbam-10-language-release-update.md)

 

 





