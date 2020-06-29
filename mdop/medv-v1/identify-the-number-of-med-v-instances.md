---
title: 找出 MED-V 執行個體數目
description: 找出 MED-V 執行個體數目
author: dansimp
ms.assetid: edea9bdf-a28c-4d24-9298-7bd6536c3a94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22f7d54318d2dc489461474e5531c5162d8c087d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810448"
---
# 找出 MED-V 執行個體數目


您必須判斷 MED-V 實例數，並為每個實例定義範圍，以便設計伺服器基礎結構。 MED-V 實例包括下列各項：

-   在伺服器上儲存的 MED-V 伺服器和 MED-V 工作區，包括 Active Directory 許可權。

-   儲存用戶端事件的 SQL Server 資料庫。 資料庫可能是由多個 MED-V 實例所共用。

-   封裝的 MED-V 影像的影像存放庫。 您可以透過多個 MED-V 實例來共用知識庫。

-   用來建立及打包影像及建立 MED-V 工作區的管理主控台。 主機不能同時由多個 MED-V 實例使用，但它可以中斷與一個 MED-V 伺服器的連線，然後再連接到不同的 MED-V 伺服器。

-   從伺服器接收 MED-V 工作區並授權使用的 MED-V 用戶端。

個別的 MED-V 實例不能整合或共用 MED-V-V 工作區。 因此，每個額外的實例 decentralizes 虛擬化管理。

## 決定所需的 MED-V 實例數


首先，假設您使用的是一個 MED-V 實例。 接著，請考慮下列條件，並針對每個適用于您基礎結構的條件，新增其他實例。

-   支援的使用者數目，每個 MED-V 實例最多可支援5000個併發活動用戶端。 [同時作用中] 表示用戶端與 MED-V 伺服器連線，並將輪詢傳送到伺服器以進行原則與影像更新，以及事件。 如果您的基礎結構將包含超過5000個作用中的使用者，請為每個5000使用者新增一個實例。

-   不受信任網域中的使用者-MED-V 伺服器會將 MED-V 工作區許可權與 Active Directory 使用者和/或群組建立關聯。 這需要在 MED-V 伺服器的信任界限記憶體在 MED-V 使用者。 針對個別、不受信任網域中的每個 MED-V 使用者組，新增一個 MED-V 實例。

-   隔離網路中的用戶端，判斷是否有任何用戶端位於隔離的網路中，因此需要個別的 MED-V 實例。 例如，組織通常會將實驗室網路與生產網路隔離。 針對將包含 MED-V 用戶端的每個隔離網路，新增 MED-V 實例。

-   組織需求-組織可能需要由個別的 MED-V 實例來管理一組用戶端，以確保安全性，例如，只將機密應用程式傳遞到網域中受限制的使用者組。 例如，工資部門可能會拒絕其他部門的使用者存取儲存用於工資處理原則的 MED-V 實例。 此外，如果組織使用分散式管理模型，則可能需要有 MED-V 用戶端的每個商務群組都需要個別的 MED-V 實例，才能讓群組管理自己的虛擬化環境。 針對每個個別的組織需求，新增一個 MED-V 實例。

-   法律考慮-國內安全性或隱私權問題及 fiduciary 定律可能需要分隔特定資料，或避免其他資料跨越全國框線。 如有需要，請新增其他 MED-V 實例以滿足此需求。

在您決定基礎結構所需的 MED-V 實例數之後，以及每個實例的理由，為每個實例提供名稱。

 

 





