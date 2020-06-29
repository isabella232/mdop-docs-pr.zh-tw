---
title: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
description: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
author: dansimp
ms.assetid: 462f2d08-f03b-4a07-b2d3-c69205dc6f70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e75c3f9e58d784c13003feb84001f89c4607115d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810028"
---
# 如何部署 DaRT 復原映像做為修復磁碟分割的一部分


在您完成執行 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為 Windows 7 影像中的復原分區。

**在 Windows 7 影像的 [恢復] 分區中部署 DaRT**

1.  在您的 Windows 7 影像中建立一個等於或大於您使用**DaRT 復原影像嚮導**所建立之 ISO 映像檔案大小的目標磁碟分割。

    DaRT 分區所需的最小大小約為300MB。 不過，我們建議您450MB，以適應 DaRT 中的遠端連線功能。

2.  從 DaRT ISO 映像檔解壓縮啟動 .wim 檔案。

    1.  裝載您在 [**建立啟動影像**] 對話方塊中建立的 ISO 映像檔，方法是使用貴公司用來裝載影像的最佳方式。

    2.  開啟 ISO 映像檔，然後從裝載的影像中的 [\\sources] 資料夾將 boot.ini 檔案複製到電腦上或外部磁片磁碟機上的位置。

        **記事** 如果您燒錄了復原影像的 CD 或 DVD，您可以在 CD 或 DVD 上開啟檔案，然後從 \\sources 資料夾中複製 boot.ini 檔案。 這可讓您略過裝入影像的需求。

         

3.  使用 boot.ini 檔案，透過您公司的標準方法建立自訂的 Windows RE 影像，以建立可引導的復原分區。

    如需如何建立或自訂恢復分區的詳細資訊，請參閱[自訂 WINDOWS RE 體驗](https://go.microsoft.com/fwlink/?LinkId=214222)。

4.  使用 [恢復] 分區取代 Windows 7 影像中的目標分區。

在您的 Windows 7 映射準備就緒之後，您可以使用公司的標準影像部署程式，將影像發佈到企業中的電腦。 如需如何建立 Windows 7 影像的詳細資訊，請參閱[建立 windows 7 的標準影像：逐步指南](https://go.microsoft.com/fwlink/?LinkId=212103)。

如需有關如何部署恢復解決方案以在系統發生故障時重新安裝 factory 映射的詳細資訊，請參閱[部署系統復原影像](https://go.microsoft.com/fwlink/?LinkId=214221)。

## 相關主題


[部署 DaRT 7.0 復原映像](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





