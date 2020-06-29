---
title: 如何判斷遺失的電腦的 BitLocker 加密狀態
description: 如何判斷遺失的電腦的 BitLocker 加密狀態
author: dansimp
ms.assetid: 9440890a-9c63-463b-9113-f46071446388
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9b977b20ecf219830609c3b1f646a29e6678448
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810467"
---
# 如何判斷遺失的電腦的 BitLocker 加密狀態


Microsoft BitLocker 管理和監控（MBAM）可讓您判斷遺失或被盜電腦的最近已知 BitLocker 加密狀態。 使用下列程式來判斷這些卷是否已在已不在您擁有的電腦上加密。

**判斷電腦的上次已知 BitLocker 加密狀態**

1.  開啟 MBAM 網站。

    **記事** MBAM 網站的預設位址是 HTTP://* &lt; computername &gt; *。 使用完整的伺服器名稱，以取得更快的流覽結果。

     

2.  從 [功能窗格] 中選取 [**報表**] 節點，然後選取 [**電腦合規性報告**]。

3.  使用右側窗格中的篩選欄位來縮小搜尋結果的範圍，然後按一下 [**搜尋**]。 結果會顯示在您的搜尋查詢下方。

4.  針對遺失的裝置，採取您原則所決定的適當動作。

    **記事** 裝置合規性是由已部署的 BitLocker 原則所決定。 您應該在嘗試判斷裝置的 BitLocker 加密狀態時，確認這些已部署的原則。

     

## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam.md)

 

 





