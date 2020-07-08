---
title: 使用部署套件來部署 MED-V 工作區
description: 使用部署套件來部署 MED-V 工作區
author: dansimp
ms.assetid: e07fa70a-1a9f-486f-9a86-b33593b234da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc16b32fd44e45606df5502fda2e580d404dbb19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810071"
---
# 使用部署套件來部署 MED-V 工作區


部署套件安裝提供了一種安裝 MED-V 用戶端的方法，以及由管理員預先定義的所有設定。

使用部署套件時，套件是透過共用的網路或卸除式媒體來發佈。 影像可包含在套件中，或可單獨散佈。

在建立部署套件之前，請先確定您已建立 MED-V 影像準備好進行部署。 如需建立 MED-V 影像的詳細資訊，請參閱[建立 Med-v 影像](creating-a-med-v-image.md)。

準備好 MED-V 影像之後，請考慮在您的環境中散佈影像的最佳方法。 影像可以採用下列其中一種方式來散佈：

-   已上傳至 Web 並透過網頁下載進行發佈，您可以選擇使用修剪轉移技術。

-   使用影像預分段進行發佈。

-   包含在部署套件中，並與所有其他 MED-V 元件一起散佈。

如果圖像將包含在套件中，則不需要任何其他配置適用于影像。 如果 [部署套件] 中不包含該圖像，請執行下列其中一項操作：

-   如果您是透過網路部署影像，請將 MED-V 影像上傳到影像 Web 發佈伺服器。 如需有關配置影像 Web 發佈伺服器的資訊，請參閱[如何設定影像 Web 發佈伺服器](how-to-configure-the-image-web-distribution-server.md)。 如需將影像上傳到伺服器的詳細資訊，請參閱[如何將 Med-v 影像上傳到伺服器](how-to-upload-a-med-v-image-to-the-server.md)。

-   如果您是透過圖像預先暫存來部署影像，請設定 [前期階段] 資料夾，然後將 MED-V 影像推至資料夾。 如需有關如何設定影像預暫存的詳細資訊，請參閱[如何設定影像預暫存](how-to-configure-image-pre-staging.md)。

**記事** 如果您使用的是影像預暫存，請務必先設定影像前階段資料夾，然後再建立部署套件。 資料夾路徑必須包含在部署套件中。

 

最後，建立部署套件。 如需建立部署套件的詳細資訊，請參閱[如何設定部署套件](how-to-configure-a-deployment-package.md)。 套件完成後，發佈以進行部署。

部署套件發佈之後，就可以安裝 MED-V 用戶端和部署的影像。 如需安裝 MED-V 用戶端的詳細資訊，請參閱[如何安裝 med-v-v 用戶端](how-to-install-med-v-clientdeployment-package.md)。 如需有關部署影像的詳細資訊，請參閱[如何部署工作區影像](how-to-deploy-a-workspace-imagedeployment-package.md)。

 

 





