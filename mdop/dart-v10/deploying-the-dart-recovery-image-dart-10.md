---
title: 部署 DaRT 復原映像
description: 部署 DaRT 復原映像
author: dansimp
ms.assetid: 2b859da6-e31a-4240-8868-93a754328cf2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7de3ed9c01a1808364158124c4f2dcab835823a7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800263"
---
# 部署 DaRT 復原映像


在您建立包含 Microsoft Diagnostics 與復原工具集（DaRT）10復原影像的國際標準組織（ISO）檔案之後，您就可以在整個企業中部署 DaRT 10 復原影像，讓使用者可以使用它供最終使用者和技術支援人員使用。 您可以使用四種受支援的方法來部署 DaRT 恢復影像。 若要查看每個方法的優點與缺點，請參閱[規劃如何儲存及部署 DaRT 10 復原影像](planning-how-to-save-and-deploy-the-dart-10-recovery-image.md)。

使用 DaRT 復原影像嚮導將 ISO 映像檔燒制到 CD 或 DVD

使用 DaRT 復原影像嚮導，將 ISO 映像檔的內容儲存至 USB 快閃記憶體磁片磁碟機（UFD）

從 ISO 映像解壓縮啟動 .wim 檔案，並部署為可供最終使用者電腦使用的遠端分區

從 ISO 映像解壓縮啟動 .wim 檔案，並在新的 Windows 10 安裝的恢復分區中部署

**重要** **DaRT 復原影像嚮導**提供將影像燒制至 CD、DVD 或 UFD 的選項，但其他儲存及部署恢復影像的方法需要額外的步驟，涉及 DaRT 中未包含的工具。 本節中提供了這些其他方法的一些指導方針和連結。

 

## 將 DaRT 復原影像部署成恢復分區的一部分


在您完成執行 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔解壓縮 boot.ini 檔案，並將它部署為 Windows 10 影像中的復原分區。

[如何部署 DaRT 復原映像做為修復磁碟分割的一部分](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-10.md)

## 將 DaRT 復原映像部署為遠端分區


您可以在中央網路啟動伺服器（例如 Windows 部署服務）上託管復原影像，並允許使用者或支援人員將影像資料流程傳輸給電腦的需求。

[如何部署 DaRT 復原映像做為遠端磁碟分割](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-10.md)

## 部署 DaRT 恢復影像的其他資源


[部署 DaRT 10](deploying-dart-10.md)

 

 





