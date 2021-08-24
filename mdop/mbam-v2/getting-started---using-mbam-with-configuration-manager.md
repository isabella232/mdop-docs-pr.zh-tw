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
ms.openlocfilehash: 9f23a0eba923608fb6e25e44ee2843f3cde4c2dc
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910808"
---
# <a name="getting-started---using-mbam-with-configuration-manager"></a>開始使用 - 將 MBAM 與設定管理員搭配使用


當您安裝 Microsoft BitLocker 系統管理與監控 (管理與監控) 時，您可以選擇一種拓撲，將 MICROSOFTM 與 Configuration Manager 2007 或 System Center 2012 Configuration Manager 整合。 若要瞭解支援之 CONFIGURATION Manager 版本的清單，請參閱規劃使用 Configuration Manager 部署 [該版本的 CONFIGURATION Manager](planning-to-deploy-mbam-with-configuration-manager-2.md)。 在整合拓撲中，硬體合規性與報告功能會從 INM 中移除，而且會從 Configuration Manager 存取。

**重要**  
Windows當您使用 Configuration Manager 2007 安裝整合式拓撲時，不支援前往。

 

## <a name="using-mbam-with-configuration-manager"></a>使用 MBAM 搭配 Configuration Manager


將的整合以新的組組套件為基礎，該套件將下列三個專案安裝到 Configuration Manager 2007 或 System Center 2012 Configuration Manager 中，以下各節將詳細說明：

包含設定專案和設定比較基準的組組資料

集合

報告

### <a name="configuration-data"></a>組組資料

設定資料會安裝稱為「BitLocker Protection」的設定比較基準，其中包含兩個設定專案：「BitLocker 作業系統磁片磁碟機保護」和「BitLocker 固定資料磁碟機保護」。 設定比較基準會部署至集合，此集合也會在安裝時建立。 這兩個組組專案提供評估用戶端電腦合規性狀態的基礎。 此資訊在 Configuration Manager 中會進行捕獲、儲存及評估。 組組專案是根據作業系統磁片磁碟機的合規性需求 (OSD) 固定資料磁碟機 (FDD) 。 系統會收集部署電腦所需的詳細資料，以便評估這些磁碟機類型的合規性。 根據預設，設定比較基準會每隔 12 小時評估合規性狀態，並將合規性資料傳送給 Configuration Manager。

### <a name="collection"></a>集合

"管理管理」會建立一個稱為"支援電腦"的集合。 設定比較基準會以此集合中的用戶端電腦為目標。 根據預設，這是一個動態集合，每 12 小時執行一次，並評估成員資格。 成員資格是根據三個準則：

-   這是支援的作業系統Windows版本。 目前，當 WINDOWS 7 企業版 上Windows 7 旗艦版時，WINDOWS 8 企業版 Windows僅支援 Windows 8 企業版、Windows 8 企業版 Windows 8 企業版 和 Windows Go。

-   它是實體電腦。 不支援虛擬機器。

-   TPM 中 (平臺模組) 可用。 7 版本需要相容的 TPM 1.2 或更新版本Windows版本。 Windows 8和Windows都不需要 TPM。

集合會針對所有電腦進行評估，並建立相容電腦的子集合，為進行合規性評估與報告提供基礎，以用於進行用於管理與管理管理整合。

### <a name="reports"></a>報告

您可以使用四個報告來查看合規性。 這些類型包括：

-   **BitLocker Enterprise合規性**儀表板 – 為 IT 系統管理員提供單一報表上三種不同的資訊視圖：合規性狀態發佈、不合規性 – 錯誤發佈，以及合規性狀態發佈方式的雲端硬碟類型。 報表上的向下拉式選項，讓 IT 系統管理員按一下資料，並查看符合您選取狀態的電腦清單。

-   **BitLocker Enterprise合規性詳細**資料 – 可讓 IT 系統管理員查看企業 BitLocker 加密合規性狀態的資訊，並包含每部電腦的合規性狀態。 報表上的向下拉式選項，讓 IT 系統管理員按一下資料，並查看符合您選取狀態的電腦清單。

-   **BitLocker 電腦合規性** – 可讓 IT 系統管理員查看個別電腦，並判斷為何報告其狀態為符合或不符合規定。 報表也會顯示作業系統磁片磁碟機的加密狀態， (OSD) 和固定資料磁碟機 (FDD) 。

-   **BitLocker Enterprise合規性摘要**- 可讓 IT 系統管理員查看企業與 會評估每部電腦的狀態，而報表會顯示企業中所有電腦與該政策之合規性的摘要。 報表上的向下拉式選項，讓 IT 系統管理員按一下資料，並查看符合您選取狀態的電腦清單。

## <a name="high-level-architecture-of-mbam-with-configuration-manager"></a>High-Level Configuration Manager 的<a0></a0>的<a1> </a1> <a2></a


下圖顯示具有 Configuration Manager 拓撲的可進行管理管理架構。 此組配置在生產環境中最多支援 200，000 個的 200，000 個 。.

![具有組組管理員的管理架構。](images/mbam2-cmserver.gif)

以下說明此架構的伺服器、資料庫和功能。 系統架構圖像中的伺服器功能和資料庫會列在建議您安裝之電腦或伺服器下。

-   **資料庫伺服器**：**修復資料庫**、**稽**核資料庫**** 和稽核報告會安裝在Windows且支援SQL Server實例。 修復資料庫會儲存從 SQLM 用戶端電腦收集的修復資料。 稽核資料庫會儲存從已存取復原資料的用戶端電腦收集的稽核活動資料。 稽核報告會提供有關您企業用戶端電腦合規性狀態的資料。

-   **Configuration Manager 主網站伺服器**– Configuration Manager Server 包含具有 System Center Configuration Manager 整合拓撲的一種 IBMM 伺服器安裝，必須安裝在 Configuration Manager 主網站伺服器上。 Configuration Manager Server 會收集用戶端電腦的硬體庫存資訊，並用來報告用戶端電腦的 BitLocker 合規性。 當您執行此安裝時，集合和設定資料會安裝在 Configuration Manager 主網站伺服器上。

-   **系統管理與監控伺服器**-**系統管理**與監控伺服器Windows伺服器，包含系統管理與監控網站及監控 Web 服務。 系統管理與監控網站是用來稽核活動，以及存取復原資料 (例如 BitLocker 修復金鑰) 。 **系統也會在**系統管理與監控伺服器上安裝自助入口網站。 入口網站可讓用戶端電腦上的使用者獨立登入網站，以取得修復金鑰 ，如果他們失去或忘記 BitLocker 密碼。 稽核報告也會安裝在系統管理與監控伺服器上。

-   **管理工作站** - **策略範本** 包含群組原則物件，這些群組原則物件定義 BitLocker 磁片磁碟機加密的 B0 或 10000000088 -19993-2013-19993-2013-19993-20 您可以在任何伺服器或工作站上安裝策略範本，但通常安裝在受伺服器或用戶端電腦支援的管理Windows工作站上。 工作站不需要是專用電腦。

-   **管理與管理用戶端****與 Configuration Manager 用戶端電腦**

    -   **此為管理管理管理**用戶端執行下列工作：

        -   使用群組原則物件來強制執行企業用戶端電腦的 BitLocker 加密。

        -   收集三種 BitLocker 資料磁碟機類型的修復金鑰：作業系統磁片磁碟機、固定資料磁碟機，以及 USB 磁片磁碟機 (移除) 資料。

        -   收集用戶端電腦的修復資訊和電腦資訊。

    -   **Configuration Manager Client** – Configuration Manager 用戶端可讓 Configuration Manager 收集用戶端電腦的硬體相容性資料，並可讓 Configuration Manager 報告合規性資訊。

## <a name="related-topics"></a>相關主題


[使用 MBAM 搭配 Configuration Manager](using-mbam-with-configuration-manager.md)

 

 





