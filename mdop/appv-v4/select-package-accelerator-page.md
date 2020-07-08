---
title: 選取封裝加速器頁面
description: 選取封裝加速器頁面
author: dansimp
ms.assetid: 865c2702-4dfd-41ae-8cfc-3514d5f41f76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5723f8244563539c27a3fa915c1a680905e61e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800850"
---
# 選取封裝加速器頁面


使用 [**選取套件加速器**] 頁面來選取將用來建立新的虛擬應用程式套件的套件加速器。 您必須將套件加速器複製到執行 App-v 排序器的電腦上的資料夾中。 如需詳細資訊，請參閱[關於 app-v 封裝加速器（app-v 4.6 SP1）](about-app-v-package-accelerators--app-v-46-sp1-.md)。

只能從您信任的發行者執行套件加速器。 套件加速器通常包含數位簽章。 數位簽章是一種電子安全標記，可協助說明軟體的發行者，以及封裝轉換為最初簽署後是否已被篡改。 如果您使用的轉換是由發行商數位簽署的，且發行商已透過憑證授權單位驗證其身分識別，您就可以更有把握該轉換來自該特定的發行者，而且尚未變更。

如果下列任一條件成立，App-v 排序器會通知您：

-   選取的轉換尚未經過數位簽署。

-   所選的轉換是由尚未使用憑證授權單位驗證其身分識別的發行者所簽署。

-   所選取的轉換在經過數位簽署及放開後已變更。

如果您在使用套件加速器時顯示這些訊息中的任何一種，請造訪封裝加速器發行者的網站，以取得經過數位簽章的轉換版本。

此頁面包含下列元素：

<a href="" id="browse"></a>**瀏覽**  
按一下 **[流覽]** ，指定您將用來建立虛擬應用程式套件的套件加速器。 在執行排序器的電腦上，儲存您所指定的套件加速器。

## 相關主題


[Sequencer 精靈 - 封裝加速器 (AppV 4.6 SP1)](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





