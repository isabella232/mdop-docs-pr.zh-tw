---
title: 如何安裝 MBAM 2.0 群組原則範本
description: 如何安裝 MBAM 2.0 群組原則範本
author: dansimp
ms.assetid: bc193232-d060-4285-842e-d194a74dd3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6420fc4d499de05ed740b038b40aff6a9cd8a05f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811643"
---
# <span data-ttu-id="cf485-103">如何安裝 MBAM 2.0 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="cf485-103">How to Install the MBAM 2.0 Group Policy Template</span></span>


<span data-ttu-id="cf485-104">除了伺服器相關的 Microsoft BitLocker 管理與監控（MBAM）功能之外，伺服器安裝應用程式還包含 Microsoft BitLocker 管理和監視群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="cf485-104">In addition to the server-related Microsoft BitLocker Administration and Monitoring (MBAM) features, the server setup application includes an Microsoft BitLocker Administration and Monitoring Group Policy template.</span></span> <span data-ttu-id="cf485-105">此範本可安裝在任何能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上。</span><span class="sxs-lookup"><span data-stu-id="cf485-105">This template can be installed on any computer capable of running the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="cf485-106">下列步驟說明如何安裝 MBAM 群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="cf485-106">The following steps describe how to install the MBAM Group Policy template.</span></span>

<span data-ttu-id="cf485-107">**記事** 請務必在32位伺服器上使用32位設定，以及在64位伺服器上進行64位設定。</span><span class="sxs-lookup"><span data-stu-id="cf485-107">**Note** Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>

 

**<span data-ttu-id="cf485-108">若要安裝 MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="cf485-108">To install the MBAM Group Policy template</span></span>**

1.  <span data-ttu-id="cf485-109">在您要安裝 MBAM 的伺服器上，執行**MBAMSetup.exe** ，啟動 [MBAM 安裝] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="cf485-109">On the server where you want to install MBAM, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="cf485-110">在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="cf485-110">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="cf485-111">閱讀並接受 Microsoft 軟體授權條款，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="cf485-111">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="cf485-112">根據預設，系統會選取所有 Microsoft BitLocker 管理和監視功能來進行安裝。</span><span class="sxs-lookup"><span data-stu-id="cf485-112">By default, all Microsoft BitLocker Administration and Monitoring features are selected for installation.</span></span> <span data-ttu-id="cf485-113">清除 [**原則範本**] 以外的所有功能選項，然後按 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="cf485-113">Clear all feature options except for **Policy Template**, and then click **Next** to continue the installation.</span></span>

    <span data-ttu-id="cf485-114">**記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。</span><span class="sxs-lookup"><span data-stu-id="cf485-114">**Note** The installation wizard checks the prerequisites for your installation and displays prerequisites that are missing.</span></span> <span data-ttu-id="cf485-115">如果符合所有先決條件，安裝會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="cf485-115">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="cf485-116">如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。</span><span class="sxs-lookup"><span data-stu-id="cf485-116">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="cf485-117">一旦符合所有先決條件，就會繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="cf485-117">Once all prerequisites are met, the installation will resume.</span></span>

     

5.  <span data-ttu-id="cf485-118">如需如何以及在哪裡安裝範本的相關步驟，請參閱[如何下載和部署 MDOP 組原則（admx）範本](https://technet.microsoft.com/library/dn659707.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cf485-118">For specific steps about how and where to install the templates, see [How to Download and Deploy MDOP Group Policy (.admx) Templates](https://technet.microsoft.com/library/dn659707.aspx).</span></span>

6.  <span data-ttu-id="cf485-119">在 Microsoft BitLocker 管理及監視安裝精靈顯示所選功能的安裝頁面之後，按一下 **[完成]** 以關閉 MBAM 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="cf485-119">After the Microsoft BitLocker Administration and Monitoring Setup wizard displays installation pages for the selected features, click **Finish** to close MBAM Setup.</span></span>

## <span data-ttu-id="cf485-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="cf485-120">Related topics</span></span>


[<span data-ttu-id="cf485-121">部署 MBAM 2.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="cf485-121">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





