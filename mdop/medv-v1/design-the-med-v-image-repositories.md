---
title: 設計 MED-V 映像存放庫
description: 設計 MED-V 映像存放庫
author: dansimp
ms.assetid: e153154d-2751-4990-b94d-a2d76242c15f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0c59a0dd2d1b3a78bd211c6a6353a86c77d8fc2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810059"
---
# 設計 MED-V 映像存放庫


在建立並封裝 MED-V 影像之後，就可以將它們儲存在任何位置的檔案伺服器上。 檔案可能是透過 HTTP 或來自一或多個 IIS 伺服器的 HTTPS 傳送。 影像儲存庫可由多個 MED-V 實例共用。

若要設計影像資料庫，您必須先決定要將影像部署到每個用戶端的方式，以及該用戶端是否需要本機映射存放庫。 接著會設計並放置每個知識庫，以及隨附的 IIS 伺服器。

## 決定要部署影像的方式


針對每個 MED-V 工作區，決定如何規劃將 MED-V 影像部署到用戶端。 這對於決定要儲存打包的影像所需多少儲存庫（存放這些資料庫的位置），然後再設計這些資料庫是很重要的。

您可以透過下列方式部署打包的影像：

-   透過網路從影像發佈伺服器下載，由檔案伺服器與 IIS 伺服器組成。

-   在卸除式媒體（例如 USB 磁片磁碟機或 DVD）上。

-   使用企業軟體發行中心，預先暫存到用戶端電腦上的影像存放區目錄。

決定要使用哪一種方法或方法，將 MED-V 影像部署到每個用戶端，以及該位置是否需要影像儲存庫。

## 決定影像存放庫的數目


現在您已經決定了您所需的最小儲存庫數，請在下列任一準則適用時新增更多專案：

-   組織或管理的理由若要分隔 MED-V 影像，一些 MED-V 影像可能無法在同一個儲存庫中共存。 例如，機密的個人資料可能需要只提供給需要存取資料之一組有限員工的伺服器儲存空間。

-   隔離網路中的用戶端：如果影像將在網路上部署，請判斷是否有任何網路是隔離的，而且需要個別的儲存庫。 例如，組織通常會將實驗室網路與生產網路隔離。

-   遠端網路中的用戶端（如果影像將透過網路部署），某些用戶端電腦可能會以沒有足夠頻寬的網路連結分隔，在用戶端載入 MED-V 工作區時提供適當的體驗。 如有需要，請設計其他 MED-V 實例來解決此需求。

將這些資料庫新增到設計中。 針對每個存放庫選擇一個名稱，以及設計原因。 決定存放資料庫將保留哪些 MED-V 影像，以及哪些 MED-V 用戶端將使用知識庫中的圖像載入 MED-V 工作區。

## 設計並放置影像存放庫


當用戶端可以使用新的影像時，用戶端開始下載影像，可能同時進行。 這會在儲存庫中產生高需求，且必須在設計影像存放庫時納入考慮。

針對每個存放庫，決定要儲存的資料量。 加總將儲存在儲存庫中的影像大小。 這是檔案伺服器上所需的磁碟空間值。

接下來，新增可能從儲存庫下載 MED-V 影像的用戶端數量。 這是將新的 MED-V 影像載入到知識庫時，可能會發生的併發下載數目上限。 檔案伺服器必須用可滿足此建立的 IO 需求的磁片子系統設計。

影像存放庫可以與 MED-V 伺服器以及執行 SQL Server 的伺服器，或是在遠端檔案共用上。 您也可以在 Windows Server2008 Hyper-v VM 中執行它。 檢查影像存放庫將提供服務的用戶端的網路位置，然後將知識庫放在具有足夠頻寬的網路位置，以符合這些用戶端的服務層級預期。

### 容錯

如果影像儲存庫無法使用，用戶端將無法下載新的或更新的 MED-V 影像。 若要針對檔案伺服器和容錯磁片設計容錯選項，請參閱[基礎結構規劃與設計 MICROSOFT SQL server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南。

## 設計並放置 IIS 伺服器


此區段僅在用戶端將在使用 HTTP 或 HTTPS 的網路上下載影像檔案時才適用。

IIS 伺服器可以與 MED-V 伺服器以及執行 SQL Server 的伺服器共存于同一個系統上。 它也可以在 Windows Server2008 Hyper-v VM 中執行。 IIS 伺服器基礎結構必須具備足夠的輸送量，才能將影像傳送給組織中服務層級預期的用戶端。 它必須設計在能滿足此建立的 IO 需求的磁片子系統上。

針對每個影像儲存庫，加總可使用 IIS 下載 MED-V 影像的用戶端數量。 這是將影像載入到存放庫時，可能會發生的併發下載數目上限。 使用 [輸送量總和] 和 [服務層級預期][定義專案範圍](define-the-project-scope.md)來規劃 IIS 伺服器基礎結構的設計，並判斷要為儲存庫配置適當的頻寬量。

若要設計 IIS 基礎結構，請參閱[基礎結構規劃及設計 Microsoft 網際網路資訊服務](https://go.microsoft.com/fwlink/?LinkId=160826)指南。

### 容錯

如果 IIS 伺服器基礎結構無法使用，用戶端將無法下載新的或更新的影像。 若要設定容錯，可以將 Windows Server2008 的 IIS 伺服器放在容錯移轉叢集中。 若要為 IIS 伺服器基礎結構設計容錯性，請參閱[基礎結構規劃及設計 Microsoft 網際網路資訊服務](https://go.microsoft.com/fwlink/?LinkId=160826)指南。

## 相關主題


[使用企業軟體發佈系統來部署 MED-V 工作區](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)

[使用部署套件來部署 MED-V 工作區](deploying-a-med-v-workspace-using-a-deployment-package.md)

 

 





