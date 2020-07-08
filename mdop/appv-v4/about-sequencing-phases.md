---
title: 關於排序階段
description: 關於排序階段
author: dansimp
ms.assetid: c1cb7b6c-204c-48f2-848c-4bd5a3d5ecb6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e3d1504f0af82f3d21806b38bb4640b6f7ebc45
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802442"
---
# 關於排序階段


[順序] 是您使用 Microsoft Application Virtualization （App-v） Sequencer 來建立順序式應用程式套件的處理方式。 在排序期間，Sequencer 會監視及記錄應用程式的所有安裝與設定進程，並建立下列檔案： .ICO、OSD、SFT 及 SPRJ。 這些檔案包含有關應用程式的所有必要資訊，並可讓該應用程式在虛擬環境中執行。

排序應用程式及建立虛擬應用程式套件的四個階段，包括安裝、啟動、自訂及儲存。 下列清單提供每個階段的相關資訊：

1.  **安裝階段**：您可以在安裝階段指定套件名稱，以及將與套件相關聯的選擇性相關批註。 您也可以在此階段設定高級監視選項。 [高級監視] 選項包括指定區塊大小，以及在監視期間是否會安裝自動更新。 Sequencer 會記錄建立虛擬應用程式套件所需的所有必要資訊和設定，以及相關聯的檔案和註冊表設定。

    **重要** 若要查看 [高級選項]，請選取 [**套件資訊**] 頁面上的 [**顯示高級監視選項**]。

     

2.  **啟動階段**：啟動階段期間，您可以指定任何所需的檔案關聯和安全描述項，以在套件中進行設定。 您應該視需要多次開啟應用程式，以確保應用程式的功能和穩定性。

3.  **自訂階段**：在自訂階段期間，您可以使用相關聯的 .osd 檔案來設定您的套件。 您可以指定任何相關聯的腳本應該在虛擬環境內或外部執行、指定要執行的其他動作、指定關聯腳本執行的方式（同步或非同步），以及指定應該在使用者內容下執行的任何其他腳本。

4.  **儲存階段**：在儲存階段中，會建立虛擬應用程式套件所需的所有檔案。 建立的檔案為 sprj、sft、.osd、.ico、.xml 資訊清單，以及 Windows installer （.msi）檔案。

## 相關主題


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

 

 





