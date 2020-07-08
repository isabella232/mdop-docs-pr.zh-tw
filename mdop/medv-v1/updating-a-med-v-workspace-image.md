---
title: 更新 MED-V 工作區映像
description: 更新 MED-V 工作區映像
author: dansimp
ms.assetid: 1b9c4a73-3487-43d2-98e3-43dbc79e10e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60a5d12622e0cb7012c6d0a22124d63c085f6d0a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811403"
---
# 更新 MED-V 工作區映像


您可以使用下列其中一種方式來更新影像：

-   您可以使用企業軟體發佈系統，將更新推送到客體作業系統。

-   更新可以上傳到影像 Web 發佈伺服器，然後由用戶端下載並套用至 MED-V 影像。

-   MED-V 基底影像可以更新並重新部署。

## <a href="" id="bkmk-howtoupdateamedvimageusinganesd"></a>如何使用企業軟體發佈系統更新 MED-V 影像


**使用企業軟體發佈系統來更新 MED-V 影像**

-   請參閱您正在使用的系統檔。

## <a href="" id="bkmk-howtoupdateamedvimageusingwebdownload"></a>如何使用網頁下載來更新 MED-V 影像


**使用網頁下載來更新 MED-V 影像**

1.  在 MED-V 管理中，請在 [**虛擬機器**] 索引標籤上，確保將下列設定套用到與要更新之 med-v 影像相關聯的 med-v 工作區原則：

    -   已選取 [**新版本可供使用時的建議更新**] 核取方塊。

    -   或者，用戶端應該在已選取 [**下載此工作區的影像時，使用修剪轉移**] 核取方塊。

    如需詳細資訊，請參閱[如何將虛擬機器設定套用至 Med-v 工作區](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)。

2.  將影像更新上傳到影像 Web 發佈伺服器。

    所有含有需要更新之影像的用戶端，都會自動下載更新並將其套用至影像。

## <a href="" id="bkmk-howtoupdateamedvbaseimage"></a>如何更新 MED-V 基底影像


**若要更新 MED-V 基底影像**

1.  在 [虛擬 PC2007] 中開啟現有的影像。

2.  對影像進行所需的變更，更新影像（例如安裝新軟體）。

3.  關閉 [虛擬 PC2007]。

4.  測試影像。

5.  測試完圖像之後，請使用與現有影像相同的名稱將它打包至本機知識庫。

    **記事** 如果您將影像命名為與現有版本不同的名稱，將會建立新的影像，而不是現有影像的新版本。

     

6.  將新版本上傳到伺服器、將其推入影像的暫存資料夾，或透過部署套件發佈。

## 相關主題


[建立 MED-V 映像](creating-a-med-v-image.md)

[如何更新 MED-V 映像](how-to-update-a-med-v-image.md)

[設定 MED-V 工作區原則](configuring-med-v-workspace-policies.md)

[如何設定映像 Web 發佈伺服器](how-to-configure-the-image-web-distribution-server.md)

 

 





