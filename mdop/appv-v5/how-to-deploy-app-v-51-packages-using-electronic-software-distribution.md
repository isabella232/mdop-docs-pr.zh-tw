---
title: 如何使用電子軟體發佈來部署 App-V 5.1 封裝
description: 如何使用電子軟體發佈來部署 App-V 5.1 封裝
author: dansimp
ms.assetid: e1957a5a-1f18-42da-b2c1-a5ae5a4cca7a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a9ed5fbb264f8fb9676d7fa18fe4de8019ea8e79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800530"
---
# <span data-ttu-id="9b471-103">如何使用電子軟體發佈來部署 App-V 5.1 封裝</span><span class="sxs-lookup"><span data-stu-id="9b471-103">How to deploy App-V 5.1 Packages Using Electronic Software Distribution</span></span>


<span data-ttu-id="9b471-104">您可以使用電子軟體發佈（ESD）系統，將 App-v 5.1 虛擬應用程式部署到 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="9b471-104">You can use an electronic software distribution (ESD) system to deploy App-V 5.1 virtual applications to App-V clients.</span></span> <span data-ttu-id="9b471-105">如需詳細資訊，請參閱您使用的 ESD 提供的說明文件。</span><span class="sxs-lookup"><span data-stu-id="9b471-105">For details, see the documentation available with the ESD you are using.</span></span>

<span data-ttu-id="9b471-106">如需元件需求，以及使用 ESD 來部署 app-v 套件的選項，請參閱[規劃以使用電子軟體發佈系統部署 app-v 5.1](planning-to-deploy-app-v-51-with-an-electronic-software-distribution-system.md)。</span><span class="sxs-lookup"><span data-stu-id="9b471-106">For component requirements and options for using an ESD to deploy App-V packages, see [Planning to Deploy App-V 5.1 with an Electronic Software Distribution System](planning-to-deploy-app-v-51-with-an-electronic-software-distribution-system.md).</span></span>

<span data-ttu-id="9b471-107">使用下列其中一種方法，將套件發佈至有 ESD 的 App-v 用戶端電腦：</span><span class="sxs-lookup"><span data-stu-id="9b471-107">Use one of the following methods to publish packages to App-V client computers with an ESD:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9b471-108">方法</span><span class="sxs-lookup"><span data-stu-id="9b471-108">Method</span></span></th>
<th align="left"><span data-ttu-id="9b471-109">描述</span><span class="sxs-lookup"><span data-stu-id="9b471-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9b471-110">協力廠商 ESD 提供的功能</span><span class="sxs-lookup"><span data-stu-id="9b471-110">Functionality provided by a third-party ESD</span></span></p></td>
<td align="left"><p><span data-ttu-id="9b471-111">使用協力廠商 ESD 中的功能。</span><span class="sxs-lookup"><span data-stu-id="9b471-111">Use the functionality in a third-party ESD.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9b471-112">獨立 Windows 安裝程式</span><span class="sxs-lookup"><span data-stu-id="9b471-112">Stand-alone Windows Installer</span></span></p></td>
<td align="left"><p><span data-ttu-id="9b471-113">在目標用戶端電腦上，使用您最初為應用程式排序時所建立的關聯 Windows 安裝程式（.msi）檔案，在目標用戶端電腦上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b471-113">Install the application on the target client computer by using the associated Windows Installer (.msi) file that is created when you initially sequence an application.</span></span> <span data-ttu-id="9b471-114">Windows Installer 檔案包含相關聯的 App-v 5.1 套件檔案資訊，用於設定套件，並將所需的套件檔案複製到用戶端。</span><span class="sxs-lookup"><span data-stu-id="9b471-114">The Windows Installer file contains the associated App-V 5.1 package file information used to configure a package and copies the required package files to the client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9b471-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b471-115">PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="9b471-116">使用 PowerShell Cmdlet 來部署虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b471-116">Use PowerShell cmdlets to deploy virtualized applications.</span></span> <span data-ttu-id="9b471-117">如需有關使用 PowerShell 與 App-v 5.1 的詳細資訊，請參閱 <a href="administering-app-v-51-by-using-powershell.md" data-raw-source="[Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md)"> 使用 powershell 管理 app-v 5.1 </a> 。</span><span class="sxs-lookup"><span data-stu-id="9b471-117">For more information about using PowerShell and App-V 5.1, see <a href="administering-app-v-51-by-using-powershell.md" data-raw-source="[Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md)">Administering App-V 5.1 by Using PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="9b471-118">使用 ESD 部署 app-v 5.1 套件</span><span class="sxs-lookup"><span data-stu-id="9b471-118">To deploy App-V 5.1 packages by using an ESD</span></span>**

1.  <span data-ttu-id="9b471-119">在您的環境中的電腦上安裝 app-v 5.1 排序器。</span><span class="sxs-lookup"><span data-stu-id="9b471-119">Install the App-V 5.1 Sequencer on a computer in your environment.</span></span> <span data-ttu-id="9b471-120">如需安裝排序器的詳細資訊，請參閱[如何安裝排序](how-to-install-the-sequencer-51beta-gb18030.md)器。</span><span class="sxs-lookup"><span data-stu-id="9b471-120">For more information about installing the sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

2.  <span data-ttu-id="9b471-121">使用 App-v 5.1 Sequencer 來建立虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b471-121">Use the App-V 5.1 Sequencer to create virtual application.</span></span> <span data-ttu-id="9b471-122">如需建立虛擬應用程式的相關資訊，請參閱[建立及管理 app-v 5.1 虛擬化應用程式](creating-and-managing-app-v-51-virtualized-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="9b471-122">For information about creating a virtual application, see [Creating and Managing App-V 5.1 Virtualized Applications](creating-and-managing-app-v-51-virtualized-applications.md).</span></span>

3.  <span data-ttu-id="9b471-123">建立虛擬應用程式之後，請使用您的 ESD 方案部署套件。</span><span class="sxs-lookup"><span data-stu-id="9b471-123">After you create the virtual application, deploy the package by using your ESD solution.</span></span>

    <span data-ttu-id="9b471-124">如果您使用的是 System Center Configuration Manager，請先查看[Configuration Manager 中的應用程式管理簡介](https://go.microsoft.com/fwlink/?LinkId=281816)，以取得使用 app-v 5.1 和 System Center2012 Configuration Manager 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9b471-124">If you are using System Center Configuration Manager, start by reviewing [Introduction to Application Management in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=281816) for information about using App-V 5.1 and System Center2012 Configuration Manager.</span></span>

    <span data-ttu-id="9b471-125">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="9b471-125">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="9b471-126">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="9b471-126">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="9b471-127">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="9b471-127">Got an App-V issue?</span></span>** <span data-ttu-id="9b471-128">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="9b471-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="9b471-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="9b471-129">Related topics</span></span>


[<span data-ttu-id="9b471-130">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="9b471-130">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





