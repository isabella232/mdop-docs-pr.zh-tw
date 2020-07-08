---
title: UE-V 2.0 的新功能
description: UE-V 2.0 的新功能
author: dansimp
ms.assetid: 5d852beb-f293-4e3a-a33b-c40df59a7515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a7566bd82432dcf7e4c46e1fa3e66e55d1515b79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810869"
---
# UE-V 2.0 的新功能


Microsoft 使用者體驗虛擬化（UE-V）2.0 提供與 UE-V 1.0 相比的這些新功能和功能。 [Microsoft 使用者體驗虛擬化（ue-v）2.0 版本資訊](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)提供關於 ue-v 2.0 發行的詳細資訊。

## 不再需要用戶端快取（CSC）


這個版本的 UE-V 引入**同步處理提供程式**，它會取代 Windows 離線檔案功能的需求，以支援用戶端的設定快取。

雖然 UE-V 只會在應用程式開啟、關閉或 Windows 鎖定或解除鎖定時，或在登入或登出時同步處理設定，但同步處理提供者也會使用 .。。

-   使用「**觸發事件**」同步處理本機應用程式和 Windows 設定

-   使用**排程任務**，以您針對企業需求所選擇的任何間隔來同步處理設定儲存套件（預設為每30分鐘一次）

某些條件可提供更頻繁的同步處理。

-   當使用者按一下新的公司設定中心應用程式中的 [**立即同步**處理] 按鈕時，設定就會同步處理。

-   同步處理提供者也可以在單一應用程式中開始，而不需要等候排程的同步處理工作。 例如，當應用程式關閉時，任何設定變更都會寫入本機快取，同步處理提供程式進程會以非同步方式執行，以將這些新的設定變更移至設定儲存位置。

## Windows 應用程式同步處理


Windows 應用程式的開發人員可以定義要同步處理的設定（如果有的話），而這些設定現在可以使用 UE-V 捕獲並同步處理。

根據預設，UE-V 會同步處理 Windows 8 和 Windows 8.1 中包含的許多 Windows 應用程式的設定。 您可以使用 Windows PowerShell、Windows 管理工具（WMI）或群組原則來修改已同步處理應用程式的清單。

**記事** 如果網域使用者將登入認證連結到其 Microsoft 帳戶，UE-V 就不會同步處理 Windows 應用程式設定。 此連結會同步處理設定至 Microsoft OneDrive，因此 UE-V 只會同步處理桌面應用程式。

 

## Microsoft 帳戶連結


如果您是使用 Microsoft 帳戶登入，或是將您的 Microsoft 帳戶連結至網域帳戶，則在 Windows 8 上進行的 [設定同步處理] 就是 Windows 8 的新功能。 如果網域使用者使用 UE-V，且已登入 Microsoft 帳戶，請 .。。

-   UE-V 只同步處理桌面應用程式的設定

-   Microsoft 帳戶處理 Windows 應用程式設定和 Windows 桌面設定

## 公司設定中心


您可以為使用者提供一些控制哪些設定會透過 UE-V 2 （稱為「公司設定中心」）中的應用程式進行同步處理。 [公司設定中心] 與 UE-V Agent 一起安裝，使用者可以從 [控制台]、[**開始**] 功能表或 [**開始**] 畫面，以及從 ue-v 通知區域圖示存取。

[公司設定中心] 會顯示已同步處理的設定，並讓使用者看到 UE-V 的同步處理狀態。 如果您允許，使用者可以使用 [公司設定中心] 來選取要同步處理的設定。 他們也可以按一下 [**立即同步**處理] 按鈕，立即同步處理所有設定。






## 相關主題


[UE-V 2.x 入門](get-started-with-ue-v-2x-new-uevv2.md)

[準備 UE-V a.x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

 

 





