---
title: 進階群組原則管理概觀
description: 進階群組原則管理概觀
author: dansimp
ms.assetid: 028de9dd-848b-42bc-a982-65ba5c433772
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38396de6bd8bdace72d3add1bba09769ae26de32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809381"
---
# 進階群組原則管理概觀


您可以使用高級群組原則管理（AGPM）來延伸群組原則管理主控台（GPMC）的功能，為群組原則物件（Gpo）提供全面的變更控制與增強的管理。

## 含變更控制的群組原則物件開發


使用 AGPM，您可以將每個 GPO 的複本儲存在中央封存中，這樣群組原則管理員就可以在離線時查看及修改它，而不會立即影響已部署的 GPO 版本。 此外，AGPM 會在封存中儲存每個受控制 GPO 版本的複本，以便在需要時回滾到較舊的版本。

「取出」和「取出」一詞的用法與文件庫（或提供以程式設計開發的原始程式碼控制、版本控制或原始程式碼管理）中的方式幾乎相同。 若要使用文件庫中的活頁簿，您可以從文件庫中取出該活頁簿。 您已取出時，其他人都無法使用它。完成書籍之後，您可以將它存回文件庫，讓其他人可以使用。

使用 AGPM 開發 Gpo 時：

1.  建立新的受控 GPO 或控制先前不受管理的 GPO。

2.  請取出該 GPO，讓您和您只能進行修改。

3.  編輯 GPO。

4.  核取已編輯的 GPO，讓其他人可以修改，或部署它。

5.  審閱變更。

6.  將 GPO 部署到生產環境。

## 以角色為基礎的委派


AGPM 提供全面且便於使用的以角色為基礎的委派。 網域層級許可權可讓 AGPM 管理員在不提供存取其他網域的情況下，提供個別網域的存取權。 [GPO 式委派] 可讓 AGPM 系統管理員只允許存取特定的 Gpo。

在 AGPM 中，有專門定義的角色： AGPM 系統管理員（完全控制）、審核者、編輯者和檢閱者。 AGPM 系統管理員角色包含所有其他角色的許可權。 根據預設，只有核准者具備將 Gpo 部署到生產環境的權力，保護環境不受較少經驗的編輯者無意間失誤的錯誤。 而且根據預設，所有角色都包含檢閱者角色，因此能夠在報表中查看 GPO 設定。 不過，AGPM 提供的 AGPM 系統管理員可以靈活地自訂 GPO 存取，以符合貴組織的需求。

## 多重群組原則系統管理員環境中的委派


在多人對 Gpo 進行變更的環境中，AGPM 管理員會以群組或個人身分委派編輯者、核准者和檢閱者的許可權。 如需編輯者和核准者的一般 GPO 開發程式，請參閱[檢查清單：建立、編輯和部署 GPO](checklist-create-edit-and-deploy-a-gpo.md)。

### 其他參考資料

-   [檢查清單︰建立、編輯及部署 GPO](checklist-create-edit-and-deploy-a-gpo.md)

-   [執行 AGPM 系統管理員工作](performing-agpm-administrator-tasks.md)

-   [執行編輯器工作](performing-editor-tasks.md)

-   [執行核准者工作](performing-approver-tasks.md)

-   [執行檢閱者工作](performing-reviewer-tasks.md)

-   [疑難排解進階群組原則管理](troubleshooting-advanced-group-policy-management.md)

-   [使用者介面：進階群組原則管理](user-interface-advanced-group-policy-management.md)

 

 





