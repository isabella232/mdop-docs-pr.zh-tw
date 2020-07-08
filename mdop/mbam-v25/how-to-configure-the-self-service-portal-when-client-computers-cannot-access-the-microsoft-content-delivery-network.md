---
title: 如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時設定自助入口網站
description: 如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時設定自助入口網站
author: dansimp
ms.assetid: 90ee76db-9876-41b5-994a-118556d5ed3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ffce3dd023cb6ff9bd5cdb13ea789b348661de24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810587"
---
# 如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時設定自助入口網站


如果貴組織中的用戶端電腦無法存取 Microsoft Ajax 內容傳遞網路（CDN），請遵循下列指示進行。

**為什麼您需要設定：**

您的用戶端電腦需要存取 CDN，這可讓自助服務入口網站所需的特定 JavaScript 檔案存取權。 如果您未在用戶端電腦無法存取 CDN 時設定自助入口網站，則只有公司名稱和最終使用者登入所使用的帳戶才會顯示。 不會顯示任何錯誤訊息。

**記事** 在 MBAM 2.5 SP1 中，JavaScript 檔案包含在產品中，您不需要按照本節中的指示，將 SSP 設定為支援無法存取網際網路的用戶端。

 

**當用戶端電腦無法存取 CDN 時，如何設定自助服務入口網站**

1. 從 CDN 下載下列 JavaScript 檔案：

   -   [jQuery-1.10.2.min.js](https://go.microsoft.com/fwlink/?LinkID=390515)

   -   [jQuery.validate.min.js](https://go.microsoft.com/fwlink/?LinkID=390516)

   -   [jQuery.validate.unobtrusive.min.js](https://go.microsoft.com/fwlink/?LinkID=390517)

2. 將 JavaScript 檔案複製到自助服務入口網站的 [**腳本**] 目錄。 此目錄位於 <em> &lt; MBAM 自助安裝目錄 &gt; \\ </em> 自助服務 Website\\Scripts。

3. 開啟 [網際網路資訊服務（IIS）管理員]。

4. 展開 [**網站** &gt; **Microsoft BitLocker 管理與監視**]，然後醒目提示 [ **SelfService**]。

   **注意**  
   *SelfService*是預設的虛擬目錄名稱。 如果您在設定期間為此目錄選擇其他名稱，請記得以您所選擇的名稱取代這些指示中的*SelfService* 。

     

5. 按兩下中間窗格中的 [**應用程式設定**]。

6. 針對下列清單中的每個專案，透過 &lt; 使用/SelfService/（或您在設定期間選擇的任何名稱）來取代/*虛擬目錄*/以參照新位置來編輯應用程式設定 &gt; 。 例如，虛擬目錄路徑會類似/selfservice/Scripts/jQuery-1.10.2.min.js。

   -   jQueryPath：/ &lt; *virtual directory* &gt; /Scripts/jQuery-1.10.2.min.js

   -   jQueryValidatePath：/ &lt; *virtual directory* &gt; /Scripts/jQuery.validate.min.js

   -   jQueryValidateUnobtrusivePath：/ &lt; *virtual directory* &gt; /Scripts/jQuery.validate.unobtrusive.min.js



## 相關主題


[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





