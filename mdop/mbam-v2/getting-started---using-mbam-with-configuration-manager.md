---
title: 開始使用 - 將 MBAM 與設定管理員搭配使用
description: 開始使用 - 將 MBAM 與設定管理員搭配使用
author: dansimp
ms.assetid: b0a1d3cc-0b01-4b69-a2cd-fd09fb3beda4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 654de38918102a41395efe37dc593ce8f49113e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810994"
---
# 開始使用 - 將 MBAM 與設定管理員搭配使用


當您安裝 Microsoft BitLocker 管理和監控（MBAM）時，您可以選擇將 MBAM 與 Configuration Manager 2007 或 SystemCenter2012 ConfigurationManager 整合的拓撲。 如需 MBAM 支援之支援版本 Configuration Manager 的清單，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。 在整合拓朴中，會從 MBAM 中移除硬體合規性和報告功能，並從 Configuration Manager 存取。

**重要** 當您安裝 MBAM 與 Configuration Manager 2007 的整合拓撲時，系統不支援 Windows To Go。

 

## 使用 MBAM 搭配 Configuration Manager


MBAM 的整合是依據將下列三個專案安裝到 Configuration Manager 2007 或 SystemCenter2012 ConfigurationManager 的新配置套件所決定，以下各節將詳細說明這些專案：

由設定項目和配置比較基準組成的配置資料

集合

報告

### 配置資料

配置資料會安裝名為「BitLocker Protection」的設定比較基準，其中包含兩個設定專案：「BitLocker 作業系統磁片磁碟機保護」和「BitLocker 固定資料磁碟機保護」。 配置基線會部署到集合，在安裝 MBAM 時也會建立該集合。 這兩個設定專案提供評估用戶端電腦合規性狀態的基礎。 此資訊是在 Configuration Manager 中捕獲、儲存及評估。 設定專案是根據作業系統磁片磁碟機（OSDs）和固定資料磁碟機（FDDs）的規範需求而定。 系統會收集已部署電腦所需的詳細資料，以便評估這些磁碟機類型的合規性。 根據預設，設定比較基準會每隔12小時評估合規性狀態，並將合規性資料傳送至 Configuration Manager。

### 集合

MBAM 會建立一個名為 MBAM 支援的電腦的集合。 配置基線是針對此集合中的用戶端電腦所設定。 這是一種動態集合，預設會每12小時執行一次，並會評估成員資格。 成員資格以三個準則為基礎：

-   它是受支援版本的 Windows 作業系統。 目前，MBAM 只支援 Windows 7 企業版和 Windows 7 旗艦版、Windows 8 企業版和 Windows To Go，在 Windows 8 企業版上執行 Windows。

-   它是物理電腦。 不支援虛擬機器。

-   可使用受信任的平臺模組（TPM）。 Windows 7 需要相容版本的 TPM 1.2 或更新版本。 Windows 8 和 Windows To Go 不需要 TPM。

針對所有電腦評估集合，並建立相容電腦的子集，為 MBAM 整合提供合規性評估與報告的基礎。

### 報告

您可以使用四種報告來查看合規性。 這些類型包括：

-   **BitLocker Enterprise 合規性儀表板**-可讓 IT 系統管理員在單一報告上提供三種不同的資訊視圖：合規性狀態發佈、不相容–錯誤發佈，以及依磁片磁碟機類型進行合規性狀態發佈。 報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合您所選狀態的電腦清單。

-   **BitLocker Enterprise 合規性詳細資料**：讓 IT 系統管理員可以查看企業的 BitLocker 加密合規性狀態相關資訊，並包括每個電腦的相容性狀態。 報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合您所選狀態的電腦清單。

-   **BitLocker 電腦合規性**-可讓 IT 系統管理員查看個別的電腦，並判斷它為什麼會以符合或不符合規範的特定狀態報表。 報告也會顯示作業系統磁片磁碟機（OSD）和固定資料磁碟機（FDDs）的加密狀態。

-   **BitLocker Enterprise 合規性摘要**：可讓 IT 系統管理員透過 MBAM 原則來查看企業合規性的狀態。 會評估每個電腦的狀態，而報告會顯示企業中所有電腦對原則的合規性摘要。 報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合您所選狀態的電腦清單。

## 含 Configuration Manager 之 MBAM 的高層次架構


下圖顯示具有 Configuration Manager 拓撲的 MBAM 結構。 此設定在生產環境中最多可支援 200000 MBAM 用戶端。

![含 configuration manager 的 mbam 架構](images/mbam2-cmserver.gif)

此架構的伺服器、資料庫和功能說明如下。 體系結構中的伺服器功能和資料庫會列在電腦或伺服器下，我們建議您安裝它們。

-   **資料庫伺服器**–復原**資料庫**、**審核資料庫**及**審核報告**都安裝在 Windows Server 和支援的 SQLServer 實例上。 復原資料庫會儲存從 MBAM 用戶端電腦收集的復原資料。 審核資料庫會儲存從已存取復原資料的用戶端電腦收集的審核活動資料。 審計報告提供企業中用戶端電腦合規性狀態的相關資料。

-   **Configuration Manager 主要網站伺服器**： Configuration manager 伺服器包含含 System Center Configuration Manager 整合拓撲的 MBAM 伺服器安裝，必須安裝在 Configuration Manager 主要網站伺服器上。 Configuration Manager 伺服器會從用戶端電腦收集硬體清查資訊，並使用它來報告用戶端電腦的 BitLocker 合規性。 當您執行 MBAM 安裝伺服器安裝時，系統會在 Configuration Manager 主要網站伺服器上安裝集合和設定資料。

-   **管理和監控伺服器**-系統會在 Windows Server 上安裝 [**管理與監控伺服器**]，並由 [管理與監控] 網站和 [監視] web 服務組成。 管理和監控網站是用來審核活動，以及存取復原資料（例如，BitLocker 復原金鑰）。 [**自助式入口網站**] 也會安裝在 [管理] 和 [監視伺服器] 上。 入口網站可讓用戶端電腦上的使用者能夠獨立登錄至網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。 審計報告也會安裝在 [管理和監控伺服器] 上。

-   **管理工作站**-**原則範本**是由定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的群組原則物件所組成。 您可以在任何伺服器或工作站上安裝此原則範本，但通常會將它安裝在支援 Windows server 或用戶端電腦的管理工作站上。 工作站不一定是專用電腦。

-   **MBAM 用戶端**與**Configuration Manager 用戶端**電腦

    -   **MBAM 用戶端**會執行下列任務：

        -   使用群組原則物件來強制執行企業用戶端電腦的 BitLocker 加密。

        -   收集三個 BitLocker 資料磁片磁碟機類型的復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動資料（USB）硬碟。

        -   收集用戶端電腦的恢復資訊和電腦資訊。

    -   **Configuration Manager 用戶端**-configuration manager 用戶端可讓 configuration manager 收集用戶端電腦的硬體相容性資料，並讓 configuration manager 報告合規性資訊。

## 相關主題


[使用 MBAM 搭配 Configuration Manager](using-mbam-with-configuration-manager.md)

 

 





