---
title: 在 MBAM 2.5 SP1 上套用 Hotfix
description: 在 MBAM 2.5 SP1 上套用 Hotfix
ms.author: dansimp
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: ea564d93a3eec6a46ec7d4c1be0f794abba9c93e
ms.sourcegitcommit: 8ecbf818a6ff2ddafd80b93614c01256484737ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "11014987"
---
# 在 MBAM 2.5 SP1 上套用 Hotfix
本主題描述在 MBAM) Server 2.5 SP1 中套用 Microsoft BitLocker 管理和監控 (的程式的處理常式

### 在開始之前，請先在 MBAM) Server 2.5 SP1 中下載 Microsoft BitLocker 管理和監視 (的最新修復程式
[桌面優化套件](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> 如需有關修補程式版本的詳細資訊，請參閱 [MBAM 版本圖表](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)。

#### 更新現有 MBAM 環境之 MBAM 伺服器的步驟 
1. 移除 MBAM server 功能 (執行此動作的方法是開啟 [MBAM 伺服器設定] 工具，然後選取 [移除功能]) 。
2. 從 [控制台] 中移除 [MDOP MBAM] |程式和功能。
3. 安裝 MBAM 2.5 SP1 RTM 伺服器元件。
4. 安裝 lastest MBAM 2.5 SP1 中的修補程式匯總。
5. 使用 MBAM 伺服器配置器設定 MBAM 功能。

#### 安裝新的 MBAM 2.5 SP1 server 修復程式的步驟
請參閱檔以瞭解 [新的伺服器安裝](deploying-the-mbam-25-server-infrastructure.md)。
