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
ms.openlocfilehash: 22a69fe8f6853c02a818bb026b36771cd09632f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810748"
---
# 部署 MBAM 2.0 伺服器基礎結構


您可以在生產環境中的兩個或多個伺服器上，將獨立拓朴的 Microsoft BitLocker 管理與監控（MBAM）伺服器功能安裝在不同的配置中。 根據您的可伸縮性需求而定，建議的配置是針對生產環境的兩個伺服器。 僅在測試環境中使用單一伺服器進行 MBAM 安裝。 如需規劃 MBAM Server 功能部署的詳細資訊，請參閱[MBAM 2.0 Server 部署規劃](planning-for-mbam-20-server-deployment-mbam-2.md)。

下圖顯示您可以如何設定建議的雙伺服器 MBAM 部署的範例。 此設定在生產環境中最多可支援 200000 MBAM 用戶端。 體系結構中的伺服器功能和資料庫會在下一節中說明，並列在電腦或伺服器（我們建議您安裝它們）底下。

![mbam 2 2-伺服器部署拓朴](images/mbam2-3-servers.gif)

## 管理和監控伺服器


此伺服器上已安裝下列功能：

-   **管理和監控伺服器**。 系統會在 Windows Server 上安裝 [管理和監控伺服器] 功能，並由技術支援網站和監視 web 服務組成。

-   **自助入口網站**。 自助入口網站已安裝在 Windows 伺服器上。 自助式入口網站可讓用戶端電腦上的使用者能夠獨立地登入網站，讓他們可以取得修復金鑰來復原鎖定的 BitLocker 卷。

## 資料庫伺服器


此伺服器上已安裝下列功能：

-   [**恢復資料庫**]。 已在 Windows server 和支援的 Microsoft SQLServer 實例上安裝復原資料庫。 此資料庫儲存從 MBAM 用戶端電腦收集的復原資料。

-   **合規性和審核資料庫**。 合規性與審計資料庫是安裝在 Windows server 和支援的 SQLServer 實例上。 此資料庫儲存 MBAM 用戶端電腦的合規性資料。 此資料主要用於 SQL Server Reporting Services （SSRS）主機的報表。

-   **合規性和審核報告**。 合規性和審核報告會安裝在 Windows server 上，以及已安裝 SQL Server Reporting Services （SSRS）功能的 SQLServer 實例支援。 這些報表提供 MBAM 報表，您可以從技術支援網站或從 SSRS 伺服器直接存取。

## 管理工作站


下列功能已安裝在管理工作站（可以是 Windows server 或用戶端電腦）上。

-   **原則範本**。 原則範本由定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的群組原則所組成。 您可以在任何伺服器或工作站上安裝此原則範本，但通常會將它安裝在管理工作站上（這是受支援的 Windows server 或用戶端電腦）。 工作站不一定是專用電腦。

## <a href="" id="---------mbam-client"></a> MBAM 用戶端


MBAM 用戶端已安裝在 Windows 電腦上，且具有下列特性：

-   使用群組原則，強制企業中用戶端電腦的 BitLocker 磁碟機加密。

-   收集三個 BitLocker 資料磁片磁碟機類型的復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動資料（USB）硬碟。

-   收集電腦的規範資料，並將資料傳遞到報告系統。

## 部署 MBAM 2.0 Server 功能的其他資源


[部署 MBAM 2.0](deploying-mbam-20-mbam-2.md)

 

 





