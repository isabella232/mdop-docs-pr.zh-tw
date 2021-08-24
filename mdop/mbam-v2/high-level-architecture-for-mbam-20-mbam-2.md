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
ms.openlocfilehash: f19480b5797362e6e4119fff9a14afd9d5a74d98
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910498"
---
# <a name="high-level-architecture-for-mbam-20"></a>MBAM 2.0 的概要架構


Microsoft BitLocker 系統管理與監控 () 是一種用戶端/伺服器解決方案，可協助簡化 BitLocker 的部署與部署、改善 BitLocker 的合規性與報告，並降低支援成本。 Microsoft BitLocker 系統管理與監控包含本主題所述的功能。

Microsoft BitLocker 系統管理與監控可以部署在獨立拓撲中，或與 Microsoft System Center Configuration Manager 2007 或 Microsoft System Center 2012 Configuration Manager 整合的拓撲中。 本主題說明獨立拓撲的架構。 有關在整合式 Configuration Manager 拓撲中部署的資訊，請參閱在 [Configuration Manager](using-mbam-with-configuration-manager.md)中使用

下圖顯示由兩個伺服器和一個管理工作站所組成的生產環境的一個建議架構。 此架構最多支援 200，000 個的 200，000 個 。. 架構圖像中的伺服器功能和資料庫如下節所述，並列于建議您安裝之電腦或伺服器下。

**注意**  
單一伺服器架構應僅適用于測試環境。

 

![ibmm 2 雙伺服器部署拓撲。](images/mbam2-3-servers.gif)

## <a name="administration-and-monitoring-server"></a>系統管理與監控伺服器


此伺服器上已安裝下列功能：

-   **系統管理與監控伺服器**。 系統管理與監控伺服器功能會安裝在 Windows 伺服器上，並包含系統管理與監控網站，包括報告和技術支援中心入口網站，以及監控 Web 服務。

-   **自助入口網站**。 Self-Service入口網站會安裝在Windows伺服器上。 Self-Service入口網站可讓用戶端電腦上的使用者獨立登入網站，以便取得復原金鑰以復原鎖定的 BitLocker 音量。

## <a name="database-server"></a>資料庫伺服器


此伺服器上已安裝下列功能：

-   **復原資料庫**。 修復資料庫會安裝在Windows伺服器和支援的 Microsoft SQL Server。 此資料庫會儲存從 SQLM 用戶端電腦收集的修復資料。

-   **合規性和稽核資料庫**。 合規性和稽核資料庫會安裝在Windows伺服器和支援的 SQL Server。 此資料庫會儲存適用于 SQLM 用戶端電腦的合規性資料。 此資料主要用於 SSRS SQL Server Reporting Services (主機) 報表。

-   **合規性和稽核報告**。 合規性和稽核報告會安裝在Windows伺服器上，以及已安裝 SSRS SQL Server SSRS SQL Server Reporting Services (支援的) 實例。 這些報告提供您可從系統管理與監控網站或直接從 SSRS 伺服器存取的 IBMM 報告。

## <a name="management-workstation"></a>管理工作站


下列功能已安裝在管理工作站上，可以是Windows伺服器或用戶端電腦。

-   **策略範本**。 策略範本包含群組原則設定，可定義 BitLocker 磁片磁碟機加密的 B00 B0 B0 1000 -20100 -19993-19993-19993-20133- 您可以在任何伺服器或工作站上安裝策略範本，但通常安裝在管理工作站上，而管理工作站是伺服器或用戶端電腦Windows支援。 工作站不需要是專用電腦。

## <a name="mbam-client"></a><a href="" id="---------mbam-client"></a> 國際管理管理組織用戶端


在電腦上安裝了WINDOWS，具有下列特性：

-   使用群組原則來強制執行企業用戶端電腦的 BitLocker 磁片磁碟機加密。

-   收集三種 BitLocker 資料磁碟機類型的修復金鑰：作業系統磁片磁碟機、固定資料磁碟機，以及 USB 磁片磁碟機 (移除) 資料。

-   收集電腦的合規性資料，並將資料傳遞至報告系統。

## <a name="related-topics"></a>相關主題


[開始使用 MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)

 

 





