---
title: 如何當地語系化自助入口網站的 HelpdeskURL
description: 如何當地語系化自助入口網站的 HelpdeskURL
author: dansimp
ms.assetid: 86798460-077b-459b-8d54-4b605e07d2f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0d7ec4ce87bbe5aab56e9fa877ced5f51625a5dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811918"
---
# 如何當地語系化自助入口網站的 HelpdeskURL


您可以設定當地語系化版本的自助入口網站 URL，預設會顯示給使用者。 自助入口網站 URL 是由參數**HelpdeskURL**表示。

如果您建立當地語系化版本，請參閱下列指示中的 [Microsoft BitLocker 管理與監視（MBAM）]，找出並顯示當地語系化版本。 如果 MBAM 找不到當地語系化版本，則會顯示針對參數**HelpDeskURL**設定的 URL。

**記事** 在下列指示中， *SelfService*是自助服務入口網站的預設虛擬目錄名稱。 您在設定自助入口網站時，可能會使用不同的名稱。

 

**若要當地語系化自助入口網站 URL**

1.  在您設定自助入口網站的伺服器上，流覽至 [**網站** &gt; **Microsoft BitLocker 管理及監視** &gt; **SelfService** &gt; **應用程式設定**]。

2.  在 [**動作**] 窗格中，按一下 [**新增**] 以開啟 [**新增應用程式設定**] 對話方塊。

3.  在 [ **Name** ] （名稱）欄位中，輸入**HelpdeskURL**\ _ &lt; *語言* &gt; ，其中 &lt; [*語言*] &gt; 是 URL 的適當語言代碼。

    例如，若要在西班牙文中建立值的當地語系化版本 `HelpdeskURL` ，請將參數**HelpdeskURL 為 \ _es**。

    語言資料夾的名稱也可以是語言中性名稱**es** ，而不是**es**。 如果最終使用者的瀏覽器設定為**es** ，且該資料夾不存在，則會以遞迴方式檢索及檢查父區域設定（在 .net 中定義），並在最終成為預設 Notice.txt 檔案之前，進行遞迴檢索及檢查 &lt; MBAM 自助安裝目錄 &gt;\\SelfServiceWebsite\\es\\Notice.txt。 這個遞迴回退會模仿 .NET 資源載入規則。

    如需您可以使用的有效語言代碼清單，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)。

4.  在 [**值**] 欄位中，輸入 `HelpdeskURL` 您要向使用者顯示的值的當地語系化版本。



## 相關主題


[為組織自訂自助入口網站](customizing-the-self-service-portal-for-your-organization.md)

 

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




