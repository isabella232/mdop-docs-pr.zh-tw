---
title: MBAM 1.0 的高階架構
description: MBAM 1.0 的高階架構
author: dansimp
ms.assetid: b1349196-88ed-4d6c-8a1d-998f18127b6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de3529fdb565859fcc212d1a9a614ac4ef4b183e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811036"
---
# MBAM 1.0 的高階架構


Microsoft BitLocker 管理和監控（MBAM）是一種用戶端/伺服器資料加密解決方案，可協助您簡化 BitLocker 的預配及部署、改善 BitLocker 合規性與報告，並減少支援成本。 MBAM 包含本主題中所述的功能。

此外，還有一個影片，提供 MBAM 架構和 MBAM 設定的概覽。 如需詳細資訊，請參閱[MBAM 部署與架構概述](https://go.microsoft.com/fwlink/p/?LinkId=258392)。

## 架構概述


下圖顯示 MBAM 結構。 會顯示單一伺服器 MBAM 部署拓朴，以介紹 MBAM 的功能。 不過，建議僅針對實驗室環境使用此 MBAM 部署拓撲。

**記事** 針對生產部署，建議至少使用三台電腦 MBAM 部署拓撲。 如需 MBAM 部署拓撲的詳細資訊，請參閱[部署 MBAM 1.0 伺服器基礎結構](deploying-the-mbam-10-server-infrastructure.md)。

 

![mbam 單一伺服器部署拓朴](images/mbam-1-server.jpg)

1.  **管理和監控伺服器**。 MBAM 管理和監視伺服器已安裝在 Windows 伺服器上，且託管 MBAM 管理和管理網站及監視 web 服務。 MBAM 管理和管理網站是用來判斷企業合規性狀態、審核活動、管理硬體功能，以及存取復原資料（例如 BitLocker 復原金鑰）。 管理和監視伺服器會連接到下列資料庫和服務：

    -   [復原] 和 [硬體資料庫]。 在 Windows 版伺服器和支援的 SQLServer 實例上，會安裝恢復和硬體資料庫。 此資料庫儲存從 MBAM 用戶端電腦收集的復原資料和硬體資訊。

    -   合規性和審核資料庫。 合規性與審計資料庫已安裝在 Windows server 和支援的 SQLServer 實例上。 此資料庫儲存 MBAM 用戶端電腦的合規性資料。 此資料主要用於由 SQL Server Reporting Services （SSRS）託管的報表。

    -   合規性和審核報告。 合規性和審核報告會安裝在 Windows 版伺服器上，且已安裝 SSRS 功能的支援 SQLServer 實例。 這些報告提供 Microsoft BitLocker 管理和監控報告。 您可以從 MBAM 管理和管理網站或直接從 SSRS 伺服器存取這些報告。

2.  **MBAM 用戶端**]。 Microsoft BitLocker 管理和監視用戶端會執行下列工作：

    -   使用群組原則，在企業中強制執行用戶端電腦的 BitLocker 加密。

    -   收集三個 BitLocker 資料磁片磁碟機類型的復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動資料（USB）硬碟。

    -   收集用戶端電腦的恢復資訊和硬體資訊。

    -   收集電腦的規範資料，並將資料傳遞到報告系統。

3.  **原則範本**。 MBAM 群組原則範本是安裝在支援的 Windows 版伺服器或用戶端電腦上。 這個範本是用來指定 BitLocker 磁片磁碟機加密的 MBAM 實現設定。

## 相關主題


[開始使用 MBAM 1.0](getting-started-with-mbam-10.md)

 

 





