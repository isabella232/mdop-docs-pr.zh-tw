---
title: 關於 MBAM 2.0
description: 關於 MBAM 2.0
author: dansimp
ms.assetid: b43a0ba9-1c83-4854-a2c5-14eea0070e36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7bdf24d1f375dd1fa8b18ac90c2fc49d2887c6c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810484"
---
# 關於 MBAM 2.0


Microsoft BitLockerAdministration 和 Monitoring （MBAM）2.0 提供簡化的管理介面以進行 BitLocker 磁碟機加密。 BitLocker 針對遺失或被盜電腦的資料竊取或資料暴露提供增強型保護。 BitLocker 會加密儲存在 Windows 作業系統卷和已設定資料量的所有資料。

## 關於 MBAM 2。0


BitLockerAdministration 和 Monitoring 2.0 會強制您為企業設定的 BitLocker 加密原則選項，監視用戶端電腦與這些原則的合規性，以及企業和個別電腦的加密狀態。 此外，MBAM 可讓您在使用者忘記其 PIN 或密碼時，或當他們的 BIOS 或開機記錄變更時，存取復原金鑰資訊。

**記事** 本指南未涵蓋 BitLocker 的詳細資料。 如需 BitLocker 的概覽，請參閱[Bitlocker 磁片磁碟機加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。

 

下列群組可能會對使用 MBAM 來管理 BitLocker 感興趣：

-   管理員、IT 安全性專業人員，以及負責確保機密資料在未授權的情況下公開的合規性官員

-   負責遠端或分支辦公室中電腦安全性性的管理員

-   負責執行 Windows 之用戶端電腦的系統管理員

## <a href="" id="what-s-new-in-mbam-2-0"></a>MBAM 2.0 的新功能


MBAM 2.0 提供下列新功能和功能。

### 將 System Center Configuration Manager 與 MBAM 整合

MBAM 現在支援與 System Center Configuration Manager 整合。 此整合將 MBAM 合規性基礎結構移至 Configuration Manager 的原生環境。 在企業中使用 Configuration Manager 的 IT 系統管理員現在可以在 Microsoft 管理主控台中查看其企業的合規性狀態，並深入探索報表來查看個別電腦。

### 硬體相容性僅適用于 Configuration Manager 整合拓撲

將 Configuration Manager 與 MBAM 整合可啟用 Configuration Manager 功能，允許或禁止搭配 MBAM 使用特定的硬體類型，並提供比 MBAM 1.0 中提供的硬體相容性更大的彈性。 IT 管理員可以建立自己的集合來限制硬體，並可將 MBAM 配置基線部署到這些集合。 MBAM 1.0 中目前的 MBAM 硬體相容性現在僅提供 MBAM Configuration Manager 拓撲，且是從 Configuration Manager 管理的。

### 保護彈性原則

已使用保護器加密的電腦（例如，TPM + PIN 或自動解鎖及密碼），而且會收到需要該加密子集的 MBAM 原則（例如，TPM 或自動解鎖）。 在上述範例中，不會自動移除 PIN 及密碼，除非 IT 系統管理員明確定義這些功能，否則不允許。

未加密且接收 MBAM 原則的電腦（例如，TPM 或自動解鎖）會據此加密。 擁有本機管理員的使用者可以使用 BitLocker 工具（[控制台專案-BitLocker 磁片磁碟機加密或 manage-bde）] 來新增或修改現有的保護器（例如，TPM + PIN 或自動解鎖及密碼）。 除非 MBAM 原則明確定義，否則它們會維持合規性。

### 升級 MBAM 用戶端的能力

MBAM 2.0 用戶端 Windows 安裝程式會偵測現有用戶端的版本，並執行必要步驟，以升級到舊版的 MBAM 2.0 用戶端。

### 從舊版升級 MBAM 伺服器的能力

您可以從舊版 MBAM 升級 MBAM 2.0 Server 基礎結構，如下所示：

**手動就地伺服器取代**-您必須手動卸載現有的 MBAM 伺服器基礎結構，然後再安裝 MBAM 2.0 server 基礎結構。 您不需要移除資料庫即可進行升級。 相反地，您會選取先前版本的 MBAM 用戶端所建立的現有資料庫。 MBAM 2.0 升級安裝接著會將現有的資料庫移轉至 MBAM 2.0。

**分散式用戶端升級**：如果您使用的是獨立 MBAM 拓朴，您可以在安裝 MBAM 2.0 伺服器基礎結構之後，逐漸升級 MBAM 用戶端。 MBAM 2.0 伺服器會偵測現有用戶端的版本，並執行所需的步驟以升級至2.0 用戶端。

在您升級 MBAM 2.0 伺服器基礎結構之後，MBAM 1.0 用戶端會繼續成功向 MBAM 2.0 伺服器報告，escrowing 復原資料，但合規性將根據 MBAM 1.0 中的原則而定。 您必須將用戶端升級至 MBAM 2.0，讓用戶端電腦能根據 MBAM 2.0 原則精確地報告合規性。 您可以將用戶端升級至 MBAM 2.0 用戶端，而不卸載先前的用戶端，用戶端就會開始套用並報告 MBAM 2.0 原則。

如果您是使用 MBAM 與 Configuration Manager，您必須將 MBAM 1.0 用戶端升級至 MBAM 2.0。

### <a href="" id="mbam-support-for-bitlocker-s-enterprise-scenarios-on-the-windows-8-platform"></a>在 Windows 8 平臺上 MBAM BitLocker 企業案例的支援

MBAM 支援 Windows 8 作業系統做為 MBAM 用戶端安裝的目標平臺。 此支援可讓 IT 系統管理員安裝 MBAM agent、加密 Windows 8 作業系統磁片磁碟機，以及報告電腦合規性。 MBAM 利用 TPM 和 TPM + PIN 保護器來管理 Windows 8 作業系統，就像在 Windows 7 作業系統中一樣。 MBAM 2.0 也會新增加密 Windows 的支援以取得用戶端。

### 自助服務入口網站的新增

最終使用者現在可以使用自助入口網站來復原其修復金鑰。 自助式入口網站可以使用其他 MBAM 功能部署在單一伺服器上，或在獨立的伺服器上，讓 IT 系統管理員能根據需要將自助式入口網站公開給使用者。 在自助入口網站驗證使用者之後，使用者只需要輸入復原金鑰識別碼的前八位數，即可接收其修復金鑰。

MBAM 也可以讓使用者只針對使用者的電腦復原金鑰來保護金鑰，這會減少其他使用者獲得未經授權存取的風險。

### 自動從暫停狀態繼續 BitLocker 保護的功能

MBAM 不允許 IT 系統管理員將 BitLocker 保持暫停狀態，並在長時間內受到保護。 如果 IT 系統管理員暫停 BitLocker，MBAM 會在電腦重新開機時自動重新啟用，這會降低電腦可能受到攻擊的風險。

### 固定資料磁碟機可以設定為自動解除鎖定而不需要密碼

您現在可以將固定資料磁碟機（FDD）原則設定為允許自動解鎖磁片磁碟機（不需密碼）。 在加密 FDD 之前，系統不會提示使用者輸入密碼，而且 FDD 會受到保護，並自動解除鎖定作業系統磁片磁碟機。

## <a href="" id="---------mbam-2-0-release-notes"></a> MBAM 2.0 版本資訊


如需詳細資訊，以及不包含在檔中的最新新聞，請參閱[MBAM 2.0 的版本](release-notes-for-mbam-20-mbam-2.md)資訊。

## 如何取得 MBAM 2。0


這項技術是 Microsoft 桌面優化套件（MDOP）的一部分。 企業客戶可以使用 Microsoft 軟體保證進行 MDOP。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop？](https://go.microsoft.com/fwlink/p/?LinkId=322049)

## 相關主題


[開始使用 MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)

 

 





