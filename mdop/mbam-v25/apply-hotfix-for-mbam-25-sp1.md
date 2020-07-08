---
title: 在 MBAM 2.5 SP1 上套用 Hotfix
description: 在 MBAM 2.5 SP1 上套用 Hotfix
ms.author: ppriya-msft
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: 71f840ce4d57a0698289128f92b9d760ca14ddfc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810406"
---
# 在 MBAM 2.5 SP1 上套用 Hotfix
本主題描述針對 Microsoft BitLocker 管理和監控（MBAM） Server 2.5 SP1 應用修復程式的程式

### 在開始之前，請先下載 Microsoft BitLocker 管理和監控（MBAM） Server 2.5 SP1 的最新修復程式
[桌面優化套件](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> 如需有關修補程式版本的詳細資訊，請參閱[MBAM 版本圖表](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)。

#### 更新現有 MBAM 環境之 MBAM 伺服器的步驟 
1. 移除 MBAM server 功能（若要執行此動作，請開啟 [MBAM 伺服器設定] 工具，然後選取 [移除功能]）。
2. 從 [控制台] 中移除 [MDOP MBAM] |程式和功能。
3. 安裝 MBAM 2.5 SP1 RTM 伺服器元件。
4. 安裝 lastest MBAM 2.5 SP1 中的修補程式匯總。
5. 使用 MBAM 伺服器配置器設定 MBAM 功能。

#### 安裝新的 MBAM 2.5 SP1 server 修復程式的步驟
請參閱檔以瞭解[新的伺服器安裝](deploying-the-mbam-25-server-infrastructure.md)。
