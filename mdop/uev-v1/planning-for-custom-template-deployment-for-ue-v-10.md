---
title: 規劃 UE-V 1.0 的自訂範本部署
description: 規劃 UE-V 1.0 的自訂範本部署
author: dansimp
ms.assetid: be76fc9a-31ca-4290-af11-7640dcb87d50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d17f058bff452f88003ab4488daa7afa846f688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802918"
---
# 規劃 UE-V 1.0 的自訂範本部署


Microsoft 使用者體驗虛擬化（UE-V）使用設定位置範本（XML 檔案）來定義由 UE-V 捕獲並套用的設定。 您可以使用 UE-V 發生器來建立自訂設定位置範本，讓使用者可以漫遊除預設 UE-V 範本中所包含的應用程式以外的應用程式設定。 在您測試自訂範本以確保應用程式設定在測試環境中正確漫遊之後，您就可以將這些設定位置範本部署到企業中的電腦。

您可以使用現有的部署基礎結構（例如企業軟體發佈（ESD）、群組原則喜好設定或設定 UE-V 設定範本目錄，來部署您的自訂設定位置範本。 使用 ESD 或群組原則部署的範本，必須使用 UE-V WMI 或 PowerShell 註冊。

## 設定範本目錄


使用者體驗虛擬化設定範本目錄是 UE-V 電腦或伺服器郵件區塊（SMB）網路共用上的資料夾路徑，可儲存所有的自訂設定位置範本。 UE-V agent 會從這個位置中檢索新的或更新的範本。 UE-V agent 每天都會檢查這個位置，並根據此資料夾中的範本更新其同步處理行為。 在資料夾最後一次檢查之後，在此資料夾中新增或更新的範本是由 UE-V agent 註冊。 從這個資料夾移除的 UE-V agent deregisters 範本。 根據預設，範本是在每天淩晨3:30 登錄並取消註冊一次。 [任務排程者] 的當地時間。 如需 UE-V 任務的詳細資訊，請參閱[變更 Ue-v 排程任務的頻率](changing-the-frequency-of-ue-v-scheduled-tasks.md)。

您可以使用 [安裝] 命令列選項、[群組原則]、[WMI] 或 [PowerShell] 來設定設定範本的目錄路徑。 儲存在設定範本目錄路徑的範本會自動由排程的工作進行註冊和取消註冊。 您可以視需要自訂此排程任務。

## 取代預設的 Microsoft 範本


UE-V agent 會安裝適用于常見 Microsoft 應用程式和 Windows 設定的預設設定位置範本組。 如果您的企業需要這些範本的自訂版本，則可以將 UE-V agent 設定為使用設定範本目錄，然後您應該取代預設的 Microsoft 範本。

在安裝 UE-V agent 期間，命令列參數， `RegisterMSTemplates` 可以用來停用預設 Microsoft 範本的註冊。 如需如何設定 UE-V 參數的詳細資訊，請參閱[規劃 Ue-v 配置方法](planning-for-ue-v-configuration-methods.md)。

當您使用群組原則來設定設定範本目錄路徑時，您可以選擇取代預設的 Microsoft 範本。 如果您將原則設定設定為取代預設的 Microsoft 範本，則會從電腦中刪除由 UE-V agent 所安裝的所有預設 Microsoft 範本，而且只會使用位於設定範本目錄中的範本。 UE-V Agent 設定設定 `RegisterMSTemplates` 必須設定為 true，才能覆寫預設的 Microsoft 範本。

**記事** 如果您在啟用此原則設定後停用它，UE-V agent 將無法還原預設的 Microsoft 範本。

 

如果設定範本目錄中有使用與預設 Microsoft 範本相同的識別碼的自訂範本，而 UE-V agent 並未設定為取代預設的 Microsoft 範本，則會忽略目錄中的 Microsoft 範本。

您也可以使用 UE-V PowerShell 功能取代預設範本。 若要將預設的 Microsoft 範本替換成 PowerShell，請登出所有預設的 Microsoft 範本，然後註冊自訂範本。

**記事** 即使為應用程式部署新的設定範本，仍會保留在 [設定] 儲存位置中的舊設定套件。 這些套件不會由代理程式讀取，但它們不會自動刪除。

 

## 相關主題


[為 UE-V 1.0 進行規劃](planning-for-ue-v-10.md)

[規劃要與 UE-V 1.0 同步處理的應用程式](planning-which-applications-to-synchronize-with-ue-v-10.md)

[為 UE-V 組態方法進行規劃](planning-for-ue-v-configuration-methods.md)

規劃自訂範本部署
 

 





