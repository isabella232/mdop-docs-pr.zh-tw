---
title: 關於 MBAM 2.5 SP1
description: 關於 MBAM 2.5 SP1
author: dansimp
ms.assetid: 6f12e605-44e6-4646-9c20-aee89c8ff0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 41e47e1561629c00d30b45ad2dcd94f37753af5b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810161"
---
# 關於 MBAM 2.5 SP1


MBAM 2.5 SP1 為 BitLocker 磁片磁碟機加密提供簡化的管理介面。 BitLocker 針對遺失或被盜電腦的資料竊取或資料暴露提供增強型保護。 BitLocker 會加密儲存在 Windows 作業系統上的所有資料，以及磁片磁碟機和已設定的資料硬碟。

## MBAM 概覽


MBAM 2.5 SP1 具有下列功能：

-   可讓系統管理員自動處理整個企業用戶端電腦上的加密量。

-   可讓安全性監察官快速判斷個別電腦或甚至企業本身的合規性狀態。

-   使用 Microsoft System Center Configuration Manager 提供集中式報告及硬體管理。

-   減少支援中心的工作負荷，協助最終使用者使用 BitLocker PIN 和復原金鑰要求。

-   讓使用者能夠使用自助入口網站，獨立地復原加密的裝置。

-   讓安全官員能夠輕鬆地審核存取權，以復原金鑰資訊。

-   讓 Windows 企業使用者能在任何地方繼續運作，保證公司資料受到保護。

MBAM 會強制執行您針對企業所設定的 BitLocker 加密原則選項、監控用戶端電腦與這些原則的合規性，以及企業及個人電腦的加密狀態報表。 此外，MBAM 可讓您在使用者忘記其 PIN 或密碼時，或當他們的 BIOS 或開機記錄變更時，存取復原金鑰資訊。

下列群組可能會對使用 MBAM 來管理 BitLocker 感興趣：

-   管理員、IT 安全性專業人員，以及負責確保機密資料在未授權的情況下公開的合規性官員

-   負責遠端或分支辦公室中電腦安全性性的管理員

-   負責執行 Windows 之用戶端電腦的系統管理員

**記事** 在本 MBAM 檔中不詳細說明 BitLocker。 如需詳細資訊，請參閱[BitLocker 磁片磁碟機加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。

 

## <a href="" id="what-s-new-in-mbam-2-5-sp1"></a>MBAM 2.5 SP1 的新功能


本節說明 MBAM 2.5 SP1 中的新功能。

### MBAM 2.5 SP1 用戶端的新支援語言

目前僅支援 MBAM 用戶端的 MBAM 2.5 SP1 中的下列其他語言，包括自助入口網站：

捷克文（捷克共和國） cs-CZ

丹麥文（丹麥） da-深色

荷蘭文（荷蘭） nl-nl&platform-NL-NL&PLATFORM

芬蘭文（芬蘭） fi

希臘文（希臘） el-GR

匈牙利文（匈牙利） hu

挪威文、博克瑪律文（挪威） nb-否

波蘭文（波蘭） pl-PL

葡萄牙文（葡萄牙） pt

斯洛伐克文（斯洛伐克） sk-SK

斯洛維尼亞文（斯洛維尼亞） sl-SI

瑞典文（瑞典） sv-SE

土耳其文（土耳其） tr-TR

如需 MBAM 2.5 和 MBAM 2.5 SP1 中用戶端和伺服器支援的所有語言清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。

### Windows 10 支援

MBAM 2.5 SP1 除了與舊版 MBAM 中支援的相同軟體之外，還會新增 Windows 10 和 Windows Server 2016 支援。

Windows 10 在 MBAM 2.5 和 MBAM 2.5 SP1 中都有支援。

### Microsoft SQL Server 2014 SP1 的支援

MBAM 2.5 SP1 會新增 Microsoft SQL Server 2014 SP1 的支援，以及舊版 MBAM 中支援的相同軟體。

### MBAM 不會再隨附個別的 MSI

從 MBAM 2.5 SP1 開始，MBAM 產品不再隨附個別的 MSI。 不過，您可以從隨附于產品的可執行檔（.exe）中解壓縮 MSI。

### MBAM 可以在不擁有 TPM 的情況下保管 OwnerAuth 密碼

之前，如果 MBAM 不擁有 TPM，TPM OwnerAuth 無法 escrowed 至 MBAM 資料庫。 若要設定 MBAM 擁有 TPM 並儲存密碼，您必須停用 TPM 自動供給，並在用戶端電腦上清除 TPM。

在 Windows 8 及更高版本中，MBAM 2.5 SP1 現在可以在不擁有 TPM 的情況下，來保管 OwnerAuth 密碼。 在服務啟動期間，MBAM 查詢以查看 TPM 是否已擁有，如果是，它會要求作業系統的密碼。 然後將密碼 escrowed 到 MBAM 資料庫。 此外，必須將群組原則設定為防止在本機刪除 OwnerAuth。

在 Windows 7 中，MBAM 必須擁有 TPM，才能在 MBAM 資料庫中自動委託 TPM OwnerAuth 資訊。 如果 MBAM 不擁有 TPM，且已透過群組原則設定 TPM 的 Active Directory （AD）備份，您必須使用**MBAM Active Directory （ad）資料匯入 Cmdlet** ，才能將 TPM OWNERAUTH 從 AD 複製到 MBAM 資料庫。 這些是五個新的 PowerShell Cmdlet，這些 Cmdlet 會使用儲存在 Active Directory 中的大量復原及 TPM 擁有者資訊預先填入 MBAM 資料庫。

如需詳細資訊，請參閱[MBAM 2.5 安全性考慮](mbam-25-security-considerations.md#bkmk-tpm)。

### MBAM 可以在封鎖之後自動解除鎖定 TPM

在執行 TPM 1.2 的電腦上，您現在可以將 MBAM 設定為在封鎖時自動解除鎖定 TPM。 如果已啟用 TPM 封鎖自動重設功能，MBAM 會偵測到使用者已被封鎖，然後從 MBAM 資料庫取得 OwnerAuth 密碼，以便自動解除鎖定使用者的 TPM。

在伺服器端和用戶端的群組原則中，都必須啟用這項功能。 如需詳細資訊，請參閱[MBAM 2.5 安全性考慮](mbam-25-security-considerations.md#bkmk-autounlock)。

### 支援 FIPS 相容的 BitLocker 數位密碼保護器

在 MBAM 2.5 中，在執行 Windows 8.1 作業系統的裝置上，為聯邦資訊處理標準（FIPS）相容的 BitLocker 復原金鑰新增支援。 不過，Windows 沒有在 Windows 7 中實現 FIPS 相容的復原金鑰。 因此，Windows 7 和 Windows 8 裝置仍需要資料復原代理程式（DRA）保護器來進行恢復。

Windows 小組擁有與熱修復程式 backported FIPS 相容的復原金鑰，而 MBAM 2.5 SP1 也已新增支援。

**記事** 執行 Windows8 作業系統的用戶端電腦仍需要 DRA 保護器，因為修復程式未 backported 至該作業系統。 若要下載並安裝適用于 Windows 7 和 Windows 8 電腦的 BitLocker 修復程式，請參閱[BitLocker 管理和監視2.5 的修補程式套件 2](https://support.microsoft.com/kb/3015477) 。 如需 DRA 的相關資訊，請參閱將[資料修復代理程式與 BitLocker 配合使用](https://go.microsoft.com/fwlink/?LinkId=393557)。

 

若要在貴組織中啟用 FIPS 相容性，您必須設定聯邦資訊處理標準（FIPS）群組原則設定。 如需配置指示，請參閱[BitLocker 群組原則設定](https://go.microsoft.com/fwlink/?LinkId=393560)。

### 使用新的群組原則設定自訂啟動前恢復訊息和 URL

新的群組原則設定、**設定預先啟動的復原訊息和 URL**，可讓您設定自訂的復原訊息，或指定一個 URL，當作業系統磁片磁碟機鎖定時，就會顯示在預啟動的 BitLocker 恢復畫面上。 這個設定只能在執行 Windows 10 的用戶端電腦上使用。

如果您啟用此原則設定，您可以針對預啟動還原訊息選取下列其中一個選項：

-   **使用自訂**的復原訊息：選取這個選項，即可在 [預啟動 BitLocker 恢復] 畫面中包含自訂訊息。

-   **使用自訂**的復原 URL：選取這個選項，以取代 [預啟動 BitLocker 恢復] 畫面中顯示的預設 URL。

-   **使用預設的復原訊息和 URL**：選取這個選項，即可在 [啟動前的 bitlocker 恢復] 畫面中顯示預設的 BitLocker 復原訊息和 URL。 如果您先前已設定自訂的復原訊息或 URL，且想要還原為預設訊息，您必須啟用此原則，然後選取此選項。

新的群組原則設定位於下列 GPO 節點： [電腦設定**Computer Configuration** &gt; **策略**] &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **作業系統磁片磁碟機**。 如需詳細資訊，請參閱[規劃 MBAM 2.5 群組原則需求](planning-for-mbam-25-group-policy-requirements.md)。

### MBAM 已新增對已使用空間加密的支援

在 MBAM 2.5 SP1 中，如果您透過 BitLocker 群組原則啟用 [使用空間加密]，MBAM 用戶端就會接受這項功能。

這個群組原則設定稱為**在操作系統磁碟機上強制執行磁片磁碟機加密類型**，且位於下列 GPO 節點： [**電腦設定] 系統** &gt; **管理範本** &gt; **Windows 元件**（ &gt; **BitLocker 磁片磁碟機加密** &gt; **操作系統磁碟機**）。 如果您啟用此原則，並選取 [**僅限已使用的空間**] 加密的加密類型，MBAM 將會服從原則，而 BitLocker 將只會將在該卷上使用的磁碟空間加密。

如需詳細資訊，請參閱[規劃 MBAM 2.5 群組原則需求](planning-for-mbam-25-group-policy-requirements.md)。

### MBAM 加密硬碟的用戶端支援

MBAM 支援針對 Opal 和 IEEE 1667 標準提供 TCG 規格需求的加密硬碟磁碟機上的 BitLocker。 在這些裝置上啟用 BitLocker 時，它會在加密的磁片磁碟機上產生金鑰並執行管理功能。 如需詳細資訊，請參閱[加密的硬碟](https://technet.microsoft.com/library/hh831627.aspx)。

### 註冊 Spn 時不再需要委派設定

在 MBAM 2.5 SP1 中，您不再需要針對您為應用程式池帳戶所註冊的 Spn 設定受限制委派的需求。 不過，它仍是 MBAM 2.5 的必要條件。

### 使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker

在 MBAM 2.5 SP1 中，您可以使用 PowerShell 腳本，將 BitLocker 磁碟機加密和保管中的修復金鑰設定為 MBAM 伺服器。

如需詳細資訊，請參閱[如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)

### 自助式入口網站可以使用 PowerShell 或 SSP 自訂嚮導來自訂

從 MBAM 2.5 SP1，自助式入口網站可以使用 [自訂嚮導] 以及 [使用 PowerShell] 進行設定。 瞭解[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)。

### 網頁瀏覽器不會再以系統管理員身分執行

MBAM 2.5 中的問題導致伺服器設定工具中的 [說明] 連結導致瀏覽器視窗以系統管理員許可權開啟。 這個問題已在 MBAM 2.5 SP1 中修正。

### 當 CDN 無法存取時，不再需要下載 JavaScript 檔案以設定自助入口網站

在 MBAM 2.5 及較舊版本中，如果用戶端存取自助入口網站沒有網際網路存取權，就必須預先從 CDN 下載用於自助處理的 jQuery 檔案。 在 MBAM 2.5 SP1 中，所有的 JavaScript 檔案都包含在產品中，因此不需要下載這些檔案。

### 報表可在報表建立器3.0 中開啟

在 MBAM 2.5 SP1 中，報表已更新為最新的報表定義語言架構，讓使用者能夠在報表建立器3.0 中開啟及自訂報表，並立即儲存，而不會損壞報表檔案。

### 新的 PowerShell Cmdlet

新的 MBAM 2.5 SP1 的 PowerShell Cmdlet 可讓您設定及管理不同的 MBAM 功能，包括資料庫、報告和 web 應用程式。 每個功能都有對應的 PowerShell Cmdlet，您可以用來啟用或停用功能，或是取得該功能的相關資訊。

已針對 MBAM 2.5 SP1 執行下列 Cmdlet：

-   寫入 MbamTpmInformation

-   寫入 MbamRecoveryInformation

-   讀取 ADTpmInformation

-   讀取 ADRecoveryInformation

-   寫入 MbamComputerUser

下列參數已在 MBAM 2.5 SP1 的 Enable-MbamWebApplication 和 Test MbamWebApplication Cmdlet 中實現：

-   DataMigrationAccessGroup

-   TpmAutoUnlock

如需有關 Cmdlet 的詳細資訊，請參閱[MBAM 2.5 安全考慮](mbam-25-security-considerations.md)及[Microsoft Bitlocker 管理與監視 Cmdlet](https://technet.microsoft.com/library/dn720418.aspx)說明。

### MBAM 代理程式偵測簡報模式

MBAM agent 可以偵測到電腦處於簡報模式時，避免在該時間喚醒調用 MBAM UI。

### MBAM agent 服務現已設定為使用延遲啟動

安裝之後，服務現在會將 MBAM agent 服務設定為使用延遲啟動，減少啟動 Windows 所需的時間長度。

### 已鎖定的固定資料量現已完工合規

「已鎖定的固定資料」磁片的合規性計算邏輯已變更為將磁片報告為「合規」，但保護性狀態和加密狀態為「未知」，且符合「大量已鎖定」的相容性狀態詳細資料。 先前，鎖定的卷已報告為「不相容」、「已加密」的保護程式狀態、「未知」的加密狀態，以及「未知錯誤」的規範狀態詳細資料。


## 如何取得 MDOP 技術


MBAM 是 Microsoft Desktop 優化套件（MDOP）的一部分。 MDOP 是 Microsoft 軟體保證程式的一部分。 如需 Microsoft 軟體保證計畫的詳細資訊，以及如何取得 MDOP，請參閱[如何取得 mdop？](https://go.microsoft.com/fwlink/?LinkId=322049)。

## MBAM 2.5 SP1 版本資訊


如需本檔中未包含的詳細資訊及最新資訊，請參閱[MBAM 2.5 SP1 的版本](release-notes-for-mbam-25-sp1.md)資訊。

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。

## 相關主題


[Microsoft BitLocker Administration and Monitoring 2.5](index.md)

[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)

 

 





