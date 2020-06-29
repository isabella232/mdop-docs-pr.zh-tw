---
title: 如何設定 Application Virtualization Management Server
description: 如何設定 Application Virtualization Management Server
author: dansimp
ms.assetid: a9f96148-bf2d-486f-98c2-23409bfb0935
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6d54dd213efb8d5cbff5d0e730e6dc08c8d19b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801578"
---
# 如何設定 Application Virtualization Management Server


您必須先設定應用程式虛擬化管理伺服器，才能將虛擬化應用程式流式傳送到應用程式虛擬化桌面用戶端或用戶端以進行遠端桌面服務（舊稱終端服務）。 當您設定伺服器時，您就是在儲存 SFT 檔案的位置設定 [*內容目錄*]。 SFT 檔案包含虛擬化的應用程式（或應用程式）。

**重要** 應用程式虛擬化伺服器會以 RTSP 或 RTSPS 通訊協定，將 SFT 檔案串流給桌面用戶端和遠端桌面服務的用戶端。 .ICO （圖示）檔案和 OSD （開放式軟體描述項）檔案可以設定為從不同的檔案或 HTTP 伺服器進行資料流。

 

**設定應用程式虛擬化管理伺服器**

1.  完成下列程式：

    [如何安裝 Application Virtualization Management Server](how-to-install-application-virtualization-management-server.md)

    **記事** 在安裝過程中，您會在 [**內容路徑**] 畫面上指定 \\Content 目錄的位置。

     

2.  流覽至您為 \\Content 目錄指定的位置，並視需要建立目錄。

3.  建立內容目錄時，請將此目錄設定為標準檔案共用。

## 相關主題


[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)

[Application Virtualization 系統需求](application-virtualization-system-requirements.md)

[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[如何針對以伺服器為基礎的部署設定伺服器](how-to-configure-servers-for-server-based-deployment.md)

 

 





