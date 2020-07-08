---
title: 如何建立 App-V 專案範本 (App-V 4.6 SP1)
description: 如何建立 App-V 專案範本 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 7e87fba2-b72a-4bc9-92b8-220e25aae99a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e264d5c41b663bc9c450dc642e2b26297ee7ea1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801501"
---
# 如何建立 App-V 專案範本 (App-V 4.6 SP1)


您可以使用 App-v 專案範本來儲存與現有虛擬應用程式套件相關聯的一般套用設定。 當您在您的環境中建立新的虛擬應用程式套件時，就可以套用這些設定，這有助於簡化建立虛擬應用程式套件的程式。

**記事** 您可以在建立新的虛擬應用程式套件時，套用 V 專案範本。 不支援將專案範本套用至現有的虛擬應用程式套件。

 

如需有關套用 app-v 專案範本的詳細資訊，請參閱[如何套用 App-v 專案範本（app-v 4.6 SP1）](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)。

App-v 專案範本與 App-v 應用程式加速器有所不同，因為 App-v 應用程式加速器是應用程式專用的，而 app-v 專案範本可以套用到多個應用程式。 此外，當您使用套件加速器建立虛擬應用程式套件時，您無法使用專案範本。

下列一般設定會儲存為 App-v 專案範本：

-   [**高級監視] 選項**。 可讓 Microsoft 更新在監視、變基 **.dll**中執行。

-   **封裝部署設定**。 包含**通訊協定**、**主機名稱**、**埠**、**路徑**、**作業系統**、**強制安全性描述項**、**建立 MSI**、**壓縮套件**。

-   **一般選項**。 可讓您**產生 Microsoft Windows Installer （MSI）** 套件、**允許虛擬化事件**、**允許虛擬化服務**、**將套件版本附加至 Filename**。

-   **排除專案**。 包含 [排除] 模式清單。

**建立專案範本**

1.  若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。

2.  如果應用程式套件目前已在 App-v 排序器中開啟，請跳至此程式的步驟3。 若要開啟現有的虛擬應用程式套件，其中包含您想要使用 app-v 專案範本儲存的設定，請**按一下 [**  /  **開啟**檔案]，然後按一下 [**編輯****套件**]。 在 [**選取套件**] 頁面上，按一下 **[流覽]** 並找出您要開啟的虛擬應用程式套件。 按一下**編輯**。

3.  在 app-v 排序器主控台中 **，按一下 [**  /  **儲存為範本**]。 在您檢查將與新範本一起儲存的設定後，請按一下 **[確定]**。 指定將與新的 App-v 專案範本相關聯的名稱。 按一下 **[儲存]**。

    新的 App-v 專案範本會儲存在此程式步驟3中所指定的目錄中。

## 相關主題


[Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[如何套用 App-V 專案範本 (App-V 4.6 SP1)](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)

 

 





