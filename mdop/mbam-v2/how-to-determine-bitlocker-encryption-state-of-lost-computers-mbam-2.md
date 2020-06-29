---
title: 如何判斷遺失的電腦之 BitLocker 加密狀態
description: 如何判斷遺失的電腦之 BitLocker 加密狀態
author: dansimp
ms.assetid: dbd23b64-dff3-4913-9acd-affe67b9462e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b9ea4afd6dd08f2040b9e2bd1e1a8998181d1e60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810659"
---
# 如何判斷遺失的電腦之 BitLocker 加密狀態


您可以使用 Microsoft BitLocker 管理和監控（MBAM）來判斷遺失或被盜電腦的最近已知 BitLocker 加密狀態。 下列程式說明如何在發生遺失或失竊情況時，判斷電腦上的卷是否已加密。

**若要判斷遺失的電腦的上次已知 BitLocker 加密狀態**

1.  開啟網頁瀏覽器，然後流覽至 [管理] 和 [監視] 網站。

    **記事** 注意： [管理] 和 [監視] 網站的預設位址是 HTTP://* &lt; computername &gt; *。 使用完全限定的伺服器名稱將會產生更快的流覽結果。

     

2.  從 [功能窗格] 中選取 [**報表**] 節點，然後選取 [**電腦合規性報告**]。

3.  使用右窗格中的篩選欄位來縮小搜尋結果的範圍，然後按一下 [**搜尋**]。 結果會顯示在您的搜尋查詢下方。

4.  採取適當的動作，由您的原則決定遺失的裝置。

    **記事** 裝置合規性是由您的企業已部署的 BitLocker 原則所決定。 您可能會想要驗證已部署的原則，然後再嘗試判斷裝置的 BitLocker 加密狀態。

     

## 相關主題


[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





