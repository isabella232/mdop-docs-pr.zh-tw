---
title: MED-V 1.0 版本資訊
description: MED-V 1.0 版本資訊
author: dansimp
ms.assetid: 006a3537-5c5b-43b5-8df8-4bf6ddd3cd2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 683056f768a3d547828996a9b191d58337c21ad6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811847"
---
# MED-V 1.0 版本資訊


## MED-V 的已知問題


本節提供有關 Microsoft 企業桌面虛擬化（MED-V）平臺一般問題的最新資訊。 這些問題不會出現在產品檔中，某些情況下，可能會矛盾現有的產品檔。 只要有可能，這些問題就會在後續版本中解決。

### 檔案下載不遵循 Web 重新導向規則

檔案下載不遵循 MED-V 工作區原則中設定的 Web 重新導向規則。

### 將主控台發佈的應用程式視窗展開到全螢幕時，它就會消失

如果您將主控台發佈的應用程式（例如 cmd.exe）視窗展開至全螢幕（在 [無縫整合] 模式中設定的 MED-V 工作區中），應用程式視窗可能會消失或無法回應。

### 在完整桌面圖案中工作時，電腦上的圖示位置不會儲存

在完整桌面圖案中工作時，桌面上圖示的手動位置變更不會儲存在 MED-V 工作區會話中。

### 同一個網域中不能有相同名稱的本機映射與測試影像

如果本機映射已加入網域，且系統管理員使用與測試映射相同的電腦名稱稱來建立新版本的同一個影像，則在測試映射加入網域時，[加入網域] 動作失敗或成功，並從網域移除本機影像。

### MED-V 不支援 Windows Aero 功能

MED-V 不支援 Windows Aero 功能（例如 Aero 翻轉3D）。

### 每個電腦只有一個 Windows 使用者可以使用管理主控台

MED-V 管理主控台只能由管理員和安裝管理應用程式的 Windows 使用者使用。

### MED-V 伺服器設定實用程式會在使用者內容下測試 Microsoft SQL Server 連線，而不是在 MED-V 伺服器服務內容下進行

MED-V 使用 MED-V 伺服器服務內容來收集來自 Microsoft SQL Server 報表資料庫的報表。 MED-V 伺服器設定實用程式會驗證資料庫並測試資料庫連線字串。 它不會驗證 MED-V Server 服務對資料庫的存取權。

 

 





