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
ms.openlocfilehash: 82914de48a5a5777f6ce4b50fe3e8af34dd82494
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910778"
---
# <a name="introduction-to-the-application-virtualization-security-guide"></a>應用程式虛擬化安全性指南簡介


本 Microsoft Application 虛擬化 (App-V) 安全指南提供指示給負責為 App-V 部署所選取之安全性功能的系統管理員。

**注意**  
本文不提供選擇特定安全性選項的指引。 這項資訊是在 App-V 安全性最佳做法白皮書中提供，提供于 <https://go.microsoft.com/fwlink/?LinkId=127120> 。

 

作為使用本指南的 App-V 系統管理員，您應該熟悉下列安全性相關技術：

-   Active Directory Domain Services

-   公用金鑰基礎結構 (PKI) 

-   網際網路通訊協定安全性 (IPsec) 

-   群組原則

-   Internet Information Services (IIS) 

## <a name="app-v-infrastructure-components"></a>APP-V 基礎結構元件


規劃增強的安全性 App-V 環境時，您可以考慮數種不同的基礎結構模型。

**注意**  
有關 App-V 基礎結構模型的資訊，請參閱下列檔：

-   [App-V 規劃與部署指南](https://go.microsoft.com/fwlink/?LinkId=122063)

-   [基礎結構規劃與設計指南系列](https://go.microsoft.com/fwlink/?LinkId=151986)

 

這些模型會使用下列圖例中描述的一些但可能並非全部的 App-V 元件。

![app-v 分支辦公室圖表。](images/appvbranchoffices.gif)

<a href="" id="application-virtualization--app-v--management-server"></a>應用程式虛擬化 (App-V) 管理伺服器  
App-V 管理伺服器會流式處理套件內容，併發布快捷方式和檔案類型關聯至 App-V 用戶端。 App-V 管理伺服器也支援使用中的升級、授權管理，以及可用來報告的資料庫。

<a href="" id="application-virtualization--app-v--streaming-server"></a>應用程式虛擬化 (App-V) 串流伺服器  
App-V 串流伺服器在分支辦公室等環境中託管串流至 App-V 用戶端的套件，而 App-V 管理伺服器的連接頻寬不足，無法將套件內容串流至用戶端。 串流伺服器僅包含串流功能，而且不會為您提供 App-V 管理主控台或 App-V 管理 Web 服務。

<a href="" id="application-virtualization--app-v--data-store"></a>應用程式虛擬化 (App-V) 資料存放區  
App-V 資料存放區在 SQL資料庫中，會保留與 App-V 基礎結構有關的資訊。 App-V 資料存放區的資訊包括所有應用程式記錄、應用程式指派，以及管理應用程式虛擬化環境的群組。

<a href="" id="application-virtualization--app-v--management-service"></a>應用程式虛擬化 (App-V) 管理服務  
App-V 管理服務會向應用程式虛擬化資料存放區傳達讀/寫要求。 此元件可以安裝在與 App-V 管理伺服器相同的電腦上，或安裝 IIS 的個別電腦上。

<a href="" id="application-virtualization--app-v--management-console"></a>應用程式虛擬化 (App-V) 管理主控台  
App-V 管理主控台是 App-V Server 系統管理中的管理單元管理公用程式。 此元件可以安裝在與 App-V Server 相同的電腦上，或安裝 MMC 3.0 和 .NET 2.0 的個別工作站上。

<a href="" id="application-virtualization--app-v--sequencer"></a>應用程式虛擬化 (App-V) 序程式  
App-V Sequencer 會監控並捕獲應用程式的安裝，並建立虛擬應用程式套件。 Sequencer 的輸出包含應用程式圖示、包含應用程式定義資訊的 OSD 檔案、套件清單檔案，以及包含應用程式內容檔案的 SFT 檔案。 您也可以選擇Windows安裝程式檔案來安裝套件，而不需要使用 App-V 基礎結構。

<a href="" id="application-virtualization--app-v--client"></a>應用程式虛擬化 (App-V) 用戶端  
App-V 用戶端安裝在 App-V 桌面用戶端電腦或 App-V 終端服務用戶端電腦上。 它提供虛擬應用程式套件的虛擬環境。 App-V 用戶端會管理套件串流至緩存、虛擬應用程式發佈重新更新，以及與應用程式虛擬化伺服器的互動。

 

 





