---
title: 如何為 App-V 設定 Windows Server 2008 防火牆
description: 如何為 App-V 設定 Windows Server 2008 防火牆
author: dansimp
ms.assetid: 57f4ed17-0651-4a3c-be1e-29d9520c6aeb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 19e4cda9ac3b908f68e4f69b9663033d8a21ae41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801529"
---
# <span data-ttu-id="ce760-103">如何為 App-V 設定 Windows Server 2008 防火牆</span><span class="sxs-lookup"><span data-stu-id="ce760-103">How to Configure Windows Server 2008 Firewall for App-V</span></span>


<span data-ttu-id="ce760-104">隨著 Windows Server2008 的推出，防火牆和 IPsec 元件會合並成一個服務，而這項服務的功能也得到加強。</span><span class="sxs-lookup"><span data-stu-id="ce760-104">With the introduction of Windows Server2008, the firewall and IPsec components were merged into one service, and the capabilities of this service were enhanced.</span></span> <span data-ttu-id="ce760-105">新的防火牆服務支援傳入及傳出狀態檢查。</span><span class="sxs-lookup"><span data-stu-id="ce760-105">The new firewall service supports incoming and outgoing stateful inspection.</span></span> <span data-ttu-id="ce760-106">此外，您也可以透過 [群組原則] 設定特定的防火牆規則及 IPsec 原則。</span><span class="sxs-lookup"><span data-stu-id="ce760-106">Also, you can configure specific firewall rules and IPsec policies through group policies.</span></span> <span data-ttu-id="ce760-107">如需 Windows Server2008 中 Windows 防火牆的其他相關資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=151980> 。</span><span class="sxs-lookup"><span data-stu-id="ce760-107">For additional information about the Windows firewall in Windows Server2008, see <https://go.microsoft.com/fwlink/?LinkId=151980>.</span></span>

<span data-ttu-id="ce760-108">下列程式不包含透過 SMB 或 HTTP/HTTPS 新增 .ICO 和 OSD 發佈例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ce760-108">The following procedure does not include adding an exception for ICO and OSD publishing through SMB or HTTP/HTTPS.</span></span> <span data-ttu-id="ce760-109">這些例外狀況會根據安裝在 Windows Server 2008 防火牆的網路設定檔和角色來自動新增。</span><span class="sxs-lookup"><span data-stu-id="ce760-109">Those exceptions are automatically added based on the network profile and roles installed on the Windows Server 2008 firewall.</span></span>

<span data-ttu-id="ce760-110">**記事** 如果管理伺服器已設定為使用 RTSP，請重複此程式以新增 `sghwsvr.exe` 程式作為例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ce760-110">**Note** If the Management Server is configured to use RTSP, repeat this procedure to add the `sghwsvr.exe` program as an exception.</span></span>

<span data-ttu-id="ce760-111">App-v 流式處理伺服器需要程式例外狀況 `sglwdsptr.exe` 才能進行 RTSPS 通信。</span><span class="sxs-lookup"><span data-stu-id="ce760-111">The App-V Streaming Server requires the program exception `sglwdsptr.exe` for RTSPS communication.</span></span> <span data-ttu-id="ce760-112">使用 RTSP 通訊的 App-v 流式處理伺服器也需要程式例外狀況 `sglwsvr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="ce760-112">An App-V Streaming Server that uses RTSP for communication also requires a program exception for `sglwsvr.exe`.</span></span>

 

**<span data-ttu-id="ce760-113">若要設定 App-V 的 Windows Server2008 防火牆</span><span class="sxs-lookup"><span data-stu-id="ce760-113">To configure Windows Server2008 firewall for App-V</span></span>**

1.  <span data-ttu-id="ce760-114">透過 [控制台] 或在 [執行] 行上輸入 **，以開啟 [高級安全**管理] 主控台的 Windows 防火牆 `wf.msc` 。</span><span class="sxs-lookup"><span data-stu-id="ce760-114">Open the **Windows Firewall with Advanced Security** management console through the Control Panel or by typing `wf.msc` on the Run line.</span></span>

2.  <span data-ttu-id="ce760-115">建立新的入站規則，然後選取 [**程式**]。</span><span class="sxs-lookup"><span data-stu-id="ce760-115">Create a new inbound rule, and select **Program**.</span></span>

3.  <span data-ttu-id="ce760-116">選取程式路徑，然後流覽至 `sghwdsptr.exe` ，其預設位於中 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` 。</span><span class="sxs-lookup"><span data-stu-id="ce760-116">Select the program path, and browse to `sghwdsptr.exe`, which is located by default at `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin`.</span></span>

4.  <span data-ttu-id="ce760-117">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="ce760-117">Click **Next**.</span></span>

5.  <span data-ttu-id="ce760-118">在 [**動作**] 頁面上，選取 [**允許**連線]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce760-118">On the **Action** page, select **Allow the connection**, and then click **Next**.</span></span>

6.  <span data-ttu-id="ce760-119">選取要套用至入站規則的適當**設定檔**。</span><span class="sxs-lookup"><span data-stu-id="ce760-119">Select the appropriate **Profiles** to apply to the inbound rule.</span></span>

7.  <span data-ttu-id="ce760-120">提供規則的名稱和描述，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ce760-120">Provide a name and description for the rule, and click **Finish**.</span></span>

## <span data-ttu-id="ce760-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="ce760-121">Related topics</span></span>


[<span data-ttu-id="ce760-122">如何為 App-V 設定 Windows Server 2003 防火牆</span><span class="sxs-lookup"><span data-stu-id="ce760-122">How to Configure Windows Server 2003 Firewall for App-V</span></span>](how-to-configure-windows-server-2003-firewall-for-app-v.md)

 

 





