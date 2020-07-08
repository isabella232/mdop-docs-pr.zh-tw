---
title: 建立 DaRT 7.0 復原映像
description: 建立 DaRT 7.0 復原映像
author: dansimp
ms.assetid: ebb2ec58-0349-469d-a23f-3f944fe4c1fa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f19ff144cac61ca7ea5a8498f67caf8a99229d77
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809861"
---
# 建立 DaRT 7.0 復原映像


Microsoft Diagnostics 與修復工具組（DaRT）7包含 Windows 中用來建立可引導的國際標準組織（ISO）影像的**DaRT 復原影像嚮導**。 ISO 影像是代表 CD 原始內容的檔案。

## 使用 DaRT 復原映像嚮導來建立恢復影像


由 DaRT 復原映射嚮導建立的 ISO 包含可讓您啟動至有問題電腦的 DaRT 復原影像，即使它可能不會啟動也一樣。 將電腦引導至 DaRT 之後，您可以執行不同的 DaRT 工具來嘗試診斷並修復電腦。

您可以將 ISO 寫入可錄製的 CD 或 DVD、將其儲存至 USB 快閃磁片磁碟機，或將它儲存為可從遠端分區或從復原分區引導至 DaRT 的格式。 如需詳細資訊，請參閱[部署 DaRT 7.0 恢復影像](deploying-the-dart-70-recovery-image-dart-7.md)。

**記事** 如果您的電腦包含 cd-rw 磁片磁碟機，此嚮導會提供將 ISO 影像燒錄至空白的 CD 或 DVD。 如果您的電腦不包含嚮導所支援的磁片磁碟機，您可以使用大多數可以燒錄 CD 或 DVD 的程式，將 ISO 影像燒制到 CD 或 DVD 上。

 

若要從 ISO 影像建立可啟動的 CD 或 DVD，您必須具備：

-   CD-RW 磁片磁碟機。

-   可錄製的 CD 或 DVD （採用可燒錄磁片磁碟機支援的格式）。

-   支援可燒錄磁片磁碟機並支援將 ISO 影像直接燒錄至 CD 或 DVD 的軟體。

    **重要** 在您想要支援的所有不同電腦上，測試您所建立的 CD 或 DVD，因為部分電腦無法從所有類型的可錄製媒體啟動。

     

若要將 ISO 影像儲存至 USB 快閃記憶體磁片磁碟機（UFD），您必須具備：

-   格式正確的 UFD。

-   您可以用來裝載 ISO 映像的程式。

[如何使用 DaRT 復原映像精靈來建立復原映像](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)

## 建立限制時間的復原影像


您可以建立一個只能在產生特定天數後使用的 DaRT 恢復影像。 若要這樣做，您必須在命令提示字元執行**DaRT 復原映射嚮導**，並指定天數。

[如何建立限時復原映像](how-to-create-a-time-limited-recovery-image-dart-7.md)

## 建立 DaRT7 復原影像的其他資源


-   [部署 DaRT 7.0](deploying-dart-70-new-ia.md)

 

 





