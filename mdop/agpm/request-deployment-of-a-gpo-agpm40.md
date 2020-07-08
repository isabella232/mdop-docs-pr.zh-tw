---
title: 要求部署 GPO
description: 要求部署 GPO
author: dansimp
ms.assetid: 5783cfd0-bd93-46b4-8fa0-684bd39aa8fc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 46e9cc0fc12962dbdd7758c429a20fdd7c55b3cb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802594"
---
# 要求部署 GPO


在您修改並檢查群組原則物件（GPO）之後，請部署該 GPO，如此會在生產環境中生效。

必須具備高級群組原則管理（AGPM）中具有編輯者角色或必要許可權的使用者帳戶，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**要求將 GPO 部署到網域的生產環境**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  以滑鼠右鍵按一下要部署的 GPO，然後按一下 [**部署**]。

4.  除非您是核准者或 AGPM 管理員，或是擁有部署 Gpo 的特殊許可權，否則您必須提交部署的要求。 若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。 輸入要顯示在該 GPO 之歷程**記錄**中的批註，然後按一下 [**提交**]。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 GPO 會顯示在 [**擱置**] 索引標籤上的 [gpo] 清單中。當核准者核准您的要求之後，該 GPO 就會從 [**擱置**] 索引標籤移至 [**受控**] 索引標籤，並進行部署。

### 其他考量

-   根據預設，您必須是編輯器才能執行此程式。 具體說來，您必須擁有 [**清單內容**] 和 [**編輯設定**] GPO 的 [設定] 許可權。

-   若要在獲核准前收回您的要求，請按一下 [**待定**] 索引標籤。以滑鼠右鍵按一下該 GPO，然後按一下 [**收回**]。 GPO 將會傳回 [**受控**] 索引標籤。

### 其他參考資料

-   [執行編輯器工作](performing-editor-tasks-agpm40.md)

 

 





