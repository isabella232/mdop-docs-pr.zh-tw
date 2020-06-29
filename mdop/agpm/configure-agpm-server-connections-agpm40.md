---
title: 設定 AGPM 伺服器連線
description: 設定 AGPM 伺服器連線
author: dansimp
ms.assetid: bbbb15e8-35e7-403c-b695-7a6ebeb87839
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b6b065b9855c6edf44456026baa32e8d9a4674f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802070"
---
# 設定 AGPM 伺服器連線


每個受控制的群組原則物件（GPO）的所有版本都會儲存在中央封存中，讓群組原則系統管理員可以在離線時查看及修改 Gpo，而不會立即影響每個 GPO 的部署版本。

使用 AGPM 系統管理員（完全控制）角色的使用者帳戶、在這些程式中建立 GPO 所用的核准者使用者帳戶，或是在高級群組原則管理（AGPM）中具有必要許可權的使用者帳戶，都必須完成這些程式來集中設定所有群組原則管理員的封存位置。 請參閱本主題中的「其他注意事項」中的詳細資料。

## 配置 AGPM 服務器連線


就像 AGPM 管理員一樣，您可以透過集中設定關聯的設定，以確保所有群組原則管理員都連線到相同的 AGPM 服務器。 如果您的環境需要部分或所有網域的個別 AGPM 服務器，請將這些額外的 AGPM 服務器設定為預設的例外狀況。 如果您沒有集中設定 AGPM 服務器連線，每個群組原則管理員都必須手動設定要針對每個網域顯示的 AGPM 服務器。

-   [針對所有群組原則管理員設定 AGPM 服務器連線](#bkmk-defaultarchiveloc)

-   [針對所有群組原則管理員設定其他 AGPM 服務器連線](#bkmk-additionalarchiveloc)

-   [針對您的帳戶手動設定 AGPM 服務器連線](#bkmk-manuallyconfigurearchiveloc)

### <a href="" id="bkmk-defaultarchiveloc"></a>

**針對所有群組原則管理員設定 AGPM 服務器連線**

1.  在 [**群組原則管理] 主控台**樹狀結構中，編輯套用至所有群組原則系統管理員的 GPO。 （如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo-agpm40.md)）。

2.  在 [**群組原則管理編輯器**] 視窗中，按一下 [**使用者**設定、**原則**、**管理範本**、 **Windows 元件**及**AGPM**]。

3.  在 [詳細資料] 窗格中，按兩下 [ **agpm]：指定預設的 Agpm 伺服器（所有網域）**。

4.  在 [**屬性**] 視窗中，選取 [**啟用**] 核取方塊，然後輸入完整的電腦名稱稱和埠（例如，server.contoso.com:4600）。

5.  按一下 \[確定\] ****。 除非您想要設定其他的 AGPM 服務器連線，否則請關閉 [**群組原則管理編輯器**] 視窗並部署 GPO。 （如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo-agpm40.md)）。更新群組原則時，會針對所有群組原則管理員設定 AGPM 服務器連線。

### <a href="" id="bkmk-additionalarchiveloc"></a>

**針對所有群組原則管理員設定其他 AGPM 服務器連線**

1.  如果尚未設定任何 AGPM 服務器連線，請依照上述程式來設定所有網域的預設 AGPM 服務器。

2.  若要針對部分或所有網域設定個別的 AGPM 服務器（覆寫預設的 AGPM 服務器），請在 [**群組原則管理主控台**] 樹狀結構中，編輯套用至所有群組原則系統管理員的 GPO。 （如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo-agpm40.md)）。

3.  在 [**群組原則管理編輯器**] 視窗中，按一下 [**使用者**設定]、[**原則**]、[系統**管理範本**]、[ **Windows 元件**] 和 [ **AGPM**]。

4.  在 [詳細資料] 窗格中，按兩下 [ **agpm]： [指定 Agpm 伺服器**]。

5.  在 [**屬性**] 視窗中，選取 [**啟用**] 核取方塊，然後按一下 [**顯示**]。

6.  在 [**顯示內容**] 視窗中：

    1.  按一下**新增**。

    2.  針對 [**值名稱**]，輸入功能變數名稱（例如，server1.contoso.com）。

    3.  在 [**值**] 中，輸入要用於此網域的 AGPM 服務器名稱和埠（例如，server2.contoso.com:4600），然後按一下 **[確定]**。 （根據預設，AGPM 服務會偵聽埠4600。 若要使用不同的埠，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm40.md)。）

    4.  針對不是使用預設 AGPM 服務器的每個網域重複上述步驟。

7.  按一下 **[確定]** 以關閉 [**顯示內容**和**屬性**] 視窗。

8.  關閉 [**群組原則管理編輯器**] 視窗。 （如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo-agpm40.md)）。更新群組原則時，系統會針對所有群組原則管理員設定新的 AGPM 服務器連線。

### <a href="" id="bkmk-manuallyconfigurearchiveloc"></a>

如果您已集中設定 AGPM 服務器連線，則所有群組原則管理員都無法使用手動設定的選項。

**手動設定要針對您的帳戶顯示的 AGPM 服務器**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格中，按一下 [ **AGPM 服務器**] 索引標籤。

3.  針對管理此網域使用之封存的 AGPM 服務器（例如，server.contoso.com）和 AGPM 服務偵聽的埠（預設為埠4600）輸入完整的電腦名稱稱。

4.  按一下 [套用] **，然後按一下** **[是]** 以確認。

### 其他考量

-   您必須能夠編輯和部署 GPO，以執行集中為所有群組原則管理員設定 AGPM 服務器連線的程式。 如需更多詳細資料，請參閱[編輯 gpo](editing-a-gpo-agpm40.md)及[部署 gpo](deploy-a-gpo-agpm40.md) 。

-   選取的 AGPM 服務器會判斷哪些 Gpo 會顯示在 [**目錄**] 索引標籤上，以及 [**網域委派**] 索引標籤設定的套用位置。 如果不是透過管理範本來集中管理，每個群組原則管理員都必須設定此設定，以指向網域的 AGPM 服務器。

-   [群組原則建立人擁有者] 群組中的成員資格應該受到限制，不會使用 soit 來避開對 Gpo 存取的 AGPM 管理。 （在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）

### 其他參考資料

-   [設定進階群組原則管理](configuring-advanced-group-policy-management-agpm40.md)

 

 





