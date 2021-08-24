---
title: 設定 App-V 以使用安全管理
description: 設定 App-V 以使用安全管理
author: dansimp
ms.assetid: 4543fa81-c8cc-4b10-83b7-060778eb1349
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c95fab4b2b4f402df4ff0f82f2f346c9bd226e00
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910478"
---
# <a name="configuring-app-v-for-secure-administration"></a>設定 App-V 以使用安全管理


在保護系統管理作業重要的環境中，App-V 可讓 App-V Web 管理服務與 App-V 管理主控台之間的安全通訊。 由於管理服務是 Web 型應用程式，因此需要保護託管管理服務之 Web 服務器上 App-V Management Server 應用程式的安全。 如下圖所示，此套裝程式括使用 HTTPS 進行通訊，以及將 IIS 伺服器Windows整合驗證。

![app-v Web 服務網路組組。](images/appvmgmtwebservice.gif)

App-V Web 管理服務是在 IIS 上安裝為 Web 型應用程式。 若要讓 Web 管理服務支援 App-V 管理主控台與 Web 管理服務之間的安全 (SSL) 連接，您必須設定安裝 Web 管理服務的 IIS 伺服器，並設定 App-V 管理主控台。

## <a name="in-this-section"></a>在此區段


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[設定憑證以支援 APP-V Web 管理服務](configuring-certificates-to-support-the-app-v-web-management-service.md)  
提供有關建立憑證以支援 SSL 型連接的實用資訊，協助保護 App-V Web 管理服務的通訊安全。

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[如何安裝及設定 APP-V 管理主控台以用於更安全的環境](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
提供使用安全連線來連接 App-V Web 管理服務的逐步程式。

 

 





