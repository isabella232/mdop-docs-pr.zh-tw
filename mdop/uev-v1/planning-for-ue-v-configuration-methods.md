---
title: 為 UE-V 組態方法進行規劃
description: 為 UE-V 組態方法進行規劃
author: dansimp
ms.assetid: 57bce7ab-1be5-434b-9ee5-c96026bbe010
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4894644d72392ae984d0de290bf634e137d5b85e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812147"
---
# 為 UE-V 組態方法進行規劃


Microsoft 使用者體驗虛擬化（UE-V）設定決定如何在整個企業中同步處理設定。 本主題描述如何建立 UE-V 設定，以協助您表述最符合您的業務需求的設定方案。

## UE-V 的配置方法


您可以在安裝代理程式之前、期間或之後設定 UE-V，視您使用的配置方法而定。

**群組原則：** 現有的群組原則基礎結構可以用來設定 ue-v agent 部署之前或之後的 ue-v。 UE-V ADMX 範本可提供通用 UE-V Agent 設定選項的集中管理，並包含設定 UE-V 同步處理的設定。 使用群組原則的網路環境可以預先配置 UE-V，以預期的代理部署。

[使用群組原則物件來設定 UE-V](configuring-ue-v-with-group-policy-objects.md)

[安裝 UE-V 群組原則 ADMX 範本](installing-the-ue-v-group-policy-admx-templates.md)

**命令列或批次腳本安裝：** 與 ue-v Agent 部署搭配使用的參數，可讓您設定多個 ue-v 設定。 電子軟體發佈系統（例如系統中心建構管理員），在部署並安裝 UE-V Agent 軟體時，請使用這些參數來設定用戶端。 如需安裝參數及範例安裝腳本的清單，請參閱[部署 Ue-v Agent](deploying-the-ue-v-agent.md)。

**PowerShell 與 wmi：** 使用 POWERSHELL 或 wmi 的腳本式命令可在已安裝 ue-v agent 之後，用來修改設定。 如需 PowerShell 與 WMI 命令的清單，請參閱[使用 PowerShell 和 Wmi 管理 ue-v 1.0 Agent 和套件](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)。

**編輯註冊表設定：** UE-V 設定會儲存在登錄中，而且可以使用任何可修改註冊表設定的工具（例如 RegEdit）來修改。

**記事** 註冊表修改可能導致資料遺失或電腦變慢。 建議您使用其他配置方法。

 

### UE-V 設定

下列是 UE-V 設定的範例：

-   **設定儲存路徑：** 指定儲存 ue-v 設定的檔案共用位置。

-   **設定範本目錄路徑：** 指定通用命名慣例（UNC）路徑，該路徑定義已針對新設定位置範本檢查的位置。

-   **註冊 Microsoft 範本：** 指定是否應在安裝期間註冊預設的 Microsoft 範本。

-   **同步處理方法：** 指定是否要使用 Windows 離線檔案功能來進行離線支援。

-   **同步處理超時：** 指定從 [設定] 儲存位置中檢索使用者設定時，電腦在超時前等待的毫秒數。

-   **啟用同步處理：** 指定是否已啟用或停用 ue-v 設定同步處理。

-   **最大套件大小：** 指定 ue-v agent 報告警告的設定套件檔閾值大小（以位元組為單位）。

## 相關主題


[為 UE-V 1.0 進行規劃](planning-for-ue-v-10.md)

[為 UE-V 組態進行規劃](planning-for-ue-v-configuration.md)

 

 





