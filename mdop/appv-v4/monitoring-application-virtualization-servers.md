---
title: 監視 Application Virtualization 伺服器
description: 監視 Application Virtualization 伺服器
author: dansimp
ms.assetid: d84355ae-4fe4-41d9-ac3a-3eaa32d9a61f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a53c0c37ca609c701727a7f4e18019a9f20110ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800960"
---
# 監視 Application Virtualization 伺服器


若要簡化應用程式虛擬化（App-v）伺服器管理，您可以使用 System Center Operations Manager2007 管理套件。 此管理套件只支援應用程式虛擬化（App-v）4.5 伺服器;它不支援舊版伺服器版本。 管理套件可將 App V 伺服器可用性最大化，以處理 App-v 用戶端的要求。

## 狀態指示器


App-v 伺服器健康情況指示器以色彩標示。 這些色彩代表下列狀態值：

-   [無色彩] 表示伺服器執行沒有無法復原的錯誤。

-   黃色表示其中一個元件無法正常運作。 伺服器的整體功能已降級，但伺服器仍可供使用。

-   紅色表示伺服器無法使用且無法提供重要服務或與外部服務相依性進行通訊。

## 監視準則


管理套件會監視伺服器健康情況的下列幾個方面：

-   伺服器狀態-監視伺服器事件以驗證服務器是否提供其預期的服務。

-   資料儲存區存取：追蹤一或多個應用程式 V 管理伺服器存取並與 App-v 資料儲存區通訊的能力。

-   內容資料存取-監視 \\Content 目錄的存取權（可能是本機目錄或網路共用），以及讀取要求的檔案的功能。

-   安全性：使用 App-v 伺服器的憑證和安全通訊來報告錯誤。

-   用戶端要求處理-監視一或多個 App-v 伺服器處理的功能，並正確回應用戶端要求。 這些要求包括發佈諸如設定要求、套件載入要求，以及不順序要求等專案。

-   伺服器設定：檢查 App-v 伺服器的設定設定。 這些設定會將設定包含在 registry 和 App-v 資料儲存區中。

## 伺服器差異


App V 管理伺服器與 App-v 流式處理伺服器之間的主要差異如下：

-   App-v 管理伺服器可提供發佈、流式處理、管理及報表服務。 因此，管理套件可以管理 App-v Management Server 的其他方面，而不能在僅提供套件資料流程的 App-v 資料流程伺服器上管理。

-   App-v 流式處理伺服器沒有 App-v 資料儲存區，因此不會監視資料儲存區存取。 App-v 流式處理伺服器的設定資訊是在登錄中進行管理。

-   App-v 流式處理伺服器不使用 App-v Server 管理主控台介面;使用其他工具管理設定。

## 相關主題


[Application Virtualization 伺服器](application-virtualization-server.md)

 

 





