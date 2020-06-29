---
title: 離線編輯 GPO
description: 離線編輯 GPO
author: dansimp
ms.assetid: 51677d8a-6209-41b5-82ed-4f3be817abc0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74b6ae9fdf11456a9a45cb5504ed97a9bc6aecb4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801890"
---
# 離線編輯 GPO


若要變更受控制的群組原則物件（GPO），您必須先從封存中取出一個 GPO 複本。 除非再次存回 GPO，否則任何人都無法修改該 GPO，從而避免由多個群組原則管理員引入相互衝突的變更。 修改完 GPO 之後，您可以將它簽入封存，以便在生產環境中審查並部署。

具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶、建立 GPO 之核准者的使用者帳戶，或是必須具備高級群組原則管理（AGPM）中所需許可權的使用者帳戶才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

## 離線編輯 GPO


若要編輯 GPO，您可以從封存中取出該 gpo，在離線時編輯該 gpo，然後將該 GPO 核取到封存中，讓它可以檢查並部署（或由其他編輯者修改）。

-   [從封存中取出一個 GPO 進行編輯](#bkmk-checkout)

-   [離線編輯 GPO](#bkmk-edit)

-   [將 GPO 檢查到封存](#bkmk-checkin)

### <a href="" id="bkmk-checkout"></a>

**從封存取出一個 GPO 進行編輯**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  以滑鼠右鍵按一下要編輯的 GPO，然後按一下 [**取出]。**

4.  輸入要在已取出之 GPO 之歷程記錄中顯示的批註，然後按一下 **[確定]**。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 在 [**受控**] 索引標籤上，GPO 的狀態現在已標示為 [**已取出**]。

### <a href="" id="bkmk-edit"></a>

**若要離線編輯 GPO**

1.  在 [**受控**] 索引標籤上，以滑鼠右鍵按一下要編輯的 GPO，然後按一下 [**編輯**]。

2.  在 [**群組原則管理編輯器**] 視窗中，對 GPO 的離線複本進行變更。

    **記事** 若要停用所有電腦設定設定或所有使用者設定設定，請在 [**群組原則管理編輯器**] 視窗中，以滑鼠右鍵按一下該 GPO，然後按一下 [**屬性**]。 視需要選取 [**停用電腦設定**] 或 [**停用使用者設定設定**]。

     

3.  修改完 GPO 之後，請關閉 [**群組原則管理編輯器**] 視窗。

### <a href="" id="bkmk-checkin"></a>

**將 GPO 檢查到封存**

1.  在 [**受控**] 索引標籤上：

    -   如果您沒有對 GPO 進行任何變更，請以滑鼠右鍵按一下該 GPO，然後按一下 [**復原**取出]，然後按一下 **[是]** 以進行確認。

    -   如果您已對 GPO 進行變更，請以滑鼠右鍵按一下該 GPO，然後按一下 [**存回**]。

2.  輸入要在 [GPO 審核追蹤] 中顯示的批註，然後按一下 **[確定]**。

3.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已核**取]。

### 其他考量

-   若要取出並編輯 GPO，請根據預設，您必須是建立或控制 GPO、編輯者或 AGPM 系統管理員的核准者（完全控制）。 具體說來，您必須擁有 [**清單內容**] 和 [**編輯設定**] GPO 的 [設定] 許可權。 此外，若要編輯 GPO，您必須是已取出 GPO 的人員。

-   若要在 GPO 中檢入，您必須是 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）]。 具體說來，您必須擁有**清單內容**，並**編輯設定**或為 gpo**部署 gpo**許可權。 如果您不是核准者或 AGPM 管理員（或具有「**部署 GPO** 」許可權的其他群組原則管理員），則您必須是已取出該 Gpo 的編輯者。

-   在編輯 GPO 時，在其他 GPO 中，任何群組原則軟體安裝套件的升級，都應該參照已部署的 GPO，而不是取出的版本。

### 其他參考資料

-   [編輯 GPO](editing-a-gpo-agpm30ops.md)

-   檢查 GPO

    -   [檢閱 GPO 設定](review-gpo-settings-agpm30ops.md)

    -   [檢閱 GPO 連結](review-gpo-links-agpm30ops.md)

    -   [找出 GPO、GPO 版本或範本之間的差異](identify-differences-between-gpos-gpo-versions-or-templates-agpm30ops.md)

-   部署 GPO

    -   [要求部署 GPO](request-deployment-of-a-gpo-agpm30ops.md)

    -   [部署 GPO](deploy-a-gpo-agpm30ops.md)

 

 





