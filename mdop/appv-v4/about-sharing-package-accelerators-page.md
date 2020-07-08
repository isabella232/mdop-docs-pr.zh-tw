---
title: 關於共用封裝加速器頁面
description: 關於共用封裝加速器頁面
author: dansimp
ms.assetid: 9630cde0-e2c3-476f-8fa1-58b3c9f7d3f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 34fe55d910a7532f011b239ff5b8162aa9240f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802438"
---
# 關於共用封裝加速器頁面


下列資訊提供如何共用套件加速器的最佳做法資訊。 如果您打算共用套件加速器檔案，諸如電腦名稱稱、使用者帳戶資訊等資訊，以及有關轉換中所包含之應用程式的相關資訊，都可能包含在封裝加速器檔案中。 您應該檢查與虛擬應用程式套件相關聯的任何設定或設定檔，以確保應用程式不包含任何個人資訊。此頁面包含下列元素。

-   [使用者**名稱**]。 當您登入執行 Microsoft App-v 排序器的電腦時，您應該使用一般的使用者帳戶，例如內建的**系統管理員**帳戶。 您不應該使用以現有的使用者名稱為基礎的帳戶。

-   [**電腦名稱稱**]。 指定執行排序器之電腦的一般、非識別名稱。

-   **伺服器 URL**。 在 App-v 排序器主控台的 [**部署**] 索引標籤上，使用伺服器 URL 設定資訊的預設設定。

-   **應用程式**。 如果您不想在建立套件加速器時共用執行 Sequencer 之電腦上所安裝的應用程式清單，您必須刪除**appv\_manifest.xml**檔案。 此檔案位於虛擬應用程式套件的套件根目錄中。

## 相關主題


[建立封裝加速器精靈 (AppV 4.6 SP1)](create-package-accelerator-wizard--appv-46-sp1-.md)

[關於 App-V 封裝加速器 (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md)

 

 





