---
title: 規劃部署 DaRT 7.0
description: 規劃部署 DaRT 7.0
author: dansimp
ms.assetid: 05e97cdb-a8c2-46e4-9c75-a7d12fe26fe8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 09725e994a95f4f93ae655402e7577e137e33f18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808684"
---
# 規劃部署 DaRT 7.0


您必須先考慮幾個不同的部署設定和先決條件，才能建立您的部署規劃。 本節包含可協助您收集資訊的資訊，這些資訊可協助您收集最符合您的業務需求的部署方案。

規劃 Microsoft Diagnostics 與修復工具組（DaRT）7安裝時，請考慮下列事項：

-   當您安裝 DaRT 時，您可以在 IT 系統管理員電腦上安裝所有與執行 DaRT 相關聯之工作的功能。 或者，您只能安裝在 IT 系統管理員電腦上建立復原影像的 DaRT 功能。 然後，在技術支援人員的電腦上安裝 DaRT （例如**DaRT 遠端連線檢視器**和損**毀分析**程式）所用的功能。

-   若要能夠遠端執行 DaRT，請確認 [服務台代理電腦] 和您在遠端進行疑難排解的所有電腦都在相同的網路上。

-   在您將 DaRT 推出到生產環境之前，您可以先組建實驗環境以進行測試。 測試實驗室至少應包含兩台電腦，其中一個是作為 IT 系統管理員/支援者代理電腦，另一個則充當最終使用者電腦。 或者，如果您想要將 IT 系統管理員的職責與技術支援人員的責任區分開來，您可以在實驗室中使用三台電腦。

## 查看支援的設定


您應該查看 Microsoft Diagnostics 與復原工具集（DaRT）7支援的設定資訊，以確認您針對用戶端或功能安裝所選取的電腦符合最低硬體與作業系統需求。

[DaRT 7.0 支援的組態](dart-70-supported-configurations-dart-7.md)

## 規劃建立 DaRT 恢復影像


當您建立 DaRT 復原影像時，必須決定要在影像中包含哪些工具。 當您作出決定時，請記住，最終使用者可能會偶爾存取各種 DaRT 工具。 當您建立恢復影像時，您也會指定是否要包含其他驅動程式或檔案。 決定您想要包含在 DaRT 復原影像中的任何其他驅動程式或檔案的位置。

您應該注意到建立 DaRT 復原影像的先決條件及其他額外規劃建議。

[規劃建立 DaRT 7.0 復原映像](planning-to-create-the-dart-70-recovery-image.md)

## 規劃儲存及部署 DaRT 恢復影像


您可以使用數種方法儲存和部署 DaRT 恢復影像。 當您決定要使用的方法時，請考慮每個方法的優點與缺點。 此外，請考慮您想要在企業中使用 DaRT 的方式。

**記事** 您可能會想要在您的組織中使用一個以上的方法。 例如，在大多數情況下，您可以從遠端分區引導至 DaRT，並在使用者電腦無法連線到網路時，有可用的 USB 快閃記憶體磁片磁碟機。

 

[規劃如何儲存和部署 DaRT 7.0 復原映像](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)

## 規劃部署 DaRT 的其他資源


[規劃 DaRT 7.0](planning-for-dart-70-new-ia.md)

 

 





