---
title: 管理 MED-V 工作區上的印表機
description: 管理 MED-V 工作區上的印表機
author: dansimp
ms.assetid: ba0a65ad-444f-4d18-95eb-8b9fa1a3ffba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bc7a62075c95e8816a425eff89ffb992f1185d04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811564"
---
# <span data-ttu-id="25acb-103">管理 MED-V 工作區上的印表機</span><span class="sxs-lookup"><span data-stu-id="25acb-103">Managing Printers on a MED-V Workspace</span></span>


<span data-ttu-id="25acb-104">在 Microsoft 企業版桌面虛擬化（MED-V）2.0 中，印表機重新導向功能可讓使用者在 MED-V 虛擬機器與主機電腦之間保持一致的列印體驗。</span><span class="sxs-lookup"><span data-stu-id="25acb-104">In Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, printer redirection provides end users with a consistent printing experience between the MED-V virtual machine and the host computer.</span></span>

<span data-ttu-id="25acb-105">本主題提供如何在 MED-V 工作區中管理列印的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="25acb-105">This topic provides information about how to manage printing in a MED-V workspace.</span></span>

## <span data-ttu-id="25acb-106">在 MED-V 工作區中管理印表機</span><span class="sxs-lookup"><span data-stu-id="25acb-106">Managing Printers in MED-V Workspaces</span></span>


<span data-ttu-id="25acb-107">在大多數情況下，MED-V 會自動處理印表機重新導向。</span><span class="sxs-lookup"><span data-stu-id="25acb-107">In most cases, MED-V handles printer redirection automatically.</span></span> <span data-ttu-id="25acb-108">在第一次設定完成後，MED-V 會識別主機上已安裝的所有網路印表機、從網路列印伺服器中檢索對應的驅動程式，如果找到的話，就會在 MED-V 工作區中安裝相關的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="25acb-108">After first time setup finishes, MED-V identifies all network printers installed on the host, retrieves the corresponding drivers from the network print server, and if found, installs the relevant drivers in the MED-V workspace.</span></span> <span data-ttu-id="25acb-109">找到並安裝所有驅動程式後，MED-V 會重新開機 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="25acb-109">After all drivers are found and installed, MED-V reboots the MED-V workspace.</span></span> <span data-ttu-id="25acb-110">只有在 MED-V 工作區重新開機之後，主機印表機才存在並可在來賓上使用，通常在幾分鐘內才會出現。</span><span class="sxs-lookup"><span data-stu-id="25acb-110">Only after the MED-V workspace restarts, the host printers are present and available on the guest, typically in a few minutes.</span></span>

<span data-ttu-id="25acb-111">**記事** 如果應用程式是在 MED-V 工作區執行，系統會提示使用者讓重新開機繼續進行，或將它推遲到較新的狀態。</span><span class="sxs-lookup"><span data-stu-id="25acb-111">**Note** If applications are running on the MED-V workspace, the end user is prompted to let the restart continue or postpone it until later.</span></span> <span data-ttu-id="25acb-112">如果沒有任何應用程式正在執行，則會自動重新開機，而不會向使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="25acb-112">If no applications are running, the restart is automatic and not shown to the end user.</span></span>

 

<span data-ttu-id="25acb-113">每當 MED-V 重新開機時，它會檢查主機上是否已安裝任何新的印表機，如果有的話，也會從網路列印伺服器中檢索對應的驅動程式，並將其安裝在來賓機上。</span><span class="sxs-lookup"><span data-stu-id="25acb-113">Every time MED-V is re-started, it checks whether any new printers are installed on the host and, if found, retrieves the corresponding drivers from the network print server and installs them on the guest.</span></span> <span data-ttu-id="25acb-114">然後，MED-V 會重新開機 MED-V 工作區，就如同第一次設定完成時一樣。</span><span class="sxs-lookup"><span data-stu-id="25acb-114">MED-V then restarts the MED-V workspace just as when first time setup was completed.</span></span>

<span data-ttu-id="25acb-115">**重要** 在來賓上安裝相關的驅動程式之後，印表機只有在重新開機後才會顯示在來賓中。</span><span class="sxs-lookup"><span data-stu-id="25acb-115">**Important** After the relevant drivers are installed on the guest, the printers only become visible on the guest after the restart occurs.</span></span>

 

<span data-ttu-id="25acb-116">如果在任何時候找不到或無法安裝驅動程式，必須手動將其安裝在來賓上，才能讓最終使用者使用網路印表機。</span><span class="sxs-lookup"><span data-stu-id="25acb-116">If at any time a driver cannot be located or installed, it must be manually installed on the guest for the network printer to be available to the end user.</span></span>

<span data-ttu-id="25acb-117">下列清單提供一些其他指導方針：</span><span class="sxs-lookup"><span data-stu-id="25acb-117">The following list offers some additional guidance:</span></span>

<span data-ttu-id="25acb-118">**Med-v 只會管理網路印表機**。</span><span class="sxs-lookup"><span data-stu-id="25acb-118">**MED-V only manages network printers**.</span></span> <span data-ttu-id="25acb-119">本機安裝于主機上的印表機驅動程式不會自動安裝在來賓上。</span><span class="sxs-lookup"><span data-stu-id="25acb-119">Drivers for printers that are installed locally on the host are not automatically installed on the guest.</span></span>

<span data-ttu-id="25acb-120">**[Med-v] 只會安裝在列印伺服器上找到的印表機驅動程式**。</span><span class="sxs-lookup"><span data-stu-id="25acb-120">**MED-V only installs printer drivers if found on the print server**.</span></span> <span data-ttu-id="25acb-121">如果找不到，必須手動安裝印表機驅動程式。</span><span class="sxs-lookup"><span data-stu-id="25acb-121">If not found, printer drivers must be manually installed.</span></span>

<span data-ttu-id="25acb-122">**主機無法存取手動安裝在來賓上的印表機**。</span><span class="sxs-lookup"><span data-stu-id="25acb-122">**Printers manually installed on the guest are not accessible to the host**.</span></span> <span data-ttu-id="25acb-123">根據預設，MED-V 只支援從來賓到主機的印表機重新導向。</span><span class="sxs-lookup"><span data-stu-id="25acb-123">By default, MED-V only supports printer redirection from the guest to the host.</span></span>

<span data-ttu-id="25acb-124">**警告** 如果您已在來賓上手動安裝印表機，且主機上安裝了相同的印表機，結果就是在來賓中安裝了兩次印表機。</span><span class="sxs-lookup"><span data-stu-id="25acb-124">**Warning** If a printer is manually installed on the guest, and the same printer is later installed on the host, the result is that the printer is installed two times in the guest.</span></span> <span data-ttu-id="25acb-125">若要避免這種情況，MED-V 最佳做法只需一種方式即可管理印表機重新導向：停用來賓的重新導向及手動安裝印表機，或啟用重新導向，並不要在來賓上手動安裝印表機。</span><span class="sxs-lookup"><span data-stu-id="25acb-125">To avoid this situation, a MED-V best practice is to manage printer redirection in one manner only: either disable redirection and install printers manually on the guest, or enable redirection and do not install printers manually on the guest.</span></span>

 

## <span data-ttu-id="25acb-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="25acb-126">Related topics</span></span>


[<span data-ttu-id="25acb-127">管理 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="25acb-127">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





