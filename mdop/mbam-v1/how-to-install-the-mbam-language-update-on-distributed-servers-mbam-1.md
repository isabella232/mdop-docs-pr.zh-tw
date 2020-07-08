---
title: 如何在分散式伺服器上安裝 MBAM 語言更新
description: 如何在分散式伺服器上安裝 MBAM 語言更新
author: dansimp
ms.assetid: 5ddc64c6-0417-4a04-843e-b5e18d9f1a52
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6758463c6fc038c4d6ea86c0d49804f29bb543d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811312"
---
# 如何在分散式伺服器上安裝 MBAM 語言更新


Microsoft BitLocker 管理與監控（MBAM）包括可在一或多部電腦上執行的四個伺服器角色。 不過，只有兩個 MBAM 伺服器功能需要更新，才能支援 MBAM 1.0 語言發行和 MBAM 原則範本的安裝。 在配置中，將 MBAM 伺服器功能安裝在多部電腦上，只需要更新下列伺服器功能：

-   MBAM 合規性與審計報告

-   MBAM 管理和監控伺服器

**重要** MBAM 伺服器功能必須以下列順序進行更新：首先是合規性和審核報告，然後是系統管理和監控伺服器。 您可以隨時更新 MBAM 群組原則範本，而不需考慮順序。

 

**在 MBAM 合規性和審核報表伺服器功能上安裝 MBAM 語言更新**

1.  在執行 MBAM 合規性和審核報告功能的電腦上，找出並執行 [MBAM 語言更新設定] 嚮導（MBAMsetup.exe）。

2.  針對合規性和審核報告完成嚮導，然後關閉嚮導。

**若要在 [MBAM 管理及監視伺服器] 功能上安裝 MBAM 語言更新**

1.  在執行 MBAM 管理和監視功能的電腦上，開啟 [網際網路資訊服務（IIS）管理主控台]，移至 [**網站**]，然後關閉 Microsoft BitLocker 管理和監視網站。

2.  選擇編輯 MBAM 網站的系結，然後修改該網站的系結。 例如，將埠從443變更為9443。

3.  找出並執行 MBAM 語言更新設定向導（MBAMsetup.exe）。 完成 [管理及監視伺服器] 功能的嚮導，然後關閉嚮導。

4.  在您升級伺服器資料庫之後，請開啟 IIS 管理主控台並查看 Microsoft BitLocker 管理及監視網站的系結。

5.  刪除舊的系結，並確認其餘的系結有正確的主機名稱、憑證和埠號碼供 MBAM 企業設定。

6.  重新開機 MBAM 網站。

7.  測試 MBAM 網站的功能：

    -   開啟 MBAM 網頁介面，並確認您可以取得用戶端的復原金鑰。

    -   強制加密新的或手動解密的用戶端電腦。

        **記事** MBAM 用戶端只會在能與恢復與硬體資料庫通訊時開啟。

         

## 相關主題


[部署 MBAM 1.0 語言版本更新](deploying-the-mbam-10-language-release-update.md)

 

 





