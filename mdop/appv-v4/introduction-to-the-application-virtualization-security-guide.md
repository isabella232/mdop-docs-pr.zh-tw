---
title: 應用程式虛擬化安全性指南簡介
description: 應用程式虛擬化安全性指南簡介
author: dansimp
ms.assetid: 50e1d220-7a95-45b8-933b-3dadddebe26f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4b41c65c5ad753aa606d47d2eafe4a28e035cc4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800985"
---
# 應用程式虛擬化安全性指南簡介


此 Microsoft Application Virtualization （App-v） security guide （應用程式-V）安全性指南為負責設定 App V 部署所選取的安全性功能的管理員提供指示。

**記事** 本檔不提供選擇特定安全性選項的指導方針。 該資訊是在 App-V 安全性最佳做法中提供的白皮書中提供 <https://go.microsoft.com/fwlink/?LinkId=127120> 。

 

如果您是使用本指南的 App-v 系統管理員，您應該熟悉下列與安全性相關的技術：

-   Active Directory Domain Services

-   公開金鑰基礎結構（PKI）

-   網際網路通訊協定安全性（IPsec）

-   群組原則

-   網際網路資訊服務（IIS）

## APP-V 基礎結構元件


規劃增強的安全性 App V 環境時，您可以考慮數種不同的基礎結構模型。

**記事** 如需 App V 基礎結構模型的詳細資訊，請參閱下列檔：

-   [App-v 規劃與部署指南](https://go.microsoft.com/fwlink/?LinkId=122063)

-   [基礎結構規劃與設計指南系列](https://go.microsoft.com/fwlink/?LinkId=151986)

 

這些模型會利用部分（但不是所有）在下圖中描述的 App-v 元件。

![app-v 分支辦公室圖表](images/appvbranchoffices.gif)

<a href="" id="application-virtualization--app-v--management-server"></a>應用程式虛擬化（App-v）管理伺服器  
App-v 管理伺服器會流式處理套件內容，並將快捷方式和檔案類型關聯發佈到 App-v 用戶端。 App-v 管理伺服器也支援 [作用中升級]、[授權管理]，以及可用於報告的資料庫。

<a href="" id="application-virtualization--app-v--streaming-server"></a>應用程式虛擬化（App-v）流式處理伺服器  
App-v 流式處理伺服器會將用於流式處理的套件託管至應用程式中的 App-v 用戶端（例如分支辦公室），在此情況下，到 App-v 管理伺服器的連線頻寬不足以流式套件內容傳送給用戶端。 流式處理伺服器只包含流式處理功能，並不提供 App-v 管理主控台或 App-v Management Web 服務。

<a href="" id="application-virtualization--app-v--data-store"></a>應用程式虛擬化（App-v）資料存放區  
SQL 資料庫中的 App-v 資料儲存區會保留與 App-v 基礎結構相關的資訊。 App-v 資料存放區中的資訊包含所有應用程式記錄、應用程式指派，以及管理應用程式虛擬化環境的群組。

<a href="" id="application-virtualization--app-v--management-service"></a>應用程式虛擬化（App-v）管理服務  
App-v 管理服務會將讀/寫要求傳達給應用程式虛擬化資料存放區。 此元件可以安裝在與 App-v 管理伺服器相同的電腦上，或安裝在裝有 IIS 的個別電腦上。

<a href="" id="application-virtualization--app-v--management-console"></a>應用程式虛擬化（App-v）管理主控台  
App-v 管理主控台是 App-v Server 管理的管理單元管理公用程式。 此元件可以安裝在應用程式 V 伺服器所在的電腦上，或安裝在裝有 MMC 3.0 和的個別工作站上。已安裝 NET 2.0。

<a href="" id="application-virtualization--app-v--sequencer"></a>應用程式虛擬化（App-v） Sequencer  
App-v 排序器會監視並捕獲應用程式的安裝，並建立虛擬應用程式套件。 排序器的輸出包含應用程式圖示、包含應用程式定義資訊的 OSD 檔案、套件資訊清單檔案，以及包含應用程式內容檔案的 SFT 檔案。 或者，您可以建立 Windows 安裝程式檔案來安裝套件，而不需要使用 App-v 基礎結構。

<a href="" id="application-virtualization--app-v--client"></a>應用程式虛擬化（App-v）用戶端  
App v 用戶端安裝在 App-v Desktop 用戶端電腦或 App-v 終端服務用戶端電腦上。 它提供虛擬應用程式套件的虛擬環境。 App-v 用戶端可將套件資料流程管理到快取、虛擬應用程式發佈重新整理，以及與應用程式虛擬化伺服器互動。

 

 





