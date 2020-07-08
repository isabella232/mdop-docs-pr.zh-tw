---
title: 從 MBAM 2.5 升級至 MBAM 2.5 SP1 服務版本更新
author: dansimp
ms.author: ksharma
manager: miaposto
audience: ITPro
ms.topic: article
ms.prod: w10
ms.localizationpriority: Normal
ms.openlocfilehash: 372822e1ec049871c62af9f429290b88bbfac949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800176"
---
# 從 MBAM 2.5 升級至 MBAM 2.5 SP1 服務版本更新

本文提供逐步指示，以升級 Microsoft BitLocker 管理和監控（MBAM）2.5，以 MBAM 2.5 Service Pack 1 （SP1）搭配[Microsoft 桌面優化套件（MDOP），在獨立設定中可能會2019服務更新](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)。

在本指南中，我們將使用雙伺服器設定。 一台伺服器將是執行 Microsoft SQL Server 2016 的資料庫伺服器。 這個伺服器將裝載 MBAM 資料庫與報告。 另一台伺服器將是 Windows Server 2012 R2 web 伺服器。 這個伺服器將主持「管理和監控」和「自助服務入口網站」。

## 準備升級 MBAM 2.5 SP1

### 瞭解您環境中的 MBAM 伺服器

1. SQL Server 資料庫引擎：託管 MBAM 資料庫的伺服器。
2. SQL Server Reporting Services：託管 MBAM 報表的伺服器。
3. 網際網路 Information Services （IIS） web 伺服器：託管 MBAM Web 應用程式和 MBAM 服務的伺服器。
4. 可選Microsoft System Center Configuration Manager 主要網站伺服器：此伺服器上執行的 MBAM 設定應用程式，可將 MBAM 報表與 Configuration Manager 整合。 然後，這些報告就會與 Configuration Manager SQL Server Reporting Services （SSRS）實例上的現有 Configuration Manager 報告合併。

### 識別服務帳戶、群組、伺服器名稱和報告 URL

1. 找出 IIS web 伺服器所用的 MBAM 應用程式池服務帳戶，以讀取並將資料寫入 MBAM 的資料庫。
2. 找出在 MBAM web 功能配置和報告 web 服務 URL 期間所使用的群組。
3. 找出 SQL Server 名稱和實例名稱。 觀看這段影片以深入瞭解。

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ANP1]

4. 找出用來從合規性和審核資料庫讀取合規性資料的 SQL Server Reporting Services 帳戶。 觀看這段影片以深入瞭解。

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALdZ]

## 將 MBAM 基礎結構升級至最新版本

MBAM Server 基礎結構的安裝或升級總是依下列循序執行：

- SQL Server 資料庫引擎：資料庫
- SQL Server Reporting Services：報表
- Web 服務器： Web 應用程式
- SCCM Server：適用的 SCCM 整合報表
- 用戶端： MBAM 代理程式或用戶端更新
- 群組原則範本：使用新的範本更新現有的群組原則，並啟用現有 MBAM 組原則上的新設定

> [!NOTE]
> 我們建議您在執行升級前，先建立 MBAM 資料庫的完整資料庫備份。

### 升級 MBAM SQL Server

觀看這段影片，瞭解如何升級 MBAM SQL Server：

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALew]

### 升級 MBAM Web 服務器

觀看這段影片，瞭解如何升級 MBAM Web 服務器：

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALex]

## 詳細資訊

如需有關 MBAM 2.5 SP1 中已知問題的詳細資訊，請參閱[MBAM 2.5 SP1 的版本](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/release-notes-for-mbam-25-sp1)資訊。
