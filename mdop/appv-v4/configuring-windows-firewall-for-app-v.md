---
title: 正在為 App-V 設定 Windows 防火牆
description: 正在為 App-V 設定 Windows 防火牆
author: dansimp
ms.assetid: 6b5e253c-473f-4afc-a48b-631eda11d9ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 274f6993b7e3d9dc60778ac5a5521c69e016f060
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808979"
---
# <span data-ttu-id="a18e5-103">正在為 App-V 設定 Windows 防火牆</span><span class="sxs-lookup"><span data-stu-id="a18e5-103">Configuring Windows Firewall for App-V</span></span>


<span data-ttu-id="a18e5-104">保護 App-v 基礎結構中元件間的通訊，只是保護環境的一個元素。</span><span class="sxs-lookup"><span data-stu-id="a18e5-104">Securing the communication between components in an App-V infrastructure is only one element in securing the environment.</span></span> <span data-ttu-id="a18e5-105">在伺服器上使用防火牆程式有助於減少受攻擊 surface 區域。</span><span class="sxs-lookup"><span data-stu-id="a18e5-105">Using a firewall program on the server can help reduce the attack surface area.</span></span> <span data-ttu-id="a18e5-106">本節中的主題提供設定 Windows 內建防火牆功能（支援 App-v）的程式。</span><span class="sxs-lookup"><span data-stu-id="a18e5-106">The topics in this section provide procedures for configuring Windows built-in firewall capabilities that support App-V.</span></span> <span data-ttu-id="a18e5-107">這些程式假設您已安裝管理伺服器，且已針對 RTSPS 通訊進行設定。</span><span class="sxs-lookup"><span data-stu-id="a18e5-107">These procedures assume that you installed a Management Server and that it has been configured for RTSPS communication.</span></span> <span data-ttu-id="a18e5-108">筆記包含在流式處理伺服器的程式中，以及使用 RTSP 進行通訊的環境。</span><span class="sxs-lookup"><span data-stu-id="a18e5-108">Notes are included in the procedures for Streaming Servers and environments where RTSP is being used for communication.</span></span>

## <span data-ttu-id="a18e5-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="a18e5-109">In This Section</span></span>


<a href="" id="how-to-configure-windows-server-2003-firewall-for-app-v"></a>[<span data-ttu-id="a18e5-110">如何為 App-V 設定 Windows Server 2003 防火牆</span><span class="sxs-lookup"><span data-stu-id="a18e5-110">How to Configure Windows Server 2003 Firewall for App-V</span></span>](how-to-configure-windows-server-2003-firewall-for-app-v.md)  
<span data-ttu-id="a18e5-111">提供您可以用來設定 App-V 的 Windows Server 2003 防火牆的程式。</span><span class="sxs-lookup"><span data-stu-id="a18e5-111">Provides a procedure you can use to configure the Windows Server 2003 firewall for App-V.</span></span>

<a href="" id="how-to-configure-windows-server-2008-firewall-for-app-v"></a>[<span data-ttu-id="a18e5-112">如何為 App-V 設定 Windows Server 2008 防火牆</span><span class="sxs-lookup"><span data-stu-id="a18e5-112">How to Configure Windows Server 2008 Firewall for App-V</span></span>](how-to-configure-windows-server-2008-firewall-for-app-v.md)  
<span data-ttu-id="a18e5-113">提供您可以用來設定 App-V 的 Windows Server 2008 防火牆的程式。</span><span class="sxs-lookup"><span data-stu-id="a18e5-113">Provides a procedure you can use to configure the Windows Server 2008 firewall for App-V.</span></span>

 

 





