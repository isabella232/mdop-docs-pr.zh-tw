---
title: Microsoft BitLocker Administration and Monitoring 2.5
description: Microsoft BitLocker Administration and Monitoring 2.5
author: dansimp
ms.assetid: fd81d7de-b166-47e8-b6c7-d984830762b6
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 2e5243131853207f0ed3cbb6d0cd8fb8e3d56108
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795506"
---
# Microsoft BitLocker Administration and Monitoring 2.5

Microsoft BitLocker 管理和監控（MBAM）2.5 提供簡化的管理介面，您可以用來管理 BitLocker 磁碟機加密。 您可以設定 MBAM 群組原則範本，讓您設定適合您企業的 BitLocker 磁片磁碟機加密原則選項，然後使用這些範本來監視用戶端是否符合這些原則。 您也可以針對個別電腦和企業整體，報告其加密狀態。 此外，您也可以在使用者忘記 PIN 或密碼或其 BIOS 或開機記錄變更時，存取復原金鑰資訊。 如需 MBAM 的詳細說明，請參閱[關於 MBAM 2.5](about-mbam-25.md)。

若要取得 MBAM，請參閱[如何取得 MDOP](https://docs.microsoft.com/microsoft-desktop-optimization-pack/index#how-to-get-mdop)。

## 大綱

- <a href="" id="getting-started-with-mbam-2-5"></a>[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)
  - [關於 MBAM 2.5](about-mbam-25.md)
  - [MBAM 2.5 版本資訊](release-notes-for-mbam-25.md)
  - [關於 MBAM 2.5 SP1](about-mbam-25-sp1.md)
  - [MBAM 2.5 SP1 版本資訊](release-notes-for-mbam-25-sp1.md)
  - [在測試環境中評估 MBAM 2.5](evaluating-mbam-25-in-a-test-environment.md)
  - [MBAM 2.5 的概要架構](high-level-architecture-for-mbam-25.md)
  - [MBAM 2.5 的協助工具](accessibility-for-mbam-25.md)
- <a href="" id="planning-for-mbam-2-5"></a>[MBAM 2.5 規劃](planning-for-mbam-25.md)
  - [MBAM 2.5 的環境準備](preparing-your-environment-for-mbam-25.md)
  - [MBAM 2.5 部署必要條件](mbam-25-deployment-prerequisites.md)
  - [MBAM 2.5 群組原則需求規劃](planning-for-mbam-25-group-policy-requirements.md)
  - [MBAM 2.5 群組與帳戶規劃](planning-for-mbam-25-groups-and-accounts.md)
  - [如何保護 MBAM 網站的規劃](planning-how-to-secure-the-mbam-websites.md)
  - [規劃部署 MBAM 2.5](planning-to-deploy-mbam-25.md)
  - [MBAM 2.5 支援的組態](mbam-25-supported-configurations.md)
  - [MBAM 2.5 高可用性規劃](planning-for-mbam-25-high-availability.md)
  - [MBAM 2.5 安全性考量](mbam-25-security-considerations.md)
  - [MBAM 2.5 規劃檢查清單](mbam-25-planning-checklist.md)
- <a href="" id="deploying-mbam-2-5"></a>[部署 MBAM 2.5](deploying-mbam-25.md)
  - [部署 MBAM 2.5 伺服器基礎結構](deploying-the-mbam-25-server-infrastructure.md)
  - [部署 MBAM 2.5 群組原則物件](deploying-mbam-25-group-policy-objects.md)
  - [部署 MBAM 2.5 用戶端](deploying-the-mbam-25-client.md)
  - [MBAM 2.5 部署檢查清單](mbam-25-deployment-checklist.md)
  - [從舊版升級至 MBAM 2.5 或 MBAM 2.5 SP1](upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md)
  - [移除 MBAM 伺服器功能或軟體](removing-mbam-server-features-or-software.md)
- <a href="" id="operations-for-mbam-2-5"></a>[適用於 MBAM 2.5 的操作](operations-for-mbam-25.md)
  - [管理 MBAM 2.5 功能](administering-mbam-25-features.md)
  - [使用 MBAM 2.5 監視與報告 BitLocker 符合性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)
  - [使用 MBAM 2.5 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)
  - [維護 MBAM 2.5](maintaining-mbam-25.md)
  - [使用 Windows PowerShell 管理 MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md)
- <a href="" id="troubleshooting-mbam-2-5"></a>[MBAM 2.5 疑難排解](troubleshooting-mbam-25.md)
- <a href="" id="technical-reference-for-mbam-2-5"></a>[MBAM 2.5 技術參考資料](technical-reference-for-mbam-25.md)
  - [用戶端事件記錄檔](client-event-logs.md)
  - [伺服器事件記錄檔](server-event-logs.md)

## 其他資訊

- [MDOP 資訊體驗](index.md)

  尋找您的 MDOP 技術的檔、影片及其他資源。

- [MBAM 部署指南](https://www.microsoft.com/download/details.aspx?id=38398)

  取得為 MBAM 選擇部署方法的說明，包括每個方法的逐步指示。
    
- [在 MBAM 2.5 SP1 伺服器上套用熱修復程式](apply-hotfix-for-mbam-25-sp1.md)

  如何套用 MBAM 2.5 SP1 Server 熱修復程式的指南
