---
title: 管理 UE-V 1.0
description: 管理 UE-V 1.0
author: dansimp
ms.assetid: c399ae8d-c839-4f84-9bfc-adacd8f89f34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce4dcafd1949dcedd195569dabb7540ce55a2f1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809512"
---
# 管理 UE-V 1.0


部署 Microsoft 使用者體驗虛擬化（UE-V）之後，您必須能夠執行各種進行中的管理工作。 下列各節將說明這些安裝後的工作。

## 管理 UE-V 資源


在 UE-V 的生命週期期間，您必須管理 UE-V agent 的設定，也需要管理資源的儲存位置（例如設定套件）。 您可能需要執行其他工作，例如，將使用者的設定還原到已安裝 UE-V 之前的原始狀態，以便復原遺失的設定。 下列主題提供管理 UE-V 資源的指導方針。

### 變更 UE-V 排程工作的頻率

您可以設定在 UE-V 檢查 [設定] 範本目錄中的新、更新或移除自訂設定位置範本時所管理的排程任務。

[變更 UE-V 排程工作的頻率](changing-the-frequency-of-ue-v-scheduled-tasks.md)

### <a href="" id="sharing-settings-location-templates-with-the-ue-v-template-gallery-"></a>使用 UE-V 範本庫來共用設定位置範本

UE-V 範本庫能協助您共用 UE-V 設定位置範本。 圖庫可讓您上傳您的設定位置範本與其他人共用，並下載其他人所建立的範本。

[使用 UE-V 範本庫來共用設定位置範本](sharing-settings-location-templates-with-the-ue-v-template-gallery.md)

### 還原與 UE-V 1.0 同步處理的應用程式和 Windows 設定

UE-V 的 WMI 和 PowerShell 功能提供還原設定套件的功能。 WMI 和 PowerShell 命令可讓您在啟動 UE-V agent 之後第一次啟動應用程式時，將應用程式設定和 Windows 設定還原至電腦上的設定值。

[還原與 UE-V 1.0 同步的應用程式和 Windows 設定](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)

### 使用群組原則物件來設定 UE-V

您可以使用群組原則來修改定義 UE-V 如何在電腦上同步處理設定的設定。

[使用群組原則物件來設定 UE-V](configuring-ue-v-with-group-policy-objects.md)

### 使用 PowerShell 與 WMI 來管理 UE-V

您可以使用 PowerShell 和 WMI 來修改定義 UE-V 如何在電腦上同步處理設定的設定。

[使用 PowerShell 與 WMI 來管理 UE-V 1.0 Agent 與套件](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

### 移轉 UE-V 設定套件

您可以在遷移到新的伺服器或備份時，重新置放使用者設定套件。

[移轉 UE-V 設定套件](migrating-ue-v-settings-packages.md)

## 此產品的其他資源


[UE-V 1.0 作業](operations-for-ue-v-10.md)

 

 





