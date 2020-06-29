---
title: 使用 Application Virtualization Management Server 發佈虛擬應用程式
description: 使用 Application Virtualization Management Server 發佈虛擬應用程式
author: dansimp
ms.assetid: f3d79284-3f82-4ca3-b741-1a80b61490da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 01b85d73ed0a6a8bf723be381e947fbbc003bf6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800885"
---
# 使用 Application Virtualization Management Server 發佈虛擬應用程式


在應用程式虛擬化伺服器的部署中，已排序、經過測試且找到可部署的虛擬應用程式套件會複製到應用程式虛擬化管理伺服器所要使用的主要內容共用。 將套件匯入應用程式虛擬化管理伺服器之後，就可以將它們發佈給最終使用者。

**記事** 內容共用應該位於伺服器的已附加磁片儲存空間。 您應該謹慎考慮使用網路儲存裝置（例如 SAN 或 DFS 共用），因為這會影響網路。

 

將應用程式預配至 Active Directory 群組。 通常，應用程式虛擬化管理員會針對每個要發佈的虛擬應用程式建立 Active Directory 群組，然後將適當的使用者新增到這些群組。 當使用者登入其工作站時，應用程式虛擬化用戶端預設會使用已登入使用者的認證執行發佈重新整理。 然後，使用者就可以從放置快速鍵的任何地方開始應用程式。 應用程式虛擬化管理員會在應用程式排序期間判斷用戶端系統上的快速鍵位置和數目。

**記事** *發佈*重新整理是在應用程式虛擬化用戶端上定義之應用程式虛擬化伺服器的呼叫，以判斷要傳送給客戶供最終使用者使用的虛擬應用程式快捷方式。

 

## 相關主題


[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)

[如何在用戶端上發佈虛擬應用程式](how-to-publish-a-virtual-application-on-the-client.md)

[Application Virtualization 系統元件概觀](overview-of-the-application-virtualization-system-components.md)

[在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

 

 





