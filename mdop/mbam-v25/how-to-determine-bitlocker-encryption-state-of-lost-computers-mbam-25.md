---
title: 如何判斷遺失的電腦之 BitLocker 加密狀態
description: 如何判斷遺失的電腦之 BitLocker 加密狀態
author: dansimp
ms.assetid: 4f4bec1b-df3e-40ee-b431-291440268d64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 95fb843b230804417e375946814a585d1d681634
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810575"
---
# 如何判斷遺失的電腦之 BitLocker 加密狀態


使用此程式與 [管理] 和 [監視] 網站來判斷下列事項：

-   遺失或被盜電腦的上次已知 BitLocker 加密狀態

-   是否已加密遺失或被盜電腦上的卷

若要完成這項工作，您需要存取 [管理] 和 [監視] 網站的 [**報告**] 區域。 若要取得此區域的存取權，您必須獲指派 MBAM Report 使用者角色。 您可能會在建立這些角色時，為它們指定不同的名稱。 如需詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。

**記事** 裝置合規性是由您的企業已部署的 BitLocker 原則所決定。 您可能會想要驗證已部署的原則，然後再嘗試判斷裝置的 BitLocker 加密狀態。

 

**若要判斷遺失的電腦的上次已知 BitLocker 加密狀態**

1.  開啟網頁瀏覽器，然後流覽至 [**管理] 和 [監視] 網站**。

2.  在左窗格中，選取 [**報告**] 以開啟 [報告] 頁面。

3.  選取 [**電腦合規性報告**]。

4.  使用右窗格中的篩選欄位來縮小搜尋結果的範圍，然後按一下 [**搜尋**]。 結果會顯示在您的搜尋查詢底下。

5.  採取適當的動作，由您的原則決定遺失的裝置。



## 相關主題


[使用 MBAM 2.5 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





