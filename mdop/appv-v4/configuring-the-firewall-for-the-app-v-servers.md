---
title: 設定 App-V 伺服器所需的防火牆
description: 設定 App-V 伺服器所需的防火牆
author: dansimp
ms.assetid: f779c450-6c6f-46a8-ac66-5e82e0689d55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92db727eb060546ab71f2c647f2d89b662be5c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808984"
---
# <span data-ttu-id="1248c-103">設定 App-V 伺服器所需的防火牆</span><span class="sxs-lookup"><span data-stu-id="1248c-103">Configuring the Firewall for the App-V Servers</span></span>


<span data-ttu-id="1248c-104">安裝 Microsoft Application Virtualization （App-v）管理伺服器或流式處理伺服器並將其設定為使用 RTSP 或 RTSPS 通訊協定後，您必須建立 App-v 程式的防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="1248c-104">After you install the Microsoft Application Virtualization (App-V) Management Server or Streaming Server and configure it to use the RTSP or RTSPS protocol, you must create firewall exceptions for the App-V programs.</span></span>

## <span data-ttu-id="1248c-105">設定應用程式虛擬化管理伺服器的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="1248c-105">Configuring Firewall Exceptions for Application Virtualization Management Server</span></span>


<span data-ttu-id="1248c-106">針對**sghwdsptr.exe**和**sghwsvr.exe**建立防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="1248c-106">Create a firewall exception for **sghwdsptr.exe** and **sghwsvr.exe**.</span></span> <span data-ttu-id="1248c-107">這些程式可在32位作業系統上的 [C:\\program files Files\\Microsoft System Center App Virt 管理 Server\\App Virt Management Server\\bin] 中找到。</span><span class="sxs-lookup"><span data-stu-id="1248c-107">These programs are found in the folder C:\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Server\\bin on a 32-bit operating system.</span></span> <span data-ttu-id="1248c-108">如果您使用的是64位作業系統版本，則資料夾位於 [C:\\program files Files （x86）] \\Microsoft System Center App Virt 管理 Server\\App Virt Management Server\\bin。</span><span class="sxs-lookup"><span data-stu-id="1248c-108">If you are using a 64-bit operating system version, the folder is located under C:\\Program Files (x86)\\Microsoft System Center App Virt Management Server\\App Virt Management Server\\bin.</span></span>

## <span data-ttu-id="1248c-109">設定應用程式虛擬化流程伺服器的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="1248c-109">Configuring Firewall Exceptions for Application Virtualization Streaming Server</span></span>


<span data-ttu-id="1248c-110">針對**sglwdsptr.exe**和**sglwsvr.exe**建立防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="1248c-110">Create a firewall exception for **sglwdsptr.exe** and **sglwsvr.exe**.</span></span> <span data-ttu-id="1248c-111">這些程式位於32位作業系統上的 [C:\\program files Files\\Microsoft System Center] App Virt 資料流程 Server\\App Virt 資料流程 Server\\bin。</span><span class="sxs-lookup"><span data-stu-id="1248c-111">These programs are found in the folder C:\\Program Files\\Microsoft System Center App Virt Streaming Server\\App Virt Streaming Server\\bin on a 32-bit operating system.</span></span> <span data-ttu-id="1248c-112">如果您使用的是64位作業系統版本，則資料夾位於 [C:\\program files Files （x86）] \\Microsoft System Center App Virt 串流 Server\\App Virt 串流 Server\\bin。</span><span class="sxs-lookup"><span data-stu-id="1248c-112">If you are using a 64-bit operating system version, the folder is located under C:\\Program Files (x86)\\Microsoft System Center App Virt Streaming Server\\App Virt Streaming Server\\bin.</span></span>

## <span data-ttu-id="1248c-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="1248c-113">Related topics</span></span>


[<span data-ttu-id="1248c-114">如何針對以伺服器為基礎的部署設定伺服器</span><span class="sxs-lookup"><span data-stu-id="1248c-114">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

[<span data-ttu-id="1248c-115">如何安裝和設定 Default Application</span><span class="sxs-lookup"><span data-stu-id="1248c-115">How to Install and Configure the Default Application</span></span>](how-to-install-and-configure-the-default-application.md)

 

 





