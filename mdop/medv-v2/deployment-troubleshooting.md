---
title: 部署疑難排解
description: 部署疑難排解
author: dansimp
ms.assetid: 9ee980f2-4e77-4020-9f0e-8c2ffdc390ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe9677175c9538bc070d2adea17a96351397d9a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809632"
---
# <span data-ttu-id="41b01-103">部署疑難排解</span><span class="sxs-lookup"><span data-stu-id="41b01-103">Deployment Troubleshooting</span></span>


<span data-ttu-id="41b01-104">本主題包含的資訊可協助您針對 Microsoft 企業版桌面虛擬化（MED-V）2.0 中的部署問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="41b01-104">This topic includes information to help you troubleshoot deployment issues in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="41b01-105">MED-V 部署中的疑難排解問題</span><span class="sxs-lookup"><span data-stu-id="41b01-105">Troubleshooting Issues in MED-V Deployment</span></span>


<span data-ttu-id="41b01-106">在您部署 MED-V 時，可能會發生下列問題。</span><span class="sxs-lookup"><span data-stu-id="41b01-106">The following issue might occur when you deploy MED-V.</span></span> <span data-ttu-id="41b01-107">此方案可協助您解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="41b01-107">The solution helps troubleshoot this issue.</span></span>

**<span data-ttu-id="41b01-108">如果您只為目前的使用者安裝 MED-V，就會發生問題。</span><span class="sxs-lookup"><span data-stu-id="41b01-108">Problems Occur if Installing MED-V for Current User Only.</span></span>** <span data-ttu-id="41b01-109">MED-V 只支援安裝 MED-V 工作區包裝程式、MED-V 主機代理程式，以及所有使用者的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="41b01-109">MED-V only supports the installation of the MED-V Workspace Packager, the MED-V Host Agent, and the MED-V workspace for all users.</span></span> <span data-ttu-id="41b01-110">安裝目前的使用者只會在元件安裝和 MED-V 工作區的設定中造成失敗。</span><span class="sxs-lookup"><span data-stu-id="41b01-110">Installing for the current user only causes failures in the installation of the components and in the setup of the MED-V workspace.</span></span>

**<span data-ttu-id="41b01-111">解決方案</span><span class="sxs-lookup"><span data-stu-id="41b01-111">Solution</span></span>**

<span data-ttu-id="41b01-112">安裝 MED-V 元件時，請勿使用選項**ALLUSERS = ""** 。</span><span class="sxs-lookup"><span data-stu-id="41b01-112">Never use the option **ALLUSERS=””** when installing the MED-V components.</span></span>

**<span data-ttu-id="41b01-113">MED-V 需要獨佔使用虛擬化堆疊。</span><span class="sxs-lookup"><span data-stu-id="41b01-113">MED-V Requires Exclusive Use of the Virtualization Stack.</span></span>** <span data-ttu-id="41b01-114">一次只能在電腦上執行一個虛擬化堆疊。</span><span class="sxs-lookup"><span data-stu-id="41b01-114">Only one virtualization stack can be run at a time on a computer.</span></span> <span data-ttu-id="41b01-115">Windows 虛擬電腦必須使用虛擬堆疊，而 MED-V 則視 Windows 虛擬電腦而定。</span><span class="sxs-lookup"><span data-stu-id="41b01-115">Windows Virtual PC must use the virtual stack, and MED-V depends on Windows Virtual PC.</span></span> <span data-ttu-id="41b01-116">因此，如果您嘗試在執行使用虛擬堆疊的其他應用程式時，部署或使用 MED-V，則無法執行或成功安裝 MED-V。</span><span class="sxs-lookup"><span data-stu-id="41b01-116">Therefore, if you try to deploy or use MED-V when other applications are running that use the virtual stack, MED-V cannot run or be successfully installed.</span></span>

**<span data-ttu-id="41b01-117">解決方案</span><span class="sxs-lookup"><span data-stu-id="41b01-117">Solution</span></span>**

<span data-ttu-id="41b01-118">在您安裝或執行 MED-V 之前，請先關閉執行使用虛擬化堆疊的任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="41b01-118">Close any application that is running that uses the virtualization stack before you install or run MED-V.</span></span>

**<span data-ttu-id="41b01-119">[快捷方式] 會在卸載後保留。</span><span class="sxs-lookup"><span data-stu-id="41b01-119">Shortcuts Remain after Uninstall.</span></span>** <span data-ttu-id="41b01-120">根據預設，當您卸載 MED-V 時，系統會移除最終使用者 [**開始**] 功能表中的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="41b01-120">By default, when you uninstall MED-V, shortcuts in the end user’s **Start** menu are removed.</span></span> <span data-ttu-id="41b01-121">不過，在某些情況下（例如，在執行漫遊設定檔的使用者），MED-V 發佈的應用程式的快捷方式仍會保留在使用者的 [**開始**] 功能表中。</span><span class="sxs-lookup"><span data-stu-id="41b01-121">However, in certain situations, such as for end users who are running roaming profiles, shortcuts to MED-V published applications remain in the end user’s **Start** menu.</span></span>

**<span data-ttu-id="41b01-122">解決方案</span><span class="sxs-lookup"><span data-stu-id="41b01-122">Solution</span></span>**

<span data-ttu-id="41b01-123">若要手動刪除 [**開始**] 功能表上剩餘的快速鍵，請以滑鼠右鍵按一下快捷方式，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="41b01-123">To manually delete the remaining shortcuts on the **Start** menu, right-click the shortcuts, and then click **Remove**.</span></span>

**<span data-ttu-id="41b01-124">[MED-V 工作區] 中的 [停用登入訊息群組原則] 設定。</span><span class="sxs-lookup"><span data-stu-id="41b01-124">Disable Logon Message Group Policy Setting in the MED-V Workspace.</span></span>** <span data-ttu-id="41b01-125">如果在 MED-V 工作區啟用 Windows XP 登入訊息，則使用者必須在每次想要開啟 MED-V 虛擬應用程式時登入。</span><span class="sxs-lookup"><span data-stu-id="41b01-125">If the Windows XP logon message is enabled in the MED-V workspace, the end user must log on every time they want to open a MED-V virtual application.</span></span> <span data-ttu-id="41b01-126">這會產生較差的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="41b01-126">This creates a poor user experience.</span></span>

**<span data-ttu-id="41b01-127">解決方案</span><span class="sxs-lookup"><span data-stu-id="41b01-127">Solution</span></span>**

<span data-ttu-id="41b01-128">在 MED-V 虛擬機器中停用下列群組原則設定：</span><span class="sxs-lookup"><span data-stu-id="41b01-128">Disable the following Group Policy settings in the MED-V virtual machine:</span></span>

**<span data-ttu-id="41b01-129">互動式登入: 給登入使用者的訊息本文</span><span class="sxs-lookup"><span data-stu-id="41b01-129">Interactive logon: Message text for users attempting to log on</span></span>**

**<span data-ttu-id="41b01-130">互動式登入: 給登入使用者的訊息標題</span><span class="sxs-lookup"><span data-stu-id="41b01-130">Interactive logon: Message title for users attempting to log on</span></span>**

## <span data-ttu-id="41b01-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="41b01-131">Related topics</span></span>


[<span data-ttu-id="41b01-132">作業疑難排解</span><span class="sxs-lookup"><span data-stu-id="41b01-132">Operations Troubleshooting</span></span>](operations-troubleshooting-medv2.md)

 

 





