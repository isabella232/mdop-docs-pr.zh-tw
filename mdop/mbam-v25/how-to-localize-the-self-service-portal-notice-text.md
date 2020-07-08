---
title: 如何當地語系化自助入口網站聲明文字
description: 如何當地語系化自助入口網站聲明文字
author: dansimp
ms.assetid: a4c878b7-e5c8-45af-a537-761bb2991659
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a2385f6b00713e7373bd1707b02324b80f300c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811919"
---
# 如何當地語系化自助入口網站聲明文字


您可以設定在自助入口網站中預設顯示給使用者的當地語系化通知文字。 顯示通知文字的 Notice.txt 檔案位於下列根目錄中：

&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\

若要顯示當地語系化的通知文字，您需要建立當地語系化的 Notice.txt 檔案，然後將其儲存在下列範例目錄中的特定語言資料夾中：

&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\

**記事** 您可以使用 [**應用程式設定**] 中的 [ **NoticeTextPath** ] 專案來設定路徑。

 

MBAM 會根據下列規則顯示通知文字：

-   如果您在適當的語言資料夾中建立當地語系化的**Notice.txt**檔案，MBAM 會顯示預設**Notice.txt**檔案存在的當地語系化聲明文字。 如果缺少預設**Notice.txt**檔案，則會顯示一則訊息，指出預設檔案遺失。

-   如果 MBAM 找不到 Notice.txt 檔案的當地語系化版本，則會顯示預設 Notice.txt 檔案中的文字。

-   如果 MBAM 找不到預設的 Notice.txt 檔案，它會在自助入口網站中顯示預設文字。

**記事** 如果將最終使用者的瀏覽器設定為沒有對應的語言子資料夾或 Notice.txt 的語言，則會顯示下列根目錄中的 Notice.txt 檔案中的文字：

&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\

 

**建立當地語系化的 Notice.txt 檔案**

1.  在您設定自助入口網站的伺服器上，在 &lt; *Language* &gt; 下列範例目錄中建立語言資料夾，其中的 &lt; *語言* &gt; 代表當地語系化語言的名稱：

    &lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\

    **記事** 某些語言資料夾已經存在，因此您可能不需要建立資料夾。 如果您確實需要建立語言資料夾，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)，瞭解您可以用於 &lt; *語言*資料夾的有效名稱清單 &gt; 。

     

2.  建立包含當地語系化通知文字的 Notice.txt 檔案。

3.  將 Notice.txt 檔案儲存于 [ &lt; *語言*] &gt; 資料夾中。 例如，若要在西班牙文中建立當地語系化的 Notice.txt 檔案，請在下列範例目錄中儲存已當地語系化的 Notice.txt 檔案：

    &lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\Es-es

    語言資料夾的名稱也可以是語言中性名稱**es** ，而不是**es**。 如果最終使用者的瀏覽器設定為**es** ，且該資料夾不存在，則會以遞迴方式檢索及檢查父區域設定（在 .net 中定義），並在最終成為預設 Notice.txt 檔案之前，進行遞迴檢索及檢查 &lt; MBAM 自助安裝目錄 &gt;\\SelfServiceWebsite\\es\\Notice.txt。 這個遞迴回退會模仿 .NET 資源載入規則。



## 相關主題


[為組織自訂自助入口網站](customizing-the-self-service-portal-for-your-organization.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





