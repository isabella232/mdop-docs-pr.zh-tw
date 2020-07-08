---
title: 使用 Application Virtualization 伺服器做為封裝管理解決方案
description: 使用 Application Virtualization 伺服器做為封裝管理解決方案
author: dansimp
ms.assetid: 41597355-e7bb-45e2-b300-7b1724419975
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2b81ed3ab6fa3a70fe4780904059091f22579d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800756"
---
# 使用 Application Virtualization 伺服器做為封裝管理解決方案


如果您沒有要部署應用程式虛擬化解決方案或不想要使用的 ESD 系統，您必須安裝一或多個應用程式虛擬化管理伺服器作為系統架構的核心。 應用程式虛擬化管理伺服器需要專用的伺服器電腦，且需要 Microsoft SQL Server 資料庫。 資料庫可以位於同一個伺服器上，或者可以在可在應用程式虛擬化管理伺服器（在高速局域網連線）上存取的企業資料庫伺服器上設定。 此外，您必須在應用程式虛擬化管理伺服器或指定的管理工作站上安裝 Microsoft Application Virtualization 管理主控台，而且您必須安裝 Microsoft Application Virtualization Management Web 服務，這也可以安裝在應用程式虛擬化管理伺服器或個別的 IIS 伺服器上。 應用程式虛擬化管理主控台是用來連線到應用程式虛擬化管理 Web 服務，讓系統管理員可以與應用程式虛擬化管理伺服器互動。

**記事** 應用程式的存取權是由 Active Directory 網域服務中的安全性群組所控制，因此您必須規劃一個處理常式，為每個虛擬化的應用程式設定安全性群組，以及管理每個群組中新增的使用者。 應用程式虛擬化管理伺服器管理員會將伺服器設定為使用這些 Active Directory 群組，然後伺服器就會根據 Active Directory 群組成員資格，自動控制對套件的存取權。

 

## 本節內容


<a href="" id="overview-of-the-application-virtualization-system-components"></a>[Application Virtualization 系統元件概觀](overview-of-the-application-virtualization-system-components.md)  
列出並描述 Microsoft Application Virtualization 管理系統的主要元件。

<a href="" id="publishing-virtual-applications-using-application-virtualization-management-servers"></a>[使用 Application Virtualization Management Server 發佈虛擬應用程式](publishing-virtual-applications-using-application-virtualization-management-servers.md)  
提供虛擬應用程式在應用程式虛擬化伺服器部署案例中發佈的方式的簡短概覽。

<a href="" id="planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation"></a>[在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)  
說明搭配使用應用程式虛擬化流程伺服器與您的應用程式虛擬化管理伺服器部署的可用選項。

## 相關主題


[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)

[規劃 Application Virtualization 系統部署](planning-for-application-virtualization-system-deployment.md)

 

 





