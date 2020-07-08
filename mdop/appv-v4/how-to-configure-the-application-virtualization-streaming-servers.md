---
title: 如何設定 Application Virtualization Streaming Server
description: 如何設定 Application Virtualization Streaming Server
author: dansimp
ms.assetid: 3e2dde35-9d72-40ba-9fdf-d0338bd4d561
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0ec5497b010d18bcba60e81e96cbe6334c27fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801570"
---
# 如何設定 Application Virtualization Streaming Server


在虛擬應用程式可以傳送到應用程式虛擬化桌面用戶端或遠端桌面服務的用戶端（以前稱為終端服務）之前，必須先設定應用程式虛擬化資料流程伺服器。 當您設定伺服器時，您就是在儲存 SFT 檔案的位置設定 [*內容目錄*]。 SFT 檔案包含虛擬應用程式（或應用程式）。

**重要** 應用程式虛擬化伺服器會以 RTSP 或 RTSPS 通訊協定，將 SFT 檔案串流給桌面用戶端和遠端桌面服務的用戶端。 .ICO （圖示）檔案和 OSD （開放式軟體描述項）檔案可以設定為從不同的檔案或 HTTP 伺服器進行資料流。

 

**設定應用程式虛擬化資料流程伺服器**

1.  完成應用程式虛擬化流程伺服器的安裝程式。 在安裝過程中，您會在 [**內容路徑**] 畫面上指定 \\Content 目錄的位置。

2.  流覽至您為 \\Content 目錄指定的位置，如果您需要，請建立目錄。

3.  建立內容目錄時，請將此目錄設定為標準檔案共用。

4.  將 NTFS 檔案系統許可權設定為 [內容目錄]，以及 [內容目錄] 底下的 [套件] 資料夾。 您應該在 Active Directory 網域服務中使用安全性群組，定義哪些使用者可以存取每個應用程式。

## 相關主題


[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)

[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[如何設定 Application Virtualization Management Server](how-to-configure-the-application-virtualization-management-servers.md)

[如何設定檔案伺服器](how-to-configure-the-file-server.md)

[如何設定伺服器使用 IIS](how-to-configure-the-server-for-iis.md)

 

 





