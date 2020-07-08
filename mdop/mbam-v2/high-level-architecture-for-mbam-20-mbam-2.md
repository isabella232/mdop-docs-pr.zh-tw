---
title: MBAM 2.0 的概要架構
description: MBAM 2.0 的概要架構
author: dansimp
ms.assetid: 7f73dd3a-0b1f-4af6-a2f0-d0c5bc5d183a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddc061a1aec5141548c2d2141be38f8501d2244d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810713"
---
# MBAM 2.0 的概要架構


Microsoft BitLocker 管理和監控（MBAM）是一種用戶端/伺服器方案，可協助您簡化 BitLocker 的置備及部署、改善 BitLocker 的相容性與報告，並減少支援成本。 Microsoft BitLocker 管理和監控包括本主題中所述的功能。

Microsoft BitLocker 管理和監視可以在獨立拓撲中部署，或是在與 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 整合的拓撲中部署。 本主題描述獨立拓朴的架構。 如需在整合式 Configuration Manager 拓撲結構中進行部署的相關資訊，請參閱[與 Configuration manager 一起使用 MBAM](using-mbam-with-configuration-manager.md)。

下圖顯示生產環境的 MBAM 建議架構，其中包含兩個伺服器與管理工作站。 這個架構最多可支援 200000 MBAM 用戶端。 體系結構中的伺服器功能和資料庫會在下一節中說明，並列在電腦或伺服器（我們建議您安裝它們）底下。

**記事** 單伺服器架構只能在測試環境中使用。

 

![mbam 2 2-伺服器部署拓朴](images/mbam2-3-servers.gif)

## 管理和監控伺服器


此伺服器上已安裝下列功能：

-   **管理和監控伺服器**。 系統會在 Windows Server 上安裝 [管理和監控伺服器] 功能，並包含 [管理與監控] 網站，其中包含報表與 [技術支援中心] 入口網站，以及監視 web 服務。

-   **自助入口網站**。 自助入口網站已安裝在 Windows 伺服器上。 自助式入口網站可讓用戶端電腦上的使用者能夠獨立地登入網站，讓他們可以取得修復金鑰來復原鎖定的 BitLocker 卷。

## 資料庫伺服器


此伺服器上已安裝下列功能：

-   [**恢復資料庫**]。 已在 Windows server 和支援的 Microsoft SQLServer 實例上安裝復原資料庫。 此資料庫儲存從 MBAM 用戶端電腦收集的復原資料。

-   **合規性和審核資料庫**。 合規性與審計資料庫是安裝在 Windows server 和支援的 SQLServer 實例上。 此資料庫儲存 MBAM 用戶端電腦的合規性資料。 此資料主要用於 SQL Server Reporting Services （SSRS）主機的報表。

-   **合規性和審核報告**。 合規性和審核報告會安裝在 Windows server 上，以及已安裝 SQL Server Reporting Services （SSRS）功能的 SQLServer 實例支援。 這些報告提供 MBAM 報告，您可以從 [管理] 和 [監視] 網站或直接從 SSRS 伺服器存取。

## 管理工作站


下列功能已安裝在管理工作站（可以是 Windows server 或用戶端電腦）上。

-   **原則範本**。 原則範本是由定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的群組原則設定所組成。 您可以在任何伺服器或工作站上安裝此原則範本，但通常會將它安裝在管理工作站上（這是受支援的 Windows server 或用戶端電腦）。 工作站不一定是專用電腦。

## <a href="" id="---------mbam-client"></a> MBAM 用戶端


MBAM 用戶端已安裝在 Windows 電腦上，且具有下列特性：

-   使用群組原則，強制企業中用戶端電腦的 BitLocker 磁碟機加密。

-   收集三個 BitLocker 資料磁片磁碟機類型的復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動資料（USB）硬碟。

-   收集電腦的規範資料，並將資料傳遞到報告系統。

## 相關主題


[開始使用 MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)

 

 





