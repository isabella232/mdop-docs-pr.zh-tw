---
title: 如何使用 USB 快閃磁碟來部署 DaRT 復原映像
description: 如何使用 USB 快閃磁碟來部署 DaRT 復原映像
author: dansimp
ms.assetid: 5b7aa843-731e-47e7-b5f9-48d08da732d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1228c9cb5f870162f285d726d48721dde1185107
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810094"
---
# 如何使用 USB 快閃磁碟來部署 DaRT 復原映像


完成執行**DaRT 復原映射嚮導**之後，您可以使用 at 中的工具，將 <https://go.microsoft.com/fwlink/?LinkId=218888> ISO 映像檔案複製到 USB 快閃記憶體磁片磁碟機（UFD）。

您也可以按照本節中提供的步驟，手動將 ISO 映像檔案複製到 UFD。

**將 DaRT 恢復影像儲存至 USB 快閃記憶體磁片磁碟機**

1.  格式化 USB 快閃記憶體盤磁碟機。

    1.  從執行中的有效作業系統或 WindowsPE 會話中，插入您的 UFD。

    2.  在具有系統管理員許可權的命令提示字元中，輸入**DISKPART** ，然後輸入**清單磁片**。

        [命令提示字元] 視窗會顯示 UFD 的磁片編號，例如**磁片 1**。

    3.  在命令提示字元中，一次輸入一個下列命令。

        ``` syntax
        SELECT DISK 1
        CLEAN
        CREATE PARTITION PRIMARY
        SELECT PARTITION 1
        ACTIVE
        FORMAT FS=NTFS
        ASSIGN
        EXIT
        ```

        **記事** 上述程式碼範例假設 Disk1 是 UFD。 如有需要，請將磁片1取代為您的磁片號碼。

         

2.  您可以使用貴公司的慣用方法裝載影像，裝載您在**DaRT 復原映射嚮導**的 [**建立啟動影像**] 對話方塊中建立的 ISO 映像檔。 這需要您有可裝載影像檔案的方法。

3.  開啟掛載的 ISO 映像檔，並將所有內容複寫到格式化的 USB 快閃記憶體磁片磁碟機。

    **記事** 如果您燒錄的是 CD 或 DVD 的復原影像，您可以開啟 CD 或 DVD 上的檔案，並將內容複寫到 UFD 中。 這可讓您略過裝入影像的需求。

     

## 相關主題


[部署 DaRT 7.0 復原映像](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





