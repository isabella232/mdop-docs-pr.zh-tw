---
title: UE-V 1.0 的高階架構
description: UE-V 1.0 的高階架構
author: dansimp
ms.assetid: d54f9f10-1a4d-4e56-802d-22d51646e1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b54a9a207f9b74ad3d028cf4ab1f9842d59b0b3a
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910448"
---
# <a name="high-level-architecture-for-ue-v-10"></a>UE-V 1.0 的高階架構


本主題說明系統設定漫遊解決方案Microsoft 消費者體驗虛擬化 (UE-V) 架構元素。 下列元素是標準部署UE-V一部分。

![ue-v Agent 架構圖表。](images/ue-vagentarchitecturaldiagram.gif)

當UE-V設定位置範本中識別應用程式和作業系統程式時，代理程式會UE-V程式。 當應用程式或作業系統啟動時，設定會從設定套件讀取並套用至電腦。 當應用程式關閉或作業系統鎖定或關閉時，設定會儲存于UE-V設定套件中的設定儲存位置。

## <a name="settings-storage-location"></a>設定儲存位置


設定儲存位置是使用者體驗虛擬化代理程式存取的檔案共用，可讀取和寫入設定。 此位置是 Active Directory 主目錄，或在安裝期間UE-V定義。 您可以在安裝代理程式期間設定UE-V，或稍後使用群組原則、WMI 或 PowerShell 來設定位置。 位置可以位於使用者可存取的任何共同檔案共用上。 如果在安裝期間未設定儲存位置，UE-V Active Directory 中的主目錄。 代理UE-V驗證位置，並建立使用者隱藏的系統資料夾，以儲存及存取使用者設定。 有關設定儲存空間詳細資訊，請參閱準備[您的環境UE-V。](preparing-your-environment-for-ue-v.md)

## <a name="ue-v-agent"></a>UE-V代理


系統UE-V代理程式安裝在每部電腦上，其設定是由使用者體驗虛擬化同步處理。 代理程式會監控已註冊的應用程式和作業系統，以取得對設定進行的任何變更，並同步處理電腦之間的這些設定。 設定應用程式啟動時，系統會從設定儲存位置將設定儲存位置的設定應用程式。 當應用程式關閉時，這些設定會儲存回設定儲存位置。 當使用者登錄、電腦解除鎖定，或使用者使用遠端桌面通訊協定或 RDP (遠端連線到電腦時，會 (作業系統) 。 當使用者登出、電腦鎖定或遠端連線中斷時，代理程式會保存設定。 有關代理程式UE-V，請參閱準備[您的環境UE-V。](preparing-your-environment-for-ue-v.md)

## <a name="settings-location-templates"></a><a href="" id="bkmk-settingslocationtemplate"></a>設定位置範本


設定位置範本是一個 XML 檔案，定義由使用者體驗虛擬化監控的設定位置。 只有在這些設定範本中定義的設定位置，才能在執行代理程式的電腦上UE-V應用程式。 設定位置範本不包含設定值，只會包含值儲存在電腦上的位置。

UE-V包含一組設定位置範本，這些範本可指定某些 Microsoft 應用程式的設定位置，Windows設定。 系統管理員可以使用 UE-V 建立自訂設定位置範本。

[規劃要與 UE-V 1.0 同步處理的應用程式](planning-which-applications-to-synchronize-with-ue-v-10.md)

[規劃 UE-V 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)

[使用自訂 UE-V 範本與 UE-V 產生器](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

## <a name="settings-packages"></a>設定套件


應用程式設定Windows設定儲存在由代理程式所建立之設定套件UE-V中。 設定套件是設定位置範本中代表的設定集合。 這些設定套件會建在本地儲存，然後複製到設定儲存位置。 「上次寫入成功」會決定當單一使用者將多部電腦同步到儲存位置時，會保留哪些設定。 在一部電腦上執行之代理程式會讀取並寫入設定位置，而不受在其他電腦上執行之代理程式。 當下一個代理程式從設定儲存位置讀取時，會採用最近撰寫的設定和值。

![ue-v 產生程式。](images/ue-vgeneratorprocess.gif)

## <a name="settings-template-catalog"></a>設定範本目錄


設定範本目錄是電腦上UE-V的資料夾路徑，或儲存所有自訂設定位置範本的 SMB (SMB) 網路共用。 代理UE-V會從此位置中取回新的或更新的範本。 代理UE-V每天檢查此位置一次，並依據此資料夾中的範本更新其同步處理行為。 自上次檢查以來在此資料夾中新增或更新的範本，是由 UE-V註冊。 代理UE-V取消註冊已從此資料夾移除的範本。 範本會由任務排程器每天註冊和取消註冊一次。 如果您只會使用預設設定位置範本，UE-V，則不需要設定範本目錄。 有關設定部署目錄的資訊，請參閱規劃[1.0 UE-V範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

## <a name="user-experience-virtualization-generator"></a>使用者體驗虛擬化產生器


使用者體驗虛擬化產生器可讓您建立自訂設定位置範本，這些範本會儲存企業中使用的應用程式的設定位置，以及您想要納入漫遊設定解決方案中的設定位置。 UE-V產生器會尋找註冊表值的位置，以及應用程式的設定檔案，然後將這些位置記錄在設定位置範本 XML 檔案中。 接著，您可以將這些設定位置範本發佈至使用者電腦。 UE-V產生器也允許系統管理員編輯現有的範本，或驗證使用另一個 XML 編輯器所建立範本。

UE-V產生器會監控應用程式，以探索並記錄應用程式儲存其設定的位置。 若要這麼做，它會監控應用程式在 HKEY\_CURRENT\_USER 登錄或 [使用者\\[使用者名稱\] \\ AppData**** 漫遊和使用者 \\ \[User **name\]**  \\  **** \\** **  \\  **** 的檔案資料夾中讀取或寫入的位置。

探索程式會排除登入使用者無法寫入值的登錄金鑰和檔案。 這些均不會包含在 XML 檔案中。 探索程式也會排除與作業系統核心功能相關聯的註冊表Windows檔案。

若要進一UE-V產生器，請參閱安裝 UE-V[產生器](installing-the-ue-v-generator.md)。

## <a name="related-topics"></a>相關主題


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[開始使用 User Experience Virtualization 1.0](getting-started-with-user-experience-virtualization-10.md)

[關於 User Experience Virtualization 1.0](about-user-experience-virtualization-10.md)

[使用自訂 UE-V 範本與 UE-V 產生器](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

 

 





