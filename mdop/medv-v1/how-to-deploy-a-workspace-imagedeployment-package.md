---
title: 如何部署工作區映像
description: 如何部署工作區映像
author: dansimp
ms.assetid: b2c77e0d-101d-4956-a27c-8beb0e4f262e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d691514691286c92bd62d6fda6666345e17eb9f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812099"
---
# 如何部署工作區映像


使用部署套件時，可以使用下列其中一種方法，將新的影像部署到用戶端電腦上：

-   [網頁下載](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [影像預暫存](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

-   [在部署套件內部署映射](#bkmk-howtodeployaworkspaceimageusingadeploymentapackage)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a>如何透過 Web 部署工作區圖像


**透過 Web 部署工作區圖像**

1.  將 MED-V 圖像上傳到伺服器。

    如需有關上傳影像的詳細資訊，請參閱[如何將 Med-v 影像上傳到伺服器](how-to-upload-a-med-v-image-to-the-server.md)。

2.  建立部署套件，並將伺服器路徑納入至影像的位置。

    如需建立部署套件的相關資訊，請參閱[如何設定部署套件](how-to-configure-a-deployment-package.md)。

3.  將套件部署到最終使用者。

    如需有關部署套件的詳細資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientdeployment-package.md)。

    MED-V 用戶端會在第一次安裝並啟動。 在初次開機時，用戶端會從用戶端安裝中指定的伺服器位址下載影像。

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a>如何使用影像預暫存來部署工作區圖像


**使用影像預暫存來部署工作區圖像**

1.  建立影像的暫存資料夾，並將影像推至資料夾。

    如需有關如何設定影像預暫存的詳細資訊，請參閱[如何設定影像預暫存](how-to-configure-image-pre-staging.md)。

2.  建立部署套件，並包含影像前暫存資料夾的路徑。

    如需建立部署套件的相關資訊，請參閱[如何設定部署套件](how-to-configure-a-deployment-package.md)。

3.  將套件部署到最終使用者。

    如需有關部署套件的詳細資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientdeployment-package.md)。

    MED-V 用戶端會在第一次安裝並啟動。 在第一次啟動時，用戶端會從在用戶端安裝中指定的前階段資料夾中，提取影像。

## <a href="" id="bkmk-howtodeployaworkspaceimageusingadeploymentapackage"></a>如何使用部署套件部署工作區圖像


**使用部署套件部署工作區圖像**

1.  建立部署套件，並將影像包含在套件中。

    如需建立部署套件的相關資訊，請參閱[如何設定部署套件](how-to-configure-a-deployment-package.md)。

2.  將套件部署到最終使用者。

    如需有關部署套件的詳細資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientdeployment-package.md)。

    在套件安裝過程中，會將圖像匯入到主機。

## 相關主題


[如何設定映像 Web 發佈伺服器](how-to-configure-the-image-web-distribution-server.md)

[如何設定部署套件](how-to-configure-a-deployment-package.md)

 

 





