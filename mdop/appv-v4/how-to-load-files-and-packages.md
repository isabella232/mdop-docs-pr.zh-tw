---
title: 如何載入檔案和封裝
description: 如何載入檔案和封裝
author: dansimp
ms.assetid: f86f5bf1-99a4-44d7-ae2f-e6049c482f68
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9427fd8089ec9c22d7d379b15ae94bf421ca2d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801337"
---
# 如何載入檔案和封裝


您可以使用下列程式，在應用程式虛擬化伺服器上載入檔案和套件。

**記事** 在安裝過程中，您已在 [**內容路徑**] 頁面上指定 \\Content 目錄的位置。 在您指向其位置之前，應該先建立並將此目錄設定為標準檔案共用。

 

**載入檔案和套件**

1.  在您要將應用程式流式處理的電腦上，流覽至您為 \\Content 目錄指定的位置。 如有需要，請建立目錄並將它設定為標準檔案共用。

2.  將虛擬應用程式和套件的 SFT 檔案移至 \\Content 目錄。 若要讓 SFT 檔案保持井然有序並避免混淆，請將應用程式和套件放在專用的子資料夾中。

3.  根據案例和設定的需求載入應用程式和套件，考慮下列情況：

    -   如果您的應用程式和套件儲存在應用程式虛擬化（App-v）管理伺服器上，請透過管理主控台載入它們。 如需詳細資訊，請參閱[如何載入或卸載應用程式](how-to-load-or-unload-an-application.md)，或[如何從桌面通知區域載入虛擬應用程式](how-to-load-virtual-applications-from-the-desktop-notification-area.md)。

    -   如果您的應用程式儲存在 App-v 流式處理伺服器、Web 服務器或設定為檔案伺服器的電腦上，則可以自動載入應用程式。

        **記事** App-v 流式處理伺服器會自動為應用程式和套件輪詢 \\Content 目錄，並將此資訊放在 RAM 中以服務于應用程式要求。

        App-v 用戶端必須正確設定，才能從 Web 服務器與檔案伺服器中檢索應用程式和套件。 如需詳細資訊，請參閱[如何針對應用程式套件檢索設定用戶端](how-to-configure-the-client-for-application-package-retrieval.md)。

         

## 相關主題


[Application Virtualization 伺服器](application-virtualization-server.md)

 

 





