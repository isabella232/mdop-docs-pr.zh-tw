---
title: 如何為 App-V 設定 Windows Server 2003 防火牆
description: 如何為 App-V 設定 Windows Server 2003 防火牆
author: dansimp
ms.assetid: 2c0e80f8-41e9-4164-ac83-b23b132b489a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af75479504b454851ee2efc7ca2638d2daf45053
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801533"
---
# <span data-ttu-id="71b0c-103">如何為 App-V 設定 Windows Server 2003 防火牆</span><span class="sxs-lookup"><span data-stu-id="71b0c-103">How to Configure Windows Server 2003 Firewall for App-V</span></span>


<span data-ttu-id="71b0c-104">使用下列程式來設定 App-v 的 WindowsServer 2003 防火牆。</span><span class="sxs-lookup"><span data-stu-id="71b0c-104">Use the following procedure to configure the WindowsServer 2003 firewall for App-V.</span></span>

**<span data-ttu-id="71b0c-105">若要設定 WindowsServer 2003 的 App-V 防火牆</span><span class="sxs-lookup"><span data-stu-id="71b0c-105">To configure WindowsServer 2003 firewall for App-V</span></span>**

1.  <span data-ttu-id="71b0c-106">在 [**控制台**] 中，開啟 [ **Windows 防火牆**]。</span><span class="sxs-lookup"><span data-stu-id="71b0c-106">In **Control Panel**, open the **Windows Firewall**.</span></span>

    <span data-ttu-id="71b0c-107">**記事** 如果伺服器尚未設定為在執行此步驟之前執行防火牆服務，系統會提示您啟動防火牆服務。</span><span class="sxs-lookup"><span data-stu-id="71b0c-107">**Note** If the server has not been configured to run the firewall service before this step, you will be prompted to start the firewall service.</span></span>

     

2.  <span data-ttu-id="71b0c-108">如果 .ICO 和 OSD 檔案是透過 SMB 發佈，請確定 [**例外**] 索引標籤上的 [檔案**及印表機共用**] 已啟用。</span><span class="sxs-lookup"><span data-stu-id="71b0c-108">If ICO and OSD files are published through SMB, ensure that **File and Printer Sharing** is enabled on the **Exceptions** tab.</span></span>

    <span data-ttu-id="71b0c-109">**記事** 如果 .ICO 和 OSD 檔案是透過管理伺服器上的 HTTP/HTTPS 發佈，您可能需要新增 HTTP 或 HTTPS 例外狀況。</span><span class="sxs-lookup"><span data-stu-id="71b0c-109">**Note** If ICO and OSD files are published through HTTP/HTTPS on the Management Server, you might need to add an exception for HTTP or HTTPS.</span></span> <span data-ttu-id="71b0c-110">如果裝載 .ICO 和 OSD 檔案的 IIS 伺服器裝載在與管理伺服器不同的電腦上，您需要將例外狀況新增到該電腦。</span><span class="sxs-lookup"><span data-stu-id="71b0c-110">If the IIS server hosting the ICO and OSD files is hosted on a computer separate from the Management Server, you need to add the exception to that computer.</span></span> <span data-ttu-id="71b0c-111">若要最大化效能，建議您將 .ICO 和 OSD 檔案託管在與管理伺服器不同的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="71b0c-111">To maximize performance, it is recommended that you host the ICO and OSD files on a separate server from the Management Server.</span></span>

     

3.  <span data-ttu-id="71b0c-112">新增的程式例外狀況 `sghwdsptr.exe` ，也就是管理伺服器服務的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="71b0c-112">Add a program exception for `sghwdsptr.exe`, which is the Management Server service executable.</span></span> <span data-ttu-id="71b0c-113">此可執行檔的預設路徑是 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` 。</span><span class="sxs-lookup"><span data-stu-id="71b0c-113">The default path to this executable is `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin`.</span></span>

    <span data-ttu-id="71b0c-114">**記事** 如果管理伺服器使用 RTSP 進行通訊，您也必須新增程式例外狀況 `sghwsvr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="71b0c-114">**Note** If the Management Server uses RTSP for communication, you must also add a program exception for `sghwsvr.exe`.</span></span>

    <span data-ttu-id="71b0c-115">App-v 流式處理伺服器需要程式例外狀況 `sglwdsptr.exe` 才能進行 RTSPS 通信。</span><span class="sxs-lookup"><span data-stu-id="71b0c-115">The App-V Streaming Server requires a program exception `sglwdsptr.exe` for RTSPS communication.</span></span> <span data-ttu-id="71b0c-116">使用 RTSP 通訊的 App-v 流式處理伺服器也需要程式例外狀況 `sglwsvr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="71b0c-116">The App-V Streaming Server that uses RTSP for communication also requires a program exception for `sglwsvr.exe`.</span></span>

     

4.  <span data-ttu-id="71b0c-117">確保針對每個例外設定適當的範圍。</span><span class="sxs-lookup"><span data-stu-id="71b0c-117">Ensure that the proper scope is configured for each exception.</span></span> <span data-ttu-id="71b0c-118">若要降低風險，請移除任何電腦，並嚴格限制伺服器將回應的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="71b0c-118">To reduce risk, remove any computer and strictly limit the IP addresses to which the server will respond.</span></span>

## <span data-ttu-id="71b0c-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="71b0c-119">Related topics</span></span>


[<span data-ttu-id="71b0c-120">如何為 App-V 設定 Windows Server 2008 防火牆</span><span class="sxs-lookup"><span data-stu-id="71b0c-120">How to Configure Windows Server 2008 Firewall for App-V</span></span>](how-to-configure-windows-server-2008-firewall-for-app-v.md)

 

 





