---
title: 管理 UE-V 2.x 的設定
description: 管理 UE-V 2.x 的設定
author: dansimp
ms.assetid: e2332eca-a9cd-4446-8f7c-d17058b03466
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 20d5d2942dbd805a4054a9431b237c821cbb70fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812321"
---
# 管理 UE-V 2.x 的設定


在 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 或 2.1 SP1 週期中，您必須管理 UE-V Agent 的設定，也可以管理資源的儲存位置，例如設定套件檔案。 您可能需要執行其他工作，例如設定公司設定中心來定義使用者與 UE-V 互動的方式。 下列主題提供管理這些 UE-V 資源的指導方針。

## 使用群組原則物件來設定 UE-V 2. x


您可以使用群組原則物件來修改定義 UE-V 如何在電腦上同步處理設定的設定。

[使用群組原則物件設定 UE-V 2. x](configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)

## 使用 System Center Configuration Manager 2012 設定 UE-V 2. x


您可以使用 SystemCenter2012 ConfigurationManager 來管理 ue-v Agent，方法是使用 UE-V 2 配置包。

[使用 System Center Configuration Manager 2012 設定 UE-V 2. x](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

## 使用 PowerShell 和 WMI 管理 UE-V 2. x


UE-V 提供 Windows PowerShell Cmdlet，可協助管理員執行各種 UE-V 工作。

[使用 Windows PowerShell 和 WMI 管理 UE-V 2. x](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

## 設定 UE-V 2. x 的公司設定中心


您可以設定使用 UE-V Agent 所安裝的公司設定中心，以定義使用者與 UE-V 互動的方式。

[設定 UE-V 2. x 的公司設定中心](configuring-the-company-settings-center-for-ue-v-2x-both-uevv2.md)

## UE-V 2. x 的配置設定範例


以下是 UE-V 設定設定的一些範例：

-   **設定儲存路徑：** 指定儲存 UE-V 設定的檔案共用位置。

-   **設定範本目錄路徑：** 指定通用命名慣例（UNC）路徑，該路徑定義已針對新設定位置範本檢查的位置。

-   **註冊 Microsoft 範本：** 指定是否應在安裝期間註冊預設的 Microsoft 範本。

-   **同步處理方法：** 指定 UE-V 是使用同步處理提供者或 "none"。 "SyncProvider" 支援的電腦已從網路中斷連線。 當電腦永遠連線至網路時，就會套用「無」。 如需同步處理方法的詳細資訊，請參閱[ue-v 2. x 的同步處理方法](sync-methods-for-ue-v-2x-both-uevv2.md)。

-   **同步處理超時：** 指定當它從 [設定] 儲存位置中檢索使用者設定時，電腦在超時前等待的毫秒數。

-   **啟用同步處理：** 指定是否已啟用或停用 UE-V 設定同步處理。

-   **套件最大大小：** 指定 UE-V Agent 報告警告的設定套件檔閾值大小（以位元組為單位）。

-   **不要同步處理 Windows 應用程式設定：** 指定 UE-V 不應同步處理 Windows 應用程式。

-   **啟用/停用第一次使用通知：** 指定在第一次 UE-V Agent 在使用者的電腦上執行時，UE-V 是否會顯示一個對話方塊。

-   **啟用/停用託盤圖示：** 指定 UE-V 是否在通知區域中顯示圖示，以及與它相關聯的任何通知。 此圖示提供 [公司設定中心] 的連結。

-   **自訂連絡人它的超連結：** 在 [公司設定中心] 中定義 [**連絡人 IT** ] 超連結的路徑、文字及描述。






## 相關主題


[管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)

[部署 UE-V 2.x 的必要功能](deploy-required-features-for-ue-v-2x-new-uevv2.md)

[部署自訂應用程式的 UE-V 2. x](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





