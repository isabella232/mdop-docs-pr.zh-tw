---
title: 部署 DaRT 7.0 復原映像
description: 部署 DaRT 7.0 復原映像
author: dansimp
ms.assetid: 6bba7bff-800f-44e4-bcfc-e143115607ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cef626e50bf1049529c51afca5e536b03b3d915d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800148"
---
# 部署 DaRT 7.0 復原映像


在您建立包含 Microsoft Diagnostics 與復原工具集（DaRT）7復原影像的國際標準組織（ISO）檔案之後，您就可以在整個企業中部署 DaRT 復原影像，讓最終使用者和技術支援人員都能使用它。 您可以使用四種受支援的方法來部署 DaRT 恢復影像。

-   將 ISO 映像檔燒錄至 CD 或 DVD

-   將 ISO 映像檔的內容儲存至 USB 快閃記憶體磁片磁碟機（UFD）

-   從 ISO 映像解壓縮啟動 .wim 檔案，並部署為可供最終使用者電腦使用的遠端分區

-   從 ISO 映像抽取 boot.ini 檔案，並在新的 Windows 7 安裝的 [恢復] 分區中部署

**重要** **DaRT 復原映像嚮導**只提供燒錄 CD 或 DVD 的選項。 所有其他儲存及部署復原影像的方法，都需要一些額外的步驟，涉及 DaRT 中未包含的工具。 本節中提供了這些其他方法的一些指導方針和連結。

 

## 使用 USB 快閃記憶體磁片磁碟機部署 DaRT 復原影像


完成執行 DaRT 復原映射嚮導之後，您可以使用 at 中的工具，將 <https://go.microsoft.com/fwlink/?LinkId=218888> ISO 映像檔案複製到 USB 快閃記憶體磁片磁碟機（UFD）。

[如何使用 USB 快閃磁碟來部署 DaRT 復原映像](how-to-deploy-the-dart-recovery-image-using-a-usb-flash-drive-dart-7.md)

## 將 DaRT 復原影像部署成恢復分區的一部分


在您完成執行 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為 Windows 7 影像中的復原分區。

[如何部署 DaRT 復原映像做為修復磁碟分割的一部分](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-7.md)

## 將 DaRT 復原映像部署為遠端分區


當您執行了 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為網路上的遠端分區。

[如何部署 DaRT 復原映像做為遠端磁碟分割](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-7.md)

## 維護部署 DaRT 恢復影像的其他資源


-   [部署 DaRT 7.0](deploying-dart-70-new-ia.md)

 

 





