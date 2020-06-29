---
title: 定義專案範圍
description: 定義專案範圍
author: dansimp
ms.assetid: 84637d2a-2e30-417d-b150-dc81f414b3a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4f33562452327bba9036f56d9f6f96650f00c1f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810077"
---
# 定義專案範圍


定義專案範圍時，請判斷下列事項：

1.  MED-V 的使用者-使用者在判斷 MED-V 用戶端安裝的位置和 MED-V 實例的數目，以及 MED-V 影像儲存庫的數量和位置，使用使用者的位置和數目。

2.  由 MED-V 管理的虛擬機器（VM）影像，以判斷發佈影像及放置影像存放庫的方法。

3.  組織的服務層級預期-可判斷 MED-V 伺服器和資料庫以及影像存放庫的效能與容錯需求。

4.  與業務驗證-確保規劃的基礎結構對企業有何影響的完整瞭解。

## 定義 MED-V 端使用者


首先，決定最終使用者的位置，以及每個位置的使用者數目。 接著，取得網路基礎結構圖表，以顯示使用者位置，以及這些位置的可用頻寬。 第三，找出使用者是否在不同位置間出差。 如果使用者出差，可能需要在伺服器基礎結構和影像儲存庫的設計中使用額外的容量。

## 決定由 MED-V 管理的 MED-V 圖像


在已定義 MED-V 使用者之後，決定將由 MED-V 針對每個位置的使用者管理哪些 Vm。

如果有任何 Vm 儲存在集中式文件庫中，請判斷文件庫的位置，以便將它評估成可做為 MED-V 儲存庫使用。

## <a href="" id="determine-the-organization-s-service-level-expectations"></a>判斷組織的服務層級預期


針對每個 MED-V 工作區，請注意要載入新影像的可接受時間，以及要部署重要更新的時間範圍。

如果適用的話，請記錄 MED-V 報告的服務層級預期，以用於伺服器基礎結構的設計。

## 使用業務進行驗證


詢問商業專案關係人及應用程式擁有者下列問題：

-   是否有任何現有的圖像可結合使用？ 例如，如果應用程式 A on WindowsXP 是一個 VPC 影像，而 WindowsXP 上的應用程式 B 是另一個 VPC 影像，可能是因為單一影像可以包含這兩個應用程式，因而減少了影像下載所需的儲存庫空間和頻寬。

-   如果由 MED-V 在 VM 中傳送，則是由作用中的應用程式授權並支援嗎？ 透過 MED-V 提供應用程式，與應用程式供應商確認不會違反授權和支援條款。

 

 





