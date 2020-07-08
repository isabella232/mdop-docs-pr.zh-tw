---
title: 如何部署工作區映像
description: 如何部署工作區映像
author: dansimp
ms.assetid: ccc8e89b-1625-4b58-837e-4c6d93d46070
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4cb16b0a4c278d135fdc9b737aa7a6e9b46115e1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812093"
---
# 如何部署工作區映像


使用企業軟體發佈系統時，可以使用下列其中一種方式，將新影像部署到用戶端電腦上：

-   [網頁下載](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [影像預暫存](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a>如何透過 Web 部署工作區圖像


**透過 Web 部署工作區圖像**

1.  將 MED-V 圖像上傳到伺服器。

    如需有關上傳影像的詳細資訊，請參閱[如何將 Med-v 影像上傳到伺服器](how-to-upload-a-med-v-image-to-the-server.md)。

2.  使用您的企業軟體發佈系統，在使用者的電腦上安裝 MED-V 封裝。

    如需安裝 MED-V 用戶端 .msi 套件的相關資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientesds.md)。

    MED-V 用戶端會在第一次安裝並啟動。 在初次開機時，用戶端會從用戶端安裝中指定的伺服器位址下載影像。

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a>如何使用影像預暫存來部署工作區圖像


**使用影像預暫存來部署工作區圖像**

1.  建立影像的暫存資料夾，並將影像推至資料夾。

    如需有關如何設定影像預暫存的詳細資訊，請參閱[如何設定影像預暫存](how-to-configure-image-pre-staging.md)。

2.  使用您的企業軟體發佈系統，在使用者的電腦上安裝 MED-V 封裝。

    如需安裝 MED-V 用戶端 .msi 套件的相關資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientesds.md)。

    MED-V 用戶端會在第一次安裝並啟動。 在第一次啟動時，用戶端會從在用戶端安裝中指定的前階段資料夾中，提取影像。

## 相關主題


[如何設定映像 Web 發佈伺服器](how-to-configure-the-image-web-distribution-server.md)

 

 





