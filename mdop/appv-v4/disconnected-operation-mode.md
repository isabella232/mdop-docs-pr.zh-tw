---
title: 中斷連線的操作模式
description: 中斷連線的操作模式
author: dansimp
ms.assetid: 3f9849ea-ba53-4c68-85d3-87a4218f59c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e9534b93f23b17e5258ef5e2d548eb93213f2f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808865"
---
# 中斷連線的操作模式


中斷式作業模式設定（由滑鼠右鍵按一下**應用程式虛擬化**節點、選取 [**屬性**]，然後按一下 [**連接**] 索引標籤），可讓遠端桌面服務的應用程式虛擬化桌面用戶端或用戶端在用戶端無法連線到應用程式虛擬化管理伺服器時，執行儲存在用戶端檔案系統快取中的應用程式。

無法連線至伺服器的原因包括伺服器故障、網路中斷或從網路斷開連線。 如果發生任何失敗，用戶端會自動切換到 [中斷連線] 的操作。 中斷連線後，如果用戶端需要來自伺服器的其他資料來繼續執行應用程式，或斷開連接的作業超時時間已過期，用戶端會嘗試重新連線到伺服器。 如果此連接嘗試失敗，應用程式將會關閉。

根據預設，會啟用中斷連線的作業，而超時會設定為90天。 超時值是指定為您要限制斷開連接操作模式的天數，您可以輸入1到999之間的值。

## 相關主題


[如何停用或修改中斷連線的操作模式設定](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





