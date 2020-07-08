---
title: 如何部署 DaRT 復原映像做為遠端磁碟分割
description: 如何部署 DaRT 復原映像做為遠端磁碟分割
author: dansimp
ms.assetid: 757c9340-8eac-42e8-85de-4302e436713a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a3acdbf72a2c6dac0238f868c7280f1c389b1311
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810034"
---
# 如何部署 DaRT 復原映像做為遠端磁碟分割


當您執行了 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為網路上的遠端分區。

**將 DaRT 部署為遠端分區**

1.  從 DaRT ISO 映像檔解壓縮啟動 .wim 檔案。

    1.  裝載您在 [**建立啟動影像**] 對話方塊中建立的 ISO 映像檔，方法是使用貴公司用來裝載影像的最佳方式。

    2.  開啟 ISO 映像檔，然後從裝載的影像中的 [\\sources] 資料夾將 boot.ini 檔案複製到電腦上或外部磁片磁碟機上的位置。

        **記事** 如果您燒錄了復原影像的 CD 或 DVD，您可以在 CD 或 DVD 上開啟檔案，然後從 \\sources 資料夾中複製 boot.ini 檔案。 這可讓您略過裝入影像的需求。

         

2.  將啟動 .wim 檔案部署到可從企業中的最終使用者電腦存取的 WDS 伺服器。

3.  依照您的標準 WDS 部署程式，將 WDS 伺服器設定為使用 DaRT 的 boot.ini 檔案。

如需如何將 DaRT 部署為遠端分區的詳細資訊，請參閱下列內容：

-   [逐步解說：使用 PXE 部署影像](https://go.microsoft.com/fwlink/?LinkId=212108)

-   [Windows 部署服務快速入門手冊](https://go.microsoft.com/fwlink/?LinkId=212106)

## 相關主題


[部署 DaRT 7.0 復原映像](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





