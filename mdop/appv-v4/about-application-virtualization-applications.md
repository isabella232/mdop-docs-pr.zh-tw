---
title: 關於 Application Virtualization 應用程式
description: 關於 Application Virtualization 應用程式
author: dansimp
ms.assetid: 3bf833b7-d172-4eef-a9e8-4b4f0c7eb15b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4eeea7a0ec4454aefcdde5196ae15ed029da45b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802477"
---
# 關於 Application Virtualization 應用程式


在應用程式虛擬化中，*應用程式*是從應用程式虛擬化管理伺服器傳送到應用程式虛擬化桌面用戶端或用戶端（舊稱終端服務）的可執行程式，例如 Microsoft Visio。 在將應用程式流入用戶端之前，必須先透過應用程式虛擬化排序器處理應用程式，才能進行流式處理。

## 管理應用程式


您必須先將應用程式新增至系統，才能讓使用者使用這些應用程式。 在系統中新增應用程式最常見的方法是匯入。 若要存取此功能，請以滑鼠右鍵按一下應用程式虛擬化伺服器管理主控台中的**應用程式**節點，然後選擇 [匯**入應用程式**]。

您可以一次匯入一個以上的開啟軟體描述項（OSD）檔案，或者您可以匯入一個可包含多個 OSD 檔案的 Sequencer 專案檔案（SPRJ）。 此功能可讓您以類似的方式設定相關的應用程式。

您也可以使用下列功能來協助您管理您的應用程式：

-   [**應用程式群組**]-可讓您建立應用程式的邏輯群組，以簡化管理。 對群組進行變更時（例如，存取許可權），這些變更會套用到群組中的所有應用程式。 群組中的應用程式可以來自不同的套件。

-   **多重選取**-可讓您在按一下應用程式來修改應用程式屬性時，按住 CTRL 鍵，同時選取多個應用程式。 不過，如果您想要維持應用程式之間的關係，您應該建立應用程式群組來存放應用程式。

-   **跨系統複本**-可讓您將應用程式從一個環境複製到另一個在一個步驟中執行相同版本 App-V 的環境。 例如，您可能會有一個使用者驗收測試環境，您可以在這裡開始部署和設定應用程式。 完成測試階段之後，您可能會想要將一組相同的應用程式（包括許可權）複製到生產環境。

## 相關主題


[關於 Application Virtualization 封裝](about-application-virtualization-packages.md)

[關於 Application Virtualization 伺服器管理主控台](about-the-application-virtualization-server-management-console.md)

[如何在伺服器管理主控台中管理應用程式群組](how-to-manage-application-groups-in-the-server-management-console.md)

[如何在伺服器管理主控台中管理應用程式](how-to-manage-applications-in-the-server-management-console.md)

 

 





