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
ms.openlocfilehash: 76703cf4c7297401e6516830bf194cef741d60ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812152"
---
# UE-V 1.0 的高階架構


本主題描述 Microsoft 使用者體驗虛擬化（UE-V）設定漫遊解決方案的高層次結構元素。 下列元素是標準 UE-V 部署的一部分。

![ue-v agent 結構圖表](images/ue-vagentarchitecturaldiagram.gif)

UE-V Agent 會監視應用程式及作業系統進程，因為它們是在 UE-V 設定位置範本中識別。 當應用程式或作業系統啟動時，會從 [設定] 套件讀取設定，並將其套用到電腦。 當應用程式關閉或作業系統鎖定或關閉時，設定就會儲存在 [設定] 儲存位置中的 UE-V 設定套件中。

## 設定儲存位置


[設定儲存位置] 是使用者體驗虛擬化代理程式存取來讀取和寫入設定的檔案共用。 這個位置是 Active Directory 主目錄，或在 UE-V 安裝期間定義。 您可以在安裝 UE-V agent 期間設定位置，或者您可以在稍後使用 [群組原則]、[WMI] 或 [PowerShell] 進行設定。 位置可以是使用者可以存取的任何常見檔案共用。 如果在安裝期間未設定儲存位置，則 UE-V 會使用 Active Directory 中的主目錄。 UE-V agent 會驗證位置，並建立要儲存及存取使用者設定的使用者所隱藏的系統資料夾。 如需設定儲存空間的詳細資訊，請參閱為[Ue-v 準備您的環境](preparing-your-environment-for-ue-v.md)。

## UE-V Agent


UE-V agent 是在每一台電腦上安裝，其設定是由使用者體驗虛擬化所同步處理。 Agent 會監視已註冊的應用程式與作業系統，以瞭解對設定所做的任何變更，並在電腦之間同步處理這些設定。 當應用程式啟動時，設定會從 [設定] 儲存位置套用到應用程式。 然後，在應用程式關閉時，這些設定會儲存回 [設定] 儲存位置。 當使用者登入時、電腦已解除鎖定，或當使用者使用遠端桌面通訊協定（RDP）連線到電腦時，就會套用作業系統設定。 當使用者登出、電腦被鎖定時，或當遠端連線中斷時，agent 會儲存設定。 如需 UE-V Agent 的詳細資訊，請參閱為[Ue-v 準備您的環境](preparing-your-environment-for-ue-v.md)。

## <a href="" id="bkmk-settingslocationtemplate"></a>設定位置範本


[設定位置] 範本是一個 XML 檔案，可定義使用者體驗虛擬化所監視的設定位置。 只有在這些設定範本中定義的設定位置，才會在執行 UE-V Agent 的電腦上捕獲或套用。 [設定位置] 範本不包含設定值，只能包含值儲存在電腦上的位置。

UE-V 包含一組設定位置範本，這些範本指定一些 Microsoft 應用程式和 Windows 設定的設定位置。 系統管理員可以使用 UE-V 發生器來建立自訂設定位置範本。

[規劃要與 UE-V 1.0 同步處理的應用程式](planning-which-applications-to-synchronize-with-ue-v-10.md)

[規劃 UE-V 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)

[使用自訂 UE-V 範本與 UE-V 產生器](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

## 設定套件


[應用程式設定] 和 [Windows 設定] 儲存在由 UE-V Agent 建立的 [設定套件] 中。 [設定套件] 是 [設定位置] 範本中所代表的設定集合。 這些設定套件會建立並儲存在本機，然後複製到 [設定] 儲存位置。 「上次寫入 wins」決定當單一使用者將多台電腦同步處理到儲存位置時，會保留哪些設定。 在一部電腦上執行的代理程式會讀取並寫入到 [設定] 位置，而不受在其他電腦上執行的代理程式。 下次代理從設定儲存位置讀取時，就會套用最近寫入的設定和值。

![ue-v 發生器程式](images/ue-vgeneratorprocess.gif)

## 設定範本目錄


[設定範本目錄] 是 UE-V 電腦或伺服器郵件區塊（SMB）網路共用上的資料夾路徑，可儲存所有的自訂設定位置範本。 UE-V agent 會從這個位置中檢索新的或更新的範本。 UE-V agent 每天都會檢查這個位置，然後根據此資料夾中的範本，更新其同步處理行為。 在此資料夾中新增或更新的範本，自上次檢查之後，由 UE-V agent 註冊。 UE-V agent 會 deregisters 從這個資料夾移除的範本。 範本是由任務排程器每日登錄並取消註冊一次。 如果您只會使用 UE-V 隨附的預設設定位置範本，則不需要設定範本目錄。 如需設定部署目錄的詳細資訊，請參閱[規劃 ue-v 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

## 使用者體驗虛擬化發生器


使用者體驗虛擬化發生器可讓您建立自訂設定位置範本，這些範本會儲存在企業中使用且您想要包含在漫遊設定方案中之應用程式的設定位置。 UE-V 發生器將搜尋以探索登錄的位置和應用程式的設定檔案，然後將這些位置記錄在設定位置範本 XML 檔案中。 然後，您可以將這些設定位置範本發佈到使用者電腦。 UE-V 發生器也可讓系統管理員編輯現有的範本，或驗證與其他 XML 編輯器建立的範本。

UE-V 發生器會監視應用程式，以探索並記錄儲存其設定的位置。 若要這麼做，它會監視應用程式在 HKEY \ _CURRENT \ _USER 登錄或在 [**使用者**\\] 下的檔案資料夾中讀取或寫入的位置 \ \ [使用者 \] [使用者名稱 \] \] **AppData**  \\  **漫遊，以及使用者**\\ [user name \\] **AppData**  \\  **Local**。

探索程式會排除登入使用者無法寫入值的登錄機碼和檔案。 這些內容不會包含在 XML 檔案中。 探索程式也會排除與 Windows 作業系統核心功能相關聯的登錄機碼和檔案。

如需 UE-V 發生器的詳細資訊，請參閱[安裝 Ue-v 發生器](installing-the-ue-v-generator.md)。

## 相關主題


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[開始使用 User Experience Virtualization 1.0](getting-started-with-user-experience-virtualization-10.md)

[關於 User Experience Virtualization 1.0](about-user-experience-virtualization-10.md)

[使用自訂 UE-V 範本與 UE-V 產生器](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

 

 





