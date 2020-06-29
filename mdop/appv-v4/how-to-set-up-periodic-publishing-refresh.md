---
title: 如何設定定期重新整理發佈
description: 如何設定定期重新整理發佈
author: dansimp
ms.assetid: c358c765-cb88-4881-b4e7-0a2e87304870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5bbea1c661d6cb5a78f0bb9de29538e0222cda6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801062"
---
# 如何設定定期重新整理發佈


您可以使用下列程式來設定用戶端定期重新整理 App-v 伺服器的發佈資訊。 用戶端設定之後，就會自動重新整理作業。 這些設定會設定用戶端的預設設定，讓此電腦上的所有使用者都能看到相同的設定。

**記事** 在您執行此程式後，在登入後第一次重新整理之後，會根據新的設定來更新發佈資訊。 第一次重新整理髮生時，伺服器可能會根據設定的設定，覆寫電腦設定。 [**屬性**] 對話方塊中的 [重新**整理] 索引**標籤會顯示本機設定的用戶端電腦設定，以及任何可能已由發佈伺服器為使用者設定的設定。

 

**若要定期重新整理應用程式虛擬化伺服器的發佈資訊**

1.  按一下 [**範圍**] 窗格中的 [**發佈伺服器**]。

2.  在 [**結果**] 窗格中，以滑鼠右鍵按一下所需的伺服器，然後從快顯功能表中選取 [**屬性**]。

3.  在 [內容 **] 對話方塊中的 [** 重新**整理] 索引**標籤上，選取 [**每隔**] 核取方塊的 [重新整理設定]，然後在欄位中輸入代表頻率的數位。 然後從下拉式功能表中選取 [**分鐘**]、[**小時**]、[**天**]。

    **記事** 此設定將會導致用戶端在每次經過設定的期間時重新整理髮布資訊。 如果您需要重新整理的使用者沒有登入，則當使用者下一次登入時，就會進行重新整理。 接著，隨後就會再次啟動該計時器。

     

4.  按一下 **[** 套用] 以變更配置。

5.  完成伺服器的設定後，請按一下 **[確定**] 結束對話方塊，然後返回應用程式虛擬化用戶端管理主控台。

## 相關主題


[如何在 Application Virtualization Client 管理主控台中設定用戶端](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

 

 





