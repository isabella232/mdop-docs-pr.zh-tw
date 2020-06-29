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
# <span data-ttu-id="30401-103">設定 App-V 以使用安全管理</span><span class="sxs-lookup"><span data-stu-id="30401-103">Configuring App-V for Secure Administration</span></span>


<span data-ttu-id="30401-104">在加強管理作業安全的環境中，App V 可提供 App-v Web 管理服務與 App-v 管理主控台之間的安全通訊。</span><span class="sxs-lookup"><span data-stu-id="30401-104">In an environment where securing administrative operations is important, App-V allows for secure communication between the App-V Web Management Service and the App-V Management Console.</span></span> <span data-ttu-id="30401-105">由於管理服務是以 Web 為基礎的應用程式，因此需要在託管管理服務的網頁伺服器上保護 App-v Management Server 應用程式。</span><span class="sxs-lookup"><span data-stu-id="30401-105">Because the Management Service is a Web-based application, it requires securing the App-V Management Server application on the Web server that hosts the Management Service.</span></span> <span data-ttu-id="30401-106">如下圖所示，此套裝程式括使用 HTTPS 進行通訊，並將 IIS 伺服器設定為只允許 Windows 整合驗證。</span><span class="sxs-lookup"><span data-stu-id="30401-106">As shown in the following illustration, this process includes using HTTPS for communication and configuring the IIS server to allow only Windows Integrated Authentication.</span></span>

![app-v web 服務網路設定](images/appvmgmtwebservice.gif)

<span data-ttu-id="30401-108">App-v Web 管理服務是在 IIS 上以 Web 型應用程式的形式安裝。</span><span class="sxs-lookup"><span data-stu-id="30401-108">The App-V Web Management Service is installed as a Web-based application on IIS.</span></span> <span data-ttu-id="30401-109">若要在應用程式 V 管理主控台與 Web 管理服務之間支援安全（SSL）連線的 Web 管理服務，您必須設定安裝 Web 管理服務的 IIS 伺服器，並設定 App-v 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="30401-109">For the Web Management Service to support secure (SSL) connections between the App-V Management Console and the Web Management Service, you will need to configure the IIS server where the Web Management Service is installed and configure the App-V Management Console.</span></span>

## <span data-ttu-id="30401-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="30401-110">In This Section</span></span>


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[<span data-ttu-id="30401-111">設定憑證以支援 APP-V Web 管理服務</span><span class="sxs-lookup"><span data-stu-id="30401-111">Configuring Certificates to Support the App-V Web Management Service</span></span>](configuring-certificates-to-support-the-app-v-web-management-service.md)  
<span data-ttu-id="30401-112">提供有關將憑證設定為支援 SSL 連線的實用資訊，以協助您安全地與 app-v Web 管理服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="30401-112">Provides helpful information about configuring certificates to support SSL-based connections, to help secure communication for the App-V Web Management Service.</span></span>

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[<span data-ttu-id="30401-113">如何安裝及設定 APP-V 管理主控台以用於更安全的環境</span><span class="sxs-lookup"><span data-stu-id="30401-113">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
<span data-ttu-id="30401-114">提供透過安全連線連接到 App-v Web 管理服務的逐步程式。。</span><span class="sxs-lookup"><span data-stu-id="30401-114">Provides a step-by-step procedure for connecting to an App-V Web Management Service by using a secure connection.</span></span>

 

 





