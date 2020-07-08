---
title: 如何建立及使用專案範本
description: 如何建立及使用專案範本
author: dansimp
ms.assetid: 2063f0b3-47a1-4090-bf99-0f26b107331c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e7640b9dc1e7baec194315400ee5672dfa83f394
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800549"
---
# 如何建立及使用專案範本


您可以使用 App-v 5.0 專案範本來儲存與現有虛擬應用程式套件相關聯的一般套用設定。 當您在您的環境中建立新的虛擬應用程式套件時，就可以套用這些設定。 使用專案範本可以簡化建立虛擬應用程式套件的過程。

**記事** 您可以，通常應該在套件升級期間套用 app-v 5.0 專案範本。 例如，如果您以自訂排除清單為應用程式排序，建議您在升級已排序的應用程式時，會建立並儲存相關的範本供日後使用。

App-v 5.0 專案範本與 App-v 5.0 應用程式加速器不同，因為 App-v 5.0 應用程式加速器是應用程式專用的，而 App-v 5.0 專案範本可以套用到多個應用程式。

使用下列程式來建立並套用新範本。

**建立專案範本**

1.  若要啟動 app-v 5.0 排序器，請在執行排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**。

**記事** 如果應用程式套件目前已在 App-v 5.0 排序器主控台中開啟，請跳至此程式的步驟3。

2. 若要開啟包含您想要儲存 App-V 5.0 專案範本之設定的現有虛擬應用程式套件，**請按一下 [**  /  **開啟**檔案]，然後按一下 [**編輯套件**]。 在 [**選取套件**] 頁面上，按一下 **[流覽]** 並找出您要開啟的虛擬應用程式套件。 按一下**編輯**。

3. 在 app-v 5.0 Sequencer 主機中，若要儲存範本檔案，**請按一下 [** 檔案  /  **另存為範本**]。 在您檢查將與新範本一起儲存的設定後，請按一下 **[確定]**。 指定將與新的 App-v 5.0 專案範本相關聯的名稱。 按一下 [儲存]。
   新的 App-v 5.0 專案範本會儲存在此程式步驟3中所指定的目錄中。

**若要套用專案範本**

**重要** 不支援使用專案範本與套件加速器結合建立虛擬應用程式套件。

1.  若要啟動 app-v 5.0 排序器，請在執行排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**。

2.  若要使用 app-v 5.0 專案範本來建立或升級新的虛擬應用程式套件，**請按一下 [**  /  **從範本新增**檔案]。

3.  若要選取您要使用的專案範本，請流覽至儲存專案範本的目錄，選取專案範本，然後按一下 [**開啟**]。

    建立新的虛擬應用程式套件。 儲存在指定範本的設定將會套用至您要建立的新虛擬應用程式套件。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)









