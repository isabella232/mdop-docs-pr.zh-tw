---
title: App-V 4.6 版本資訊
description: App-V 4.6 版本資訊
author: dansimp
ms.assetid: a3eba129-edac-48bf-a933-3bf43a9873e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9eee3c309a927a72155dec707d8dd95f43e90fb9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809314"
---
# App-V 4.6 版本資訊


若要搜尋這些版本筆記，請按 CTRL + F。

**重要** 安裝 Microsoft Application Virtualization （App-v）管理系統之前，請先閱讀這些版本資訊。 這些版本資訊包含成功安裝應用程式虛擬化（app-v）4.6 所需的資訊。 此檔包含產品檔中不提供的資訊。 如果這些版本資訊與其他 App-v 檔之間有差異，最新的變更應該視為權威性。

 

## 防範安全性漏洞與病毒


若要協助防範安全性漏洞和病毒，請務必為任何要安裝的新軟體安裝最新的可用安全更新。 如需詳細資訊，請參閱[Microsoft 安全性網站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。

## Application Virtualization 4.6 的已知問題


本節提供有關 Microsoft 應用程式虛擬化（App-v）4.6 問題的最新資訊。 這些問題不會出現在產品檔中，某些情況下，可能會矛盾現有的產品檔。 只要有可能，這些問題就會在後續版本中解決。

### 執行 App-v 4.5 排序器所產生的 Windows 安裝程式檔案時發生載入/安裝錯誤

執行 App-v 4.5 排序器所產生的 Windows 安裝程式檔案，會在嘗試在 App-v 4.6 用戶端上執行時產生載入/安裝錯誤。 您會看到下列訊息：「此套件需要 Microsoft Application Virtualization Client 4.5 或更新版本」。 請使用下列因應措施。

使用 App-v 4.5 SP1 排序器或 App-v 4.6 排序器 WORKAROUNDOpen 舊的套件，並為套件產生新的 .msi 檔案。

**記事** 或者，在命令提示字元中，App-v 排序器會使用 */OPEN*和 */MSI*參數來產生新的 .msi 檔案，例如 `SFTSequencer /Open:”package.sprj” /MSI` 。 如需詳細資訊，請參閱[如何使用命令列升級虛擬應用程式](how-to-upgrade-a-virtual-application-by-using-the-command-line.md)。

 

### 版本資訊版權資訊

本檔是以「原樣」提供。 本文件中提供的資訊及檢視 (包括 URL 及其他網際網路網站參照) 如有變更，恕不另行通知。 您會承擔使用它的風險。

本文中描述的一些範例只提供給說明，且是虛構的。沒有任何實際的關聯或連線是有意或無意的。

本文件不為您提供對任何 Microsoft 產品中的任何智慧財產的法定權利。 您可以複製本文件供內部參照之用。 您可以針對內部、參考目的來修改這份檔。



Microsoft、Active Directory、ActiveSync、ActiveX、Excel、SQL Server、Windows、Windows PowerShell、Windows Server 和 Windows Vista 是 Microsoft 公司群組的商標。

所有其他商標都是其各自擁有者的財產。

 

 





