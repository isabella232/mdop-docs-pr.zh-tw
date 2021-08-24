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
ms.openlocfilehash: d06c7bd801a9dd63916d310af75e88a307e7226a
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910408"
---
# <a name="high-level-architecture-for-mbam-10"></a>MBAM 1.0 的高階架構


Microsoft BitLocker 系統管理與監控 () 是一種用戶端/伺服器資料加密解決方案，可協助簡化 BitLocker 的部署與部署、改善 BitLocker 合規性與報告，並降低支援成本。 本主題中所描述的功能為 ：：。

此外，還有一個影片提供一個概觀的  ：。 如要詳細資訊，請參閱 [管理及架構概觀](https://go.microsoft.com/fwlink/p/?LinkId=258392)。

## <a name="architecture-overview"></a>架構概觀


下圖顯示的是該架構。 系統會顯示單一伺服器的 IBMM 部署拓撲，以介紹該 IBMM 功能。 不過，只有實驗室環境才建議使用此此 LABM 部署拓撲。

**注意**  
針對生產部署，建議使用至少三部電腦型的可進行區位管理部署拓撲。 有關 IBMM 部署拓撲的更多相關資訊，請參閱 [部署 IBMM 1.0 Server 基礎結構](deploying-the-mbam-10-server-infrastructure.md)。

 

![管理單一伺服器部署拓撲。](images/mbam-1-server.jpg)

1.  **系統管理與監控伺服器**。 此管理與監控伺服器會安裝在 Windows伺服器上，並主管該管理與管理網站及監控 Web 服務。 用於判斷企業合規性狀態、稽核活動、管理硬體功能，以及存取修復資料 ，例如 BitLocker 修復金鑰的 。. 系統管理與監控伺服器會連接到下列資料庫和服務：

    -   修復與硬體資料庫。 修復與硬體資料庫會安裝在Windows伺服器上，並且支援SQL Server實例。 此資料庫會儲存從 SQLM 用戶端電腦收集的修復資料和硬體資訊。

    -   合規性與稽核資料庫。 合規性和稽核資料庫會安裝在Windows且支援SQL Server實例。 此資料庫會儲存適用于 SQLM 用戶端電腦的合規性資料。 此資料主要用於由 SSRS SQL Server Reporting Services (託管) 。

    -   合規性和稽核報告。 合規性和稽核報告會安裝在Windows型伺服器上，且支援SQL Server安裝 SSRS 功能的實例。 這些報告提供 Microsoft BitLocker 系統管理與監控報告。 這些報告可以從專案管理與管理網站存取，或直接從 SSRS Server 存取。

2.  **。** Microsoft BitLocker 系統管理與監控用戶端會執行下列工作：

    -   使用群組原則來強制執行企業用戶端電腦的 BitLocker 加密。

    -   收集三種 BitLocker 資料磁碟機類型的修復金鑰：作業系統磁片磁碟機、固定資料磁碟機，以及 USB 磁片磁碟機 (移除) 資料。

    -   收集用戶端電腦的修復資訊和硬體資訊。

    -   收集電腦的合規性資料，並將資料傳遞至報告系統。

3.  **策略範本**。 在支援的 WINDOWS 伺服器或用戶端電腦上安裝的就是該 B0 的 B0 群組原則Windows範本。 此範本用於指定 BitLocker 磁片磁碟機加密的 "慢化管理」的實現設定。

## <a name="related-topics"></a>相關主題


[開始使用 MBAM 1.0](getting-started-with-mbam-10.md)

 

 





