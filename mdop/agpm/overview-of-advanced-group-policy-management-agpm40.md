---
title: 進階群組原則管理概觀
description: 進階群組原則管理概觀
author: dansimp
ms.assetid: 2c12f3b4-8472-4c5b-b7f8-1c98a80d6b47
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94e47075ae865096f9fe7d327cc7b11cb54217d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809386"
---
# 進階群組原則管理概觀


您可以使用 [高級群組原則管理] （AGPM）來延伸群組原則管理主控台（GPMC）的功能，以提供完整的變更控制，以及改善群組原則物件（Gpo）的管理。

## 含變更控制的群組原則物件開發


使用 AGPM，您可以將每個 GPO 的複本儲存在中央封存中，這樣群組原則管理員就可以在離線時查看並變更它，而不會立即影響已部署的 GPO 版本。 此外，AGPM 會在封存中儲存每個受控制 GPO 版本的複本，以便在必要時回滾到較舊的版本。

「取出」和「取出」一詞，就如同在文件庫中（或在提供程式設計中提供變更控制、版本控制或來源控制）的應用程式中使用。 若要使用文件庫中的活頁簿，您可以從文件庫中取出該活頁簿。 您已取出時，其他人都無法使用它。完成書籍之後，您可以將它存回文件庫，讓其他人可以使用。

若要使用這些 GPO 控制功能，您將會在 [群組原則管理編輯器] 中按一下 [變更控制] 節點。 只有在您安裝了 AGPM 用戶端之後，才會出現 [變更控制] 節點。

使用 AGPM 開發 Gpo 時：

1.  建立新的受控 GPO 或控制先前不受管理的 GPO。

2.  請取出該 GPO，讓您和您的使用者都能變更它。

3.  編輯 GPO。

4.  核取已編輯的 GPO，讓其他人可以變更，或進行部署。

5.  審閱變更。

6.  將 GPO 部署到生產環境。

## 以角色為基礎的委派


AGPM 提供全面且便於使用的以角色為基礎的委派，可管理對封存中 Gpo 的存取權。 網域層級許可權可讓 AGPM 管理員在不提供存取其他網域的情況下，提供個別網域的存取權。 [GPO 式委派] 可讓 AGPM 管理員提供對特定 Gpo 的存取權，而不提供全域存取權。

在 AGPM 中，有專門定義的角色： AGPM 系統管理員（完全控制）、審核者、編輯者和檢閱者。 AGPM 系統管理員角色包含所有其他角色的許可權。 根據預設，只有核准者能將 Gpo 部署到網域的生產環境，以避免較少經驗的編輯者的錯誤來保護環境。 而且根據預設，所有角色都包含檢閱者角色，因此能夠在報表中查看 GPO 設定。 不過，AGPM 提供的 AGPM 系統管理員可以靈活地自訂 GPO 存取，以符合貴組織的需求。

## 多重群組原則系統管理員環境中的委派


在多人變更 Gpo 的環境中，AGPM 管理員會以群組或個人身分委派編輯者、核准者和檢閱者的許可權。 如需編輯者和核准者的一般 GPO 開發程式，請參閱[檢查清單：建立、編輯和部署 GPO](checklist-create-edit-and-deploy-a-gpo-agpm40.md)。

### 其他參考資料

-   [進階群組原則管理 4.0](advanced-group-policy-management-40.md)

 

 





