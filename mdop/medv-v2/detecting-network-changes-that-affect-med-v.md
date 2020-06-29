---
title: 偵測影響 MED-V 的網路變更
description: 偵測影響 MED-V 的網路變更
author: dansimp
ms.assetid: fd29b95a-cda2-464d-b86d-50b6bd64b4ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5f43c30dee9ef8e06a7ae226849a4f21e83257c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809915"
---
# <span data-ttu-id="aa80a-103">偵測影響 MED-V 的網路變更</span><span class="sxs-lookup"><span data-stu-id="aa80a-103">Detecting Network Changes that Affect MED-V</span></span>


<span data-ttu-id="aa80a-104">Microsoft 企業桌面虛擬化（MED-V）2.0 解決方案可讓您設定您的環境，以偵測在部署 MED-V 工作區且可能會影響 MED-V 的特定網路變更。</span><span class="sxs-lookup"><span data-stu-id="aa80a-104">The Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 solution lets you configure your environment to detect certain network changes that might occur after MED-V workspaces are deployed and that can affect MED-V.</span></span>

<span data-ttu-id="aa80a-105">此功能包含在客體作業系統中執行的元件，系統會在主機電腦上收到網路設定變更的通知。</span><span class="sxs-lookup"><span data-stu-id="aa80a-105">The feature includes a component running in the guest operating system that is notified of network configuration changes on the host computer.</span></span> <span data-ttu-id="aa80a-106">它允許在來賓中執行的非 Microsoft ESD 或其他應用程式解析為主機 ESD 或應用程式解析的相同網路端點。</span><span class="sxs-lookup"><span data-stu-id="aa80a-106">It allows a non-Microsoft ESD or other application that is running in the guest to resolve to the same network endpoints that the host ESD or application resolves to.</span></span>

<span data-ttu-id="aa80a-107">**記事** 此功能只有在虛擬機器設定為「網路位址轉譯（NAT）」模式時才能使用。</span><span class="sxs-lookup"><span data-stu-id="aa80a-107">**Note** This feature is only available if the virtual machine is configured for network address translation (NAT) mode.</span></span> <span data-ttu-id="aa80a-108">如果虛擬機器是針對橋接模式進行設定，則不會產生變更指示。</span><span class="sxs-lookup"><span data-stu-id="aa80a-108">If the virtual machine is configured for BRIDGED mode, no change indications are generated.</span></span>

 

<span data-ttu-id="aa80a-109">本節提供資訊與指示，協助您監視那些可能會影響 MED-V 的網路變更。</span><span class="sxs-lookup"><span data-stu-id="aa80a-109">This section provides information and instruction to assist you in monitoring those network changes that can affect MED-V.</span></span>

## <span data-ttu-id="aa80a-110">若要偵測 MED-V 的網路變更</span><span class="sxs-lookup"><span data-stu-id="aa80a-110">To detect network changes for MED-V</span></span>


<span data-ttu-id="aa80a-111">部署 MED-V 工作區之後，您可以 preforming 下列工作來監視某些網路設定的變更：</span><span class="sxs-lookup"><span data-stu-id="aa80a-111">After you have deployed your MED-V workspaces, you can monitor changes to certain network configurations by preforming the following tasks:</span></span>

1. <span data-ttu-id="aa80a-112">建立受管理的物件格式（MOF）檔案，該檔案會尋找您要監視的網路設定變更。</span><span class="sxs-lookup"><span data-stu-id="aa80a-112">Create a Managed Object Format (MOF) file that will look for the network configuration changes that you want to monitor.</span></span> <span data-ttu-id="aa80a-113">下列程式碼會顯示您可以建立的 MOF 檔案範例。</span><span class="sxs-lookup"><span data-stu-id="aa80a-113">The following code shows an example of the MOF file that you can create.</span></span>

   ``` syntax
   #pragma namespace ("\\\\.\\root\\ccm\\NetworkConfig")

   class CCM_IPConfig
   {
       [NotNull: ToInstance ToSubClass] uint32 AddressFamily; // AF_INET, AF_INET6
       [Key, NotNull: ToInstance ToSubClass] string IPAddress; // IPv4 or IPv6 address
       [NotNull: ToInstance ToSubClass] string SubnetMask; // IPv4 subnet mask
   };

   class CCM_NetworkAdapter
   {
       [Key, NotNull: ToInstance ToSubClass] string Name;
       [NotNull: ToInstance ToSubClass] uint32 DHCPEnabled = 0; 
       [NotNull: ToInstance ToSubClass] uint32 Quarantined = 0; // To check if it is quarantined.
       CCM_IPConfig IPConfigInfo[];
   };

   [singleton]
   class CCM_NetworkAdapters
   {
       [NotNull: ToInstance ToSubClass] String ProviderName; // MED-V or other provider
       CCM_NetworkAdapter AdaptersInfo[];
   };
   ```

2. <span data-ttu-id="aa80a-114">編譯 MOF 檔案。</span><span class="sxs-lookup"><span data-stu-id="aa80a-114">Compile the MOF file.</span></span>

3. <span data-ttu-id="aa80a-115">在來賓中安裝 MOF 檔案。</span><span class="sxs-lookup"><span data-stu-id="aa80a-115">Install the MOF file in the guest.</span></span>

<span data-ttu-id="aa80a-116">安裝 MOF 檔案之後，您就可以建立一個事件訂閱，以訂閱對**CCM \ _NetworkAdapters**類別進行的 Windows Management INSTRUMENTATION （WMI）建立、修改或刪除事件。</span><span class="sxs-lookup"><span data-stu-id="aa80a-116">After you have installed the MOF file, you can create an event subscription that subscribes to Windows Management Instrumentation (WMI) creation, modification, or deletion events for the **CCM\_NetworkAdapters** class.</span></span> <span data-ttu-id="aa80a-117">這會偵測到主機的下列變更：</span><span class="sxs-lookup"><span data-stu-id="aa80a-117">This detects the following changes to the host:</span></span>

<span data-ttu-id="aa80a-118">網路是否有任何設定變更，例如 IP 位址或網路介面卡的變更？</span><span class="sxs-lookup"><span data-stu-id="aa80a-118">Are there any configuration changes to the network, such as changes to the IP address or network adapter?</span></span>

<span data-ttu-id="aa80a-119">網路可用或無法使用？</span><span class="sxs-lookup"><span data-stu-id="aa80a-119">Is the network available or unavailable?</span></span>

<span data-ttu-id="aa80a-120">網路設定是否已從橋接模式變更為 NAT 模式？</span><span class="sxs-lookup"><span data-stu-id="aa80a-120">Was the network setup changed from BRIDGED mode to NAT mode?</span></span>

<span data-ttu-id="aa80a-121">網路設定是否已從 NAT 模式變更為橋接模式？</span><span class="sxs-lookup"><span data-stu-id="aa80a-121">Was the network setup changed from NAT mode to BRIDGED mode?</span></span>

<span data-ttu-id="aa80a-122">主機上的 MED-V 元件會針對這些變更監視網路，然後向訪客指示變更。</span><span class="sxs-lookup"><span data-stu-id="aa80a-122">A MED-V component on the host monitors the network for these changes and then signals the guest of the change.</span></span> <span data-ttu-id="aa80a-123">來賓中的元件會建立 WMI 實例來監視 MED-V 工作區，以瞭解這些變更。</span><span class="sxs-lookup"><span data-stu-id="aa80a-123">A component in the guest creates a WMI instance to monitor the MED-V workspace for these changes.</span></span>

<span data-ttu-id="aa80a-124">您所建立的事件訂閱會在其中一或多個網路變更時（即建立、修改或刪除），在 WMI 系統中提供通知。</span><span class="sxs-lookup"><span data-stu-id="aa80a-124">The event subscription you created provides notification through the WMI system when one or more of these network changes – creation, modification, or deletion – occurs.</span></span>

## <span data-ttu-id="aa80a-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa80a-125">Related topics</span></span>


[<span data-ttu-id="aa80a-126">監控 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="aa80a-126">Monitor MED-V Workspaces</span></span>](monitor-med-v-workspaces.md)

[<span data-ttu-id="aa80a-127">管理 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="aa80a-127">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





