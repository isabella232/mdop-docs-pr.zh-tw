---
title: 獨立傳遞案例概觀
description: 獨立傳遞案例概觀
author: dansimp
ms.assetid: b109f309-f3c1-43af-996f-2a9b138dd171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f29b1c8d1c9ae97f7a21498369647f31f552839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800793"
---
# 獨立傳遞案例概觀


獨立傳遞案例是適用于低頻寬連接或無連線性的環境的理想應用程式虛擬化方案，可限制應用程式虛擬化桌面用戶端從集中式伺服器對流應用程式的功能。 在這些環境中，使用者通常會使用 Windows 安裝程式檔案，在遠端和裝置擁有者安裝應用程式。

您可以使用應用程式虛擬化 Sequencer 來建立包含 Windows 安裝程式檔案的順序應用程式。 這些套件包括虛擬化應用程式、發佈資訊，以及在用戶端系統上安裝套件所需的安裝程式常式。 安裝程式會將虛擬應用程式套件新增至 Microsoft Application Virtualization 桌面用戶端。 發佈資訊被設定為從本機位置載入應用程式，而不是在 WAN 上對流進行資料流。 使用者可以暫時連線到網路，以取得 Windows 安裝程式檔案，或從 DVD 執行這些檔案。

獨立的交付案例會為使用者提供下列好處：

-   簡單的部署作業。

-   在執行時間中不需要網路和伺服器。

-   已預先快取並可供所有使用者使用的應用程式。

獨立傳遞案例有下列限制：

-   內建的自動報告功能無法使用;報表必須是使用外部報表工具產生的。

-   應用程式必須手動傳送到用戶端，就像原始的 Windows 安裝程式檔案一樣。

## 相關主題


[如何手動安裝 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何在用戶端上發佈虛擬應用程式](how-to-publish-a-virtual-application-on-the-client.md)

 

 





