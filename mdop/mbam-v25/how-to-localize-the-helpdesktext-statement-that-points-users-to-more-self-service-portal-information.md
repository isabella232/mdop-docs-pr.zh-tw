---
title: 如何將 HelpdeskText 聲明當地語系化，指引使用者取得更多自助入口網站資訊
description: 如何將 HelpdeskText 聲明當地語系化，指引使用者取得更多自助入口網站資訊
author: dansimp
ms.assetid: 09ba2a07-3186-45d9-adef-4034c70ae7cf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2367424185da813a46fa52f3614c03083864f75f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809945"
---
# 如何將 HelpdeskText 聲明當地語系化，指引使用者取得更多自助入口網站資訊


您可以設定當地語系化版本的自助入口 "HelpdeskText" 語句，這會通知最終使用者如何在使用自助入口網站時取得其他協助。 如果您設定語句的當地語系化文字，請參閱下列指示中的 MBAM 顯示當地語系化版本。 如果 MBAM 找不到已當地語系化的版本，則會顯示**HelpdeskText**參數中的值。

**記事** 在下列指示中， *SelfService*是自助服務入口網站的預設虛擬目錄名稱。 您在設定自助入口網站時，可能會使用不同的名稱。

 

**顯示 HelpdeskText 語句的當地語系化版本**

1.  在您設定自助入口網站的伺服器上，流覽至 [**網站** &gt; **Microsoft BitLocker 管理及監視** &gt; **SelfService** &gt; **應用程式設定**]。

2.  在 [**動作**] 窗格中，按一下 [**新增**] 以開啟 [**新增應用程式設定**] 對話方塊。

3.  在 [ **Name** ] （名稱）欄位中，輸入**HelpdeskText**\ _ &lt; *語言* &gt; ，其中 [ &lt; *語言*] &gt; 是該文字的適當語言代碼。

    例如，若要在西班牙文中建立當地語系化的 HelpdeskText 語句，請將參數命名為**HelpdeskText \ _es-es**。

    語言資料夾的名稱也可以是語言中性名稱**es** ，而不是**es**。 如果最終使用者的瀏覽器設定為**es** ，且該資料夾不存在，則會以遞迴方式檢索及檢查父區域設定（在 .net 中定義），並在最終成為預設 Notice.txt 檔案之前，進行遞迴檢索及檢查 &lt; MBAM 自助安裝目錄 &gt;\\SelfServiceWebsite\\es\\Notice.txt。 這個遞迴回退會模仿 .NET 資源載入規則。

    如需您可以使用的有效語言代碼清單，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)。

4.  在 [**值**] 欄位中，輸入您要顯示給最終使用者的當地語系化文字。



## 相關主題


[為組織自訂自助入口網站](customizing-the-self-service-portal-for-your-organization.md)

 

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。



