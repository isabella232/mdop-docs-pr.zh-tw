---
title: 如何使用命令列安裝用戶端
description: 如何使用命令列安裝用戶端
author: dansimp
ms.assetid: ed372403-64ff-48ff-a3cd-a46cad04a4d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca594e1399b4ca4f680f68efffcd011fdc5f042
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801370"
---
# <span data-ttu-id="8926b-103">如何使用命令列安裝用戶端</span><span class="sxs-lookup"><span data-stu-id="8926b-103">How to Install the Client by Using the Command Line</span></span>


<span data-ttu-id="8926b-104">本節中的主題包含使用 setup.exe 或 setup.msi，將應用程式虛擬化（app-v）桌面用戶端或 App-v 用戶端安裝至遠端桌面服務（舊稱終端服務）的程式。</span><span class="sxs-lookup"><span data-stu-id="8926b-104">The topics in this section include procedures to install either the Application Virtualization (App-V) Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services) by using either setup.exe or setup.msi.</span></span> <span data-ttu-id="8926b-105">必須具備系統管理許可權，才能執行其中一個安裝程式。</span><span class="sxs-lookup"><span data-stu-id="8926b-105">Administrative rights are required to run either setup program.</span></span>

<span data-ttu-id="8926b-106">您可以在安裝期間，使用選用的命令列參數，將特定的設定設定套用到 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8926b-106">You can use optional command-line parameters to apply specific configuration settings to the App-V client during the installation.</span></span> <span data-ttu-id="8926b-107">如需使用參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="8926b-107">For more information about using parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span> <span data-ttu-id="8926b-108">如果您在部署用戶端之前已將登錄設定套用至電腦（例如使用群組原則），這些設定就會保留，並會套用任何其他的命令列參數。</span><span class="sxs-lookup"><span data-stu-id="8926b-108">If you have applied registry settings to a computer before deploying a client—for example, by using Group Policy—these settings are retained and any additional command line parameters are applied.</span></span> <span data-ttu-id="8926b-109">命令列參數值將會取代任何現有的相同設定值。</span><span class="sxs-lookup"><span data-stu-id="8926b-109">Command line parameter values will replace any existing value for the same setting.</span></span>

<span data-ttu-id="8926b-110">**記事** 當您安裝 App-V 用戶端以搭配唯讀快取（例如使用 VDI 伺服器實現）時，您必須將*AUTOLOADTARGET*參數設定為 NONE，以免用戶端在快取為唯讀時嘗試更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="8926b-110">**Note** When you install the App-V client to use with a read-only cache, for example with a VDI server implementation, you must set the *AUTOLOADTARGET* parameter to NONE to prevent the client from trying to update applications when the cache is read-only.</span></span>

 

<span data-ttu-id="8926b-111">如需在安裝後設定這些參數值的詳細資訊，請參閱[如何使用命令列](https://go.microsoft.com/fwlink/?LinkId=169355)（ https://go.microsoft.com/fwlink/?LinkId=169355) 在應用程式虛擬化（App-v）操作指南中）來設定 app-v 用戶端的註冊表設定。</span><span class="sxs-lookup"><span data-stu-id="8926b-111">For more information about setting these parameter values after installation, see [How to Configure the App-V Client Registry Settings by Using the Command Line](https://go.microsoft.com/fwlink/?LinkId=169355) (https://go.microsoft.com/fwlink/?LinkId=169355) in the Application Virtualization (App-V) Operations Guide.</span></span>

<span data-ttu-id="8926b-112">**記事** 如果使用者電腦上的設定是由用戶端安裝路徑所決定，請注意應用程式虛擬化（App-v）4.5 用戶端會將安裝檔案複製到與先前版本不同的資料夾。</span><span class="sxs-lookup"><span data-stu-id="8926b-112">**Note** If a configuration setting on the user’s computer depends on the client installation path, note that the Application Virtualization (App-V)4.5 client copies its installation files to a different folder than previous versions did.</span></span> <span data-ttu-id="8926b-113">根據預設，App-V 4.5 用戶端的新安裝會將其安裝檔案複製到 \\Program Files\\Microsoft 應用程式虛擬化用戶端資料夾。</span><span class="sxs-lookup"><span data-stu-id="8926b-113">By default, a new installation of the App-V4.5 client will copy its installation files to the \\Program Files\\Microsoft Application Virtualization Client folder.</span></span> <span data-ttu-id="8926b-114">如果已安裝較舊版本的用戶端，執行 App-v 4.5 用戶端安裝程式將會使用現有的安裝資料夾來升級現有的用戶端。</span><span class="sxs-lookup"><span data-stu-id="8926b-114">If an earlier version of the client is already installed, running the App-V 4.5 client installer will perform an upgrade of the existing client using the existing installation folder.</span></span>

 

<span data-ttu-id="8926b-115">\ [範本標記值 \]</span><span class="sxs-lookup"><span data-stu-id="8926b-115">\[Template Token Value\]</span></span>

<span data-ttu-id="8926b-116">**記事** 針對 App-v 及更新版本，安裝 app-v 用戶端時，SFTLDR.DLL 會複製到 Windows\\system32 目錄。</span><span class="sxs-lookup"><span data-stu-id="8926b-116">**Note** For App-V version4.6 and later, when the App-V client is installed, SFTLDR.DLL is copied to the Windows\\system32 directory.</span></span> <span data-ttu-id="8926b-117">如果 App-v 用戶端安裝在64位系統上，SFTLDR\_WOW64.DLL 會複製到 Windows\\SysWOW64 目錄。</span><span class="sxs-lookup"><span data-stu-id="8926b-117">If the App-V client is installed on a 64-bit system, SFTLDR\_WOW64.DLL is copied to the Windows\\SysWOW64 directory.</span></span>

 

<span data-ttu-id="8926b-118">\ [範本標記值 \]</span><span class="sxs-lookup"><span data-stu-id="8926b-118">\[Template Token Value\]</span></span>

## <span data-ttu-id="8926b-119">本節內容</span><span class="sxs-lookup"><span data-stu-id="8926b-119">In This Section</span></span>


<span data-ttu-id="8926b-120">下列主題說明如何使用 setup.exe 或 setup.msi 來安裝應用程式虛擬化（app-v）桌面用戶端或 App-V 用戶端（以前稱為 [終端服務]）。</span><span class="sxs-lookup"><span data-stu-id="8926b-120">The following topics describe how to install either the Application Virtualization (App-V) Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services) by using either setup.exe or setup.msi.</span></span>

<a href="" id="how-to-install-the-app-v-client-by-using-setup-exe"></a>[<span data-ttu-id="8926b-121">如何使用 Setup.exe 安裝 App-V Client</span><span class="sxs-lookup"><span data-stu-id="8926b-121">How to Install the App-V Client by Using Setup.exe</span></span>](how-to-install-the-app-v-client-by-using-setupexe-new.md)  
<span data-ttu-id="8926b-122">提供使用 setup.exe 程式來安裝 App-v 用戶端的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="8926b-122">Provides a step-by-step procedure for installing the App-V client by using the setup.exe program.</span></span>

<a href="" id="how-to-install-the-app-v-client-by-using-setup-msi"></a>[<span data-ttu-id="8926b-123">如何使用 Setup.msi 安裝 App-V Client</span><span class="sxs-lookup"><span data-stu-id="8926b-123">How to Install the App-V Client by Using Setup.msi</span></span>](how-to-install-the-app-v-client-by-using-setupmsi-new.md)  
<span data-ttu-id="8926b-124">提供使用 setup.msi 程式來安裝任何必備軟體和 App-v 用戶端的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="8926b-124">Provides step-by-step procedures for installing any prerequisite software and also the App-V client by using the setup.msi program.</span></span>

## <span data-ttu-id="8926b-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="8926b-125">Related topics</span></span>


[<span data-ttu-id="8926b-126">Application Virtualization Client 安裝程式命令列參數</span><span class="sxs-lookup"><span data-stu-id="8926b-126">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

[<span data-ttu-id="8926b-127">如何手動安裝 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="8926b-127">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="8926b-128">如何在用戶端上發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="8926b-128">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="8926b-129">如何解除安裝 App-V Client</span><span class="sxs-lookup"><span data-stu-id="8926b-129">How to Uninstall the App-V Client</span></span>](how-to-uninstall-the-app-v-client.md)

 

 





