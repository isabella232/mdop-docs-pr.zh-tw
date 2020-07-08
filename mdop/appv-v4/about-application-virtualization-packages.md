---
title: 關於 Application Virtualization 封裝
description: 關於 Application Virtualization 封裝
author: dansimp
ms.assetid: 69bd35c1-7af3-43db-931b-3074780aa926
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cfe6df90881ea4179fa8cd224609ca6d28ff5f61
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802474"
---
# 關於 Application Virtualization 封裝


在應用程式虛擬化中，*套件*是先後順序程式的輸出。 當您第一次在伺服器上部署應用程式，且使用新版本升級應用程式時，就會使用套件。 套件可讓您控制應用程式虛擬化管理伺服器上的虛擬應用程式版本。 單一套件可以包含一或多個應用程式。 每個應用程式套件都包含一組檔案，作為自包含的單元。

## 管理套件


在排序器建立一個或多個應用程式的套件做為其進程的一部分之後，您可以將 Sequencer 產生的檔案複製到應用程式虛擬化管理伺服器，並讓它們可供流式處理使用。

可用的套件會出現在應用程式虛擬化管理主控台左窗格中的 [**套件**] 容器底下。 當您匯入含有 Sequencer 專案（SPRJ）檔案或開啟軟體描述項（OSD）檔案的應用程式時，會在 [**套件**] 容器中出現相關專案。 您可以從應用程式虛擬化伺服器管理主控台，部署、升級或刪除套件及版本。

每個虛擬應用程式都有一個相關聯的套件。 此套件包含下列檔案：

-   SFT：將應用程式流向用戶端的檔案。

-   OSD —開啟的軟體描述項檔案包含尋找及啟動應用程式所需的資訊。

-   .ICO：圖示檔案，以視覺方式代表使用者介面和快速鍵中的應用程式。

-   SPRJ-Sequencer 專案檔案。

當您匯入 SPRJ 檔案時，預設會提供所有已排序的應用程式，但不會啟用應用程式來進行流式處理。 您可以選擇在套件中傳輸所有或部分應用程式。 例如，如果您已排序並匯入 Microsoft Office，您可以選擇不部署某些應用程式（例如 [儲存我的設定] 嚮導）。 在這種情況下，以滑鼠右鍵按一下您要部署的每個應用程式，選擇 [**屬性**]，並確認已清除 [**啟用**] 方塊（空白）。 只有已選取 [**啟用**] 方塊的應用程式才會資料流程至用戶端電腦。

在您 resequence 套件並產生新的 SFT 檔案以進行流式處理之後，您就可以透過應用程式虛擬化伺服器管理主控台快速且輕鬆地升級舊套件。

需要您使用 [**套件**] 節點的唯一操作案例就是當您為套件推出新版本（SFT 檔案）時。 每當您匯入應用程式、將存取權和授權指派給應用程式等，應用程式虛擬化系統就會在封裝層級追蹤此資訊。 這表示當您授權使用者使用應用程式時，您會給予使用者許可權，以在同一個套件中執行任何應用程式。

### 套件版本

套件版本是由特定的 SFT 檔案所代表。 當您升級套件時（將更新套用至應用程式或將應用程式新增到套件），您會產生新的 SFT 檔案。 每當您建立新的 SFT 檔案時，就會建立新的套件版本。

當您透過應用程式虛擬化伺服器管理主控台匯入應用程式時，軟體會自動建立套件和套件版本（如果它們尚不存在的話）。

## 相關主題


[關於 Application Virtualization 應用程式](about-application-virtualization-applications.md)

[關於 Application Virtualization 伺服器管理主控台](about-the-application-virtualization-server-management-console.md)

[如何在伺服器管理主控台中管理封裝](how-to-manage-packages-in-the-server-management-console.md)

 

 





