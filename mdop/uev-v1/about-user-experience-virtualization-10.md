---
title: 關於 User Experience Virtualization 1.0
description: 關於 User Experience Virtualization 1.0
author: dansimp
ms.assetid: 3758b100-35a8-4e10-ac08-f583fb8ddbd9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6010f9c4ebc260eec0324fb880dc2c92fd675130
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809519"
---
# 關於 User Experience Virtualization 1.0


Microsoft 使用者體驗虛擬化（UE-V）會監視使用者對應用程式設定和 Windows 作業系統設定所做的變更。 系統會捕獲使用者設定並將其集中到設定儲存位置。 然後，這些設定可以套用到使用者所存取的不同電腦，包括桌上型電腦、膝上型電腦和虛擬桌面基礎結構（VDI）會話。

使用者體驗虛擬化使用設定位置範本來指定使用者電腦上的哪些應用程式和 Windows 設定受到監視及集中式。 [設定位置] 範本是一個 XML 檔案，可指定哪些檔案和登錄位置與每個應用程式或作業系統設定相關聯。 範本不包含設定的值;它只包含要監控之設定的位置。

當使用者在電腦上工作時，就會透過 UE-V 監控應用程式設定和 Windows 設定。 當使用者關閉應用程式時，應用程式設定的值會儲存在 [設定] 儲存伺服器上。 Windows 設定的值會在使用者登出、電腦被鎖定時，或當其從電腦遠端中斷連線時儲存。

系統管理員可以建立 UE-V 設定位置範本，以指定要漫遊的企業應用程式設定。 UE-V 包含一些 Microsoft 應用程式和 Windows 設定的設定位置樣板集合。 如需 UE-V 中預設應用程式和設定的清單，請參閱[規劃要與 ue-v 1.0 同步處理哪些應用程式](planning-which-applications-to-synchronize-with-ue-v-10.md)。

## UEV 1.0 版本資訊


如需詳細資訊，以及未在檔中使用的最新消息，請參閱[Microsoft 使用者體驗虛擬化（ue-v）1.0 版本](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)資訊。

## 相關主題


[開始使用 User Experience Virtualization 1.0](getting-started-with-user-experience-virtualization-10.md)

[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[UE-V 1.0 的高階架構](high-level-architecture-for-ue-v-10.md)

 

 





