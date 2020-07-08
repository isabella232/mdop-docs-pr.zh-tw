---
title: 如何設定檔案伺服器
description: 如何設定檔案伺服器
author: dansimp
ms.assetid: 0977554c-1741-411b-85e7-7e1cd017542f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a8971ad5c9f83dec4d0c77a16f1093ef7026b5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801554"
---
# 如何設定檔案伺服器


您可以使用下列程式，將本機電腦設定為檔案共用，並將應用程式流式處理到應用程式虛擬化桌面用戶端和遠端桌面服務的用戶端（以前稱為 [終端服務]）。 當您不想要將其他伺服器基礎結構新增到您現有的硬體環境時，就會用到此案例。

如果您是使用應用程式虛擬化管理伺服器作為在本機辦公室中安裝之檔案共用的發佈點，則您必須先設定此伺服器，才能將虛擬應用程式流式傳送到用作檔案共用的電腦。 當您設定伺服器與檔案共用時，您將會設定在其中載入並儲存 SFT 檔案的內容目錄。 SFT 檔案包含虛擬應用程式（或應用程式）。

**重要** 若要將應用程式正確地資料流程傳送到應用程式虛擬化桌面用戶端和遠端桌面服務的用戶端，SFT 檔案會從您儲存虛擬應用程式的伺服器上的內容目錄傳送資料流程;.ICO （圖示）檔案和 OSD （開放式軟體描述項）檔案可以設定為從其他伺服器進行資料流程。

 

**設定應用程式虛擬化檔案伺服器**

1.  完成下列安裝程式，以設定用來做為發佈點的伺服器：

    [如何安裝 Application Virtualization Management Server](how-to-install-application-virtualization-management-server.md)

    **記事** 在安裝過程中，您會在 [**內容路徑**] 畫面上指定 \\Content 目錄的位置。

     

2.  建立 \\Content 目錄，該目錄會對應到您在安裝伺服器時所指定的目錄，並在您要做為檔案共用的每個電腦上使用。

    **重要** 設定應用程式虛擬化桌面用戶端，以從您要做為檔案共用的電腦（而不是從應用程式虛擬化伺服器或 IIS 伺服器）來資料流應用程式。

     

3.  建立 \\Content 目錄時，請將此目錄設定為標準檔案共用。

## 相關主題


[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)

[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[如何設定 Application Virtualization Management Server](how-to-configure-the-application-virtualization-management-servers.md)

[如何設定 Application Virtualization Streaming Server](how-to-configure-the-application-virtualization-streaming-servers.md)

[如何設定伺服器使用 IIS](how-to-configure-the-server-for-iis.md)

 

 





