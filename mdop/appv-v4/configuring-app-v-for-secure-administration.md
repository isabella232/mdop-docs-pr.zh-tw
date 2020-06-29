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
ms.openlocfilehash: de70c1df734bbf1168fd7dacf9410d3451a8a3c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809033"
---
# 設定 App-V 以使用安全管理


在加強管理作業安全的環境中，App V 可提供 App-v Web 管理服務與 App-v 管理主控台之間的安全通訊。 由於管理服務是以 Web 為基礎的應用程式，因此需要在託管管理服務的網頁伺服器上保護 App-v Management Server 應用程式。 如下圖所示，此套裝程式括使用 HTTPS 進行通訊，並將 IIS 伺服器設定為只允許 Windows 整合驗證。

![app-v web 服務網路設定](images/appvmgmtwebservice.gif)

App-v Web 管理服務是在 IIS 上以 Web 型應用程式的形式安裝。 若要在應用程式 V 管理主控台與 Web 管理服務之間支援安全（SSL）連線的 Web 管理服務，您必須設定安裝 Web 管理服務的 IIS 伺服器，並設定 App-v 管理主控台。

## 本節內容


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[設定憑證以支援 APP-V Web 管理服務](configuring-certificates-to-support-the-app-v-web-management-service.md)  
提供有關將憑證設定為支援 SSL 連線的實用資訊，以協助您安全地與 app-v Web 管理服務進行通訊。

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[如何安裝及設定 APP-V 管理主控台以用於更安全的環境](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
提供透過安全連線連接到 App-v Web 管理服務的逐步程式。。

 

 





