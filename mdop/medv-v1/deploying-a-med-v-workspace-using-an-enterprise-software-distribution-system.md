---
title: 使用企業軟體發佈系統來部署 MED-V 工作區
description: 使用企業軟體發佈系統來部署 MED-V 工作區
author: dansimp
ms.assetid: 867faed6-74ce-4573-84be-8bf26e66c08c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fb9ebbc0fb605f84c5a8e67fc77fd9be51b29ff4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810070"
---
# 使用企業軟體發佈系統來部署 MED-V 工作區


MED-V 用戶端可以使用企業軟體發佈系統（例如 Microsoft System Center Configuration Manager）進行發佈。

**記事** 如果 MED-V 是使用 Microsoft System Center Configuration Manager 安裝，則在建立 MED-V 的套件時，請將 [執行模式] 設定為 [系統管理許可權]。

 

在使用企業軟體發佈系統部署 MED-V 之前，請先確定您已建立 MED-V 影像以供部署。 如需建立 MED-V 影像的詳細資訊，請參閱[建立 Med-v 影像](creating-a-med-v-image.md)。

準備好 MED-V 影像之後，請考慮在您的環境中散佈影像的最佳方法。 影像可以採用下列其中一種方式來散佈：

-   已上傳至 Web 並透過網頁下載進行發佈，可選擇利用修剪轉移技術。

-   使用影像預分段進行發佈。

## 透過網路部署影像


如果您是透過網路部署影像，請將 MED-V 影像上傳到影像 Web 發佈伺服器。 如需有關配置影像 Web 發佈伺服器的資訊，請參閱[如何設定影像 Web 發佈伺服器](how-to-configure-the-image-web-distribution-server.md)。 如需將影像上傳到伺服器的詳細資訊，請參閱[如何將 Med-v 影像上傳到伺服器](how-to-upload-a-med-v-image-to-the-server.md)。

## 透過預分段部署影像


如果您是透過圖像預先暫存來部署影像，請設定 [前期階段] 資料夾，然後將 MED-V 影像推至資料夾。 如需有關設定影像預暫存的詳細資訊，請參閱[如何設定影像預暫存](how-to-configure-image-pre-staging.md)。

**記事** 如果您使用的是影像預暫存，請務必先設定影像前階段資料夾，然後再推送用戶端 .msi 封裝。 資料夾路徑必須包含在用戶端 .msi 套件中。

 

最後，使用您的企業軟體發行中心推送用戶端 .msi 封裝。 接著，可以安裝 MED-V 並部署影像。 如需安裝 MED-V 用戶端的詳細資訊，請參閱[如何安裝 med-v-v 用戶端](how-to-install-med-v-clientesds.md)。 如需有關部署影像的詳細資訊，請參閱[如何部署工作區影像](how-to-deploy-a-workspace-imageesds.md)。

 

 





