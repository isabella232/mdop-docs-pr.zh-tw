---
title: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
description: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
author: dansimp
ms.assetid: 07c5d539-51d9-4759-adc7-72b40d5d7bb3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e3647d684f64a0635e2875314498bde841204369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810521"
---
# 如何部署 DaRT 復原映像做為修復磁碟分割的一部分


當您執行完 Microsoft Diagnostics 與復原工具集（DaRT）8.0 恢復鏡像嚮導並建立復原影像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為 Windows 8 影像中的復原分區。 建議使用分區，因為任何使 Windows 作業系統無法啟動的損壞問題，也會阻止復原映射的啟動。 個別的分區也不需要提供兩次 BitLocker 復原金鑰了。 考慮隱藏式磁碟分割，避免使用者在檔案上儲存檔案。

**在 Windows 8 映射的 [恢復] 分區中部署 DaRT**

1.  在您的 Windows 8 映射中建立一個等於或大於您使用**DaRT 8.0 [復原映像] 嚮導**所建立之 ISO 映像檔案大小的目標磁碟分割。

    DaRT 分區所需的最小大小是500MB，以適應 DaRT 中的遠端連線功能。

2.  從 DaRT ISO 映像檔解壓縮啟動 .wim 檔案。

    1.  使用您公司的慣用方法，裝載您在 [**建立啟動映射**] 頁面上建立的 ISO 映像檔。

    2.  開啟 ISO 映像檔，然後從裝載的影像中的 [\\sources] 資料夾將 boot.ini 檔案複製到電腦上或外部磁片磁碟機上的位置。

        **記事** 如果您燒錄了復原影像的 CD、DVD 或 USB，您可以在移除的媒體上開啟檔案，然後從 \\sources 資料夾中複製 boot.ini 檔案。 如果您複製 boot.ini 檔案，就不需要裝載影像。

         

3.  使用 boot.ini 檔案，透過您公司的標準方法建立自訂的 Windows RE 影像，以建立可引導的復原分區。

    如需如何建立或自訂恢復分區的詳細資訊，請參閱[自訂 WINDOWS RE 體驗](https://go.microsoft.com/fwlink/?LinkId=214222)。

4.  使用 [恢復] 分區取代 Windows 8 映射中的目標分區。

    如需有關如何部署恢復解決方案以在系統發生故障時重新安裝 factory 映射的詳細資訊，請參閱[部署系統復原影像](https://go.microsoft.com/fwlink/?LinkId=214221)。

## 相關主題


[建立 DaRT 8.0 復原映像](creating-the-dart-80-recovery-image-dart-8.md)

[部署 DaRT 復原映像](deploying-the-dart-recovery-image-dart-8.md)

[規劃 DaRT 8.0](planning-for-dart-80-dart-8.md)

 

 





