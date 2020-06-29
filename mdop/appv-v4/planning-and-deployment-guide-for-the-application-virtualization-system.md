---
title: 應用程式虛擬化系統的規劃與部署指南
description: 應用程式虛擬化系統的規劃與部署指南
author: dansimp
ms.assetid: 6c012e33-9ac6-4cd8-84ff-54f40973833f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10bcac26fddae2f0e5826dbd7335adda06d3987e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800923"
---
# 應用程式虛擬化系統的規劃與部署指南


Microsoft Application Virtualization 管理提供將應用程式提供給最終使用者電腦的功能，而不需要直接在那些電腦上安裝應用程式。 您可以透過稱為*應用程式順序的程式*來進行這項工作，這可讓每個應用程式在自己的用戶端電腦上獨立的虛擬環境中執行。 順序化的應用程式彼此隔離，以消除應用程式衝突，但仍可與用戶端電腦互動。

應用程式虛擬化用戶端是應用程式虛擬化系統元件，可讓使用者在應用程式發佈到電腦之後，與應用程式互動。 用戶端管理虛擬化應用程式在每個電腦上執行的虛擬環境。 在電腦上安裝用戶端之後，您必須透過稱為*發佈*的程式，將應用程式提供給電腦，讓使用者能夠執行虛擬應用程式。 發佈程式會將虛擬應用程式圖示與電腦上的快捷方式放在電腦上（通常位於 Windows 桌面或 [**開始**] 功能表上），而且也會將套件定義及檔案類型關聯資訊放在電腦上。 發佈也會將應用程式套件內容提供給最終使用者的電腦。

虛擬應用程式套件內容可以放置在一或多個應用程式虛擬化伺服器上，讓它可以根據需要流入用戶端，並在本機上緩存。 檔案伺服器和 Web 服務器也可以用來做為流式伺服器，或者內容可以直接放在最終使用者的電腦上，例如，如果您使用的是電子軟體發佈系統（例如 Microsoft 端點設定管理員）。 在多重伺服器的實現中，維護封裝內容並在所有流式處理伺服器上保持在最新狀態，都需要綜合的套件管理解決方案。 視貴組織的規模而定，您可能需要有許多虛擬應用程式可供整個世界各地的使用者存取。 管理套件，確保所有使用者都能存取適當的應用程式，以及他們需要存取這些專案的時間，因此是必不可少的需求。

應用程式虛擬化規劃與部署指南提供的資訊可協助您更清楚地瞭解及部署 Microsoft Application Virtualization 應用程式及其元件。 它也提供實現主要部署案例的逐步程式。

## 本節內容


<a href="" id="planning-for-application-virtualization-system-deployment"></a>[規劃 Application Virtualization 系統部署](planning-for-application-virtualization-system-deployment.md)  
提供規劃應用程式虛擬化系統的實施與部署所需的指導方針。

<a href="" id="application-virtualization-deployment-and-upgrade-considerations"></a>[Application Virtualization 部署與升級考量](application-virtualization-deployment-and-upgrade-considerations.md)  
提供安裝各種應用程式虛擬化元件以及升級資訊的硬體和軟體需求的相關資訊。

<a href="" id="electronic-software-distribution-based-scenario"></a>[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)  
提供有關使用電子軟體發佈（ESD）系統部署應用程式虛擬化的資訊。

<a href="" id="application-virtualization-server-based-scenario"></a>[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)  
提供有關使用應用程式虛擬化管理伺服器部署應用程式虛擬化的資訊。

<a href="" id="stand-alone-delivery-scenario-for-application-virtualization-clients"></a>[Application Virtualization Client 的獨立傳遞案例](stand-alone-delivery-scenario-for-application-virtualization-clients.md)  
說明如何在獨立模式中部署應用程式虛擬化，而不使用 ESD 或伺服器資源。

<a href="" id="application-virtualization-reference"></a>[Application Virtualization 參考資料](application-virtualization-reference.md)  
包含有關安裝與管理系統元件的詳細技術參考資料。

 

 





