---
title: 如何安裝 MBAM 1.0 群組原則範本
description: 如何安裝 MBAM 1.0 群組原則範本
author: dansimp
ms.assetid: 451a50b0-939c-47ad-9248-a138deade550
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a055c84fb6b1645592b53d957daf157a6055880
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811096"
---
# <span data-ttu-id="7a7f8-103">如何安裝 MBAM 1.0 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="7a7f8-103">How to Install the MBAM 1.0 Group Policy Template</span></span>


<span data-ttu-id="7a7f8-104">除了 Microsoft BitLocker 管理和監控（MBAM）的伺服器相關功能之外，伺服器安裝應用程式還包含 MBAM 群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-104">In addition to the server-related features of Microsoft BitLocker Administration and Monitoring (MBAM), the server setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="7a7f8-105">您可以在任何能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上安裝此範本。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-105">You can install this template on any computer that is capable of running the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="7a7f8-106">下列步驟說明如何安裝 MBAM 群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-106">The following steps describe how to install the MBAM Group Policy template.</span></span>

<span data-ttu-id="7a7f8-107">**記事** 請務必在32位伺服器上使用32位設定，以及在64位伺服器上進行64位設定。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-107">**Note** Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>

 

**<span data-ttu-id="7a7f8-108">若要安裝 MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="7a7f8-108">To install the MBAM Group Policy template</span></span>**

1.  <span data-ttu-id="7a7f8-109">啟動 MBAM 安裝精靈;然後，按一下 [歡迎] 頁面上的 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-109">Start the MBAM installation wizard; then, click **Install** on the Welcome page.</span></span>

2.  <span data-ttu-id="7a7f8-110">閱讀並接受 Microsoft 軟體授權條款，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-110">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

3.  <span data-ttu-id="7a7f8-111">根據預設，所有的 MBAM 功能都已選取 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-111">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="7a7f8-112">清除 [**原則範本**] 以外的所有功能選項，然後按 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-112">Clear all feature options except for **Policy Template**, and then click **Next** to continue the installation.</span></span>

    <span data-ttu-id="7a7f8-113">**記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-113">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="7a7f8-114">如果符合所有先決條件，安裝會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-114">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="7a7f8-115">如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後**再次按一下 [檢查先決條件**]。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-115">If a missing prerequisite is detected, you must resolve the missing prerequisite and then click **Check prerequisites again**.</span></span> <span data-ttu-id="7a7f8-116">一旦符合所有先決條件，就會繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-116">Once all prerequisites are met, the installation will resume.</span></span>

     

4.  <span data-ttu-id="7a7f8-117">在 MBAM 安裝精靈顯示所選功能的安裝頁面之後，按一下 **[完成]** 以關閉 MBAM 設定。</span><span class="sxs-lookup"><span data-stu-id="7a7f8-117">After the MBAM Setup wizard displays installation pages for the selected features, click **Finish** to close MBAM Setup.</span></span>

## <span data-ttu-id="7a7f8-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="7a7f8-118">Related topics</span></span>


[<span data-ttu-id="7a7f8-119">部署 MBAM 1.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="7a7f8-119">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)

 

 





