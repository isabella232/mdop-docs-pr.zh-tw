---
title: 部署 MBAM 2.0 伺服器基礎結構
description: 部署 MBAM 2.0 伺服器基礎結構
author: dansimp
ms.assetid: 52e68d94-e2b4-4b06-ae55-f900ea6cc59f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8aee322b9a1aacbf98ff8362e95e21c2dd3d289a
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910798"
---
# <a name="deploying-the-mbam-20-server-infrastructure"></a>部署 MBAM 2.0 伺服器基礎結構


適用于獨立拓撲的 Microsoft BitLocker (管理與監控) 管理與監控功能可在生產環境的兩台或多部伺服器上安裝不同的配置。 根據您的可縮放性需求，建議為生產環境的兩個伺服器。 只在測試環境中使用單一伺服器進行的  。 有關規劃 IBMM Server 功能部署之詳細資訊，請參閱[規劃適用于 IBMM 2.0 Server 部署 。](planning-for-mbam-20-server-deployment-mbam-2.md)

下圖顯示如何設定建議的雙伺服器 IBMM 部署範例。 此組配置在生產環境中最多支援 200，000 個的 200，000 個 。. 架構圖像中的伺服器功能和資料庫如下節所述，並列于建議您安裝之電腦或伺服器下。

![2 個雙伺服器部署拓撲。](images/mbam2-3-servers.gif)

## <a name="administration-and-monitoring-server"></a>系統管理與監控伺服器


此伺服器上已安裝下列功能：

-   **系統管理與監控伺服器**。 系統管理與監控伺服器功能會安裝在 Windows伺服器上，由技術支援中心網站和監控 Web 服務組成。

-   **自助入口網站**。 Self-Service入口網站會安裝在Windows伺服器上。 Self-Service入口網站可讓用戶端電腦上的使用者獨立登入網站，他們可以在這裡取得復原金鑰，以復原鎖定的 BitLocker 音量。

## <a name="database-server"></a>資料庫伺服器


此伺服器上已安裝下列功能：

-   **復原資料庫**。 修復資料庫會安裝在Windows伺服器和支援的 Microsoft SQL Server。 此資料庫會儲存從 SQLM 用戶端電腦收集的修復資料。

-   **合規性與稽核資料庫**。 合規性和稽核資料庫會安裝在Windows伺服器和支援的 SQL Server。 此資料庫會儲存適用于 SQLM 用戶端電腦的合規性資料。 此資料主要用於 SSRS SQL Server Reporting Services (主機) 報表。

-   **合規性和稽核報告**。 合規性和稽核報告會安裝在Windows伺服器上，以及已安裝 SSRS SQL Server SSRS SQL Server Reporting Services (支援的) 實例。 這些報告提供您可從服務台網站或直接從 SSRS 伺服器存取的 IBMM 報告。

## <a name="management-workstation"></a>管理工作站


下列功能已安裝在管理工作站上，可以是Windows伺服器或用戶端電腦。

-   **策略範本**。 策略範本包含定義 BITLocker 磁片磁碟機加密的一組群組原則 。. 您可以在任何伺服器或工作站上安裝策略範本，但通常安裝在管理工作站上，而管理工作站是伺服器或用戶端電腦Windows支援。 工作站不需要是專用電腦。

## <a name="mbam-client"></a><a href="" id="---------mbam-client"></a> 國際管理管理組織用戶端


在電腦上安裝了WINDOWS，具有下列特性：

-   使用群組原則來強制執行企業用戶端電腦的 BitLocker 磁片磁碟機加密。

-   收集三種 BitLocker 資料磁碟機類型的修復金鑰：作業系統磁片磁碟機、固定資料磁碟機，以及 USB 磁片磁碟機 (移除) 資料。

-   收集電腦的合規性資料，並將資料傳遞至報告系統。

## <a name="other-resources-for-deploying-mbam-20-server-features"></a>部署 IBMM 2.0 伺服器功能的其他資源


[部署 MBAM 2.0](deploying-mbam-20-mbam-2.md)

 

 





